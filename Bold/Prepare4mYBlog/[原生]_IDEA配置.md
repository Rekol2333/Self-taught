# 1. 类注释
`File and Code Templates`中`class`选项

```java
/**
* @Project: ${PROJECT_NAME}
* @Author: Reolcharm
* @CreatedTime: ${YEAR}-${MONTH}-${DAY} ${HOUR}:${MINUTE}
* @Description: ${description}
**/
```

# 2. 方法注释(Live Templates)
- `Live Templates`-->`+`-->`Templates Group`添加自己的动态模板
- `Abbreviation`:f --> `Description`: 左边就是模板的快捷键-->快捷键 + tab 输出模板
- `Template text`:
- 
```java
** 
* @Param: $params$ 
* @return: $returns$ 
* @Author: Reolcharm
* @Date: $date$-$time$
* @Description: $description$ 
*/ 
```
- `Edit Variables`中编辑变量对应的方法:
![LiveTemplates](G:\AllTheExercise\Magic\MarkAndMemory\Pictures\Live Templates Snipaste_2018-09-15_19-58-15.png)

# 3.Servlet 类模板
```java
/**
* @Project: ${PROJECT_NAME}
* @Author: Reolcharm
* @CreatedTime: ${YEAR}-${MONTH}-${DAY} ${HOUR}:${MINUTE}
* @Description: 
**/
#if (${PACKAGE_NAME} && ${PACKAGE_NAME} != "")package ${PACKAGE_NAME};#end
#parse("File Header.java")
@javax.servlet.annotation.WebServlet(name = "${Entity_Name}", urlPatterns = "/${Entity_Name}")
public class ${Class_Name} extends javax.servlet.http.HttpServlet {
    @Override
    protected void doPost(javax.servlet.http.HttpServletRequest request, javax.servlet.http.HttpServletResponse response) throws javax.servlet.ServletException, java.io.IOException {

    }
    
    @Override
    protected void doGet(javax.servlet.http.HttpServletRequest request, javax.servlet.http.HttpServletResponse response) throws javax.servlet.ServletException, java.io.IOException {
        doPost(request, response);
    }
}
```