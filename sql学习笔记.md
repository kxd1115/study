
###### mysql 是一种关系型数据库，确切的说，数据库软件应该称为一种数据库管理系统（DBMS）。
**存储引擎分类**
- MYISAM  不支持事物，不支持外键，访问速度极快。
- INNODB  提供事物支持，具有提交，回滚和崩溃恢复能力，速度稍慢。（5.5以后的默认类型）
- MEMORY  访问速度快，数据存放在内存中，但是一旦关闭数据库，表中数据就会丢失。

**SQL语言**
主要分为四大类
- DDL 数据定义语言
    - 用来定义数据库对象，创建库，表，列等。
- DML 数据操作语言
    - 用来操作数据表中的记录
- DQL 数据查询语言
    - 用来查询数据
- DCL 数据控制语言
    - 用来定义访问权限和安全级别
###### 基本操作：
    show databases → 查看当前数据库
    use <数据库名> → 链接选中数据库
    show tables → 查看当前数据库中有哪些表
* 使用 exit 或者 quit 退出 mysql

###### 新建数据库：
    create database <库名称> character set uft8→ sql语句不区分大小写。
       数据表 是数据库的重要组成部分之一。数据库只是一个 框架，表才是主要内容。数据库中可以有很多张表。

###### 新建数据表：
    CREATE TABLE <表的名字>
    （
    列名a  数据类型（数据长度），
    列名b  数据类型（数据长度），
    列名c  数据类型（数据长度）
    ）；
    
###### mysql 常用数据类型:
    
数据类型 | 大小(字节) | 用途 | 格式
---|---|---|---
INT | 4 | 整数 | 
FLOAT | 4 | 单精度浮点数 
DOUBLE | 8 | 双精度浮点数 
ENUM  | 单选,比如性别 | ENUM('a','b','c')
SET  | 多选 | SET('1','2','3')
DATE | 3 | 日期 | YYYY-MM-DD
TIME | 3 | 时间点或持续时间 | HH:MM:SS
YEAR | 1 | 年份值 | YYYY
CHAR | 0~255 | 定长字符串 
VARCHAR | 0~255 | 变长字符串 
TEXT | 0~65535 | 长文本数据 

###### 数据插入：
* 使用 insert 语句向表中插入数据:
```
insert into <表的名字> （列名a， 列名b， 列名c） values （值1， 值2， 值3）；
```

###### 添加一列：
```
ALTER TABLE <table_name> ADD col_name 数据类型 约束;
```
###### 修改列字段类型：
```
ALTER TABLE <table_name> MODIFY col_name 新类型 ;
```
###### SQL 约束：
**类型**：
* 主    键 （==primary key==）
    * 用来表示一个特定的行。主键不能有重复值且不能为空值，主键列中的值不允许修改或者更新，主键不能重用。
* 默认值（==default==）
    * 当有默认值的列插入数据为空值时，将会使用默认值填充。
* 唯    一（==unique==）
    * 规定一张表中的指定列必须都是唯一值，即每个值之间不能重复。
* 外    键（==foreign key==）
    * 一个表可以有多个外键，每个外键必须 REFERENCES (参考) 另一个表的主键，被外键约束的列，取值必须在它参考的列中有对应值。
    * ```CONSTRAINT  <自定义名称>  FOREIGN KEY(列名称) REFERENCES  <其他表名称>(列名称)``` 
* 非    空（==not null==）
    被约束的列在插入数据时不能是空值。

###### SQL语句详解
1. 基本 SQL 语句
    1. ```SELECT * FROM <表名称> ``` → 用于整张表信息。
    2. ```SELECT <列名1，列名2……> FROM <表名称> ``` → 用于查询表中指定列的信息。

2. 数学符号条件
    * 利用 WHERE 限制条件，可以使用数学符号 =，>，<，>=，<= 等。

3. =="AND"== 与 =="OR"==
    * WHERE 后面可以有多条限制，可以利用 AND 或者 OR 来链接它们。
    当然，类似于 ```WHERE age>25 and age<30``` 的限制条件，也可以使用 BETWEEN 来完成：```WHERE age BETWEEN 25 AND 30```。

