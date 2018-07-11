# day02 Exception

1.  错误: 不兼容的类型: 从double转换到int可能会有损失
         x = x + 2.5;

- 第一种

   ```jav
     	 int x = 10;
         x = x + 2.5;
         System.out.println(x);
   ```

- 第一种变式

```java
	int num = 8 + 2.5;
    System.out.println(num);
```



2.  错误: 不兼容的类型: 从`float`转换到`int`可能会有损失

- 第一种

   ```java
   int result = 3 > 4 ? 2.5F : 10;
   
   System.out.println(result);
   ```

- 

```JAVA
 	 int num = 8 + 2.5F;
    System.out.println(num);
```



3. 错误: 不是语句

     ```java
   a > b ? a : b;
     ```

   ` javac LogicTest.java`



4.==比较三个数的大小?==



- >  错误: 二元运算符 '>' 的操作数类型错误
  >     int otherMaxWay = (x > y) && (x > z) > x ? x :((y > z) ? y : z);
  >                                          ^
  >   第一个类型:  boolean
  >   第二个类型: int
  > 1 个错误



```java
 int x = 20;
 int y = 40;
 int z = 30;   
 int otherMaxWay = (x > y) && (x > z) > x ? x :((y > z) ? y : z);

```

三元数据类型一致.

- > 错误: 二元运算符 '>' 的操作数类型错误
  >     int otherMaxWay = ((x > y) && (x > y)) > z ? (x > y) && (x < y) : z;
  >                                            ^
  >   第一个类型:  boolean
  >   第二个类型: int
  > OperatorThreeTest.java:23: 错误: 不兼容的类型: INT#1无法转换为int
  >     int otherMaxWay = ((x > y) && (x > y)) > z ? (x > y) && (x < y) : z;
  >                                                ^
  >   其中, INT#1,INT#2是交叉类型:
  >     INT#1扩展Object,Serializable,Comparable<? extends INT#2>
  >     INT#2扩展Object,Serializable,Comparable<?>
  > 2 个错误



```java
	// int otherMaxWay = ((x > y) && (x < y)) > z ? (x > y) && (x < y) : z;
    //
    // int otherMaxWay = ((x > y) && (x < y)) > z ? (x > y) && (x < y) : z;
    //
    // int otherMaxWay = ((x > y) && (x > z)) > z ? (x > y) && (x < y) : z;
    //
    // int otherMaxWay = (x > y) && (x > z) > x ? x :((y > z) ? y : z);
```





5.