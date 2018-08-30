## DDL: Datebase Definiate Language

1. 操作数据库: 	

    1. **增**
       - `create database 数据库名;`
       - 复制数据库: `create database 数据库名 like 被复制的数据库名;`
    2. **删**
       - `drop database 数据库名;` 
    3. **改**
       - 改字符集: `alter database 数据库名 character set 'gbk';`
       - 改数据库名称: 
         - 创建新的空数据库, 复制旧的到新的.
         - - [ ] `create database 新数据库名 select * from 旧数据库名;`
    4. **查**

      - 显示所有数据库: `show databases;`
      - 显示创建与信息: `show create database 数据库名;`
      - 显示当前所用数据库: `show database();`

2. 操作表: 

    1. **增**

       - `create table 表名(属性名 属性数据类型 约束);`
       - 复制表结构: `create table 新表名 like 被复制表名;`
       - - [ ] 完全复制另外一个表里的数据.

    2. **删**

       - `drop table 表名`

    3. **改**

       - `alter table 表名 add 列名 列数据类型;`增加一列数据.
       - `alter ...modify 列名 列属性`
         1. 修改非空约束
         2. 删除自增
       - `alter ... rename to 新表名;`
       - `alter...change 旧列名 新列名 新列名类型;`

    4. **查**
      - ` show tables; ` 显示所有表
      - `show create table 表名`显示创建信息
      - `desc 表名;`显示表结构
      - `select * from 表名;`筛选并显示表中所有信息

## DML

3. 操作表中数据: 

   1. **增**

      - 增加一行(条)数据`insert into 表名称 (列1,列2,列3...) values(值1,值2,值3... );`

        1. 列类型与值类型匹配;
        2. 有默认值的前提下, 才可以插入某几列数据.

        ```sql
        INSERT INTO kindsnake (id,kind_Time,test) VALUES (5,'下午三四点',2); -- Field 'kind_Name' doesn't have a default value
        ```

        

   2. **删**

      - `delete from 表名 where 条件;`
      - `truncate 表名`

   3. **改**

      - `update 表名 set 列名 = 值 where ...条件;`

## DQL

​	4. **查**

完整格式: 

`select 字段(列名),聚合函数/* from 表名 where 条件 `

`group by 有重复记录的字段 having 条件/聚合函数 `

`order by avg(mathscore) limit(offset: 起始行数, 每页个数);`

 	1. 条件: 
```sql
 - 比较运算符: 
   - is null
   - between...and --> 区间
   - `in(.,.)`--> 集合,包含多个值
 - 逻辑运算符
   - and
   - or
   - not
 - like 模糊查询
   - 占位符
     - '_' : 占一个字符, 
     - '%': 占任意字符:  
   - '马%': 姓马的
   - '%德%': 包含德的 `where name like '%德%'`
2. 聚合函数: 五种
	1. `count(*/id)`
	2. sum
	3. avg
	4. max
	5. min(score)
```



_____

## 约束

1. 修改主键自增起始值: 

```sql
alter table tablename auto_increment = 2;
```

2. 修改唯一约束

```sql
alter table tablename drop index columnname;
```

- [ ] ###  多对多关系的建立.复合主键 以及联合主键的建立.

