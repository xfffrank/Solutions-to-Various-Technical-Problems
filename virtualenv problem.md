
#### 1.如何用virtualenv工具创建Python2.7环境

` virtualenv --python=3.4 myenv or virtualenv --python=2.7 myenv `

#### 2.激活和关闭环境

`source ../Scripts/activate`

`source ../Scripts/deactivate`

#### 3.`ERROR: virtualenv is not compatible with this system or executable`  
解决方法：  
1. `pip uninstall virtualenv`
2. `conda install virtualenv`
