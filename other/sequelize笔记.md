# sequelize

## 简介

Sequelize 是 Node.js 的一个 ORM 库，通过 Sequelize 我们能用熟悉的 js 链接，操作数据库。

## Transaciton

### 基础知识
事务（Transaction）：事务是数据库执行过程中的一个逻辑单位，由一系列有限的数据库操作序列构成。被事务包裹起来的这些操作会有共同的执行结果，（最终返回相同结果） 要么全部成功，要么失败，全部回滚。`all-or-nothing`

以银行转账为例子。用户 A 给 用户 B 转账 100。
伪代码(忽略细节)

```  
A 余额 = A余额 - 100
B 余额 = B余额 + 100
```

A 账号 -100，和 B 账号 +100 是两条独立的语句，如果在中间发生异常，导致程序中断，就会出现 A 账号上的 100 凭空消失。 为了保证转账操作完整执行，用事务包裹起来。如果这中间发生错误，则会全部回滚。

```
start transaction;
// 转账操作
commit;
```

Sequelize 提供了 Transaction 类，通过 Sequelize.transaction 创建事务，并在每一次数据库操作设置当前操作属于哪个事务。  

```js
 await sequelize.transaction({}, async (transaction) => {
    const instance = await Accounts.findOne({
      where: {
        name: 'HelKyle',
      },
      transaction,
    });
    
    await instance.update({
      balances: instance.balances + number,
    }, {
      transaction,
    })
})
// 创建事物之后，整个查询、更新操作都在事物中执行
```

log

