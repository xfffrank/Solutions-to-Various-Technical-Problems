### 在`crontab`中配置用户的环境变量
1.使用`crontab -e`，并进入编辑模式   
2.在 cron 命令前写入  
```
PATH = /myPATH
SHELL = /bin/bash  #指定执行脚本的shell
```
其中`/myPATH`为用户的环境变量，可用`echo $PATH`命令查看

### 查看隐藏文件
* `ls -a`
