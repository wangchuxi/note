# 学习JavaScript语法

JavaScript 是属于网络轻量级·功能强大。的脚本语言

### 输出方式

JavaScript没有任何打印或者输出的函数。但有传输数据方式：

```shell 
document.write("<h1>this is a demo</h1>");              # 写入HTML，修改内容
doument.getElementById("demo").innerHTML="Hello world"  # 写入HTML元素.
window.alert()        # 弹出警告框   
console.log()         # 浏览器的debug工具输出日志
```

### 字面量

**数字(number):** 一个字面量是一个常量

```js
1    3.14  1323f5 
```

**字符串(string):** 单双引号都行。

```js
"hello"    'love' 
```

**表达式:**

```js
4+5    4*5
```

**数组（Array）**

```js
[20, 100, 29]
```

**对象**

```js
{
  name:"wJ",
  age:"39",
  job:23
}
```

**函数：**

```js
function  myFunction(a,b){return:a*b;}
```

### 变量

变量用 `var 声名 = 赋值`， 用来储存数据。(变量以字母开头，区分大小写）

```js
var a = 5 ;     // a是名称， 5是字面值。语句分号隔开。
var y = a * 8;
var length = 16;          // Number  通过数字字面量赋值 
var points = x * 10;      // Number 通过表达式字面量赋值
var lastName = "Johnson"; // String 通过字符串字面量赋值
var cars = ["Saab", "Volvo", "BMW"];              // Array  通过数组字面量赋值
var person = {firstName:"John", lastName:"Doe"};  // Object #通过对象字面量赋值
var lastname ="jim", age=30,job="carpenter";      // 一条语句多条变量    
var carname;       // 声名无值变量结果为undefined；
```

声明变量类型用new，例子：

```js
var carname=new String;   // 字符串
var x=      new Number;   // 数字
var y=      new Boolean;  // 布尔值  
var cars=   new Array;    // 数组
var person= new Object;   // 对象乎所有的事物都是对象。
```

变量的作用域，在函数内申明的属于局部变量，作用在函数内，函数执行完就结束，反正就属全局变量，作用全局，例子：

```js
var carName = "Volvo";
function myfunction(){        // 在函数外作用全局             
     var carName = "Volvo";   // 作用在函数内
     carName = "Volvo";       // 没用用var声明作用全局
}
```

expample:   

```js
function myFunction(){
  var y=5;
  var x=y+2;
  var demoP=document.getElementById("demo")
  demoP.innerHTML="x=" + x;
}
```

### 函数

引用函数（执行函数内语句）可重复调用。

```js
function myFunction(a,b){
    return a-b;    // 返回a乘b结果。    
}
```

javascript 分大小写

```js
函数 getElementById != getElementbyID
变量 myVariable != myvariable
```

### 数组 

数字的三种写法

```js
// 第一种
var cars=new Array(); // 数组下标是基于零的，所以第一个项目是 [0]，第二个是 [1]，
cars[0]="saab";
cars[1]="volvo";
cars[2]="BMW";
// 第二种
var cars=new Array("saab","volvo","BMw");
// 第三种
var cars=["saab","volvo","bmw"];
```

### 对象

```js
//对象的属性以名称和值对的形式 (name : value) 来定义。
var person={firstname:"Jim",lastname:"deo",id:33};
```










### 字符串

javascript 字符串储存和处理文本。

1. 可索引位置访问字符串，`var character = carname[7];`
1. 字符圈中符号不能与字符串符号相同或者用转意符合
    - `var answer = "It's alright";`
    - `var y = "He is called \"Johnny";`
1. 字符串长度计算
    - `var txt = "abcd";`
    - `var sln = txt.length;`


### 字符串属性

| 属性 | 描述 |
| ---- | ---- |
| constructor | 返回创建字符串属性的函数 |
| length | 返回字符串的长度 |
| prototype | 允许您向对象添加属性和方法 |

### 字符串方法

| 方法 | 描述 |
| ---- | ---- |
| charAt()   | 返回指定索引位置的字符  |
| charCodeAt()   | 返回指定索引位置字符的 Unicode 值  |
| concat()   | 连接两个或多个字符串，返回连接后的字符串  |
| fromCharCode()   | 将 Unicode 转换为字符串  |
| indexOf()   | 返回字符串中检索指定字符第一次出现的位置  |
| lastIndexOf()   | 返回字符串中检索指定字符最后一次出现的位置  |
| localeCompare()   | 用本地特定的顺序来比较两个字符串  |
| match()   | 找到一个或多个正则表达式的匹配  |
| replace()   | 替换与正则表达式匹配的子串  |
| search()   | 检索与正则表达式相匹配的值  |
| slice()   | 提取字符串的片断，并在新的字符串中返回被提取的部分  |
| split()   | 把字符串分割为子字符串数组  |
| substr()   | 从起始索引号提取字符串中指定数目的字符  |
| substring()   | 提取字符串中两个指定的索引号之间的字符  |
| toLocaleLowerCase()   | 根据主机的语言环境把字符串转换成小写  |
| toLocaleUpperCase()   | 根据主机的语言环境把字符串转换成小写   |
| toLowerCase()   | 把字符串转换为小写  |
| toString()   | 返回字符串对象值  |
| toUpperCase()   | 把字符串转换为大写  |
| trim()   | 移除字符串首尾空白  |
| valueOf()   | 返回某个字符串对象的原始值  |

### 运算符

运算符：（`+`）加法，（`-`）减法，（`*`）乘法，（`／`）除法， （`%`）取模“取”，（`++`）自增，（`--`）自减。  
难以记住的是：（++）和（--）。  

example:

`y=5;z=2;`  
自减：`x=--y;`与`x=y--`  结果：`x=4,y=4;`与`x=4,y=4;`  
自增：`x=++y;`与`x=y++`  结果：`x=6,y=6;`与`x=6,y=5;`  

个人理解运算符在前面的这个值会跟随递增／递减，在后面的话就不会跟随递减。

###  算术运算符


运算符：（+）加法，（-）减法，（*）乘法，（／）除法， （%）取模“取”，（++）自增，（--）自减。  
expample:  

`x+=y` 等同于`x = x+y`

### 运算符应用

```js
var text1 ="hallo"; 
var text2 = "world";
var text3 = text1+""+text2; // 字符串相加并加空值。
var z = "hello"+5;    // 得到值hello5， #字符串于数字；
```

### 比较运算
比较运算符在逻辑语句中使用，以测定变量或值是否相等

- `==` 和 `!==` 等于和不等于（值相等或不等）
- `===`、 `!===` 绝对等于和不等于（值和类型相等或不等）
- `>`, `<`, `>=` ,`<=` 与数学运算一样。

条件运算example：

```js
if (age<18) x="Too young";
```

### 逻辑运算符 

```js
&&   // and
||   // or
!    // not
```

Example:

```js
(x==5 || y==5) 为 false
```

### 条件运算

JavaScript 还包含了基于某些条件对变量进行赋值的条件运算符

语法:

```js
variablename=(condition)?valuel:value2
```

Example:

```js
voteable=(age<18)?"年龄太小":"年龄已达到";
```

### If...Else 语句

条件语句用于基于不同的条件来执行不同的动作。

1. `if`:(只有当指定条件为 true 时，使用该语句来执行代码)

```js
if (time<20){x="Good Boy"}
```

2. `if...else`: 条件为true或else时执行不同代码

example:

```
if (time>20){
    x="Good Boy"
}else{
    Y="Good girl"
}
```


3. `if...else if....else`:多个条件判断其中一条来执行

example:

```js
if(time<10){
  document.write("<b>早上好</b>");
}else if (time>=10 && time<16){
  document.write("<b>今天好</b>");
}else{
  document.write("<b>晚上好!</b>");
}
```


4. `switch`: 选择多个代码块依次判断之一来执行，设置表达式 n（通常是一个变量）。随后依次与每个 case 的值做比较。存在匹配就执行与其相关代码，否则依次判断下去

```js
var d=new Date().getDay(); 
switch (d) { 
  case 0:
    x="今天是星期日"; break; 
  case 1:
    x="今天是星期一"; break; 
  case 2:
    x="今天是星期二"; break; 
  case 3:
    x="今天是星期三"; break; 
  case 4:
    x="今天是星期四"; break; 
  case 5:
    x="今天是星期五"; break; 
  case 6:
    x="今天是星期六"; break; 
}
```

### default关键字

default匹配不存在做的事情。

```js
var x; 
var d=new Date().getDay();
switch(d){
  case 6: x="周六";break;
  case 0: x="周末";break;   //中断
  default; x="期待周末";
}
document.getElementById("demo").innerHTML=x;
```

### 循环

循环可以将代码块执行指定的次数。

example:

```js
cars=["BMW","Volvo","Saab","Ford"];
for (var i=0;i<cars.length;i++){
    document.write(cars[i] + "<br>");
}

cars=["BMW","Volvo","Saab","Ford"];
for (var i=0,l=cars.length; i<l; i++){
    document.write(cars[i] + "<br>");
}

// 排除前面  后面循环
cars=["BMW","Volvo","Saab","Ford"];
var i=2,len=cars.length;
for (; i<len; i++){
    document.write(cars[i] + "<br>");
}

// 
cars=["BMW","Volvo","Saab","Ford"];
var i=0,len=cars.length;
for (; i<len; ){
    document.write(cars[i] + "<br>");
    i++;
}
```

### for/in循环

JavaScript for/in 语句循环读取所有属性：

```js
function myFunction(){
    var x;
    var txt="";
    var person={fname:"Bill",lname:"Gates",age:56}; 
    for (x in person){
        txt=txt + person[x];
    }
    document.getElementById("demo").innerHTML=txt;
}
```

### while循环

while 循环会在指定条件为真时循环执行代码块

```js
function myFunction(){
    var x="",i=0;
    while (i<5){
        x=x + "该数字为 " + i + "<br>";
        i++;
    }
    document.getElementById("demo").innerHTML=x;
}
```

### do/while循环：

do/while循环在条件还没判断之前读取一次代码。

```js
function myFunction(){
    var x="",i=0;
    do {x = x + "该数字" +i;
        i++;
    }
    while(i<5)
}
```

### break：跳出循环

符合break负载的条件，循环就会跳出；

```js
function myFunction(){
    var x = "",i=0:
    for(i=0;i<10;i++){
        if (i==3){
            break;
        }                            //if 语句就一句所以打括号可以不用。
        x=x+"数字为" + i + "<br>";
    }
    console.log("------>",x);   //打印x
};
myFunction();     //执行fanction
```

### Continue 语句:

continue 语句中断循环中的迭代， 跳过指定条件执行后面的跌代。

```js
function myFunction(){
    var x ="",i=0;
    for (i=0;i<10;i++){
        if (i==3){
            continue;
        }
        x=x + "数字" + i +"<br>"; 
    }
}
```

### typeof 操作符：

typeof 操作符来检测变量的数据类型。

```js
typeof "John"                 //返回  string
typeof "3.14"                 //返回  number    
typeof "false"                //返回  boolean  
typeof [1,2,3]                //返回  object
typeof {name:'john', age:34}  //返回  object

```

### Null

null 表示 "什么都没有"是个空值

```js
var person;                    //值为空
person = unfined;              //通过unfined清空   
typeof undefined               // undefined
typeof null                    // object
null === undefined             // false
null == undefined              // true

```

### js数据类型（以及查看类型类型）

Number() 转换为数字， String() 转换为字符串， Boolean() 转化为布尔值。

```
| 转换符|数据 | 返回结果 |
| ---- | ---- |
|typeof |John     | string|
|       |3.14     |number|
|       |NaN     |boolean|
|       |False     |object|
|       |[1,2,3]     |object|
|       |{name:'Jone', age:34;}|object|
|       |function(){}  |object|
|       |myCar    |nuderfined| //(没有申明)
|       |null     |object|
|        |   |function|
```

### constructor 属性

constructor 属性返回所有 JavaScript 变量的构造函数。
  写法 "John".constructor
```js
| 转换符|数据 | 返回结果 |
| ---- | ---- |
|constructor|"John"     | String(){ [native code] }|
|           |(3.14)     |Number()  { [native code] }|
|            |false     |Boolean() { [native code] }|
|            |[1,2,3]   | Array()   { [native code] }|
|            |{name:'Jone', age:34;}|Object(){ [native code] }|
|            |function(){}  |Function(){ [native code] }|
|            |new Date()   |Date(){ [native code] }
```

#### 例子：1

```js
var myDate = new Date();
document.getElementById("demo").innerHTML = isDate(myDate);
function isDate(myDate) {
    return myDate.constructor.toString().indexOf("Date") > -1;
}
// indexOF(); 返回字符串到首次出现的地方并返回字母所在的位置。
// isDate();  判断函数是否是时间
// constructor  返回变量的函数构造
// toString();  可把一个逻辑值转换为字符串,并返回结果
// 结果为true
```

#### 例子：2

```js
var fruits = ["Banana", "Orange", "Apple", "Mango"];
document.getElementById("demo").innerHTML = isArray(fruits);
function isArray(myArray) {
    return myArray.constructor.toString().indexOf("Array") > -1;
}

//isArray()  判断函数是否是数组
```

### to string()

   将数字，字母，变量布尔值，表达式：，日期 等 转换为字符串：
   Number方法有类似效果

```js
x.toString()      = string(x)           //变量转换为字符圈 x 并返回
(123).toString()  = string(123)         //数字转换为字符串 123  并反回
(100 + 23).toString() = string(100+23)  //数字表达式转换为字符串
false toString() = String(false)        //返回false
ture toString() = String(true)          //返回 "ture" 
Date().toString() = string(Date)        //返回"Thu Mar 23 2017 22:01:49 GMT+0800 (CST)"
```

#### 更多讲数字转换为字符串

```js
|方法|描述|
| -------- | ----------- |
|toExponential()|把对象的值转换为指数计数法。|  //没有明白
|toFixed()|把数字转换为字符串，结果的小数点后有指定位数的数字|
|toPrecision()|把数字格式化为指定的长度|
```

```js


```


### Date方法 将日期转换为字符串的函数：

``` js
|方法|描述|
| ----------- | ------------ |
|getDate()|从 Date 对象返回一个月中的某一天 (1 ~ 31)|
|getDay()|从 Date 对象返回一周中的某一天 (0 ~ 6)|
|getFullYear()| Date 对象以四位数字返回年份|
|getHours()| 返回 Date 对象的小时 (0 ~ 23)。|
|getMilliseconds()|返回 Date 对象的小时 (0 ~ 23)|
|getMinutes()|返回 Date 对象的分钟 (0 ~ 59)。|
|getMonth()|从 Date 对象返回月份 (0 ~ 11)。|
|getSeconds()|返回 Date 对象的秒数 (0 ~ 59)。|
|getDTime()|返回 1970 年 1 月 1 日至今的毫秒数。|
```

### Number方法：
将自符串转换为数字,其他的字符串会转换为 NaN (不是个数字)
```js
|方法|描述|
|Number("3.14")|3.14|
|Number(" ")|0|
|Number("")|0|
|Number("11 12")|NaN|
```

#### 其它转换数字的方法

```js

|方法|描述|
|parseFloat()|解析一个字符串，并返回一个浮点数|
|parselnt()|解析一个字符串，并返回一个整数。|
```

```js
var date = "3.445543434";
var b = parseFloat(date.toString());
b
//3.445543434   将字符串转化为一个数

var date = "32.823232323";
var b = parseInt(date.toString());
b
// 32 返回的值去除小数点后面的数。不四舍五入s
```



### 正则表达式

正则表达式由一个字符系列形成的搜索模式，它可以是个字符也可以是复杂的模式
可以用搜索模式来描述要查询内容，可用于所有文本搜索和替换操作。
   类似于路径。邮箱可用于正表达式来规定用户输入。

匹配数字将一段数字分成几份。
```js
var code = "123456789232433423412";
var reg =/.{5}/g;
var province_city = code.match(reg);
province_city

(4) ["12345", "67892", "32433", "42341"]
```

#### 修饰符

```js
 例如：/microsoft/i

i     //匹配大小写不敏感
g    //全局匹配  找到所有匹配的。
m    //执行多个匹配
```

#### 正则表达式查找范围
[]查找某范围字符
```js
|表达式|描述|
|--------|---------|
|[abc]|查找[]之间任何数字|
|[0-9]|查找任何0-9的数字|
|(x/y)|查找以|分割对象|
```

search() 方法 用于检索字符串中指定的子字符串，或检索与正则表达式相匹配的子字符串，并返回子串的起始位置。
```js
var str = 'Visit Runoob:';
var n = str.search(/Runoob/i);
//n
6  搜索字符串的起始位置，并返回位置的数字
```

replace() 方法使用句正则表达式改变和替换

```js
  
str = "Visit Runoob";
var n =str.replace(/Runoob/i,"beijing");
console.log(n);
// VM5537:3 Visit beijing
undefined
```

test（） 方法

test() 方法用于检测一个字符串是否匹配某个模式，
```js
var patt = /e/;
patt.test("The best strings in life are free");
true
/e/.test("The best things in feel!");
true

```

exec() 方法检索字符串中正则表达式的匹配

返回的是一个数组。存放匹配结果
```js

/e/.exec("the, the, the");
// ["e", index: 2, input: "the, the, the"] 

```

一些特殊判断的实例：

```js
function isDecimal(strValue){
  var objRegExp = /^\d+\.\d+$/;
  return objRegExp.test(strValue);
}
isDecimal(23.23343);
//true  判断数字里数否带小数点



function ischina(str){
  var reg=/^[u4E00-\u9FA5]{2,4}$/;
  //定义表达式
  return reg.test(str);  //进行验证
}
ischina("中国")
//true 判断是否为中文


function isStudentNo(str){
    var reg =/^[0-9]{8}$/; //定义验证表达式
    return reg.test(str);  //进行验证
    isStudentNo('123456789')
//false  验证是否是8位数组成。
}


function isTelCode(str) {
  var reg= /^((0\d{2,3}-\d{7,8})|(1[3584]\d{9}))$/;
  return reg.test(str);
}
 // 判断电话号是否合法

/*校验邮件地址是否合法 */
function IsEmail(str) {
  var reg=/^([a-zA-Z0-9_-])+@([a-zA-Z0-9_-])+(\.[a-zA-Z0-9_-])+/;
  return reg.test(str);
}













```

#### 元字符

```js
|元字符|描述|
|-----|------|
|\d|查找数字|
|\s|查找空白字符|
|\b|匹配单词边界|
|\uxxxx|查找16进制XXXX规定的Unicode|
//后面三个不懂
```

#### 量词

```
|量词|描述|
|-----|------|
|n+|匹配至少一个n字符串|
|n*|匹配0个或多个n字符串|
|n?|匹配匹配0个或一个n的字符串|
```

#### search()方法使用字符串

```js
function myFunction(){
  var str = "visit Runoob!";
  var n = str.serach("Runoob");
  document.getElementById("demo".innerHTML = n)
}
// 返回结果为6   str变量里的字符串从0开始，到第六位出现。
```

#### replace()方法使用正则表达式和字符串。

```js
//HTML部分省略
//<p id="demo">Microsoft!</p>

function myFunction(){
  var str = document.getElementById("demo")
  var txt = str.replace(/microsoft/i,"Runoob");  
                         //表达式主体 i 为后缀修饰起不分大小写 
document.getElementById("demo").innerHTML = txt;
}

//例子2替换

function myfunction(){
  var str = document.getElementById("demo").innerHTML;
  var txt = str.replace("Microsoft","runoob");
  docunemt.getElementById("demo").innerHTML = txt;
}



```

#### test()

test()是正则表达式的方法
用来检测一个字符串是否匹配某种模式，如果字符串中含有匹配的文本，则返回true否则返回eles。

```js
/e/.test("The best things in life are free!") //搜索字符串中的e 返回为ture
```

#### exec()

exec()用来检索字符串中正则表达式的匹配，函数返回一个数组，用来存放匹配结果，如果不匹配
则返回null

```js
/e/.exec("The best things in life are free!");  //返回字符串e。
```

#### RegExp对象

RegExp 对象是一个预定义了属性和方法的正则表达式对象

```js
var patt1=new RegExp("e");   =  var patt1= /e/;
```

### js错误 — throw，try,catch
try语句测试代码块错误
catch 语句处理错误
throw语句创建自定义错误

#### try和catch
try语句允许我们定义在执行错误测试的代码块。
catch语句允许我们定义当try代码块发生错误时，所执行的代码块。
catch 和try同时出现

```js
function message()
{
  try{
    addalert("Welcome guest!");
  }catch(err){
    txt="本页一个错。\n\n;"
    txt="错误描述：+err.message + "\n\n";
    txt+="点击确定继续。\n\n";
    alert(txt);
  }
}
```

#### Throw语句

throw语句允许我们创建自定义错误。
术语：创建抛出异常（excepition）。
throw与try和catch一起使用，能够控制程序流，并生成自定义错误。

```js
function myFunction(){
  try
  {
    var x=document.getElementById("demo").value;
    if(x=="") throw "值为空";
    if(isNaN(x)) throw "不是数字";
    if(x>10) throw "太大";
    if(x<5) throw "太小";
  }
  catch(err)
  {
    var y=document.getElementById("mess");
    y.innerHTML="错误:" +err +"。";
  }
}
```

### 调试工具

对代码`错误`,`逻辑错误`，用console.log()方法进行打日志。

```js
function(c){
  a=5;
  b=6;
  c=a+b;
  console.log(c);
}

```

### 设置断点
debugger关键字
对代码进行调试时可以对后面的代码进行打断，让代码不会往下运行。
如果没有开启调试工具则断点不起作用。

```js
//<p id="demo"></p>
var x = 100 * 4;
debugeer;
document.getElementById("demo").innerHTML = x;
```

### 变量提升

函数及变量的声明都将被提升到函数的最顶部。
变量可以在使用后声明，也就是变量可以先使用再声明。

```js
x = 5; // 变量 x 设置为 5
elem = document.getElementById("demo"); // 查找元素 
elem.innerHTML = x;                     // 在元素中显示 x
var x; // 声明 x

//得出结果为 5；
//变量必须在先  声明可以在前在后都一样
```

变量初始化的话就不会被提升  var x = 4; （初始化x）

```js
var x = 5; // 初始化 x
var y;     // 声明 y
elem = document.getElementById("demo"); // 查找元素
elem.innerHTML = x + " " + y;           // 显示 x 和 y
y = 7;    // 设置 y 为 7
```

#### 严格模式（use strict）

（strict mode）严谨模式下运行。

+ use strict  不是一条语句，但是是一个字面量表达式，严格模式下不能使用没申明的变量
+ js旧版本里备被忽略。
+ 支持的浏览器有 IE10+，chrome13+，Safari5.1+,Opera12+
+ js语法有漏洞，不合理，不严谨，得到怪异的结果，从而降低了编辑器效率。
+ 用于测试时，测试代码的严谨性。

```js
"use strict";
x = 3.14;       // 报错 (x 未定义)
```

#### js使用误区

> 赋值运算符应用错误

在 JavaScript 程序中如果你在 if 条件语句中使用赋值运算符的等号 (=) 将会产生一个错误结果, 正确的方法是使用比较运算符的两个等号 (==)。

if 条件语句返回 false (是我们预期的)因为 x 不等于 10:

#### 比较运算符常见出现的错误

#### js 表单


> html表单输入的数据可以通过js来验证，验证其正确性，确保数据有效。
+ 验证表单数据是否为空？
+ 验证输入是否是一个正确的email地址？
+ 验证日期是否输入正确？
+ 验证表单输入内容是否为数字型？

下面的例子对html部分省略掉。

##### js表单验证

```js
// 判断表单字段（fname）值是否存在，如果存的就弹消息，如不存在就阻止提交
funciton validateFrom(){
  var x = document.froms["myFrom"]["fname"].value;
  if (x == null || x ==""){
    alert("请输入名称");
    return false;
  }
}
//如下 函数在from表单提交时被调用。
```

`调用上面函数的方法`

```html
<form name="myForm" action="demo-form.php" onsubmit="return validateForm()" method="post">
姓: <input type="text" name="fname">
<input type="submit" value="提交">
</form>

```

##### E-mail 验证

>检查输入数据是否符合电子邮件地址的语法
数据必须包含@和（.）符号 并且@不能在首位，@后面必须有一个(.)字符。
例如：`379925517@qq.com`

```js
function validateFrom(){
  var x = document.froms["myFrom"]["email"].value;
  var atpos = x.indexOf("@");
  var dotpos=x.lastIndexof(".");
  if (atpos<1 || dotpos<atpos+2 || dotpos+2>=x.length){
        return message(code:1; "邮箱格式错误")
  }
}
```

```html
<form name="myForm" action="demo-form.php" onsubmit="return validateForm();" method="post">
    Email: <input type="text" name="email">
    <input type="submit" value="提交">
</form>
```

```js
 // 对输入的数字进行判断。
function myFunction() {
    var x, text;

    // 获取 id="numb" 的值
    x = document.getElementById("numb").value;

    // 如果输入的值 x 不是数字或者小于 1 或者大于 10，则提示错误 Not a Number or less than one or greater than 10
    if (isNaN(x) || x < 1 || x > 10) {
        text = "输入错误";
    } else {
        text = "输入正确";
    }
    document.getElementById("demo").innerHTML = text;
}
```


``` html
// HTML表单验证通过自行
 <form action="demo_form.php" method="post">
  <input type="text" name="fname" required>
  <input type="submit" value="提交">
</form>
```

##### 数据验证

> 为确保用户输入的数据有效。
 
 数据验证有：
+ 必要字段是否输入？
+ 数据是否合法？
+ 是数据字段是否输入了文本？

数据验证为确保用户输入正确数据。可以通过不同方法定义和不同方式调用。
`服务端验证`:数据提交到服务器上做验证。
`客户端验证`: `（·side validation）`数据在发送服务端之前，在浏览器上验证。

#### 验证API
##### HTML 约束验证
（后面补充）



#### JSON

 - JSON是一种轻量级数据转换格式
 - 用于储存和传输数据的格式。
 - 用于服务端向网页传送数据。
 - JSON的格式是文本，可被任何编程语言读取并作为数据传递。

##### JSON 格式化为js的对象

JSON语法跟 创建js对象代码相同。
所以js程序很容易将JSON数据转化为js的对象。
使用 JavaScript 内置函数 JSON.parse() 将字符串转换为 JavaScript 对象:

```json      
    //json数组   
var text = '{ "sites" : [' +
  '{ "name":"Runoob" , "url":"www.runoob.com" },' +
  '{ "name":"Google" , "url":"www.google.com" },' +
  '{ "name":"Taobao" , "url":"www.taobao.com" } ]}';
  
obj = JSON.parse(text);  //将json格式的字符串转化为js对象
document.getElementById("demo").innerHTML = obj.sites[1].name + " " + obj.sites[1].url;
```

##### JSON语法规则

>例子引用上面的那个例子

+ 数据为 键/值 对。
+ 数据由逗号分隔。
+ 大括号保存对象
+ 方括号保存数组

##### 相关函数

|函数|描述|
|-------|-------|
|JSON.parse()|JSON字符串转化为js|
|JSON.string()|js转化为json字符串|

#### js:void(0)含义

> void()操作符操指定要计算一个表达式但是不返回值。

```js
void func()
javascript:void func()

或者

void(func())
javascript:void(func())
```

### js代码规范

>代码规范增强代码可读性

+ `变量名`推荐使用驼峰式   `firstName = "john`;
+ `空格`与`运算符`（= + - * ／）前后加空格  `var x = y + z`
+ `代码缩进`  （如今软件都智能化了就不用解释了）
+ 语句规则  一条代码通常以`;`



#### 函数定义

+ 使用关键字function定义函数。
+ 函数通过声明定义，也可以是一个表达式。
+ 函数声明后需要调用才能够执行。
+ 
```js
function myFunction(a,b){
    return a*b;   
}
myFunction(2,5);
 //结果为10

 
```

函数可以储存在变量里，之后变量可做函数调用，通常不为匿名函数，通过变量调用
```js
var x = function(a,b){return a * b};
var z = x(3, 4);
z  //执行z函数
```

#### 构造函数

构造函数作用：要得到一个类的实例时，往往是要运行其构造函数的

　　构造函数创建的三个基本要求：函数名首字母大写；构造函数内部使用this关键字来指向即将生成的对象实例；使用new关键字来调用构造函数并返回对象实例。






初始化一个函数，构造方法，在类被初始化的时候自动加载，无需写代码调用。
函数如果用于创建新的对象，称之为对象的构造函数。
我们声明一个类后，为这个类声明一个方法，这个方法名和类名是一样的
```js
var myFunction = new Function("a", "b", "return a * b");

var x = myFunction(4, 3);
//结果等同于
var myFunction = function (a, b) {return a * b}

var x = myFunction(4, 3);

```

函数可以作为一个值来使用，或者一个表达式。

```js
function myFunction(a, b){
  return a * b;
}
var x = myFunction(4,5);
// 函数作为一个表达式使用

function myFunction(a, b) {
    return a * b;
}

var x = myFunction(4, 3) * 2;

```

#### 函数是对象

js函数有属性和方法，所以它还是一个对象，

```js
  //arguments.length属性返回函数调用是接受函数的个数。

function myFunction(a, b) {
    return arguments.length;
}
Function(3,4);
// 返回结果是2，
```

```js
// 将函数转换为字符串并返回。

unction myFunction(a, b) {
    return a * b;
}

var txt = myFunction.toString();

```

#### 函数传参数

+ 函数对参数值没有进行检查
+ 函数传参分为显式参数(`arameters`)和隐式传参(Arguments).
+ 前者在函数定义时就列出，后者是函数调用时直接给真正的值。
+ 显示传餐函数在定义时没有指定数据类型，隐式参数也没有对类型进行检测。
+ 隐式参数在调用时没有提供参数，则默认参数为nudefined
+ 
```js
function myFunction(x, y) {
    y = y || 0;
    return x * y;
}
myFunction(4);
//y值为nudefine 所以Y就为0.
```

#### Arguments 对象

当调用时设置参数过多，则无法找到相对应的参数名就无法引用了，只能使用 arguments 对象来调用。

```js
x = findMax(1, 123, 500, 115, 44, 88);
 
function findMax() {
    var i, max = arguments[0];//声明一个i 变量和max为数组里第一个
    //判断如参数个数为一个  则返回这个值为最大
    if(arguments.length < 2) return max;
     //用循环依次拉出所有对象
    for (i = 0; i < arguments.length; i++) {
      // 依次和第一个数进行比较，如果这个值大于第一个值，则赋值Max继续比较
        if (arguments[i] > max) {
            max = arguments[i];
        }
    }
    return max;
}
500
```

```js
x = sumAll(1, 123, 500, 115, 44, 88);
 
function sumAll() {
    var i, sum = 0;
    for (i = 0; i < arguments.length; i++) {
        sum += arguments[i];
    }
    return sum;
}
```


#### 通过值传递参数


+ 在函数中调用的参数是函数的隐式参数。
+ JavaScript 隐式参数通过值来传递：函数仅仅只是获取值。
+ 如果函数修改参数的值，不会修改显式参数的初始值（在函数外定义）。
+ 隐式参数的改变在函数外是不可见的。

#### 通过对象传递参数

+ 在JavaScript中，可以引用对象的值。
+ 因此我们在函数内部修改对象的属性就会修改其初始的值。
+ 修改对象属性可作用于函数外部（全局变量）。
+ 修改对象属性在函数外是可见的。


#### 函数调用

函数的四种调用方式不同  在于`this` 的初始化。

##### this关键字

this指向函数执行时的当前对象

#### 调用函数

> 函数中的代码在函数被调用后执行。

下面例子函数不属于任何对象，默认为全局对象。
在HTML中全局对象就是页面，全局对象就是（window）
调用时可以写成`window.myFunction()`
`这种调用是常用方法，但是作用是全局容易产生冲突。`

```js
function myFunction(a, b) {
    return a * b;
}
myFunction(10, 2);           // myFunction(10, 2) 返回 20
```

#### 作为函数方法调用函数

call() 和 apply() 是预定义的函数方法。 两个方法可用于调用函数，两个方法的第一个参数必须是对象本身。
`call`方法: 
语法：`call(thisObj，Object)`
定义：调用一个对象的一个方法，以另一个对象替换当前对象。
个人理解：a.call(b,arg1,arg2..)就是a对象的方法应用到b对象上。
说明：
call 方法可以用来代替另一个对象调用一个方法。call 方法可将一个函数的对象上下文从初始的上下文改变为由 thisObj 指定的新对象。 
如果没有提供 thisObj 参数，那么 Global 对象被用作 thisObj。 

apply方法： 
语法：apply(thisObj，[argArray])
定义：应用某一对象的一个方法，用另一个对象替换当前对象。 
说明： 
如果 argArray 不是一个有效的数组或者不是 arguments 对象，那么将导致一个 TypeError。 
如果没有提供 argArray 和 thisObj 任何一个参数，那么 Global 对象将被用作 thisObj， 并且无法被传递任何参数。

```js
function myFunction(a, b) {
    return a * b;
}   //将myFunction的方法应用到myObject上
myObject = myFunction.call(myObject, 10, 2);     // 返回 20

function myFunction(a, b) {
    return a * b;
}
myArray = [10, 2];
myObject = myFunction.apply(myObject, myArray);  // 返回 20
```

```js
function sortNumber(a,b){           //封装一个方法，定义参数排序方法，
  return a-b;
}

var arr = new Array(-1, 3, 10, 6 ,5, 19, -19);

arr.sort(sortNumber);
//返回[-19, -1, 3, 5, 6, 10, 19]
// 通过返回值（两个相邻值运算得到结果小于0,就位置互换）来判断两个数的位置
```

#### 闭包
   闭包是一个概念，它描述了函数执行完毕内存释放后，依然内存驻留的一个现象     

```js
function a(){
  var i =0;
  function b(){
    alert(i++);
  }
  return b;

}

var c =a();
c(); // 1

```
##### 变量 

js变量可以是全局变量或局部变量。
`全局变量`：作用全局，在web上属于window，可作用全局所有脚本.
`局部变量`：作用所属函数内部，其它不影响。
变量如果不声明，则它就是全局变量。

###### 变量生命周期

    后面再补充
全局变量的作用域是全局性的，即在整个JavaScript程序中，全局变量处处都在。
而在函数内部声明的变量，只在函数内部起作用。这些变量是局部变量，作用域是局部性的；函数的参数也是局部性的，只在函数内部起作用。

##### 计数器困境

设想下如果你想统计一些数值，且该计数器在所有函数中都是可用的。
你可以使用全局变量，函数设置计数器递增：
```js
var counter = 0;   //页面上的任何脚本都能改变计数器，即便没有调用 add() 函数

function add() {
  //var counter = 0; 如果将上面的声明移到函数内部，
  //会是函数每次被调用计算器每次重置为1.

   return counter += 1;
}

add();
add();
add();

// 计数器现在为 3
```

#### 内嵌函数

+ 所有函数都能访问全局变量。  
+ js所有函数都能访问它们上一层的作用域。
Js支持嵌套函数。嵌套函数可以访问上一层的函数变量。
该实例中，内嵌函数 plus() 可以访问父函数的 counter 变量：

```js
function add() {
    var counter = 0;
    function plus() {counter += 1;}
    plus();    
    return counter; 
}
```

#### 闭包

闭包就是能够读取其他函数内部变量的函数。
闭包就是将函数内部和函数外部连接起来的一座桥梁。
闭包的用途:一个是前面提到的可以读取函数内部的变量，
另一个就是让这些变量的值始终保持在内存中。

```js
var add = (function () {
    var counter = 0;
    return function () {return counter += 1;}
})();

add();
add();
add();

// 计数器为 3
```

#### this关键字
函数运行时，自动生成的一个内部对象，只能在函数内部使用。
this关键字虽然会根据环境变化，但是它始终代表的是调用当前函数的那个对象。 

##### 方法调用模式

 当函数被保存为一个对象的属性时，它就可称为这个对象的方法。当一个方法被调用时，this被绑定到这个对象上。如果调用表达式包含一个提取属性的动作（. 或 []），那么它被称为方法调用。例如：

```js
var name = "window";
var obj = {
    name: "kxy",
    sayName: function() {
        console.log(this.name);
    }
};
obj.sayName();  //kxy
```


##### 函数模式调用

当一个函数并非一个对象的属性时，那么它就是被当做函数来调用的。在此种模式下，this被绑定为全局对象，在浏览器环境下就是window对象。例如：
```js
var name = "window";
function sayName() {
    console.log(this.name);
}
sayName();

// undifine
```

##### 构造函数模式

 如果在一个函数前面加上new关键字来调用，那么就会创建一个连接到该函数的prototype成员的新对象，同时，this会被绑定到这个新对象上。这种情况下，这个函数就可以成为此对象的构造函数。例如：

```js
function Obj() {
    this.name = "kxy";
}
var person = new Obj();
console.log(person.name);   //kxy
```

##### apply调用模式

 在JS中，函数也是对象，所有函数对象都有两个方法：apply和call，这两个方法可以让我们构建一个参数数组传递给调用函数，也允许我们改变this的值。例如：

```js
var name = "window";
var person = {
    name: "kxy"
};
function sayName() {
    console.log(this.name);
}
sayName();    //window
sayName.apply(person);   //kxy
sayName.apply();    //window
```


一个函数并非一个对象的属性时，那么它就是被当做函数来调用的。在此种模式下，this被绑定为全局对象，在浏览器环境下就是window对象。例如：



```js 
var name = "window";
var obj = {
    name: "kxy",
    sayName: function() {
        console.log(this.name);
    }
};
obj.sayName();  //kxy   sayName函数作为对象obj的方法调用，所以函数体中的this就代表obj对象。
```



 
#### 对象

+ 我对js面向对象编程的理解是，将需要调用或者修改的数据，封装成一个对象，会减少调用时候的一些不必要的麻烦.
+ js里所有的事物都是对象：字符串、数值、数组、函数，日期，正则表达式.....
+ 对象是一个特殊的数据，它拥有属性和方法，是特殊的数据类型。
+ js 允许自定义对象
 
 访问对象属性的语法： `objectName.propertyName`   对象名加属性名。

```js
   // 使用了 String 对象的 length 属性来获得字符串的长度;
var message = "hello World!";
var x = message.length; 
```


访问对象的方法的语法： `objectName.methodName()`

```js 
  // 使用string上的toUpcase()方法来转换文本大小写。
var message = "Hello World!";
var x = message.toUpperCase()
```

#### 创建对象

js能够定义并创建自己的对象

创建对象方法有两种：
1. 定义并创建实例

```js
 创建一个新的实例并向其添加2个属性。
person new Object();
person.Firstname="john";
person.lastname="Doe";
```

替代语法（使用对象 literals）：

```js
person={firstname:"John",lastname:"Doe",age:50,eyecolor:"blue"};

```

2. 使用对象构造器
 使用函数来构造对象：

```js
function person(firstname,lastname,age,eyecolor){
    this.firstname=firstname;
    this.lastname=lastname;
    this.age=age;
    this.eyecolor=eyecolor;
}
myFather=new person("John","Doe",50,"blue");
myFather;   //执行函数myfather.
//得出结果 person {firstname: "John", lastname: "Doe", age: 50, eyecolor: "blue"}
//this指向正在执行的函数本身，或指向所属对象。
```

有了对象构造器可以创建新的实例

```js
var myFather=new person("John","doe","50","blue")
```

把属性添加到js对象，可以通过对象赋值来添加新的属性。

```js
person.firstname="John";
person.lastname="Doe";
person.age=30;
person.eyecolor="blue";

x=person.firstname;
```

#### 把方法添加到对象

方法就是附加在对象上面的函数
构造函数内部定义对象的方法：

```
function person(firstname,lastname,age,eyecolor){
  this.firstname=firstname;
  this.lastname=lastname;
  this.age=age;
  this.eyecolor=eyecolor;
  this.changeName=changeName;
  function changeName(name){
    this.lastname=name;
  }
}

myMother=new person("wang","chunlian",53,"black");
myMother.changeName("doe");
myMother.lastname;
"doe"
myMother;
//结果
person {
  firstname: "wang", lastname: "doe", age: 53, eyecolor: "black", changeName: function
}
// chengeName() 方法吧函数name赋值给person 的lastname属性。this 指向函数父级person。
```

```
```



#### 类


JavaScript 是面向对象的语言，但 JavaScript 不使用类。
在 JavaScript 中，不会创建类，也不会通过类来创建对象（就像在其他面向对象的语言中那样）。
JavaScript 基于 prototype，而不是基于类的。

#### for in 循环

for...in 循环中的代码块将针对每个属性执行一次。

```js

function myFunction(){
  var x;
  var txt="";
  var person={fname:"Bill",Lname:"Gates",age:"56"}
  for (x in person){
    txt=txt+person[x];

  }
console.log(txt);   //结果为"BillGates56"
}
myFunction();






VM2693:9 BillGates56

```

#### number 对象
js只有一种数字类型。
所有的数字都是浮点型类型。
可用小数点或不用小数点书写。
极大或者极小可用科学计数法书写。
整数最多15位。

```js
var pi = 123e5;   // 1230000
var z = 123e-5;   // 0.00123
```

```js
myNumber=2;
while (myNumber!=Infinity){
  myNumber=myNumber*myNumber;
  console.log(myNumber);
}
//结果   Infinity为无穷大。
VM1639:4 4
VM1639:4 16
VM1639:4 256
VM1639:4 65536
VM1639:4 4294967296
VM1639:4 18446744073709552000
VM1639:4 3.402823669209385e+38
VM1639:4 1.157920892373162e+77
VM1639:4 1.3407807929942597e+154
VM1639:4 Infinity
undefined

```

#### NaN 非数字值

使用 isNaN() 全局函数来判断一个值是否是 NaN 值

```js

`数字`除 `字符串`  与 `数字字符串`的得到不同结果。

var x = 1000/"apple";
var y = 1000/"1000";
console.log(x ,y)
// NaN 1
//undefined
```

### 数字可以是数字或对象

```
数字可以私有数据进行初始化，就像 x = 123;
数字对象初始化数据， var y = new Number(123);
```




#### 数字属性

```
MAX_VALUE
MIN_VALUE
NEGATIVE_INFINITY
POSITIVE_INFINITY
NaN
prototype
constructor
```

#### 数字方法

```
toExponential()
toFixed()
toPrecision()
toString()
valueOf()      
```

### 字符串（string）

+ String 对象用于处理已有的字符块。
+ 一个字符串用于存储一系列字符就像 "John Doe".
+ 使用位置（索引）可以访问字符串中任何的字符
+ 字符串的索引从零开始,字符串第一字符为 [0],

使用字符串属性来计算长度

```js
var txt = "Hello World!";
txt.length;
//12  返回结果空格也算一位。
```

字符串使用 indexOf() 来定位字符串中某一个指定的字符首次出现的位置：
astIndexOf() 方法在字符串末尾开始查找字符串出现的位置。 
如果没有对应字符则返回 -1
```js
function myFunction(){
  var str='Click the button to locate where "locate" first occurs';
var n =str.indexOf("to");
console.log(n)

}
myFunction()
//结果 13
```

#### 内容匹配

match()函数用来查找字符串中特定的字符，并且如果找到的话，则返回这个字符

```js
var str = "Hello World!";
var c = str.match("World")
c
//返回["World", index: 6, input: "Hello World!"]
```

#### 内容替换

replace() 方法在字符串中用某些字符替换另一些字符。

```js
function myFunction(){
  var str = "microsoft sssss";
  var txt = str.replace("microsoft","Runoob");
  console.log(txt,str);

}
myFunction();
// 结果 Runoob sssss microsoft sssss
undefined
```

#### 转换大小写

字符串大小写转换使用函数 toUpperCase() / toLowerCase():

```js
var txt ="Hello World!";
var a = txt.toUpperCase();
var b = txt.toLowerCase();
var c = txt;

a;      //"HELLO WORLD!"
b;      //"hello world!"
c;      //"Hello World!"
```

#### 将字符串转化为数组

字符串使用split()函数转为数组:

```js
function myFunction(){
  var str = "a, b, c, d, e, f";
  var n=str.split(",");
  console.log(n)
}
myFunction();
// 打印结果 ["a", " b", " c", " d", " e", " f"]

txt.split(",");   // 使用逗号分隔
txt.split(" ");   // 使用空格分隔
txt.split("|");   // 使用竖线分隔 

```

```


#### 特殊字符

字符串的开始和停止使用单引号或双引号
解决以下面的问题可以使用反斜线来转义引号：

```js
var txt="We are the so-called \"Vikings\" from the north.";
txt

// 返回"We are the so-called "Vikings" from the north."
```

|代码|输出|
|------|-------|
|\'|单引号|
|\"|双引号|
|\\|斜杆|
|\n|换行|
|\r|回车|
|\t|tab|
|\b|空格|
|\f|换页|

#### 字符属性和方法
```js
属性：
length        //获取长度
prototype     //原型   （不明白）
constructor   //构造函数
方法:
charAt()
charCodeAt()
concat()
fromCharCode()
indexOf()       //查找  并返回位置
lastIndexOf()   //从末尾查找
match()         //查找字符串位置，如果有就返回字符串
replace()       //替换字符串
search()
slice()
split()         //将字符串转化为数组
substr()
substring()     
toLowerCase()   //转换成小写
toUpperCase()   //转换成大写
valueOf()       //valueOf() 方法可返回 Boolean 对象的原始值
```


要得到一个类的实例时，往往是要运行其构造函数的


### Date(日期)

>使用Date()获取当前时间

```js
var d = new Date();
d;
Wed Apr 12 2017 00:12:16 GMT+0800 (CST)
```

> 使用getFullYear();获取今年的年份

```js
两种写法
var d = new Date();
    var u = d.getFullYear();
u 
//2017

var d = new Date().getFullYear();
d;
//2017
```

> getTime() 返回从 1970 年 1 月 1 日至今的毫秒数。

```js
var x = new Date().getTime();
x;

//1491930661139   这个有错
```

> 如何使用 setFullYear() 设置具体的日期。

```js
var d = new Date();
var a=d.setFullYear(2020,10,3);
a;

//1604337913836  结果有问题明天验证。
```

> 如何使用 toUTCString() 将当日的日期（根据 UTC）转换为字符串。
getDay()

```js
function myFunction(){
  var x =new Date().toUTCString();
console.log(x)

}
myFunction();
// Tue, 11 Apr 2017 17:36:45 GMT   这是字符串  
`为毛线不能用上面的写法写??`
undefined
```

>如何使用 getDay() 和数组来显示星期，而不仅仅是数字。

```js
var today = new Date();  

b = today.getDay();
b;
// 返回星期几
4

function myFunction(){
  var d = new Date();
  var weekday=new Array(7);
  weekday[0]="周0";
  weekday[1]="周1";
  weekday[2]="周2";
  weekday[3]="周3";
  weekday[4]="周4";
  weekday[5]="周5";
  weekday[6]="周6";  
var b = weekday[d.getDay()];
console.log(b)
}
myFunction();
// 周3
```

### 设置日期

将日期设置在5天以后

```js
var today = new Date();

y = today.getDate();

//返回 13

```

```js
var myDate=new Date();
myDate.setDate(myDate.getDate()+5);
myDate()
// Tue Apr 18 2017 10:56:25 GMT+0800 (CST)
```


#js额外学习小积累

```js
var str = '{"name":"huangxiaojian","age":"23"}'


// 将字符串文件转化为json对象的方法
JSON.parse(str)
Object {name: "huangxiaojian", age: "23"}
str.age
undefined
var str = '{"name":"huangxiaojian","age":"23"}'



str = JSON.parse(str)
Object {name: "huangxiaojian", age: "23"}
str.age
"23"





```

## 将字符串转换为json.

```js
var a = {}

a['id'] =1;
a['user_profile'] = {}
a['user_profile']['name'] = "sdfdsf"
a['user_profile']['names'] = {}
a['user_profile']['names']['dsf']="dsf"
console.log("a=>",JSON.stringify(a,null,2))
VM463:8 a=> {
  "id": 1,
  "user_profile": {
    "name": "sdfdsf",
    "names": {
      "dsf": "dsf"
    }
  }
}
undefined
var a = {}

a['id'] =1;
a['user_profile'] = {}
a['user_profile']['name'] = "sdfdsf"
a['user_profile']['names'] = {}
a['user_profile']['names']['dsf']="dsf"
console.log("a=>",JSON.stringify(a,null,4))
VM464:8 a=> {
    "id": 1,
    "user_profile": {
        "name": "sdfdsf",
        "names": {
            "dsf": "dsf"
        }
    }
}
undefine
```

### 字符串（string） 对象

string对象用来储存字符类似 “John Doe”

+ 字符串用`''`或`“”` 

```
var carname = "Volvo XC60";
var carname = 'Volvo XC60';
```

+ 使用位置（索引）可访问字符串中任何字符。

```
var character=carname[7];
```

+ 字符串从0开始为第一个数字，可以在字字符串中使用引号

```js
var answer='It\'s alright';              //It's alright
var answer="He is called \"Johnny\"";    //He is called "Johnny"
```

### 字符串（string）

+ 字符串（string）使用长度属性来计算字符长度：
```js
var txt = "Hello World!";
n =txt.length;
n;    // 12
```

+ 使用indexOf()定位某个字符出现的位置。lastindexof()是倒序查找。没有就返回`-1`

```js
var str = "Hello wrold ,welcome to the unverse.";
var n=str.indexOf("wrold");
n;   //7
```

#### 内容匹配

match()函数用来查找字符串中特定的字符，并且如果找到的话，则返回这个字符。
```js
var str = "Hello Wrold!"
var n = str.match("Wrold")
n; //["Wrold", index: 6, input: "Hello Wrold!"]
```

#### 替换内容

replace()字符串中某个字符替换另一个字符

```js
str = "please visit Microsoft!"
var n =str.replace("Microsoft","w3cschool");

n;    //"please visit w3cschool!"
```

#### 字符串大小写转换

字符串大小转换使用 `toUpperCase()`/ `toLowerCase()`
```js
 var txt = "Hello World!"
 var txt1 = txt.toUpperCase();
 var txt2 = txt.toLowerCase();
 txt1;   //"HELLO WORLD!"
 txt2;   //"hello world!"


```

#### 字符串转化为数组

使用split()函数转换
```js
txt = "a,b,c,d";   //字符串
txt = split(",")   //逗号隔开  txt = [a,b,c,d]
txt = (" ")        //空格隔开
txt - ("|")        //使用 |  隔开
```


### 数组

+ 数组对像使用单独的变量名来储存一系列数字。
+ 数组可以用一个变量名存储所有的值，并且可以用变量名访问任何一个值。
+ 数组中的每个元素都有自己的的ID，以便它可以很容易地被访问到

数组的三种定义方法：

```js
var myCars =new Array();
myCars[0] = "saab";
myCars[1] = "volvo";
myCars[2] = "BMW";

myCars
//["saab", "volvo", "BMW"]
var myCars = new Array("saab", "volvo","BMw");
myCars
//["saab", "volvo", "BMw"]

var myCars = ["saab","Volvo","BWM"];
myCars;
//["saab", "Volvo", "BWM"]

```

访问和修改数组：

```js
//访问myCars[0]数字第一个值
var name = myCars[0];
//修改 重新赋值
myCar[0]="opel";

```

数组中可以有不同的变量类型：
你可以在一个数组中包含对象元素、函数、数组

```js
myArray[0]=Date.now;
myArray[1]=myFunction;
myArray[2]=myCars;

```

使用数组对象的预定义属性和方法：

```js
var x = myCars.length    //myCars中元素数量
var y = myCars.indexof("volvo")  //"volvo值的索引"

```

使用全局构造函数，构造新的js对象的属性和方法。

```js
Array.prototype.myUcase = function(){
  for (i=0;i<this.length;i++){
    this[i]=this[i].toUpperCase();
  }
}
function myFunction(){
  
  var fruits =["Banana","Orange","Apple","Mango"];
  fruits.myUcase();
 }  
   //如何调用还是有问题。。.....
```

#### 更多实例方法

合并两个或三个素组

```js
var parents = ["Jani", "Tove"];
var brothers = ["Stale", "Kai Jim", "Borge"];
var children = ["Cecilie", "Lone"];
var family = parents.concat(brothers, children);
family;
// ["Jani", "Tove", "Stale", "Kai Jim", "Borge", "Cecilie", "Lone"]
```

使用join()方法将数组元素组成字符串。

```js
var fruits = ["Banana","Orange","Mango"];
var a = fruits.join();
a
// "Banana,Orange,Mango"
```

使用pop（）方法删除数组最后一个元素。

```js
var fruits = ["banana","Orange","Apple","Mango"];
var x = fruits.pop();
fruits
//["banana", "Orange", "Apple"]

```

使用push（）给数组末尾添加新元素。

```js
 var fruits = ["banana","Orange","Apple","Mango"];
var x = fruits.push("tea");
fruits
// ["banana", "Orange", "Apple", "Mango", "tea"]
```

使用reverse()方法将数字内元素颠倒顺序。

```js
var fruits = ["Banana","Apple","Orange","mango"];
var x = fruits.reverse();
fruits;

// ["mango", "Orange", "Apple", "Bana
```

使用shift()方法删除数组第一个元素。

```js
var fruits = ["Banana","Orange","Apple","Mango"];
var x = fruits.shift();
fruits;
["Orange", "Apple", "Mango"]
```

使用slice 丛数组里选择元素
```js
var fruits = ["Banana","Orange","Apple","Mango"];
var x = fruits.shift(1，3);  //从第2个个元素开始 第四个元素之前结束。
x;
//["Orange","Apple"]
```

使用sort()将数组排分别依照`字母升序排列`，数字升序或降序排列。

```js
var fruits = ["Banana","Orange","Apple","Mango"];
var x = fruits.sort();
fruits;
// ["Apple", "Banana", "Mango", "Orange"]
var points = [1, 3 ,22, 11, 5];
var b = points.sort(function(a,b){ return b-a});// 顺序就将b-a，改为a-b.

points;
// [22, 11, 5, 3, 1]

```

在数组第二个位置添加一个元素

```js
var friuts = ["Banana", "Orange", "Apple","Mango"];
  friuts.splice(2,0,"Lemon","Kiwi");  //前面一个2是在第二个数之后插入，后面的0是替换0个
  friuts
// ["Banana", "Orange", "Lemon", "Kiwi", "Apple", "Mango"]


var friuts = ["Banana", "Orange", "Apple","Mango"];
  friuts.splice(2,2,"Lemon","Kiwi");  //前面一个2是在第二个数之后插入，后面的0是替换0个
  friuts
// ["Banana", "Orange", "Lemon", "Kiwi"]




```

使用toString()将数组转化为字符串

```js
var fruits = ["Banana","Apple", "Orange", "Mange"];
var x =fruits.toString();
x
// "Banana,Apple,Orange,Mange"
```

在数组开头添加新的元素 unshift();
不能用于 Internet Explorer 8 之前的版本

```js
var fruits = ["Banana","Apple", "Orange", "Mange"];
var x =fruits.unshift("lpineeapple");
fruits
// ["lpineeapple", "Banana", "Apple", "Orange", "Mange"]
```

#### js 布尔对象

+ Boolean 对象代表两个值:"true" 或者 "false"

定义一个名为 myBoolean的对象。

```js
var myBoolean = new Boolean;
```

布尔值无初始对象或为下面的值时，对象值为false 否则为true。
```js
0 , -0 , null , "" ,false, undefined, NaN 
```

#### math(算数) 对象

+ Math（算数）对象作用是执行常见的算数任务
+ Math 对象提供多种算数值类型和函数。无需在使用这个对象之前对它进行定义。


使用round()方法将带有小数的数字转换为接近的整数(四舍五入)

```js
var y = 2.5;
x = Math.round(y)
x
//3
```

使用random()方法返回0到1之间的随机数。

```js
var num = Math.round();
num
// 0.3648955511654066;

var num = Math.round(Math.random()*100000);
num
// 84114  做随机验证码很实用。
```

使用Max() 或Min()返回两个给定值中较大的一个。 
+ 在ECMASCript3之前，只有两个参数。

```js
var num = Math.max (1,100);
num
// 100
var num = Math.min (1,100);
num
// 1
```

使用Math对象属性和方法：

```js
var x=Math.PI;    //圆周率3.1415926......
var y=Math.sqrt(16);   //开方  结果为4
```

使用floor()方法和random()方法返回介于0和11之间的数
+ floor()方法去除小数点后面的数

```js
var num = Math.floor(Math.random()*11);
num;
//1


var num = Math.floor(Math.random()*100000);
num;
// 60221
```


##### 算数值
```js
Math.E        //自然对数
Math.PI       // 圆周率
Math.SORT2
Math.SORT1_2
Math.LN2
Math.LN10
Math.LOG2E
Math.LOG10E
```

### RegExp 对象

+ RegExp：是正则表达式（regular expression）的简写。
+ 正则表达式描述了字符的模式对象。
+ 当您检索某个文本时，可以使用一种模式来描述要检索的内容。RegExp 就是这种模式。
+ 简单的模式可以是一个单独的字符。
+ 更复杂的模式包括了更多的字符，并可用于解析、格式检查、替换等等。
+ 您可以规定字符串中的检索位置，以及要检索的字符类型，等等。

语法：

```js
var patt=new RegExp (pattern,modifiers);
或者
var patt=/pattern/modifiers;
```

+ 模式描述了一个表达式模型。
+ 修饰符(modifiers)描述了检索是否是全局，区分大小写等。
+ 注意：当使用构造函数创造正则对象时，需要常规的字符转义规则（在前面加反斜杠 \）。比如，以下是等价的：

```js
var re = new RegExp("\\w+");
var re = /|w+/;

```

RegExp 修饰符:

i - 修饰符是用来执行不区分大小写的匹配。
g - 修饰符是用于执行全文的搜索（而不是在找到第一个就停止查找,而是找到所有的匹配）。

在字符串中不区分大小写“runoob”

```js
i - 修饰符是用来执行不区分大小写的匹配。
g - 修饰符是用于执行全文的搜索（而不是在找到第一个就停止查找,而是找到所有的匹配）。
```

```js

var str = "visit RUnoob";
var patt1=/runoob/i;
str.match(patt1);
// ["RUnoob", index: 6, input: "visit RUnoob"]
```

```js
var str = "Is this all there is?";
var patt1 = /is/g;
str.match(patt1)
// ["is", "is"]
```

test()搜索字符串 的位置，根据结果返回真假。

```js
var pattl = new RegExp("e");
var banbool = pattl.test("The best is not defined");
banbool;
// true
```

当使用构造函数创造正则对象时，需要常规的字符转义规则（在前面加反斜杠 \）

```js
var str = 'runoob';
var patt1 =new RegExp('\\w','g');  //有转义作为正则表达式处理
var patt2 = new RegExp('\w','g');  // 无转义作为正则表达式处理
var patt3 = /\w+/g;                // 与patt1相同
patt1.test(str);

//true
patt2.test(str)
//false
patt3.test(str);
//true \）
```


### this 指向问题

this：是函数内部的一个属性，当函数被调用时，this 产生一个内部函数，只能在函数内部起作用。
this：指向总是函数的调用者，当没有被调用时this指向window

```js
console.log(this)  //window
var fun = function(){
  console.log(this);

}
fun();  //打印window
// 等价于下面调用方式
this.fun();
window.fun();
// 匿名函数，可以理解成window创建了个变量来保存这个函数，
(function(){
    console.log(this);
})();  //打印window
```

这里window调用函数，函数内this指向window 对象也一样

```js
// 函数作为方法被调用时 this 指向调用的这个对象
var fun = function(){
        console.log(this);
};
var o ={
  fn:fun
}
o.fn()  // 打印对象o
// 如下的方式也没有问题
var a = {
        name : "xiao2",
        sayName: function(){
              alert(this.name);
        }
};
a.sayName(); //弹出xiao2



```

# 回调函数 

>回调函数通过`函数指针`调用的函数。如果你把`函数的指针`（地址）作为`参数`传递给另一个函数，当这个`指针`被用来调用其所指向的函数时，我们就说这是回调函数

##回调函数与普通函数区别：

`普通函数调用`：当调用程序触发，程序立即执行被调用程序，等被调用程序执行完成，再返回调用程序执行。

`书写方法`：被调用函数名书写在函数内部直接调用

`应用`：单线程引用

`回调函数调用`
：当调用程序发起对回调函数调用，（不等回调函数执行完毕）调用程序和被调用程序同步执行，当调用程序执行完毕，被调用的函数会反过来调用某个事先指定的函数，通知调用程序，函数调用结束，整个过程称之为回调（callback）。

`书写方法`:作为参数传递给调用者，调用者不知道自己调用的是什么

`应用`：多线程

##回调函数作用：

作用：将同步转换成异步
回调缺点：回调函数的优点是简单、容易理解和部署，缺点是不利于代码的阅读和维护，各个部分之间高度耦合（Coupling），流程会很混乱，而且每个任务只能指定一个回调函数。

```js

function f1(callback){
  setTimeout(function(){
callback();
  console.log('回调函数--------》')
  
  }),10000
}
var f2 = function(){
  console.log('-----11111----->')
}
f1(f2);
//undefined
// -----11111----->
// 回调函数--------》


函数作为参数传四

function say(value){
  console.log(value);
};        
// 回调函数需要一个参数value


function execute(someFunction, value){
  someFunction(value);
}
execute(say, 'hi js');  //'hi js'

// 将say方法作为参数传递给execute
// 回调函数在函数内部创建

function execute(someFunction, value){
  someFunction(value);
  }
  execute(function(value){
    alert(value)}, 'hi js') //'hi js'
}
// 将匿名函数直接作为参数传递给execute，

var CallBack = function(num){
  console.log(num);
}
// 调用callback
Foo(a,Callback)

```


