#### 在`crontab`中配置用户的环境变量
1.使用`crontab -e`，并进入编辑模式   
2.在 cron 命令前写入  
```
PATH = /myPATH
SHELL = /bin/bash  #指定执行脚本的shell
```
其中`/myPATH`为用户的环境变量，可用`echo $PATH`命令查看

#### 查看隐藏文件
`ls -a`

#### 阿里云 ECS 解决 ssh 会话连接超时问题
1、设置服务器向SSH客户端连接会话发送频率和时间  
#vi /etc/ssh/sshd_config，添加如下两行  
```
ClientAliveInterval 60
ClientAliveCountMax 86400
```

注：ClientAliveInterval选项定义了每隔多少秒给SSH客户端发送一次信号；ClientAliveCountMax选项定义了超过多少秒后断开与ssh客户端连接

2、重新启动系统SSH服务   
`#sudo service ssh restart`
