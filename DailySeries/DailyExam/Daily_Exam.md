# Exam

[TOC]

____



## Question

1.

```java
//观察下列代码片段
int x = 3;
int y = 4;
int z = x + y++;
System.out.println(x+", "+y+", "+z);

//请问，在控制台输出的结果是什么?  （）

```

2.

```java
//2、观察下列代码片段
int x = 10;
x++;
++x;
System.out.println(x++);

//请问，在控制台输出的结果是什么?  （）

```



3.

```java
System.out.print(5 + 5 + "=" + 5 + 5);
```









































## Answer

1. 3, 5, 7
2. 12
3. 10=55

____



# Daily_Exam_03

1. 

```java 
int i = 1;
int count = 0;
while(i<=10) {
  if(i%2==0) {
    count++;
  }
  i++;
}
System.out.println(count)
```

> count???

1. 观察下列代码片段
   请问，在控制台输出的结果是什么? （）

```java
int result = 0;
for(int i = 1;i<10;i++) {
  if(i%2!=0) {
    result = result + i;
  }
}
System.out.println(result);

```

1. 观察下列代码片段

请问，在控制台输出的结果是什么?（）

```java
int count = 0;
for(int i = 1;i<=10;i++) {
  if(i%5==0) {
    break;
  }
  count++;
}
System.out.println(count);
```

------

























## Answer

1. 5
2. 25
3. 5



____



# Day07

1. *观察下列代码，选出正确答案：（ ）*

   ```java
   ArrayList<String> al = new ArrayList<String();
   al.add("a");al.add("b");
   System.out.println(al.get(al.size()-1)); 
   ```

A.   a

C.	[a]

B.	b

D.	[b]

















## Answer

1. `al.get(al.size() - 1)`.

> 获取最后一位的元素.

2. `sout(al)`

> [a, b]