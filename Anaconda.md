* How to deal with `CondaHTTPError`

#### 问题：
![HTTPError](https://github.com/xfffrank/Solutions-to-Various-Technical-Problems/blob/master/problem_images/conda/conda_5.JPG?raw=true)

![](https://github.com/xfffrank/Solutions-to-Various-Technical-Problems/blob/master/problem_images/conda/conda_2.JPG?raw=true)
#### 解决方法：
1. 用`conda info`命令找到配置文件路径**config file**
```
pc@pc-PC MINGW32 ~/desktop/frank/zipline-1.1.1/zipline-1.1.1                                    
$ conda info                                                                                    
Current conda install:                                                                          
                                                                                                
               platform : win-64                                                                
          conda version : 4.3.23                                                                
       conda is private : False                                                                 
      conda-env version : 4.3.23                                                                
    conda-build version : 2.0.2                                                                 
         python version : 3.5.3.final.0                                                         
       requests version : 2.14.2                                                                
       root environment : C:\Program Files\Anaconda3  (writable)                                
    default environment : C:\Program Files\Anaconda3                                            
       envs directories : C:\Program Files\Anaconda3\envs                                       
                          C:\Users\pc\AppData\Local\conda\conda\envs                            
                          C:\Users\pc\.conda\envs                                               
          package cache : C:\Program Files\Anaconda3\pkgs                                       
                          C:\Users\pc\AppData\Local\conda\conda\pkgs                            
           channel URLs : https://mirrors.tuna.tsinghua.edu.cn/anaconda/pkgs/free/win-64        
                          https://mirrors.tuna.tsinghua.edu.cn/anaconda/pkgs/free/noarch        
            config file : C:\Users\pc\.condarc                                                  
             netrc file : None                                                                  
           offline mode : False                                                                 
             user-agent : conda/4.3.23 requests/2.14.2 CPython/3.5.3 Windows/7 Windows/6.1.7601 
          administrator : True                                                                  
```
2. 修改.condarc 配置文件   
原先我的配置是这样的：   
![HTTPError](https://github.com/xfffrank/Solutions-to-Various-Technical-Problems/blob/master/problem_images/conda/conda_4.JPG?raw=true)   
改成这样即可   
![HTTPError](https://github.com/xfffrank/Solutions-to-Various-Technical-Problems/blob/master/problem_images/conda/conda_5.JPG?raw=true)    
3. 测试运行命令`conda install numpy`，成功   
![HTTPError](https://github.com/xfffrank/Solutions-to-Various-Technical-Problems/blob/master/problem_images/conda/conda_3.JPG?raw=true)

* `pip`命令无法使用  
#### 问题：
```
$ pip install -e .
Traceback (most recent call last):
  File "C:\Program Files\Anaconda3\Scripts\pip-script.py", line 11, in <module>
    load_entry_point('pip==9.0.1', 'console_scripts', 'pip')()
  File "C:\Program Files\Anaconda3\lib\site-packages\setuptools-36.2.6-py3.5.egg\pkg_resources\__init__.py", line 564, in load_entry_point
  File "C:\Program Files\Anaconda3\lib\site-packages\setuptools-36.2.6-py3.5.egg\pkg_resources\__init__.py", line 2662, in load_entry_point
  File "C:\Program Files\Anaconda3\lib\site-packages\setuptools-36.2.6-py3.5.egg\pkg_resources\__init__.py", line 2316, in load
  File "C:\Program Files\Anaconda3\lib\site-packages\setuptools-36.2.6-py3.5.egg\pkg_resources\__init__.py", line 2322, in resolve
  File "C:\Program Files\Anaconda3\lib\site-packages\pip\__init__.py", line 26, in <module>
    from pip.utils import get_installed_distributions, get_prog
  File "C:\Program Files\Anaconda3\lib\site-packages\pip\utils\__init__.py", line 27, in <module>
    from pip._vendor import pkg_resources
  File "C:\Program Files\Anaconda3\lib\site-packages\pip\_vendor\pkg_resources\__init__.py", line 70, in <module>
    from pip._vendor import appdirs
ImportError: cannot import name 'appdirs'
```
#### 解决方法： 
  在`C:\Program Files\Anaconda3\lib\site-packages\`目录下发现多个`pip`包文件夹，可能是之前重复安装了，移除体积最小的一个文件夹（即保留最新版），困扰多日的问题终于解决了。
```
$ pip

Usage:
  pip <command> [options]

Commands:
  install                     Install packages.
  download                    Download packages.
  uninstall                   Uninstall packages.
  freeze                      Output installed packages in requirements format.
  list                        List installed packages.
  show                        Show information about installed packages.
  check                       Verify installed packages have compatible dependencies.
  search                      Search PyPI for packages.
  wheel                       Build wheels from your requirements.
  hash                        Compute hashes of package archives.
  completion                  A helper command used for command completion.
  help                        Show help for commands.
```


#### `An HTTP error occurred when trying to retrieve this URL.`
解决方法：网络连接错误，检查是否挂了代理 VPN。
