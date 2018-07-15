# 犄角旮旯

[TOC]

## 2. simple Java program



## 3. Java基础程序设计

### 3.2.2	数据类型的溢出

### 3.3.1-2  	数据类型的显隐性转换。

- 显性（强制）
- 隐性（自动）
  - short/ byte---->int
  - int&float ----> float
  - Every---->String



## 5.7 String

1. 两种声明方式: 		   ![1531623888016](C:\Users\Rekol\AppData\Local\Temp\1531623888016.png)



1. ```java
   String str1 = hello;
   String str2 = hello;
   String str3 = hello;
   ```

![1531623826092](C:\Users\Rekol\AppData\Local\Temp\1531623826092.png)

**说明:**

字符串,共享设计,将对象指向已存在的实例空间.

![1531624203977](C:\Users\Rekol\AppData\Local\Temp\1531624203977.png)

1. **字符串内容不可改变**

```java
String str = "Hello";
str = str + "World";
```

![1531624369484](C:\Users\Rekol\AppData\Local\Temp\1531624369484.png)