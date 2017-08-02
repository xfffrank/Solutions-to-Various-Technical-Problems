* How to deal with `CondaHTTPError`

#### 问题：
![HTTPError](https://github.com/xfffrank/Solutions-to-Various-Technical-Problems/blob/master/problem_images/conda/conda_5.JPG?raw=true)

![](https://github.com/xfffrank/Solutions-to-Various-Technical-Problems/blob/master/problem_images/conda/conda_2.JPG?raw=true)
#### 解决方法：
1.用`conda info`命令找到配置文件路径**config file**
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
2.修改.condarc 配置文件   
原先我的配置是这样的：   
![HTTPError](https://github.com/xfffrank/Solutions-to-Various-Technical-Problems/blob/master/problem_images/conda/conda_4.JPG?raw=true)   
改成这样即可   
![HTTPError](https://github.com/xfffrank/Solutions-to-Various-Technical-Problems/blob/master/problem_images/conda/conda_5.JPG?raw=true)    
3.测试运行命令`conda install numpy`，成功     
![HTTPError](https://github.com/xfffrank/Solutions-to-Various-Technical-Problems/blob/master/problem_images/conda/conda_3.JPG?raw=true)
