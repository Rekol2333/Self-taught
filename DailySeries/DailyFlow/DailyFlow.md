---
typora-root-url: ./
typora-copy-images-to: ./
---

# DailyFlow

# 1. Day09-基于继承的发红包案例

### 1. 思路

![1532097064408](D:\MarkAndMemory\DailySeries\DailyFeedback\PicturesStorage\1532097064408.png)

### 父类: 

```java
public class User01 {
    private String name;
    private double balance;
	constuctor;
    getter&setter;    
    public void show() {
        System.out.println("Name: " + getName() + "; Balance: " + balance);
    }
}
```

### 发红包的: 

```java
import java.util.ArrayList;
import java.util.Random;

public class RandomSend extends User01 {

    public RandomSend() {
    }

    public RandomSend(String name, double balance) {
        super(name, balance);
    }

    public ArrayList<Double> send01(double targetRed, double count) {
// declare an ArrayList to store every red packets.
        ArrayList<Double> red01 = new ArrayList<>();
// judge the balance and then subtract a red packets's number.
        double balance = super.getBalance();
        if (targetRed > balance) {
            System.out.println("don't enough balance");
            return red01;
        }
        setBalance(balance - targetRed);

// CASE 1: split the targetRed to every count of red packet.
//        double redPacket = targetRed / count;
//        double mod = targetRed % count;
//CASE 2:  Random red packet.
//         for (int i = 0; ; i++) {
        for (int j = 0; j < count; j++) {
//            随机每个红包的金额
            if (j != count - 1) {
            double randRed = new Random().nextDouble() * targetRed;
//            最后一个红包
//            if (j == count - 1) {
//                red01.add(randRed + targetRed);
//            } else {

                red01.add(randRed);
//            }
//            总红包金额减去所有随机金额
                targetRed -= randRed;
            } else {
                red01.add(targetRed);
            }
        }
        return red01;
            /*for (int j = 0; j < count; j++) {
                if (j == count - 1) {
                    red01.add(randRed + mod);
                } else {
                    red01.add(randRed);
                }
            }*/

//            for (int j = 0; j < count; j++) {
//            }
//
//            if (targetRed < 0) {
//                break;
//            }
//    }
    }
}
```

### 收红包的: 

```java

import java.util.ArrayList;
import java.util.Random;

public class Accepter01 extends User01 {
    public Accepter01() {
    }

    public Accepter01(String name, double balance) {
        super(name, balance);
    }

    public void openRed(ArrayList<Double> red01) {
//  index to remove;
        int index = new Random().nextInt(red01.size());

        double redAfterOpen = red01.remove(index);

        setBalance(getBalance() + redAfterOpen);
   }
}
```

### 测试类: 

```java
import java.util.ArrayList;
import java.util.Random;

public class RandTest {
    public static void main(String[] args) {
        RandomSend s1 = new RandomSend("RandomSend", 300);
//        s1.send(30,3);
        ArrayList<Double> red01 = s1.send01(30, 3);
        Accepter01 a = new Accepter01("a", 0);
        Accepter01 a2 = new Accepter01("b", 0);
        Accepter01 a3 = new Accepter01("c", 0);

        a.openRed(red01);
        a2.openRed(red01);
        a3.openRed(red01);

        s1.show();
        a.show();
        a2.show();
        a3.show();
//        System.out.println("a.getBalance() = " + a.getBalance());
//        System.out.println("a2.getBalance() = " + a2.getBalance());
//        System.out.println("a3.getBalance() = " + a3.getBalance());
        System.out.println("AllBalance = " + (a.getBalance() + a2.getBalance() + a3.getBalance()));

//        Random r = new Random();
//        System.out.println(r.nextDouble());
    }
}
```



____



# 2. ` contains()`方法, 

- 核心: `String` 类中的 `boolean contains(sequence s) `的方法作为判断依据, 再用另一个数组进行存储, 作为返回值.

- 将数组中包含参数str的元素存入另一个String 数组中并返回

  > 当且仅当此字符串包含指定的 char 值序列时，返回 true

  ```java
  public static String[] filter(String[] arr, String str) {	
  		int count = 0;
          for (int i = 0; i < arr.length; i++) {
  
              if (arr[i].contains(str)) {
                  count++;
              }
          }
  //并不知道新存储的数组长度是多少.  
          String[] str2 = new String[count];
  
          for (int i = 0; i < arr.length; i++) {
  
              if (arr[i].contains(str)) {
                  str2[i] = arr[i];
              }
          }
          return str2;
      
  }
  ```




# 3. 类型转换汇总.

## 3.1 基本数据类型 <====> String

### 3.1.1 基本类型----> String

```java
int s = 100;
String s1 = s + "";
//String s2 = new String(100); Wrong!
String s2 = Integer.toString(100);
String s3 = String.valueOf(100);

```



### 3.1.2 String ---> 基本类型( '=' 运算顺序从右至左)

- 使用包装类的静态方法`static parseXXX(String str)`

```java
int i = Integer.parseInt(s1);
double d = Double.parseDouble("23.0");
```





## 3.2 String <====> StringBuilder

### 3.2.1 StringBuilder ---->  String  

   `toStirng()`



### 3.2.2 String ----> StringBuilder

利用构造方法



# 4. 统计字符串字符个数

1. HashMap 式