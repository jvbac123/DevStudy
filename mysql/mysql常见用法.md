### MySQL终端命令（不属于SQL语句）
+   查看数据库列表
~~~
    show databases;
~~~
+ 使用（选择）数据库 
~~~
    use [数据库名字]
~~~
+ 显示表列表
~~~sql
    show tables
~~~
+ 导入sql文件到数据库
~~~
    sourse [文件路径]
~~~

~~~
查看当前选择的库
select database();
查看MySQL版本号
select version();
~~~

~~~
结束语句    \c
退出mysql终端   \q
~~~