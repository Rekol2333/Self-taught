# 【课上摘要】今日重点; 易错点；易混淆点

[TOC]



# Day01

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

   ```java
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



# Day02_课堂重点

[TOC]

------

## 自动转换:

- 是不是有转换?
- 左右两边是不是一样的类型?
- 两个默认类型.

## 强制转换:

1.脑中默认类型:

- 整型 ---->`int`
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

  ------

- 一旦`char` 类型进行数字运算, 字符就会被翻译成一个数字,`char` 被提升为`int` 类型

  ```java
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

- 虽然num++ 和 ++num 在打印输出语句中,但也仍将 num 加加了.

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

```java
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

  - 第二种

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



____



# Day03_Bold

[TOC]

____

```flow 
st=>start: FirstFlow e => end op => operation : Faster? cond=>condition : Fast Or slow? st->op->cond cond(Fast)->e cond(slow)->op 
```



```flow
st=>start:FirstFlow

```

1. > // 0 -100 之内的偶数和.---->引入累加思想.
   > // 找到所有的偶数,并记录下下来
   > //偶数相加.

```java
public class EvenNumberInLoop {
  public static void main(String[] args) {
    int sum = 0;
    for(int i = 1; i <= 100; i++) {
      if (i % 2 == 0) {
        // 需定义存储器来存储偶数,并相加.
        sum = sum + i;
        System.out.println("sum = " + sum + "\n" + "i = " + i);
      }
    }
  }
}

