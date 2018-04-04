* flagpages的坑，如何使about页面正常显示：     
    1.要在`settings.py` 中加入`SITE_ID = 1`      
    2.要在admin页面把flat page中的Sites参数改为`example.com`，不要用`localhost`
    
* 设置管理员账号密码  
```
python manage.py createsuperuser
```
* 设置`pymysql`为`django`项目的`mysql`客户端  
在`__init__.py`中添加代码
```
import pymysql
pymysql.install_as_MySQLdb()
```

* 数据库迁移后查看数据库改变的源码  
`python manage.py sqlmigrate [appName] [migrate_number, e.g. 0001]`

* pyCharm 中添加已创建的 virtualenv 环境  
> add local选择创建的虚拟环境env中的python解释器（如D:\venv\Scripts\python.exe）就可以了  
 **路径不可以含有中文或表情字符**

* (python3.6)安装 fabric3 后一键部署命令    
`fab deploy`

* Django shell 内运行 Python 脚本    
`python manage.py shell < xxx.py`
