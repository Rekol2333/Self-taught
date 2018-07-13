# Daily_Thinking_05

## 1.[补] 计数器



## 2. 容器

### 2.1 借助第三方, 存储一方变量,

> 用第三个变量倒手.

```java


```



### 2.2 假定数组内某元素是最大值,最小值.

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

### 2.3 关注数组索引, 而不是数组内元素.

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

### 2.4 数组与`方法`的结合

- 声明新的数组存储方法返回的数组.
- `新的数组元素` 与 ` 返回的数组元素`元素无关系.
- 应用场景: 方法内要多个返回值, 用数组来存储不同的返回值; 外部用数组盛装和获取不同返回值.

```java

```

