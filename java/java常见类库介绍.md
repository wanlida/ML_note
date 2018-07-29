Java 类库和常用类库介绍——序
作者： zccst


Java 类库概念： Java 的应用程序接口 (API) 以包的形式来组织，每个包提供了大量的相关类、接口和异常处理类，这些包的集合就是 Java 的类库

包名以 Java 开始的包是 Java 核心包 (Java Core Package) ；
包名以 Javax 开始的包是 Java 扩展包 (Java Extension Package) ，例如 javax.swing 包；

常用的 Java 核心包 (Java Core Package)
1.       java.lang      Java 编程语言的基本类库
2.       java.applet     创建 applet 需要的所有类
3.       java.awt       创建用户界面以及绘制和管理图形、图像的类
4.       java.io        通过数据流、对象序列以及文件系统实现的系统输入、输出
5.       java.NET       用于实现网络通讯应用的所有类
6.       java.util       集合类、时间处理模式、日期时间工具等各类常用工具包
其它还有
7.       java.sql        访问和处理来自于 Java 标准数据源数据的类
8.       java.test       以一种独立于自然语言的方式处理文本、日期、数字和消息的类和接口
9.       java.security    设计网络安全方案需要的一些类
10.   java.beans     开发 Java Beans 需要的所有类
11.   java.math      简明的整数算术以及十进制算术的基本函数
12.   java.rmi       与远程方法调用相关的所有类

常用的 Java 扩展包 (Java Extension Package)
1.  javax.accessibility  定义了用户界面组件之间相互访问的一种机制
2.  javax.naming.*     为命名服务提供了一系列类和接口
3.  javax.swing.*       提供了一系列轻量级的用户界面组件，是目前 Java 用户界面常用的包


注 1 ：最重要且常用的是 1 和 6 ，已用黑体标出的为，需重点掌握
注 2 ：在使用 Java 时，除了 java.lang 外，其他的包都需要 import 语句引入之后才能使用。


重点讲解内容：java.lang和java.util。
java.lang 包
这个包称为 java 语言包，是由编译器自动引入的。程序中不必用 import 语句就可以使用。它所包含的类和接口对所有实际的 Java 程序都是必要的。
1.       object 类
2.       数学类 (Math)
3.       数据类型类
4.       线程类
5.       字符串类 (String 类和 StringBuffer 类 )
6.       系统及运行类 (System 类和 Runtime 类 )
7.       错误和异常处理类 (Throwable 、 Exception 、 Error)
8.       过程类 (process)


java.util 包
1. 日期类、日历类（ Data 、 Calendar 、 GregorianCalendar ）
2. 随机数类（ Random ）
3. 位运算类（ BitSet ）
4. 矢量类（ Vector ）
5. 数据结构类（ Stack ）
6. 散列表类（ Hashtable ）
7. StringTokenizer类
