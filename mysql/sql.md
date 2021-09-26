### SQL

+ SQL语句是不分大小写的

  

#### Select查询

##### 查询执行顺序

~~~sql
select 
from
where
group by
having
order by
~~~





##### where 条件查询

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

#### 



######  like 模糊查询

+ _代表单个字符

+ %代表多个字符

```sql
SELECT	`user`.* FROM`user` WHERE nickname LIKE 'J%'
```

##### order 排序

+ ASC 升序
+ DESC 降序
~~~sql
SELECT	`user`.* FROM`user` ORDER BY username ASC 
SELECT	`user`.* FROM`user` ORDER BY username DESC 
~~~

##### 分组函数/聚合函数/多行处理函数

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

##### 单行处理函数

非多行处理函数 如:四目运算符

~~~sql
select money/1000  from user 
~~~

###### 注意

​	 如果数据为null与 非null 函数相加 结果都为null,多行

##### group by分组

#### 联合查询

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



​	
