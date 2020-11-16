通过设置别名，访问远程服务器：

ssh相关配置文件位于~/.ssh中，主要包括config、known_hosts两个文件。如果有使用过ssh的话，那么known_hosts就会存在。

编辑config文件，

touch config， 或者vim config 或者gedit config 

添加如下内容：

```javascript
Host jhd
HostName 1xx.1xx.1xx.67
User root
IdentitiesOnly yes
```

host后面为别称，hostname为主机ip，user为主机登录的用户名，IdentitiesOnly yes为固有配置