```
Executing (444a5afe-9635-40fd-90d7-10f5aa16077a): START TRANSACTION;
Executing (444a5afe-9635-40fd-90d7-10f5aa16077a): SELECT "name", "balances" FROM "accounts" AS "accounts" WHERE "accounts"."name" = 'HelKyle';
Executing (444a5afe-9635-40fd-90d7-10f5aa16077a): UPDATE "accounts" SET "balances"=$1 WHERE "name" = $2
Executing (444a5afe-9635-40fd-90d7-10f5aa16077a): COMMIT;
```
如果不想每次都手动传 transaction 对象，可以通过配置 [CLS](http://docs.sequelizejs.com/manual/transactions.html)  的方式，配置全局默认 transaction。

### 并发问题  

事务只解决了操作原子性的问题，另一个棘手的问题是并发。假设在 A 给 B 转账的过程中，恰巧 C 也给 A 转账 80，用 table 的形式演示并发过程中可能会发生的问题。

| | |
|-----|-----|
| 事务1（A 给 B 转账）|事务2（C 给 A 转账）|
||查询 A 余额 200|
|查询 A 余额 200||
||更新 A 余额 = 200 + 80|
|更新 A 余额 = 200 - 100	||

从结果上可以看到，A 最终没有收到来自 C 的 80，C 用户的💰丢了。并发的问题可以通过加锁来避免。

### 锁的概念

#### 悲观锁 VS 乐观锁

`悲观锁`: 对外界持保留态度，为了避免冲突，先给记录加上锁，在当前事务释放之前，其他事务要对该记录执行操作必须等待

| | |
|----|----|
| 事务一（A 给 B 转账）| 事务二（C 给 A 转账）|
| |查询 A 余额 200，并锁定记录 |
|查询 A 余额，发现有其他事务锁定了记录，等待...| |
|更新 A 余额 = 200 + 80，释放锁||
|获得执行权，查询 A 余额，280||
|更新 A 余额 = 280 - 100||

`MySql，Postgres` 都实现了悲观锁，执行相关语句即可（`select for update`），不需要开发。悲观锁的缺点是在读操作频繁的场景下，会影响吞吐量。  
 
`乐观锁`:认为冲突没那么多，任何事务都可以先读取资源，在写入更新的时候做判断。通常会增加 version 字段，每次更新的时候 verion + 1，提交更新到数据库的时候，判断 version ，如果已失效则重试。  

| | |
|-----|-----|
| 事务一（A 给 B 转账）|
| |事务二（C 给 A 转账）|
| |查询 A 余额 200，版本号 n | 
| 查询 A 余额 200，版本号 n| |
| |更新 A 余额 = 200 + 80，版本号 = n + 1|
| 发现最新版本已经不是 n, 重试||
| 查询 A 余额 280，版本号 n + 1| |
| 更新 A 余额 = 280 - 100，版本号 = n + 2||

```sql
select name, balances, version from accounts where name='HelKyle';

update accounts set version=version+1, balances=balances+100
    where name='HelKyle' and version=#{version}
```
乐观锁在写操作频繁的场景下会不断发生重试，也会影响吞吐量。

### 排他锁 VS 共享锁：

`排他锁`:是悲观锁的一种，查询的时候时候加锁。同一资源同一时间只能有一个排他锁，其他事务往这条记录上添加排他锁必须等待当前事务的完成（其他事务读需要等待）。

```sql
select * from accounts where name='HelKyle' for update;
```

Sequelize 写法

```js
await Accounts.findOne({
    where: { name: 'HelKyle' },
    lock: Sequelize.Transaction.LOCK.UPDATE
});
```

演示： 👈 事务没有结束的时候，👉 事务只能等待，直到排他锁释放。

| 事务1|事务2 |
|-----|-----|
|start transaction|start transaction|
|select * from accounts where name='A' for update;	||
|输出：A 100||
||select * from accounts where name='A' for update;|
||waiting...|
|commit;||
||输出：A，100|
||commit;|

`共享锁`:允许同一资源同时存在多个，当需要执行修改，删除等操作时，必须等其他所有共享锁都释放之后才能执行

`sql`代码

```sql
select * from accounts where name='HelKyle' for share;
```

`Sequelize` 写法

```js
await Accounts.findOne({
    where: { name: 'HelKyle' },
    lock: Sequelize.Transaction.LOCK.SHARE
});
```

演示： 👈 👉的事务都能查询，👈事务想修改数据时，由于👉共享锁没有释放，修改操作只能等待。

| 事务1|事务2 |
|-----|-----|
|start transaction|start transaction|
|select * from accounts where name='A' for share;		||
|输出：A 100||
||select * from accounts where name='A' for share;|
||输出：A 100|
||waiting...|
|update accounts set balances=10 where name='A'	||
|waiting...||
||commit;|
||输出：A，100|
|set A.balances = 10	||
|commit;||

除了 lock，还有另一个配置和锁相关，是 sequelize.transaction(options) 的配置参数 isolationLevel，支持四个级别，分别是： 

| 级别 | 脏读 | 不可重复读 | 幻读 |
| --- | --- | --- | --- |
| READ_UNCOMMITTED 读未提交| | | |
| READ_COMMITTED 读已提交| ❌ | | |
| REPEATABLE_READ 可重复读| ❌ | ❌ | |
| SERIALIZABLE 可串行化| ❌ | ❌| ❌ |

👆的 ❌ 表示在这种级别里面，某类问题不会出现。

`脏读`:指的是在一个事务中能读取到另一个事务内未 commit 的内容，如果另一个事务最终失败了，没有写入数据库，那么第一个事务就拿到了不存在的数据。

```
| 事务1|事务2 |
|-----|-----|
|start transaction|start transaction|
|select * from accounts where name='A';	||
|输出：A 100||
|update accounts set balances=10 where name='A'	| |
| 输出：A 100||
||waiting...|
|update accounts set balances=10 where name='A'	||
| |select * from accounts where name='A';|
||输出：A 10 (这时候事务一并没有 commit)|
```

`不可重复读`: 描述在一个事务中，事务多次读取统一资源（本事务中没有修改操作），得到不同的结果。

```
| 事务1|事务2 |
|-----|-----|
|start transaction|start transaction|
|select * from accounts where name='A';	| |
|输出：A 100||
| |update accounts set balances=10 where name='A'	|
| |commit|
|select * from accounts where name='A';	| |
|输出：A 10 (这时候事务一并没有 commit)| |
```

`幻读`:指的是出现了符合查询条件，但是之前没有👀到过。比如 queryAll 一个表中所有数据，设置 balances 为 0，但是由于其他事务同时写入新内容，于是新记录明明符合 queryAll 但是没有 balances 并不为 0，像👻一样。

| 事务1|事务2 |
| ----- | ----- |
| start transaction|start transaction|
| select * from accounts;		| |
| 输出：A 100||
| update accounts set balances=0;	| | 
| | insert into accounts values ('B', 100);|
| commit| | 
| select * from accounts;	| |
| |commit|
| | 输出：A 0, B 100	 |
|输出：A 10 (这时候事务一并没有 commit)| |


在 Sequelize 中配置 isolationLevel

```js
sequelize.transaction({
	isolationLevel: Sequelize.Transaction.ISOLATION_LEVELS.SERIALIZABLE
}, transaction => {
  // your transactions
});
```




# 解决批量添加时没有主键ID
```js
Model.bulkCreate(values, { individualHooks: true })

```
