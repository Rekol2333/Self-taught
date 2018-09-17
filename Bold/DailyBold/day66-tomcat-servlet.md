`web容器`: 虚拟路径

- **localhost+端口 :/要访问的项目名字 + 要访问的页面** 

由于`service`方法, 不要有全局变量, 所以应创建局部变量.

`<load-on-startup>0</load-on-load>`中间数字0优先级最高.
**TODO**
- [x]  <a href="/demo4"></a>链接跳转到Servlet, 控制台显示 --> 路径问题.
- [ ]  request 和 response 的 api 对照.
- [ ]  http 协议中请求和响应的数据格式.
===========================

##[归纳]通过`get`方式请求
通过地址栏或者a标签访问的页面是通过`get`方式请求的，表单默认的提交方式是get
	* 在地址栏输入地址后按回车访问
	* 通过html的`<a>`标签进行跳转
	* 提交没有method属性的表单(表单没有指定method属性.)

##[归纳]路径问题
	1. html css js --> 相对路径: 
		如: "(./)index.html"<==>"../user/index2.html"
	2. java jsp	-->绝对路径:
		1. 给客户端浏览器使用: 要加虚拟目录(项目的访问路径)
			* 如:`request.getContextPath() + "/servlet"`
			* 应用: <a> , <form> 重定向...
		2. 给服务器使用：不需要加虚拟目录
			* 如: `\servlet`
			* 应用: 转发

##[归纳]页面跳转
- 前端:
	* href属性
	* location 对象
- servlet: 
	* 转发
	* 重定向.
##[归纳] forward 和  redirect 区别(转发和重定向的区别.)
			* 重定向的特点:redirect
				1. 地址栏发生变化
				2. 重定向可以访问其他站点(服务器)的资源
				3. 重定向是两次请求。不能使用request对象来共享数据
				4. 必须加工程名称
				5. 不可以使用 request 域对象
			* 转发的特点：forward
				1. 转发地址栏路径不变
				2. 转发只能访问当前服务器下的资源
				3. 转发是一次请求，可以使用request对象来共享数据
				4. 路径不能写工程名
				5. 可以使用request域对象

##[归纳]缓存问题的解决
解决缓存问题最常用的手段, 使用时间戳(盖章)
	var date = new Date().getTime();
	应用: src = .... + date;
___
ServletContext: 水	项目内资源: ![鱼](day66-tomcat-servlet_files/1.png)
___
##[归纳]文件下载的两种方式
	1. 自动超链接方式
	2. 手动方式
		* 需要设置两个头
			- Content-type
			- Content-Disposition:文件打开方式
			- 输入流: 读取要下载的文件 --> servletContext.getRealPath("/Xxx"):获取到要下载的文件所在的路径
			- 输出流: response.getOutputStream()
------

乱码原因
	* 字符缓冲区中的编码 和 浏览器打开时候的编码 不一致.
	* 解决--> response.setContentType("text/html;charset=utf-8"); 
##[归纳]需要设置处理中文乱码的地方.
	1. 向页面输出内容
```java
request.setCharacterEncoding("utf-8");
response.getWriter().write("你好, servlet");
```
	2. HttpServletResponse 对象的 setContentType()
##[归纳] 请求数据格式和响应数据格式
1. 请求数据格式
2. 响应数据格式

