* 把数据库'test'中的所有表的所有权限给用户'Frank'  
```
mysql> grant all privileges on test.* to 'Frank'@'localhost'
    -> ;
Query OK, 0 rows affected (0.01 sec)
```

* 登录'root'用户  
`mysql -u root -p`

* 收回权限  
"grant" -> "revoke"  
"to" -> "from"

* 使用数据库'test'  
`use  test;`

* 创建用户  
`CREATE USER 'username'@'host' IDENTIFIED BY 'password';`

* 删除用户  
`DROP USER 'username'@'host';`

* 安装，启动`mysql`服务  
```
brew install mysql
```
```
xiefengdeAir:~ Frank$ mysql.server stop
Shutting down MySQL
.. SUCCESS! 
xiefengdeAir:~ Frank$ mysql.server start
Starting MySQL
. SUCCESS! 
xiefengdeAir:~ Frank$ mysql.server restart
Shutting down MySQL
.... SUCCESS! 
Starting MySQL
. SUCCESS! 
```

* 修改默认值
`alter table table_name alter column_name set default default_value;`
