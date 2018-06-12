# Doxygen的安装与配置及简单注释规范

>Doxygen是一种开源跨平台的，以类似JavaDoc风格描述的文档系统，完全支持C、C++、Java、Objective-C和IDL语言，部分支持PHP、C#。注释的语法与Qt-Doc、KDoc和JavaDoc兼容

[TOC]

## Doxygen下载安装

>[doxygen](http://www.stack.nl/~dimitri/doxygen/download.html) 可能需要翻墙
[htmlhelp](https://msdn.microsoft.com/en-us/library/ms669985.aspx) 用Doxygen自动生成chm
[Graphviz](http://www.skycn.com/soft/appid/6971.html)是一个由AT&T实验室启动的开源工具包，用于绘制DOT语言脚本描述的图形。Doxygen 使用 graphviz 自动生成类之间和文件之间的调用关系图

## 配置demo

[Doxyfile demo](./Doxyfile) File->Open选择配置文件，打开后选择自己项目,修改项目名,项目描述即可使用. 具体配置参考网上教程 [doxygen配置](https://blog.csdn.net/andy_93/article/details/53125776) <strong>不保证长期有效<strong>

## 错误记录

- 字符编码错误

>核对文件编码，可以设置Expert->Project->DOXYFILE_ENCONDING为空

- Error: When enabling GENERATE_HTMLHELP the search engine (SEARCHENGINE) should be disable

>Expert->HTML->SEARCHENGINE取消掉

## 注释常用符号

- @file 档案的批注说明。
- @author 作者的信息
- @brief 用于class 或function的简易说明 eg：@brief 本函数负责打印错误信息串
- @param 主要用于函数说明中，后面接参数的名字，然后再接关于该参数的说明
- @return 描述该函数的返回值情况eg: @return 本函数返回执行结果，若成功则返回TRUE，否则返回FLASE
- @retval 描述返回值类型 eg: @retval NULL 空字符串。@retval !NULL 非空字符串。
- @note 注解
- @attention 注意
- @warning 警告信息
- @enum 引用了某个枚举，Doxygen会在该枚举处产生一个链接 eg：@enum CTest::MyEnum
- @var 引用了某个变量，Doxygen会在该枚举处产生一个链接 eg：@var CTest::m_FileKey
- @class 引用某个类，格式：@class \<name\> [\<header-file\>] [\<header-name\>] eg:@class CTest "inc/class.h"
- @exception 可能产生的异常描述 eg: @exception 本函数执行可能会产生超出范围的异常
- @todo 对将要做的事情进行注释
- @see 一段包含其他部分引用的注释，中间包含对其他代码项的名称，自动产生对其的引用链接。
- @relates \<name\> 通常用做把非成员函数的注释文档包含在类的说明文档中。
- @since 通常用来说明从什么版本、时间写此部分代码。
- @code  在注释中开始说明一段代码，直到@endcode命令。
- @endcode  在注释中代码段的结束。
- @pre 用来说明代码项的前提条件。
- @post 用来说明代码项之后的使用条件。
- @deprecated 这个函数可能会在将来的版本中取消。
- @defgroup 模块名
- @class 声明一个类
- @fn 声明一个函数