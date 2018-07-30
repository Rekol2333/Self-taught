# 犄角旮旯

[TOC]

## Java基础程序设计

### 3.2.2	数据类型的溢出

### 3.3.1-2  	数据类型的显隐性转换。

- 显性（强制）
- 隐性（自动）
  - short/ byte---->int
  - int&float ----> float
  - Every---->String



## String

1. 两种声明方式: `new`开辟新的堆内存空间: 		   ![1531623888016](D:\MarkAndMemory\MyReadingNote\assets/1531623888016.png)



2.  声明多个变量指向同一个对内存地址

```java
String str1 = hello;
String str2 = hello;
String str3 = hello;//str1 将地址值赋给了 str2, str3.????
```
![1531623826092](D:\MarkAndMemory\MyReadingNote\assets/1531623826092.png)

**说明:**

字符串,共享设计,将对象指向已存在的实例空间.

![1531624203977](C:\Users\Rekol\AppData\Local\Temp\1531624203977.png)

3. **字符串内容不可改变**

```java
String str = "Hello";
str = str + "World";

String str3 = hello;
sout(str);
String str4 = world;
String str5 = helloworld;
String str6 = str3 + str4;
System.out.println(str5 == str6);//false;
```

![1531624369484](D:\MarkAndMemory\MyReadingNote\assets/1531624369484.png)

​    **4. `String`与引用传递.**

​	1. 

```java
	public static void main(String[] args) {
        String str1 = "Hello";
        System.out.println("方法调用前");
        System.out.println("str1 = " + str1);
        fun(str1);
        System.out.println("fun()调用后");
        System.out.println("str1 = " + str1);//str1 = Hello
    }
    public static void fun(String str2) {
        str2 = "World??";
    )
```

图解:

![1531641977910](D:\MarkAndMemory\MyReadingNote\assets/1531641977910.png)

> 每一个字符串对象都表示一个匿名对象(参考匿名对象的规则)
>
> 为 str2 重写设置内容,相当于改变了 str2 的引用(地址值改变.) , 而 str1 本身内容不受任何影响.

​	2.String 作为类中属性(成员变量)

![1531643652948](C:\Users\Rekol\AppData\Local\Temp\1531643652948.png)

内存图: 

![1531643681550](D:\MarkAndMemory\MyReadingNote\assets/1531643681550.png)

> ![1531643700300](C:\Users\Rekol\AppData\Local\Temp\1531643700300.png)

![String与引用调用内存图](D:\MarkAndMemory\MyReadingNote\assets/String 与引用调用内存图.png)



_____



## 方法参数及其传递问题.

![1532571900919](D:\MarkAndMemory\MyReadingNote\assets\1532571900919.png)