```

2. 同一个

```java
	int jsum = 0;
    int osum = 0;
    for (int i = 0; i <= 100; i++) {
      if (i % 2 == 1) {
        jsum += i;
        System.out.println("jishu i: " + i);
        System.out.println("jishusum =" + jsum);
        continue;
      }
      System.out.println("===================");
      osum += i;
      System.out.println("oushu i: " + i);
      System.out.println("oushusum =" + osum);
      System.out.println();
```



3. continue 与 break

- 循环内 `break`,之后的循环都不要了.

> it's 1 floor.
> it's 2 floor.
> it's 3 floor.

-  `continue`的影响小,就当前的循环不要了

> it's 1 floor.
> it's 2 floor.
> it's 3 floor.
> it's 5 floor.
> it's 6 floor.
> it's 7 floor.
> it's 8 floor.
> it's 9 floor.



```java
for (int i = 1; i < 10; i++) {
    if (i == 4) {
        break;
      }
 	System.out.println("it's " + i + " floor." );
}
```



4. 常见循环案例

   1. 水仙花数案例

   > 找出三位数的水仙花数.

```java

for (int i = 1; i < 10; i++ ) {
    for(int j = 0; j < 10; j++) {
        for (int x = 0; x < 10; x++) {
            if ((i * i * i + j * j * j + x * x * x) == (i * 100 + j * 10 + x)) {
                System.out.println("shuixianhua shu wei: " + (i * 100 + j * 10 + x));
            }
        }
    }
}
```



	2.  

> 星号塔.



3. 死循环

- 人为: for 忘记 `步进语句`
- 故意:  

```java
int i = 0; 
while (true) {
    statements;
    if( ... ) {
        ...
        break;
    }
}
```



_____

# Day04

1. 方法重载

> 只和方法名称和参数列表有关系.

- 参数个数
- 参数类型
- 多类型位置

2. 多种方式比较大小

- ```java
  public static boolean isSame(int o, int j) {
          System.out.println("int");
          return o == j;
      }
  ```

- ```java
  public static boolean isSame(byte o, byte j) {
          boolean comp = (o == j ? true : false);
          System.out.println("byte");
          return comp;
      }
  ```

- ```java
  public static boolean isSame(short o, short j) {
          System.out.println("short");
          if (o == j) {
              return true;
          } else {
              return false;
          }
  ```

- ```java
         boolean same;
         if (c == g) {
             same = true;
         } else {
             same = false;
         }
         return same;
     ```
  ```

3. 



____


  ```

# Day05

1. 当调用方法的时候，向方法的小括号进行传参，传递进去的其实是数组的地址值。
2. 返回值数量可以为 0 个或 1 个;

> 返回值类型为数组时, 也是返回一个值, 一个地址值. 同`1.`



# Day06_Bold

**1. class 参数列表, 地址值传递.**

1. - [ ] `class` 作为参数地址值的传递.

   ```java
   	public static void main(String[] args) {
           Phone theOne = new Phone();
           theOne.color = "RED";
           theOne.price = 2345;
           asParam(theOne);
       }
   
       public static void asParam(Phone oneClass) {
           System.out.println(oneClass.color);
       }
   ```

   `Phone.class` :  

   ```java
   public class Phone {
       String name = "Apple";
       double price = 8888.0;
       String color = "blue";
   
       public void call(String who) {
           System.out.println("call sb.: " + who);
       }
       public void sendMassage() {
           System.out.println("SEND MASSAGE");
       }
   }
   
   ```

   2. - [ ] 返回值类型是 `class` 类型, 将一个方法内的变量进行处理后,返回该方法, 并用新的方法实列存储.

      ```java
      Phone storage = getReturnClass();
      
      public static Phone getReturnClass() {
                  Phone clret = new Phone();
                  return clret;
      
      ```


**2. ** `Stack` `heap ` `method area`

```java
Phone one = new Phone();
```

**栈内存: **程序运行

- 调用方法传参时, 也是在栈内存确定运行.

**堆内存: **`new` 出来的

- 保存`成员变量`

- 保存`方法区保存的成员方法`的地址值

**方法区: **class 和 main 方法.



**3. 成员变量与局部变量**:

- 定义位置
  - 成员变量: 类中方法外
  - 局部变量: 参数以及方法内;
-  作用域不同
  - 成员: 类中通用
  - 局部: 方法内使用
- 默认值不同
  - 成员: 有初始默认值;
  - 局部: 没有默认初始值, 自己初始化.
- 内存位置( 成员: 栈; 局部: 堆) 以及生命周期不同

_____



# Day07_Scanner_Random_ArrayList



## Scanner:

- `next()`输入字符串
- `nextInt()`: 将输入的字符串标记为 `int` 类型.

## **匿名对象: **

- `new ClassName()`
- 开辟堆内存,但没有将其赋给对象. 即并没有将地址值交给栈内存中的对象.也就不能反复调用.
- 基于↑, 所以**只能使用一次**, 调用一次变量后, 调用其方法, 又必须new `ClassName()`
- new 一次, 开辟新的`Heap memory`.

## Random 类

1. 第一

> ```java
> /*1. `5.fori`
> * 2. Random().nextInt(bound);   [0,5)
> * */
> ```

 2. > 获取[65, 90]的随机数字

```java
Random().nextInt(26) + 65;
```

`26 + 65 = 91 - 1 = 90`;

`26  =  90 - 65 + 1`;

3. > 生成随机字符串如: RSFIK

   ```java
   String storeRandomNum = "";
   for (int i = 0; i < 5; i++) {//控制输出多少个字母.
       int randomNum = r.nextInt(26) + 65;
       char characters = (char) randomNum;
       storeRandomNum += characters;
   }
   ```

   

4. > 往随机字符串中随机插入随机一个范围内的随机数字.

   ```JAVA
   Random r = new Random();
   int randomNum = r.nextInt(10);
   int index = r.nextInt(5);
   
   String str = "";
   
   for (int i = 0; i < 5; i++) {
   
       int alpNum = r.nextInt(26) + 65;
       char alph = (char) alpNum;
       str += alph;
   
       if (index == i) {
           str += randomNum;
       }
   ```

   > ```
   > **1. 随机字符A-Z, 对应char[65,90]
   >  * 2. 生成格式是一排,连接在一起的
   >  * 3. 随机数[1,10], 随机数的索引范围是:[0,4]
   >  * */
   > 
   > /**
   >  * 1. 5个字母的索引值是[0,4]
   >  * 2. 在什么位置添加数字是随机. 数字索引值也是[0,4]
   >  */
   > ```





## ArrayList 集合

1. 实例与基本操作: 

2. ```
   对象添加到集合
   ```



____

# Day08_String类-static-Arrays类-Math类

## 1.String类

### 1. String 类型是常量, 长度不变;

1. String 类的底层是通过字节数组`byte[]`实现的.

   打印字符数组时 ,直接打印出来. 

```java
int[] num = {12,232,43};
sout(num);//打印地址值;
char[] chars = {'a','s','d'};
sout(chars);//asd 	直接打印出来.


//通过字符数组构造
        char[] chars = {'a', 'b', 'c', 'd', 'e', 'f', 'g', 'h'};
        String str2 = new String(chars);
//通过字节数组构造
        byte[] bytes = {97, 98, 99};
        String str3 = new String(bytes);

```



2. 引用类型中`==` 比较的是地址值;
   - 直接赋值的字符串指向常量池中的字符串对象地址值
   - `new` 的是新创建的.





### 2. `String`类中方法

#### 2.1 比较方法: 

- `public boolean equals(Object obj)`
  - 对称性
  - `object`参数是一个字符串且**内容** 一致,才会return true.
  - 推荐写法: `"abc".equals(str);`
  - 字符串数组也能用该方法.OBJ



- `boolean equalsInorCase(String anotherString) ` 
  - 规定了参数类型, 不能是` String[]`.

#### 2.2 获取方法

1. `int length()`

2. `String concat(String str)`

   ```java
   String str = "Hello, "
   str += "java";//"Hello. java"
   ```

3. `char chartAt(int index)`

   - "返回指定索引处的 char 值"

   - 常与遍历

4. `int indexOf(Stirng str)`

   - **第一次出现的位置**

#### 2.3 截取方法

1. `String substring (int index)`

2. `String substring(int beginIndex, int endIndex)`

   - `[begin, end)`左闭右开

   - 光标数位数法.底层原理就是因为`左闭右开`所以末位数得＋1

     ```java
     String str = "HelloWorld";
     String str1 = str.substring(4,7);//oWo
     
     ```

   - 

#### 2.4 转换方法

1. `char[] toCharArray ()`
   - 字符串转换成 char 型数组
   - 利用`char.fori快捷键`对字符串内每个字符进行处理

2. `byte[] getBytes ()`----> 

   - "A" ----> 65, "Z" ----> 90, "a" ----> 97

   -  I / O 流常用

3. `String replace (CharSequence target, CharSequence replacement)`
   - 生成新的字符串存储,//可能需要新的 variable 存储

#### 2.5 分割方法

`public String[] split(String regex)`

- 按照字符串内容进行分割.

```java
String email = "Rekol2333@163.com";
String[] split = email.split("@");

```

- 参数是一个正则表达式, 若是以` .`为分割点, 则应:

```java
String[] point = email.split("\\.");
```

- 得到字符串数组存储分割的元素.最终得到的数组为: 

```java
split[] = {"Rekol2333", "163.com"}
```



### 3. 练习题

#### 1. 数组拼接字符串

#### 2. [统计字符个数]丶重点练习.



____

## 2. static

### 2.1 静态变量和静态方法

- `static` 被修饰的成员变量方法属于类
- 静态方法**通过类名称调用**.
  - 本类当中的可以省略`类名称.`
- **静态方法不能访问非静态**

> 内存中先加载类和静态内容, 然后才加载非静态.

> 先人不知后人.

- **静态方法中不能用this**
  - this 表示当前对象.
  - static 是通过类名称调用, 不用对象名称调用.
  - 调用方式不同, 否则矛盾.

### 2.2 静态代码块

- 位置: 类中方法外
- 随着类加载,  只执行一次
- 因为静态内容总是优先于非静态执行
- 优先于`main方法` 和`构造方法`执行
- 学JDBC处常用
- 一次性对静态成员变量赋值.



## 3. Arrays 工具类

导包.

### 1. 喜闻乐见的静态方法

1. `static String toString (int[ ] a)`

- `[a, b, c, d, d]` 的形式

2. `static void sort (int[] a)`

- 升序排列, 
  - 字符的先后顺序
  - 自定义排序.



### 2. 练习题: 数组 ----> String 的倒序遍历

1. String 类中的`toCharArray()`
   - 字符串 转成 字符数组, 再倒序打印.





## 4. Math 类

1.  `static double abs(double a) `绝对值
2. `static double ceil(double a)`
   - 向上取整.
3. `static double floor(double a)`
   - 向下取整
4. `static long round(double a)`
   - 四舍五入