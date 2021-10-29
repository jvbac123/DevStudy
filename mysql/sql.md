# SQL

+ SQL语句是不分大小写的

  

## Select查询

### 查询执行顺序

~~~sql
select 
from
where
group by
having
order by
~~~





### where 条件查询

| 操作符          | 描述                        |
| :-------------- | :-------------------------- |
| =               | 等号，                      |
| <>, !=          | 不等于                      |
| >               | 大于号                      |
| <               | 小于号                      |
| >=              | 大于等于号                  |
| <=              | 小于等于号                  |
| between ... and | 两个值之间 相对于 >= and <= |
| is null         | 为null (is not null 不为空) |
| and             | 并且                        |
| or              | 或者                        |
| in              | 包含 相对于多个or           |
| not             | 取非                        |
| like            | 模糊查询                    |
|                 |                             |





####  like 模糊查询

+ _代表单个字符

+ %代表多个字符

```sql
SELECT	`user`.* FROM`user` WHERE nickname LIKE 'J%'
```

### order 排序

+ ASC 升序
+ DESC 降序
~~~sql
SELECT	`user`.* FROM`user` ORDER BY username ASC 
SELECT	`user`.* FROM`user` ORDER BY username DESC 
~~~

### 分组函数

**分组函数不可用于where 语句下**

+ sum() 取总数

+ max() 取最大值

+ min() 取最小值

+ avg()  平均值

+ count() 取数量

  

示例：取id最大值

~~~sql
SELECT max(uid) FROM`user` 
~~~

示例：总数量

```sql
SELECT COUNT(*) FROM`user` 
SELECT COUNT(uid) FROM`user` 
```

#### 单行处理函数

非多行处理函数 如:四目运算符

~~~sql
select money/1000  from user 
~~~

##### 注意

​	 如果数据为null与 非null 函数相加 结果都为null,多行

### 结果去重 DISTINCT

~~~sql
SELECT DISTINCT job,emp.ENAME FROM emp
#DISTINCT 只能作为首个字段使用
~~~





### group by和分组函数

#### 基本用法

+ **gruop by** 是按照某个字段 或者某些字段进行分组，需要和分组函数联合执行

+ 在**group by **执行完后进行**分组函数（）**

  ~~~sql
  select max(price) from prouct grop by class
  #找出每个分类中价格最高的那个项，只显示价格列
  ~~~

  

#### 使用过滤having

如果想对分组数据再进行过滤需要使用**having**子句

~~~sql
select max(price) from prouct 
group by class
having max(price)>1000
#找出每个分类中价格最高的那个项,只显示大于1000的，只显示价格列
~~~



### 联合查询



内连接之非等值连接：最大的特点是：连接条件中的关系是非等量关系
假设A和B表进行连接，使用内连接的话，凡是A表和B表能够匹配上的记录查询出来，这就是内连接。

AB两张表没有主副之分，两张表是平等的



+ SQL92:
  ```sql
  SELECT 
  	[表1.列],
  	[表2.列] 
  FROM 
  	[表1],[表2]
  WHERE
  	表1.列=表2.列
  ```

+ SQL99:
```sql
SELECT 
	[表1.列],
	[表2.列] 
FROM 
	[表1]
JOIN 
	[表2]
ON
	表1.列=表2.列
```

#### 内连接inner join



~~~sql
SELECT 
a.*,
b.ENAME as '上级名字'

FROM
emp a
INNER JOIN
emp b
ON
a.MGR = b.EMPNO
~~~



#### 外连接







### 子查询



~~~sql
select
id,
nickname,
IFNULL(t.count1, 0) AS dcount
from
ums_member
left join
(SELECT	member_id, count(*) AS count1 FROM 	oms_order GROUP BY 	oms_order.member_id) t
on
ums_member.id = t.member_id
~~~





