# 一些SQL用法



### 1. 分割字符串

> mysql

```sql
select substring_index('7654,7698,7782,7788', ',', 1) from dual
```

```
参考资料:https://www.cnblogs.com/gered/p/10797012.html
```

### 2. 查询日期

> oracle

```sql
-- 查询当前月第一天
select trunc(sysdate, 'mm') from dual

-- 查询上个月第一天
select add_months(trunc(sysdate, 'mm'),-6) from dual
```

> mysql

```sql
select now() from ...
```



### 3. 列转行

> oracle

```sql
select 
*
from (
    select cmcode, to_char(rqsj, 'YYYY-MM') month
    ,sum(case when cmtype=1 then bmoney*DIRECTION end) as change_1
    from DBUSRCARD.CARDMONEYACCOUNT
    where rqsj>= to_date('2022-01-01','yyyy-mm-dd') and rqsj < to_date('2023-01-   01','yyyy-mm-dd')
    group by cmcode,to_char(rqsj, 'YYYY-MM')
    order by cmcode,to_char(rqsj, 'YYYY-MM')
    ) t
	pivot (sum(change_1) for month in (
        '2022-01', '2022-02', '2022-03', '2022-04', '2022-05', '2022-06', '2022-07', '2022-08', '2022-09', '2022-10', '2022-11', '2022-12'
))
```

### 4. 列合并，字段拼接

> oracle

```sql
-- 将名字按照id合并，并以逗号分隔
select id,wm_concat(',',name) as language from tmp_test group by id;


-- 字段拼接 ||
select id || name from t1
```

> mysql

```sql
-- group_concat
select id, group_concat(name,age) from t1 group by id

-- concat()
select concat(id, name) from t1
```



### 5. having

```sql
-- 跟在group by后面，对聚合后的结果进行实时筛选
select name, sum(id) from table_test group by name having sum(id) > 10 
```



### 6. 限制结果

> mysql

```sql
-- 查询前5行结果
select * from t1 limit 5

-- 查询从第5行还是的5行结果
select * from t1 limit 5 offset 5
```

> oracle

```sql
-- 查询前5行结果
select * from t1 where rownum <=5
-- rownum 行计数器
```



### 7. 去除前后空格

```sql
select ltrim(), rtrim() from t1
-- ltrim 去除左空格
-- rtrim 去除右空格
```



### 8. Between

- between ... and ... 包含指定的开始值和结束值



### 9. and 和 or

```sql
如果语句中同时存在and和or，会优先处理and语句，因此需要使用小括号来限定条件范围（）
```



### 10. NOT

```sql
select * from t1 where not name='dennis'
-- not也可以使用在需要过滤的列条件之前，此时和<>符号的功能一样
```



### 11. 通配符

1. 最常用的通配符`%`

- 使用通配符意味着需要耗费更长的查询时间
