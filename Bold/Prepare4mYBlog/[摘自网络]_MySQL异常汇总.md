mysql Access denied for user root@localhost错误解决方法总结
2016年07月06日 17:00:40 平凡希 阅读数：136306
问题重现（以下讨论范围仅限Windows环境）：
  
C:\AppServ\MySQL> mysql -u root -p 
Enter password:  
ERROR 1045 (28000): Access denied for user 'root'@'localhost' (using password: YES)



解决方法：

编辑mysql配置文件my.ini（在mysql的安装目录下，我的在D:\Program Files\MySQL\MySQL Server 5.0\my.ini），在[mysqld]这个条目下加入 skip-grant-tables 保存退出后重启mysql

1.点击“开始”->“运行”(快捷键Win+R)。

2.停止：输入 net stop mysql

3.启动：输入 net start mysql  

这时候在cmd里面输入mysql -u root -p就可以不用密码登录了，出现 password：的时候直接回车可以进入，不会出现ERROR 1045 (28000)，但很多操作都会受限制，因为我们不能grant（没有权限）。

继续按下面的流程走：

1.进入mysql数据库：
mysql> use mysql; 

Database changed

2.给root用户设置新密码：  
mysql> update user set password=password("新密码") where user="root"; 
Query OK, 1 rows affected (0.01 sec) 
Rows matched: 1 Changed: 1 Warnings: 0

3.刷新数据库
mysql> flush privileges;
Query OK, 0 rows affected (0.00 sec)  

4.退出mysql：
mysql> quit; 
Bye



改好之后，再修改一下my.ini这个文件，把我们刚才加入的 "skip-grant-tables"这行删除，保存退出再重启mysql就可以了。

