

# Daily_Exam_03
[TOC]

____



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

2. 观察下列代码片段
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
3. 观察下列代码片段

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
----

# Answer
1. 5
2. 25
3. 5

