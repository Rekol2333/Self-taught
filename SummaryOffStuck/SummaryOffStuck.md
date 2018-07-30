
①定义方法filter

```java
    要求如下：

    形参：String [] arr，String  str

    返回值类型：String []

    实现：遍历arr，将数组中包含参数str的元素存入另一个String 数组中并返回

    PS：返回的数组长度需要用代码获取

    ②在main方法中完成以下要求：

    定义一个String数组arr，数组元素有：
    "itcast","itheima","baitdu","weixin","zhifubao"

    调用filter方法传入arr数组和字符串”it”，输出返回的String数组中所有元素
```

String 中一个方法 contains 把我困在这里.
` 当且仅当此字符串包含指定的 char 值序列时，返回 true。`

```java
public String[] filter(String[] arr, String str) {
    int count = 0;
    for (int i = 0; i < arr.length, i++) {
        if (arr[i].contains(str)) {
            count++;
        }                            
    }
    String[] newArr = new String[count];
    
    for (int i = 0; i < arr.length, i++) {
    	if (arr[i].contains(str)) {
    		newArr[i] = arr[i];    	    
        }
}
```



