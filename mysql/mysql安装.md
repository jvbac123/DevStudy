## MySql安装
## 压缩包版本安装
1. 首先解压如下
      ![](..\img\QQ截图20210925161717.png)
2. 将文件保存为my.ini 放到MySQL安装目录下

 ``` ini
   [mysqld]
   # 设置3306端口
   port=3306
   # 设置mysql的安装目录
   basedir=D:\\Program\\mysql-8.0.20-winx64
   # 设置mysql数据库的数据的存放目录
   datadir=D:\\Program\\mysql-8.0.20-winx64/data 
   # 允许最大连接数
   max_connections=200
   # 允许连接失败的次数。
   max_connect_errors=10
   # 服务端使用的字符集默认为UTF8
   character-set-server=utf8
   # 创建新表时将使用的默认存储引擎
   default-storage-engine=INNODB
   # 默认使用“mysql_native_password”插件认证
   default_authentication_plugin=mysql_native_password
   [mysql]
   # 设置mysql客户端默认字符集
   default-character-set=utf8
   [client]
   # 设置mysql客户端连接服务端时默认使用的端口
   port=3306
   default-character-set=utf8
 ```
### 注意事项
+ 一定要放my.ini再初始化安装 否则无法登录数据库
------
###  初始化MySQL数据库

``` shell
mysqld --initialize-insecure
```
 请使用管理员权限执行该命令



初始化后目录下会有data目录，删除该目录相对于重置数据库
![img.png](../../img/img.png)
### Windows系统安装MySQL服务
``` 
    mysqld install [服务名]
```
默认服务名为：MySQL
### 启动和停止MySQL服务
```shell
启动MySQL服务 
net start mysql
停止MySQL服务
net stop mysql
卸载 MySQL 服务
sc delete MySQL/mysqld -remove
```
### 修改密码
MySQL登陆，无需输入密码直接回车
```shell
mysql -u root -p
```
![img.png](../../img/img2.png)
通过这两行SQL语句 将root用户的密码设置为“root”

``` sql
use mysql;
ALTER USER 'root'@'localhost' IDENTIFIED BY 'root';
```

