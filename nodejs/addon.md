# addon c++插件记录

[TOC]

## 环境配置

### 安装运行环境

- python2.7
- git for windows
- vs 2017 community
- nasm
> 具体请参考 [node源码](https://github.com/nodejs/node)中的`building.md`

### 下载源码

- `git clone https://github.com/nodejs/node.git`
- `.\vcbuild.bat Debug x64`
- node源码目录添加环境变量NODE_ROOT 仅方便以后使用配置

### 新建项目

- 新建c++空白项目
- 拷贝node官网上列子,到addon.cc中。并在项目中新建test.js用于测试addon.node
- 配置项目属性
  - 配置属性->常规->目标文件扩展名 .node  配置类型 .dll
  - 配置属性->VC++目录->包含目录 `$(NODE_ROOT)\src $(NODE_ROOT)\deps\uv\include $(NODE_ROOT)\deps\v8\include` 以及其它使用到的库 入nan
  -  配置属性->VC++目录->库目录  `$(NODE_ROOT)\$(Configuration)`

- 连接器->输入->附加依赖项 添加 node.lib
- 配置属性->调试->命令 `$(NODE_ROOT)\$(Configuration)\node.exe`   命令参数`$(ProjectDir)\test.js`

> 环境搭建好，即可在vs中生成addon.node 和 调试addon.node

## node c++函数

> [官方资料](https://nodejs.org/dist/latest-v8.x/docs/api/n-api.html)

### v8

### nan

### N-API
