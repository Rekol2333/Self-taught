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



____



# Day08

1.  观察下列代码，选出正确答案：（ ） 

   ```java
   int a = 5959;
   String str = "9527";
   if(str.equals("9527")){
     str = a + "";
   }
   System.out.println(str);
   ```

2. 观察

   ```java
   String str = "wo ai java,ni ai ma?";
   char[] ch = str.toCharArray();
   for (int i = 0; i < ch.length; i++) {
     if((ch[i]+"").equals("java")){
       System.out.println(ch[i]);
     }
   }
   ```

3. 观察

   ```java
   String str = "wo ai java,ni ai ma?";
   if(str.contains("java")){
     str.replace("java", "php");
   }
   System.out.println(str);
   ```

4. 观察

   ```java
   public class Person {
     String name;
     int age;
     public static void study() {
       sleep();    
     }
     public void sleep() {
       System.out.println("sleep");
     }
     public static void main(String[] args){
       Person.study();
     }
   }
   ```

   A. 编译报错		B. sleep		C. 运行报错		D. 什么也没输出.























## Answer

1. `str` 指向了新的数组`a + " "`的内存地址.
2. `(ch[i]+"").equals("java")` 值为false,且没有其他运行程序, 所以结果为"没有正确答案"
3. 并没有对`if`语句内的替换后的String 进行赋值, 声明新的变量进行存储.

所以`str`还是指向了原本的字符串地址值.

4. 编译报错 `Error:(14, 9) java: 无法从静态上下文中引用非静态 方法 sleep()`

_____



# Day09 extends

1. observe:

   ```java
   class Animal {
     String name="animal";
     public void print(Animal a){
       System.out.println("动物:"+a.name);
     }
   }
   class Dog extends Animal {
     String name="dog";
     public void print(Animal a ){
       System.out.println("狗:"+a.name);
     }
   }
   public static void main(String[] args){
     Dog d = new Dog();
     d.print(new Animal());
   }
   ```

   A: 动物:animal	B:动物:dog 	c:狗: animal 		D: 狗:dog

























## Answer

1.C





____

