# JAVA特性

[TOC]

> 内容不全，用到、学到后更新

## JAVA1.5

- 自动装箱与拆箱

  - Integer i1 = 13 Integer i2 = 13, i1 == i2 为true 
  - Integer i1 = 128 Integer i2 = 128, i1 == i2 为false
  - [-128, 127]为true 享元模式
  - function(Integer f)，function(Double d)调用function(10),会调用function(Double).
  > 注：新版本的j10只会封装成Integer, Double Float类型要在后面指定后缀d,f

- 枚举类型
- 静态导入
- 可变参数
- 内省

  >内省只是通过反射来操作JavaBean的属性,会调用属性的setter getter方法
PropertyDescriptor pd = new PropertyDescriptor("name", User.class);
Method w = pd.getWriteMethod();//获取属性的setter方法
w.invoke(user, "winclpt");
Method r = pd.getReadMethod();//获取属性的getter方法
r.invoke(user, null);

## 1.6

- 脚本语言支持(JSR 223)
- 轻量级Http Server

## 1.7

- switch支持字符串
- 泛型实例化类型自动推断 List<String> tempList = new ArrayList<>()
- 语法上支持集合，而不一定是数组 List<Integer> piDigits = [ 1,2,3,4,5,8 ]
- 新增一些取环境信息的工具方法
  >File System.getJavaIoTempDir() // IO临时文件夹
File System.getJavaHomeDir() // JRE的安装目录
File System.getUserHomeDir() // 当前用户目录
File System.getUserDir() // 启动java进程时所在的目录5

- Boolean类型反转，空指针安全,参与位运算
- 两个char间的equals Character.equalsIgnoreCase(char ch1, char ch2)
- 安全的加减乘除 Math.safeAdd
- map集合支持并发请求，且可以写成 Map map = {name:"xxx",age:18};

## 1.8

- 允许在接口中有默认方法实现(抽象类和接口？)

```java
  interface Formula {  
    double calculate(int a);  
  
    default double sqrt(int a) {  
        return Math.sqrt(a);  
    }  
 }
```

- Lambda表达式(ES6中的箭头函数？)
- 函数式接口

>Lambda表达式如何匹配Java的类型系统？每一个lambda都能够通过一个特定的接口，与一个给定的类型进行匹配。一个所谓的函数式接口必须要有 且仅有一个抽象方法声明。每个与之对应的lambda表达式必须要与抽象方法的声明相匹配。由于默认方法不是抽象的，因此你可以在你的函数式接口里任意添 加默认方法。
任意只包含一个抽象方法的接口，我们都可以用来做成lambda表达式。为了让你定义的接口满足要求，你应当在接口前加上@FunctionalInterface 标注。编译器会注意到这个标注，如果你的接口中定义了第二个抽象方法的话，编译器会抛出异常

```java
@FunctionalInterface  
interface Converter<F, T> {  
    T convert(F from);  
}  

Converter<String, Integer> converter = (from) -> Integer.valueOf(from);  
Integer converted = converter.convert("123");  
System.out.println(converted);
```

- 方法和构造函数引用
> 允许你通过::关键字获取方法或者构造函数的的引用.


```java
Converter<String, Integer> converter = Integer::valueOf;  
Integer converted = converter.convert("123");  
System.out.println(converted);
Integer::new;调用Integer的构造方法
```

- Lambda的范围
> 同匿名对象一样，只是局部变量不用显示声明为final，默认接口方法无效。

- 内置函数式接口
  > [阅读goole guava库](https://github.com/google/guava);

  - Predicate
  - Function
  - Suppliers
  - Consumers
  - Comparator
  - Optional
  - Streams
  - Filter
  - Sorted
  - Map
  - Match
  - Count
  - Reduce
- 时间API
- Annotations 可重复注解

## 1.9

- modularity System 模块系统 
  > 较少JVM加载jdk
- HTTP/2
- JShell
- 不可变集合工厂方法
  > 增加了List.of()、Set.of()、Map.of()和Map.ofEntries()等工厂方法来创建不可变集合
- 私有接口方法
- 多版本兼容 JAR
- I/O 流新特性

## 1.10

> [docs](https://docs.oracle.com/javase/10/docs/api/overview-summary.html)

- 局部变量类型推断
  - 可用
    - 局部变量初始化
    - for内部索引变量
    - for循环变量声明
  - 不可用
    - 方法参数
    - 构造函数参数
    - 字段
    - 方法返回类型
    - 捕获表达式

- 