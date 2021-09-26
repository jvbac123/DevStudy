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

