### 在`crontab`中配置用户的环境变量
1.使用`crontab -e`，并进入编辑模式   
2.在 cron 命令前写入  
```
PATH = /myPATH
SHELL = /bin/bash  #指定执行脚本的shell
```
其中`/myPATH`为用户的环境变量，可用`echo $PATH`命令查看

### 查看隐藏文件
`ls -a`

### 阿里云 ECS 解决 ssh 会话连接超时问题
1、设置服务器向SSH客户端连接会话发送频率和时间  
#vi /etc/ssh/sshd_config，添加如下两行  
```
ClientAliveInterval 60
ClientAliveCountMax 86400
```

注：ClientAliveInterval选项定义了每隔多少秒给SSH客户端发送一次信号；ClientAliveCountMax选项定义了超过多少秒后断开与ssh客户端连接

2、重新启动系统SSH服务   
`#sudo service ssh restart`

### Linux中搭建selenium运行环境
> 思路：安装 selenium，浏览器 Firefox --> 安装相关工具为selenium驱动浏览器提供无图形化界面 --> 安装相关驱动，配置环境变量

1. 安装 selenium，浏览器 Firefox
```
pip install selenium
sudo apt-get install firefox
```
2. 安装相关工具为selenium驱动浏览器提供无图形化界面
```
sudo apt-get install xvfb
pip install pyvirtualdisplay
```
3. 安装 geckodriver，作相关配置，参见https://askubuntu.com/questions/870530/how-to-install-geckodriver-in-ubuntu?utm_medium=organic&utm_source=google_rich_qa&utm_campaign=google_rich_qa

### Linux 设置环境变量
* 编辑`/etc/profile`文件。修改后对所有用户永久生效。例如，添加 geckodriver 驱动：
```bash
# 注意等号两边绝对不能有空格！
export PATH=$PATH:/path-to-the-folder-containing-geckodriver/
```

### 解决 vim 中文乱码问题
* 在`~/.vimrc`文件中加入以下设置  
```bash
set fileencodings=utf-8,ucs-bom,gb18030,gbk,gb2312,cp936
set termencoding=utf-8
set encoding=utf-8
```
### 解决 linux 终端无法输入中文的问题
1. 首先要从Ubuntu语言设置那里，把中文语言包安装上。
  打开`/etc/environment`，在下面添加如下两行
```bash
LANG=”zh_CN.UTF-8″
LANGUAGE=”zh_CN:zh:en_US:en”
```

2. 打开 `/var/lib/locales/supported.d/local`，添加zh_CN.GB2312字符集，如下：
```bash
en_US.UTF-8 UTF-8
zh_CN.UTF-8 UTF-8
zh_CN.GBK GBK
zh_CN GB2312
```
  保存后，执行命令：
  ```
  sudo locale-gen
  ```

3. `打开/etc/default/locale`，修改为：
```bash
LANG=”zh_CN.UTF-8″
LANGUAGE=”zh_CN:zh:en_US:en”
```

### 在`/var/log`目录中没有 cron 日志
1. 修改`/etc/rsyslog.d/50-default.conf`文件，将 #cron.*  前的  #  删掉；  
2. 重启rsyslog服务  
```bash
service rsyslog restart
```
3. 重启 cron 服务  
```bash
service cron restart
```
4. 查看 cron 日志  
```bash
tail -f /var/log/cron.log  
```

