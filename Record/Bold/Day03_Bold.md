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

