
# ES函数笔记

[TOC]

>[Node.js v10.3.0文档](http://nodejs.cn/api/buffer.html);

## 模块

- 一个文件就是一个模块，可以通过exports 或 module.exports导出对象
- 模块内的本地变量是私有的，模块会被node.js包装在一个函数中（[模块包装器](待续)）
- node xx.js运行主模块，require.main === module require('xx.js')未false。程序入口require.main.filename
- require(xx.js)不会导致模块代码执行多次，能返回“部分完成”对象。require区分文件大小写，在不区分大小写的系统中会返回不同对象
- Node.js lib/目录下有核心模块 require('http')始终返回内置模块，即使有同名文件
- require循环调用，模块可能在未完成的时候被返回
- 文件模块会尝试 .js .json .node加载模块  .node文件会被解析未dlopen加载的插件模块
- 目录模块有package.json会尝试查找里面的main入口，没有则试图加载index.js 或 index.node
- 未指定文件或不是核心模块，测尝试从父目录开始下的/node_modules下加载模块，直到根目录
- 全局目录加载，NODE_PATH环境变量，不建议使用

## 模块包装器

- Node.js会使用如下函数包装器包装

``` js
(function(exports, require, module, __filename, __dirname) {
    //模块实际代码
});
```

## new关键字

- new 实例化对象，函数中new.target为函数本身，其他的方式实例化new.target === undefined
- new.target返回子类，可用于一个写类似java的抽象类

## Object对象和方法

- prototype 理解
- freeze() seal() preventExtensions()
- assign()
- create()
- entries() keys() for ... in

## callback.call() callback() callback.apply() bind()区别

- call apply可以传入指定对象，以替换当前对象
- call apply参数不一样 call(this, arg1, arg2) apply(this, [arg1,arg2])
- ()不能指定上下文对象
- call(apply) 主要用于方法和对象的接偶
- bind()传参和call()一致，用于生成一个新函数

## setTimeout() setInterval() setImmediate() process.nextTick()

- setTimeout setInterval 执行频率不一样
- setTimeout 采用IO观察者
- setImmediate 采用check观察者
- process.nextTick() 采用idle观察者

