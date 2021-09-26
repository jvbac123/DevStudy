##  Git

#### checkout

###### 

```sh
git checkout -- <filename> #将工作区的修改丢弃 不要随意使用

#git checkout -b <branch name> <SHA1> #基于历史提交
```



#### reset

+ **--mixed** 为默认，暂存区被清空，工作区的修改保留

+ **--soft** 暂存区和工作区不变

+ **--hard** 暂存区和工作区的修改被清空



###### 回退到上一个版本  

```
git reset HEAD^ #文件名
```

###### 回退到指定版本

```sh
git reset #hash
```

**HEAD 说明：**

- HEAD 表示当前版本
- HEAD^ 上一个版本
- HEAD^^ 上上一个版本

可以使用 ～数字表示

- HEAD~0 表示当前版本
- HEAD~1 上一个版本

#### branch



 

#### merge

合并分支

```shell
git merge #分支名字
git merge --no-ff 
```



#### blame

查看文件的修改记录

~~~
git blame #文件名
~~~

显示暂存区和上一次提交(commit)的差异:

```
$ git diff --cached [file]
或
$ git diff --staged [file]
```

#### diff 

+ diff 命令比较文件的不同，即比较文件在暂存区和工作区的差异

+ diff 命令显示已写入暂存区和已经被修改但尚未写入暂存区文件对区别

  显示暂存区和工作区的差异:

  ```sh
  git diff [file]
  ```

#### rm

删除

```sh
git rm <file> #工作区 暂存区都删
git rm --cached <file> #文件从暂存区域移除，但保留工作区文件

```



##### GitHub SSH Keys 配置

1. 生成SSH密钥

```
ssh-keygen -t rsa -C "注释"
```

2. 复制生成位置的.pub文件 公钥（public  key）内容

<img src="..\img\image-20210926100914648.png" alt="image-20210926100914648"  />

3. 打开配置页面并添加公钥
   + [SSH and GPG keys (github.com)](https://github.com/settings/keys)

4. 关联远程仓库

```
git remote add origin git@github.com:[username]:[project]    
```

> ​	**请不要使用HTTPS方式**，
> 否则在push的时候会提示需要用户名和密码，但是GitHub已经停用了用户名密码方式push

5. 推送到远程仓库

```
git push
git push --set-upstream origin master /*在第一层没有将本地分支与远程封装绑定的时候*/
```



##### git远程仓库的相关操作



###### 删除远程仓库

```
git remote remove origin
```

