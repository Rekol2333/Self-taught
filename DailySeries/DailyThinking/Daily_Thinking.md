# Daily_Thinking_05

## 1. ''容器''

### 1.1 计数器

### 1.2 借助第三方, 存储一方变量,

> 用第三个变量倒手.

```java


```

### 1.3 String 作为容器

#### 1.3.1

```java
String storeRandomNum = "";
for (int i = 0; i < 5; i++) {//控制输出多少个字母.
    int randomNum = r.nextInt(26) + 65;
    char characters = (char) randomNum;
    storeRandomNum += characters;
}
```

> 同`Bold`文件

#### 1.3.2 

> 往随机字符串中随机插入随机一个范围[0,9]内的随机数字.

```java
String str = "";
if (index == i) {
        str += randomNum;
    }
```



## 2. 假定数组内某元素是最大值,最小值.

```java
int[] array = {11, 123, 323, 333, 22, 4232};
        int max = array[0];//Assume the max is the first element of array[].
        int storeMax02 = 0;
        for (int i = 0; i < array.length; i++) {
            if (array[i] > max) {
                max = array[i];
            }
//            int max02;
//            max02 = max > array[i] ? max : array[i];
            int max02 = max > array[i] ? max : array[i];// other way to find the max one.
            storeMax02 = max02;
        }

```

## 3. 数值反转, 关注数组索引, 而不是数组内元素.

- **min <  max **
- **min++, max--**
- 

```java
		int[] arr = {11, 121, 232, 434, 555, 654, 666};
        for (int min = 0, max = arr.length - 1; min < max; min++, max--) {
            int temp = arr[max];
            arr[max] = arr[min];
            arr[min] = temp;
        }
```

![图片](D:\ReKol\Documents\Itcast\day05\03_资料\07-数组元素反转的思路.png)



- 索引`min` 与`max`的循环运动, 实现需求.

## 4. 数组与`方法`的结合

- 声明新的数组存储方法返回的数组.
- `新的数组元素` 与 ` 返回的数组元素`元素无关系.
- 应用场景: 方法内要多个返回值, 用数组来存储不同的返回值; 调用处用数组盛装和获取不同返回值.



## 5.对象作为方法参数或者返回值, 存储的都是地址值.

## 6. String ----> 数组 & 数组 ---->String & ArrayList --> String

### 6.1 String ----> ''字符''数组

```
//对字符串每个字符进行处理.
char[] chars = str.toCharArray();
```

String 处理 单个字符时 `.toCharArray()`方法,转换成字符数组, 再利用循环遍历, 对每个在进行处理.

- 大小写字母, 数字, 都可以转换成char型(常应用于数组里) 的数字. 筛选时, **利用字符和数字的比较**不同情况进行筛选处理.



### 6.2 数组 ---->String.

可以调用`Arrays.toString(int[] a)`

- `[a, b, c, d, d]` 的形式, 拼接成String



### 6.3 ArrayList ----> String

1. 实现效果:

   > ```
   > {element@element@element}
   > ```

```java
	   System.out.print("{");
        for (int i = 0; i < a.size(); i++) {
            String s = a.get(i);
            if (i != a.size() - 1) {
                System.out.print(s + "@");
            } else {
                System.out.print(s + "}");
            }
        }
        System.out.println();
```





## 7. 标记 --> 有些像计数器.

编写程序，输出 200~500 之间的所有素数。

```java
int num=200;
while (num<=500) {
    boolean tag=true;       //素数标记
    for(int d=2;d<=num-1;d++){
        if(num % d==0){
            tag=false;
            break;
        }
    }
    if(tag){                //如果是素数
        System.out.println(num);
    }
    num++;
}
```

# 8.{element@element@element} 与发红包最后一个的相同思路.

代码同`6.3`

发红包: 

```java
 public ArrayList<Integer> divide(int totalMoney, int count) {
        // 创建保存各个红包金额的集合
        ArrayList<Integer> list = new ArrayList<>();
        // 定义循环次数,总个数‐1次
        int time = count ‐ 1;
        // 一次计算,生成平均金额
        int money = totalMoney / count;
        // 循环分配
        for (int i = 0; i < time; i++) {
            // 添加到集合中
            list.add(money);
            // 总金额扣除已分配金额
			totalMoney ‐= money;
        }
        // 剩余的金额,为最后一个红包
        list.add(totalMoney);
        System.out.println("普通红包金额:" + list);
        // 返回集合
        return list;
    }

```



# 9. 利用`毫秒值` 计算 日期差值.

