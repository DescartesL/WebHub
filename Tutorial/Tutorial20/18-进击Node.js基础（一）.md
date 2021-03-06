### 进击Node.js基础（一）
[教程地址：进击Node.js基础（一）](http://www.imooc.com/learn/348)

---
### 第1章 前言 
#### 1-1 Node.js基础-前言
- node运行环境可以解析js代码（没有浏览器安全级的限制），提供系统级别的API，比如文件的读写，进程的管理，网络通信

#### 1-2 为什么学习Nodejs
- 如何学习node.js
  - nodeje.org官网
  - npmjs.com npm官网
  - github.com
  - stackoverflow.com

---
###  第2章 安装 Nodejs 
#### 2-1 Node.js基础-课程简介
- 1.安装node.js
- node.js api讲解
- node.js创建小应用

#### 2-2 Nodejs版本常识
- 偶数位为稳定版本，比如0.6.x,0.8.x,0.10.x
- 奇数位为非稳定版本，如0.7.x

#### 2-3 Windows下安装Nodejs
- 安装git bash/ node.js

#### 2-4 Linux下安装Nodejs
>略

#### 2-5 Mac下安装Nodejs
>略

###  第3章 等不及了来尝鲜
#### 3-1 Node.js基础-起一个web服务器
- 按照官网的代码运行了一个最简单的web服务器

#### 3-2 Node.js基础-命令行中体验
- 浏览器和node.js环境下的顶级对象不一样，一个是window一个事global

---
###  第4章 模块与包管理工具 
#### 4-1 Node.js 的模块 与 Commonjs 规范
- Commonjs规范
  - 一个模块可以分成三个部分：定义，标识，引用

#### 4-2 模块的分类
- 模块的分类：核心模块，文件模块，第三方模块

#### 4-3 简单的Nodejs模块
- 模块的流程
  - 创建模块
  - 导出模块
  - 加载模块
  - 使用模块

###  第5章 横扫 Nodejs API
#### 5-1 Node.js-不要陷入版本选择的深渊
- 历史： node.js /io.js

#### 5-2 URL网址解析的好帮手
- node中有url模块，有format(),parse(),resolve()方法，用来解析或者凭借成一个url
- 教程中有提到的url模块只有上面三个方法，但是我本地node 版本是6.9的有5个方法，还有一个resolveObject(),url()方法

#### 5-3 QueryString参数处理小利器
- 一个和参数相关的帮助类,node.js原生自带,直接 require('querystring') 即可使用
- 序列化：querystring.stringify()
- 反序列化：querystring.parse()
- 转义：querystring.escape()
- 反转义：querystring.unescape()

#### 5-4 HTTP知识先填坑
- 介绍了请求的全过程
- 可以将一个http请求的流程粗暴拆分为请求和相应，无论是请求还是相应都会发送http头和正文信息

#### 5-5 HTTP知识填坑之“以慕课网为例分析”
- 请求状态码status code ： 
- 1XX表示请求已经接受正在处理
- 2XX请求接受，已经处理完毕
- 3XX重定向 
- 4XX 有语法错误，客户端错误 
- 5XX 服务器端的错误    
- 200 客服端请求成功 
- 400 客户端请求语法错误 
- 401 请求没有经过授权 
- 403 拒绝提供服务 是因为没有权限等等  
- 404 没找到 有可能输入的URL地址错误  
- 500 服务器 发生错误  
- 503 服务器端当前还不能处理客户端请求  可能需要过一段时间

#### 5-6 HTTP 事件回调进阶
- 什么是回调：回调是异步编程时的基础，将后续逻辑封装成起始函数的参数，逐层嵌套
- 什么是同步/异步：同步是指：发送方发出数据后，等接收方发回响应以后才发下一个数据包的通讯方式。异步是指：发送方发出数据后，不等接收方发回响应，接着发送下个数据包的通讯方式
- 什么是I/O：磁盘的写入（in）磁盘的读取（out）
- 什么的单线程/多线程：一次只能执行一个程序叫做单线程，一次能执行多个程序叫多线程
- 什么是阻塞/非阻塞：阻塞：前一个程序未执行完就得一直等待；非阻塞：前一个程序未执行完时可以挂起，继续执行其他程序，等到使用时再执行
- 什么是事件：一个触发动作（例如点击按钮）
- 什么是事件驱动：一个触发动作引起的操作（例如点击按钮后弹出一个对话框）
- 什么是基于事件驱动的回调：为了某个事件注册了回调函数，但是这个回调函数不是马上执行，只有当事件发生的时候，才会调用回调函数，这种函数执行的方式叫做事件驱动~这种注册回调就是基于事件驱动的回调，如果这些回调和异步I/O(数据写入、读取)操作有关，可以看作是基于回调的异步I/O，只不过这种回调在nodejs中是有事件来驱动的
- 什么是事件循环：事件循环Eventloop,倘若有大量的异步操作，一些I/O的耗时操作，甚至是一些定时器控制的延时操作，它们完成的时候都要调用相应的回调函数，从而来完成一些密集的任务，而又不会阻塞整个程序执行的流程，此时需要一种机制来管理，这种机制叫做事件循环.总而言之就是：管理大量异步操作的机制叫做事件循环
- Event Loop：回调函数队列。异步执行的函数会被压入这个队列; 队列被循环查询

#### 5-7 HTTP 源码解读之先了解作用域、上下文
- this解释的很好，值得多看几遍
- this 通常指的是调用函数的拥有者
- 拥有者叫做执行上下文

#### 5-8 HTTP 源码解读
- 基本看不懂 

#### 5-9 HTTP 性能测试
>略

#### 5-10 HTTP 小爬虫
- 演示了一个HTTP的爬虫
- 试用了http模块和cheerio爬虫模块
- 尝试了使用箭头函数，let/const等es6语法

#### 5-11 事件模块小插曲
- node.js里面没有浏览器端的冒泡捕获这些事件的
- Event是node.js中最重要的模块，它之对外暴露一个对象EventEmitter
- EventEmitter的作用只有两个，分别是事件的发出和监听
- EventEmitter支持多个事件监听器，最大值是10个
- `on()`绑定事件
- `emit()`触发事件
- `removeListener()`移除事件
- `removeAllListeners()`移除所有事件

#### 5-12 Node.js：request方法
- 做了一个用nodep评论慕课的demo，很赞
