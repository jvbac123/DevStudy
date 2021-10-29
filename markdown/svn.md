创建仓库

~~~sh
svnadmin create [顶层仓库路径]\[仓库名]
~~~

设置为系统服务

~~~sh
sc create SVNServer
binpath="[SVN路径] -r [仓库位置]"
start=auto #开机自启
depend=Tcpip

~~~

建立链接

~~~sh
#要求服务端目标仓库已经创建
svn checkout  svn://127.0.0.1/sms
~~~

