---
title: node.js第一个应用
date: 2018-05-15 16:10:10
tags: node.js学习
---

<br/>

#### 什么是node.js？

> 简单的说node.js就是运行在服务端的JavaScript
  node.js是一个基于chrome javascript 运行时建立的一个平台
  node.js是一个事件驱动I/O服务器JavaScript环境，基于Google的v8殷勤，v8殷勤执行JavaScript的速度非常快，性能非常好

#### 查看版本

> node -v
  注意：不同版本间是有差异性的

#### 第一个node.js程序： hello world!

> 脚本模式
  console.log("hello world!");
  保存该文件，文件名为helloworld.js，并通过node命令来执行 node helloworld.js
  程序执行结果为 hello world!

> 交互模式
  打开终端，输入node进入命令交互模式，可以输入一条代码语句后立即执行并显示结果
  node
  > console.log('hello world!')
  hello world!

#### 创建node的第一个应用

> 如果我们使用PHP来编写后端的代码时，需要Apache或者Nginx的http服务器，并配置mod_php5模块和php_cgi
  从这个角度看，整个接受http请求并提供web页面的需求根本不需要PHP来处理
  不过对node.js来说，概念就完全不一样了，使用node.js时，我们不仅仅在实现一个应用，同事还实现了整个http服务器
  事实上，我们的web应用以及对应的web服务器基本上是一致的
  在我们创建node的第一个程序“hello world!”应用前，让我们先了解下node.js应用由那几个部分组成

  1.引入required模块：我们可以使用require指令来载入node.js模块
  2.穿件服务器：服务器可以监听客户端的请求，类似于Apache、Nginx等http服务器
  3.接受请求与响应请求：服务器很容易创建，客户端可以使用浏览器或终端发送http请求，服务器接受请求后返回响应数据

#### 创建node.js应用

> 步骤一：引入required模块

我们使用require指令来载入http模块，并将实例化的http赋值给变量http

> var http = require('http')

> 步骤二：创建服务器

接下来我们使用http.createServer()方法创建服务器，并使用listen方法绑定8888端口。函数通过request、response参数来接收数据和响应数据
实例如下，在你的项目的根目录下创建一个叫server.js的文件，并写入以下代码

    var http = require('http);
    http.createServer(function (request, response) {

      // 发送http头部
      // http状态值：200 : ok
      // 内容类型：text/plain
      response.writeHead(200, {
        'Content-Type': 'text/plain'
      })

      // 发送响应数据“hello world”
    }).listen(8888)

    // 终端打印如下结果
    console.log('Server running at http://127.0.0.1:8888/')

以上代码我们完成了一个可以工作的http服务器
使用node命令执行以上代码

> node server.js

结果：Server running at http://127.0.0.1:8888/

> 分析：

* 第一行请求（require）node.js自带的http模块，并把它赋值给http变量

* 接下来我们调用http模块提供的函数：createServer，这个函数会返回一个对象，对象有个叫listen的方法，这个方法有个数值参数，指定这个http服务器监听的端口号








