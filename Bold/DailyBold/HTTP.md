JavaWeb初探

-   Servlet

    -   Servlet的生命周期

        -   创建:用户第一次访问Servlet，服务器创建Servlet(单例),init方法执行且只执行一次

        -   任何一次从客户端发送的请求服务器都会创建一个新的线程执行service方法

        -   在service方法内部根据请求方式调用不同的doXXX的方法

        -   销毁:当项目从服务器中移除的时候，或者关闭服务器的时候，destroy方法执行

-   Http

    -   Request对象( 请求 )

        -   1. 请求行:

            -   getMethod() --\> 请求方式

            -   getContextPath() --\> 虚拟目录(工程目录根路径): /day14

            -   getServletPath() --\> 要访问的 Servlet 路径: /demo01

            -   getRequestURI() --\> Uniform Resource Indentifier: /day14/demo01

            -   getQueryString() --\> 获取 get 方式时请求行携带的数据:
                \`name=zhangsan\`

        -   2. 请求头

            -   重要的请求头:

                -   User-Agent --\> 浏览器相关信息

                    -   对浏览器进行兼容(中文编码)

                -   Referer --\> 来自哪里

                    -   防盗链, 数据统计)

            -   对应方法:

                -   String getHeader(String name)

                -   Enumeration\<String\> getHeaderNames() --\> 获取所有

                    -   boolean hasMoreElements()

                    -   E nextElemet()

        -   3. 请求空格

        -   4. 请求体

            -   只有 POST 请求方式才有请求体

            -   表单提交时携带回的数据存储在请求体中

            -   四种通用(post 和 get)方法

                -   String getParameter(String name):根据参数名称获取参数值  
                     username=zs&password=123

                -   String[] getParameterValues(String
                    name):根据参数名称获取参数值的数组  hobby=xx&hobby=game

                -   Enumeration\<String\>
                    getParameterNames():获取所有请求的参数名称

                -   Map\<String,String[]\>
                    getParameterMap():获取所有参数的map集合

    -   Response 对象( 响应 )

        -   响应行

            -   常见状态码

                -   200: 连接成功

                -   302: 重定向(页面跳转)

                -   304: 读取缓存

                -   404: 输入的路径不正确或者请求路径没有对应的资源

                -   500: 服务器

            -   设置状态码: setStatus(int sc)

        -   响应头

            -   设置响应头

                -   setHeader(String name, String value)

                -   addHeader()

                    -   专门针对一对多的键值对, 增加第四个value值.

            -   重要响应头:

                -   Content-Type

                    -   设置浏览器读取的文件MIME格式

                    -   解码的字符集

                -   location

                    -   302 进行重定向

                        -   \`response.sendRedirect("/day15/responseDemo2");\`

                -   Content-disposition

                    -   in-line:默认值,在当前页面内打开

                    -   attachment;filename=xxx：以附件形式打开响应体。文件下载

        -   响应空行

        -   响应体

            -   设置响应体步骤:

                -   1. 获取输出流

                    -   字符输出流：PrintWriter getWriter()

                    -   字节输出流：ServletOutputStream getOutputStream()

                -   2. 使用输出流, 将数据输出到客户端浏览器

    -   ServletContext 对象

        -   1. 获取方式

            -   request.getServletContext();

            -   this.getServletContext()

                -   通过HttpServlet找父类方法

        -   2. 主要API

            -   String getMimeTpye() --\> 获取文件对应的MIME格式

            -   String getRealPath() --\> 获取资源路径

            -   InputStream getResourceAsStream()

            -   作为域对象

                -   setAttribute(String name, String value)

                -   getAttribute(String name)

                -   removeAttribute(String name)
