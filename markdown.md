# markdown 语法

>推荐VS code写markdown。 插件Markdown Preview Enhanced预览，插件markdownlint 语法检测，Markdown PDF用于转化pdf，html，png等
[markdown中文网](http://www.markdown.cn)

[TOC]

## 段落

一个制表符或者四个空格

## #~######六级标题 或者使用====== ------

最开始应以#一级标题开始，符号后一空格开始写内容

## 区块引用 >或多个>

## 列表

1. 无序列表 用* + -号开头
2. 有序列表 用数字 + .开头 原则上数字不影响输出结果

## 分割线

一行中用三个以上的星号、减号、底线来建立一个分隔线，行内不能有其他东西

---

## 链接

- 行内链接 [百度](https://www.baidu.com)
- 参考链接 [百度][id]
- 链接内容形式定义 [id]: https://www.baidu.com  "Optional Title Here"

  - 方括号（前面可以选择性地加上至多三个空格来缩进），里面输入链接文字
  - 接着一个冒号
  - 接着一个以上的空格或制表符
  - 接着链接的网址
  - 选择性地接着 title 内容，可以用单引号、双引号或是括弧包着

## 强调

\* 或 _ 包裹来表示\<em>, ** 或 __来表示\<strong>

- *em测试*
- **strong测试**

## 代码

```
printf();
代码段测试
```

## 图片

目前为止markdown没法指定图片的大小 可以选择用普通的\<img>标签

- 行内式 ![名字](http://t2.hddhhn.com/uploads/tu/201805/9999/89189702b5.jpg)
- 参考式 和 链接说明一致。只是开始多一个！号

## 反斜杠

```
\   反斜线
`   反引号
*   星号
_   底线
{}  花括号
[]  方括号
()  括弧
#   井字号
+   加号
-   减号
.   英文句点
!   惊叹号
```

## \[TOC]目录提取

存在问题**导出pdf html等丢失**

## ::: :::注释

::: warning
*here be dragons*
:::

## uml图

>[plantuml参考链接](http://plantuml.com/)

@startuml
actor Bob #red
Bob -[#red]> Alice : hello
Alice -[#0000FF]->Bob : ok
@enduml