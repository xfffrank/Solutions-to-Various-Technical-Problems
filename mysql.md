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
