1. 切换回自带的`python2.7`版本    
```
~ Frank$ python2.7
Python 2.7.10 (default, Feb  7 2017, 00:08:15) 
[GCC 4.2.1 Compatible Apple LLVM 8.0.0 (clang-800.0.34)] on darwin
Type "help", "copyright", "credits" or "license" for more information.
>>> exit()
~ Frank$ python3.6
Python 3.6.2 |Anaconda custom (x86_64)| (default, Jul 20 2017, 13:14:59) 
[GCC 4.2.1 Compatible Apple LLVM 6.0 (clang-600.0.57)] on darwin
Type "help", "copyright", "credits" or "license" for more information.
>>> exit()
```

2. 执行`brew update`命令出现以下错误
```
xcrun: error: invalid active developer path (/Library/Developer/CommandLineTools), missing xcrun at: /Library/Developer/CommandLineTools/usr/bin/xcrun
```
**解决方法**：`xcode-select --install`

3. 系统降级步骤  
**Step #1** 备份系统，可以使用`time machine`工具  
**Step #2** 制作系统盘，需要一个 8 G以上容量的U盘，使用命令行。（自行搜索，只需一条命令）  
**Step #3** 重启，按`option`，选择U盘启动，进入后先用磁盘工具格式化当前 mac 系统（使用mac扩展日志格式），再回到主界面，选择安装系统，done✅。