4. =="IN"== 和 =="NOT IN"==
    * 这两条命令用于筛选特定列中 “在” 或者 “不在” 范围内的特定结果。

5. 通配符
    * 关键字 ==LIKE== 在 ==SQL== 中和通配符一起使用。
    SQL 中有两种通配符：_ 和 %，其中 _ 代表一个未指定字符，% 代表不定个字符。

6. 对结果排序  =="ORDER BY"==
    * 可以利用 ORDER BY 进行排序。默认情况下，ORDER BY 是按照升序排列，而使用关键词 ==ASC== 和 ==DESC== 可 指定升序 或 降序排序。

7. SQL 内置函数和计算
    函数 | 用法
    ---|---
    COUNT | 计数
    SUM | 求和
    AVG | 求平均值
    MAX | 最大值
    MIN | 最小值
    其中 COUNT函数可以适用于任何类型的数据，而 SUM 和 AVG 只适用于数值型数据，MAX 和MIN 适用于 数值、字符串 或是 日期时间数据类型。
    例如：
    ```
    SELECT  MAX(salary)  AS  max_salary , MIN(salary)  FROM  employee;
    ```
    可以使用 AS 关键词给值重命名。

8. 子查询
    * 有时因为需要查询的结果涉及到几个表格，因此可以使用子查询来进行索引。
    * 例如： 
    ```
    SELECT of_dpt,COUNT(proj_name) AS count_project FROM project
    WHERE of_dpt IN
    (SELECT in_dpt FROM employee WHERE name='Tom'); 
    ```
    子查询可以扩展到3层，4层或者更多，但是子查询只有在结果都来自一个表中时才有用。

9. 连接查询
    * 当查询涉及到需要将过个表的结果显示为一个新的表格时，可以使用连接（join）操作。
    * 如下：
    ```
    SELECT id,name,people_num
    FROM employee,department
    WHERE employee.in_dpt = department.dpt_name
    ORDER BY id;
    ```
    可以使用 join on 进行操作：
    ```
    SELECT id,name,people_num
    FROM employee JOIN department
    ON employee.in_dpt = department.dpt_name
    ORDER BY id;
    ```
效果同上。

###### 修改和删除:

* 删除数据库

    ```DROP  DATABASE  <数据库名称> ；```

* 对表重命名

    ```RENAME  TABLE  <表名字>  TO  原名字  新名字 ；```

* 删除表

    ```DROP  TABLE  <表名字> ；```

* 增加一列

    ```ALTER  TABLE  <表名字>  ADD  列名字  数据类型  约束   ALFTER <列名>；```

    注：AFTER<列名>  可以将新列插入在某列后面，如果想放在第一列，可以将其替换为 FIRST 即可。

* 删除一列
    ```ALTER  TABLE  <列名字>  DROP  <列名字> ；```

* 重命名一列
    ```
    ALTER  TABLE  <列名字>  CHANGE  原名字  新名字  数据类型  约束 ；
    ```

* 修改某个值
    ```
    UPDATE  <表名字>  SET  列1 = 值1，列2 = 值2 WHERE  条件；
    ```
    注：想要索引到某个数据需要使用 WHERE 进行精确索引，且必须要使用 WHERE 条件。

* 删除一行记录

    ```DELETE  FROM  <表名字>  WHERE  条件；```

    注：想删除某行数据，必须要加上 WHERE 条件。

###### 其他基本操作

- 索引
    ```
    ALTER TABLE 表名字 ADD INDEX 索引名称（列名）；
    CREATE INDEX 索引名 ON 表名（列名）；
    ```
    - 以上两种方法都可以进行索引设置，索引可以让查询更加方便
    
