```java
//Source:
//    1. Tomcat调用 service() 方法, 并传入 请求和响应 两个参数
    public void service(ServletRequest req, ServletResponse res) throws ServletException, IOException {
        HttpServletRequest request;
        HttpServletResponse response;
        try {
//    1.2 并向下转型
            request = (HttpServletRequest)req;
            response = (HttpServletResponse)res;
        } catch (ClassCastException var6) {
            throw new ServletException("non-HTTP request or response");
        }
//    1.3 调用本类中的 service() 方法, 传入 HttpServletRequest 和 HttpServletResponse 两个参数.
        this.service(request, response);
    }
//    2. 调用本类中 service() 方法, 方法中进行对 请求方式进行判断.-->这也就是我们要重写的 doGet()/doPost() 方法.
    protected void service(HttpServletRequest req, HttpServletResponse resp) throws ServletException, IOException {
            String method = req.getMethod();
            long lastModified;
            if (method.equals("GET")) {
                 this.doGet();
            } else if (method.equals("POST")) {
                this.doPost();
            } else if (){...}
    }
//    2.3 没有覆写 doPost 方法则返回给客户端(浏览器页面) 405 或者 400 的错误.
      protected void doPost(HttpServletRequest req, HttpServletResponse resp) throws ServletException, IOException {
        String protocol = req.getProtocol();
        String msg = lStrings.getString("http.method_post_not_supported");
        if (protocol.endsWith("1.1")) {
            resp.sendError(405, msg);
        } else {
            resp.sendError(400, msg);
        }

    }
     
```
