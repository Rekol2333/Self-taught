# JS 弱类型语言下的自动类型转换.

## 1. 运算符

1. 1 一元运算符

- 如: `+(-)"123abc"`

> 其他类型转number：
>
> * string转number：按照字面值转换。如果字面值不是数字，则转为NaN（不是数字的数字）
> * boolean转number：true转为1，false转为0



1.2 比较运算符

- >  比较方式
  >
  >   1. 类型相同：直接比较
  >
  > * 字符串：按照字典顺序比较。按位逐一比较，直到得出大小为止。
  >
  > 2. 类型不同：先进行类型转换，再比较
  >
```javascript
     document.write(("123" === 123) +"<br>");
```
  >
  > * ===：全等于。在比较之前，先判断类型，如果类型不一样，则直接返回false ---> 对数据类型的要求很严格.

1.3  逻辑运算符

> && || !
>
> * 其他类型转boolean：
>
> ​                   1. number：0或NaN为假，其他为真
>                    2. string：除了空字符串("")，其他都是true
>                    3. null&undefined:都是false
>                    4. 对象：所有对象都为true

有就是 true, 没有就是false;

____



Little case:

```js
/**
         * 取 1~100之间的随机整数
         *      1. Math.random()产生随机数：范围 [0,1)小数===> random() 方法, 包头不包尾
         *      2. 乘以 100 --> [0,99.9999]==[0,100) 小数
         *      3. 舍弃小数部分 ：floor --> [0,99] 整数
         *      4. +1 -->[0,99] 整数 [1,100]
         */
       var number =  Math.floor((Math.random() * 100)) + 1;
```



正则对象: RegExp

```js

```



____

# BOM&DOM

```js
document.getElementById("setA").onclick() = addAttribute();
```













# 重点(不熟悉摘要) for W3C.

## 1.  重新声明 JavaScript 变量

如果重新声明 JavaScript 变量，该变量的值不会丢失：

在以下两条语句执行后，变量 carname 的值依然是 "Volvo"：

```
var carname="Volvo";
var carname;
```