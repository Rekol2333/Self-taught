# Day02_课堂重点

[TOC]

____

## 自动转换:

- 是不是有转换?
- 左右两边是不是一样的类型?
- 两个默认类型.

## 强制转换:

1.脑中默认类型:

 -  整型 ---->`int`
 - 浮点数---->`double`

2.判断: 

- 精度损失:

  ```java 
  //float 转 int
  int num =  (int) 3.5;
  ```

- 数据溢出

  ```java
  //整数中
  //"大的往小的装"
  int num = 6000000000;
  System.out.println(num);//2131280948,数据溢出
  ```

  

**3.特殊情况:**

- `byte`, `short`, `char`三种运算时,会首先各自被强制提升为`int` 类型.

- `short`, `byte`和`int`之间的相互转化

  ```java
  short sh = 34;
  short or = 32;
  short shor = sh + or;//Exception!
  int shor = sh + or;
  //or
  short shor = (short)(sh + or);
  System.out.println(shor);
  ```

  ____

- 一旦`char` 类型进行数字运算, 字符就会被翻译成一个数字,`char` 被提升为`int` 类型

  ``` java
  char c = 'A' + 1;
  System.out.println(c);//66
  ```

  > 48---->0		65 ----> A	97---->a


## 运算符注意事项:

1.运算中有不同类型的, 结果将是范围大的那种

- `double` 与 `int` ----> double
- float?

```java 
int x = 10;
double result = x + 2.5;//运算结果默认类型为double
sout(x);//12.5
```

2.`i++` 与 `++i` :

-  虽然num++ 和 ++num 在打印输出语句中,但也仍将 num 加加了.

```java
int num = 3;
    System.out.println(++num);//4
    System.out.println(num);//4
    System.out.println("--------------");
    System.out.println(num++);//4
    System.out.println(num);//5
// 虽然num++ 和 ++num 在打印输出语句中,但也仍将 num 加加了.
```

3.`+=` 运算中自带(隐含的)强制转换.

``` java
  	short m = 12;
	byte n = 5; 
    n %= 2;  
	//short m %= n?
	//n = n % 2;
	//byte = byte + int;
	//byte = int + int;
	//byte = int;
	//n = (byte) int;
	System.out.println(n);//1

```

### 4.逻辑运算符

刘老师讲的提亲的比喻

- `&&`的丈母娘要求严格
- `||`的丈母娘要求较宽松 ,有一个就true
- `短路&&`的效果

```java
int a = 10;
// false && ...(后面的不执行)
System.out.println(3 > 4 && ++a < 100);
System.out.prinln(a);//10
```

- `短路||` 的效果:

```java
int b = 20;
//true || ...(后面的不执行)
System.out.println(3 < 4 || ++b < 100);
System.out.prinln(b);//20
```



- 三元运算符中:

  - `:`左右两边必须同时满足左边数据类型的要求.

    ```java
    int result = 3 > 4 ? 2.5 : 10;
    System.out.print(result);
    //报错: 不兼容的类型: 从double转换到int可能会有损失
    ```

  - 三元运算符的结果必须被使用.

    - 要么结果被左边变量接收
    - 要么放在输出语句中

    ```java
      	int a = 100;
      	int b = 100;
      	int max = a > b ? a : b;//a <= b的情况下,输出b;
    	System.out.print(a > b ? a : b); 
    	int result = 3 > 4 ? 2.5 : 10;
    	System.out.print();
    ```

- ##### **三个数的比较(不同的思路)**

  - 第一种: 

    ```java
      int x = 20;
      int y = 40;
      int z = 30;
      int otherMaxWay = (x > y) && (x > z) ? x :((y > z) ? y : z);
    ```

  -  第二种

    ```java
    int max = (x > y ? x : y) > z ? (x > y ? x : y) : z;
    ```

  - 第三种

    ```java
    int temp = (20 > 40 ? 20 : 40);
    int finnal = (temp > 30 ? temp : 30);
    ```

  - 第三种变式

    ```java
    int max = x > y ? x : y;
    max = max > z ? max : z;
    System.out.println(max);
    ```

    


**方法**

公共功能的抽取? 

## 编译器的优化`%javac`---->`%java`的过程中

- 如果右边的数值在左边是数据类型范围内,就可以赋值。

  

  ```java
  	byte b = 10;  //可以
  //  10 是 int 类型. 自动隐式强制转化
  //	byte b = (byte) 10;
  ```

  

- 如果计算是常量的时候,编辑器会自动计算结果。如果结果没有超出左边类型的范围,可以赋值。

- 全部都是常量,在class文件中,直接显示为:

  > byte b = 70;

  ```java
  
  	byte b = 30 + 40; //编译器的常量优化
  
  ```

  

- 如果计算是变量的时候,编辑器不能计算,只能检查语法.发现大类型赋值给小类型是语法错误。编译失败！

  ```java
  	byte b = 10;
  	byte b2 = 5 + b + 20;  //不可以
  
  ```

  - e.g.

    ```java
    System.out.println(5 + 5 + "=" + 5 + 5);
    ```

    结果: 10=55

  - 

  



