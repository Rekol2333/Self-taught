# 【课上摘要】今日重点; 易错点；易混淆点

1. 【常识类】各种常量类型所占用的内存空间：

   `byte` `short` `int` `long` 

   1		2		4		8		个字节，

   8、16、32、64位

   `float` `double` 

   4			8

   **`char`范围：65535**

   2

   `boolean`

   1

   字符常量：中间有且仅有一个字符，不写也不行。

   ``` java
   //Wrong:	System.out.println('');
   Correct:	System.out.println(' ');//blankspace
   ```

2. float 描述**精度**，0.01 与0.000001

   - 科学记数法省空间:	e 本身就比较大了

   - 浮点型可能只是一个近似值，e.g.: 1/3

   - 计算机拿到一个小数，不知道他是float 还是 double，所以需要手动声明：如：第一句的后缀F

   - 浮点数默认类型是double，如果一定使用float，需加上一个F后缀。

     ```java
     float f = 0.001f;
     double d = 0.001;
     ```

    4.`byte`以及`int` 范围大小以及默认类型

   ```java
   long num01 = 3000000000L;
   float num02 = 0.0001F;
   ```

    **5.变量：**

   - **变量可以是一个容器。**

   6.同时创建多个变量。

   ```java
   int a = 100, b = 200, c = 300;
   ```

   