- 视图
    - 视图是从一个或者多个表中导出来的表，是一种==虚拟存在的表==。它就像一个窗口，通过这个窗口可以看到系统专门提供的数据，这样，用户可以不用看到整个数据库中的数据，而只关心对自己有用的数据。
    ```
    CREATE VIEW 视图名（列1，列2，列3） AS SELECT 列1，列2，列3 FROM 表名；
    ```
    - 后半句是查询语句，视图可以创建在多个表之上，只需要在查询时加入子查询或者连接查询即可。
    
- 导入
    - 将文件中的数据导入到表中。
    ```
    LOAD DATA INFILE '文件路径' INTO TABLE <表名称>；
    ```
- 导出
    - 将文件保存到指定目录下。
    ```
    SELECT col1, col2 INTO OUTFILE '文件路径' FROM <表名称>；
    导入指定列数据，文件路径下不能有同名文件
    
    SELECT * INTO OUTFILE '文件路径' FROM <表名称>；
    导入整张表数据
    ```
    
#### MySQL 操作详解
- `DISTINCT`关键字能够在索引时提取唯一值。
- `DESCRIBE <表名称>`;
    - 用于查询表中各列的属性。
- 日期计算
    - 可以使用`TIMESTAMPDIFF()`函数进行年龄计算，也可以直接使用语句`YEAR(CURDATE()) - YEAR(birth)`之类的语句进行计算，其中的`CURDATE()`表示当前日期。
    - `MONTH`函数可以提取日期中的月份信息。
- **模式匹配**
    - 使用`REGEXP`和`NOT REGEXP`对测试值进行匹配。
    - '.' 匹配任意形式的单个字符。
    - "[...]" 匹配方括号类的任意一个字符，"[a-z]" 表示匹配任意字母，"[0-9]" 表示匹配任何数字
    - "`*`" 表示匹配零个或者多个在它前面的字符，例如：'x*' 就表示匹配任何数量的x字符。
    - 为了定位一个模式以便它必须匹配被测试值的开始或者结尾，在模式开始时使用“^”符号，在模式结束时使用“$”符号。
- 计算行数
    - 使用`COUNT(*)`函数计算行数。
    - `GROUP BY`对指定列进行分类显示。
- 返回指定行数
    - 可以在查询时加上`LIMIT 需要查询的行数`或者`LIMIT a，b`表示从第a行开始获取b行数据。

#### MySQL 常用查询
- `unsigned`将整数字段限制为非零整数。
- `zreofill`将整数按照自定义格式输出，例如：01，001，0001等。
1. 输出表中某列最大值
```
SELECT MAX(列名称) AS <自定义名称> FROM 表名

```
2. 查询某列最大值所在的行
```
SELECT * FROM 表名称 WHERE 列A = (SELECT MAX(列A) FROM 表);
```
3. 利用`GROUP BY`显示每种类型最大值
```
SELECT 列1,MAX(列2) FROM 表 GROUP BY 列1；
```
4. 使用用户变量
```
mysql> CREATE TABLE person (
    -> id SMALLINT UNSIGNED NOT NULL AUTO_INCREMENT,
    -> name CHAR(60) NOT NULL,
    -> PRIMARY KEY (id)
    -> );

mysql> CREATE TABLE shirt (
    -> id SMALLINT UNSIGNED NOT NULL AUTO_INCREMENT,
    -> style ENUM('t-shirt', 'polo', 'dress') NOT NULL,
    -> color ENUM('red', 'blue', 'orange', 'white', 'black') NOT NULL,
    -> owner SMALLINT UNSIGNED NOT NULL REFERENCES person(id),
    -> PRIMARY KEY (id)
    -> );

mysql> INSERT INTO person VALUES (NULL, 'Antonio Paz');

mysql> SELECT @last := LAST_INSERT_ID();
       # 该语句表示查询ID列最后一次插入的值是多少。
       
       AUTO_INCREMENT → 作用在主键上，表示每次插入后自动填充一个值。
       例如：
       mysql> INSERT INTO person VALUES (NULL, 'Antonio Paz');
       那么就会填充：“1，Antonio Paz” 到表中，下次插入数据时，则会填充2，3，4……

```


## MySQL语言结构
#### 字符串
