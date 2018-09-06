啃点

- [ ] html中表单.
  - [ ] label
    - [ ] for
  - [ ] input 中
    - [ ] type
    - [ ] name
    - [ ] value
    - [ ] placeholder
    - [ ] id
- [ ] css 中属性选择器的理解的练手



____

# **html**

### 1. 表格: 

1. 和表格的嵌套:

```html
<table>
    <tr>
    	<td>
        	<table>
                <tr>
                    <--内在嵌套中第一行的第一格-->
                	<td>
                    </td>
                    <--内在嵌套中第一行的第二格-->
                    <td>
                    </td>
                </tr>
            </table>
        </td>
    </tr>
</table>
```

table --> tr --> td  

在格子中嵌套



2. 和表单的嵌套.

   1. 全局背景放在`<body>之间</body>`url 中地址要被""引起来.

   ```css
   body{
   	background: url("../../html/day02-form/img/register_bg.png") center no-repeat;
   				
   	}
   ```


## 2. 技巧 

### 2.1 水平居中

```css
/*让div 水平居中*/
margin:auto;
```



### 2.2  ` p:first-child`

* 注意: `: `左右两边不能有空格, 即`p : first...`是错误的!

```css
/*控制左边块内第一个元素
类选择器*/
.div_left > p:first-child{
    border: 1px solid lightsalmon;
    font-size: 20px;
    color: #FFA07A;
}

/*左边块内第一个元素:*/
```



### 2.3 `padding `&外边框

```html
padding: 2px;
/*消除padding 对外边框大小的影响*/
box-sizing: border-box;
```



### 2.4 表单项标签中:

- 下拉选表单标签: 
  - `select` 具有 `name属性`,
  - select 的子标签`option`具有`value属性`

```html
<select name="province">
    <option value="">--请选择--</option>
    <option value="1">北京</option>
    <option value="2">上海</option>
    <option value="3" selected>陕西</option>
 </select>
```





