# 进一步理解Webpack

## Webpack 做什么用的： 

    1.  一个打包工具
    2.  一个模块加载工具
    3.  各种资源都可以当成模块来处理
    4.  网站 [Webpack网站](http://webpack.github.io/)

## Webpack 优势

* webpack 是以 commonJS 的形式来书写脚本滴，但对 AMD/CMD     的支持也很全面，方便旧项目进行代码迁移。
* 能被模块化的不仅仅是 JS 了。
* 开发便捷，能替代部分 grunt/gulp 的工作，比如打包、压缩混淆、图片转base64等。
* 扩展性强，插件机制完善，特别是支持 React 热插拔（见 react-hot-loader   ）的功能让人眼前一亮。
  
##  webpack 辅助软件 

>Webpack 基于 note.js 开发。npm作为[note](https://nodejs.org/en/)管理工具。所以必须了解他们。

### Node

[note](https://nodejs.org/en/) 是一个在浏览器外部创建互联网应用程序的框架，它基于 Google 开发的 V8 JavaScript 引擎，轻量，高效，事件驱动，非阻塞I/O，特别适合运行于跨分布式设备的实时数据处理程序。
#### 作用
1. 搭建web网络应用
2. 开发Unix命令行工具
3. 开发构建工具，辅助前端开发(webpack,grunt,gulp..)

### NPM
[npm](https://www.npmjs.com/) (node package manager) node.js的包管理器，用于node插件管理（安装、卸载、更新、管理依赖等）。

#### 作用

1. JS开发人员可以轻松地更新、共享和重用代码。
2. 管理项目中的依赖包模块
3. 与他人分享和接收反馈

#### 替代工具 

cnpm：淘宝网提供的国内NPM镜像，因为npm安装插件是从外国服务器下载，受网络影响大，可能出现异常。
yarn：是Facebook、Google、Exponent 和 Tilde 联合推出了一个新的 JS 包管理工具，是为了弥补 npm 的安装包（packages）的速度不够快、拉取的 packages 可能版本不同、npm 允许在安装 packages 时执行代码可能产生安全隐患等一些缺陷而出现的

# 安装
  1.首先要安装[Note](https://nodejs.org/en/) ，Node.js 自带了软件包管理器npm,用npm 安装来安装Webpack。

###### 方法一
``` shell
$ npm install webpack -g      # 全局安装
```

###### 方法二

```
$ npm install webpack --save    # 本地安装，存储到配置（package.json）中
```

  2.安装之前需要初始化，而生成一个 package.json 文件。
  
  3.安装Webpack


###### 方法一

```shell

$ npm install webpack -g        # 全局安装

###### 方法二
$ npm install webpack --save    # 本地安装，存储到配置（package.json）中
```


## 运行
../node_modules/.bin/webpack webpack.config.js   个人理解找到webpack  来解析后面的。
../node_modules/.bin/webpack-dev-server webpack.config.js                    测试用的如果后面配置文件就一个，就不用 加webpack.config.js
     <!--  设置登录地址 -->
<!-- /Project is running at http://localhost:8080 -->  测试时用这个地址显示







module.loader: 其中test是正则表达式，对符合的文件名使用相应的加载器./.css$/会匹配 xx.css文件，但是并不适用于xx.sass或者xx.css.zip文件.
url-loader: 它会将样式中引用到的图片转为模块来处理; 配置信息的参数“?limit=8192”表示将所有小于8kb的图片都转为base64形式。
entry: 模块的入口文件。依赖项数组中所有的文件会按顺序打包，每个文件进行依赖的递归查找，直到所有模块都被打成包；
output：模块的输出文件，其中有如下参数：
filename: 打包后的文件名
path: 打包文件存放的绝对路径。
publicPath: 网站运行时的访问路径。
relolve.extensions: 自动扩展文件的后缀名，比如我们在require模块的时候，可以不用写后缀名的。
relolve.alias: 模块别名定义，方便后续直接引用别名，无须多写长长的地址
plugins 是插件项;


