### 1 代码收缩 
#### 1.1 使用自带功能    
```python
%%HTML
<button onclick="$('.input, .prompt, .output_stderr, .output_error, .output_result').toggle();">Toggle Code</button>
```

#### 1.2 下载插件   


### 2 添加目录   
#### 2.1 方法1
在cmd或者shell中安装jupyter_contrib_nbextensions 
```python
conda install -c conda-forge jupyter_contrib_nbextensions  
```
本地环境Windows Anaconda2-4.2.0 Python:2.7.12 发生报错    
在没有运行jupyer时安装，此时没有报错，但是启动jupyter notebook时，发生错误  

#### 2.2 方法2  
> 该方法配置成功，前提是不能运行jupyter notebook；
- 1 安装  
pip install jupyter_contrib_nbextensions   

- 2 配置(如果配置文件修改 jupyter需重启，重启之前执行该步骤 否则插件不起作用)  
jupyter contrib nbextension install --user(若是root用户 则--allow-root 或者忽略)  

- 3 启动jupyter notebook   
选择 Nbextensions
勾选 Table of Contents

### 3 常用moudles    
```python
# coding:utf8
import numpy as np
import pandas as pd
import matplotlib as plt

%matplotlib inline
``` 

### 4 link 跳转  
MarkDown模式下    
在一个MarkDown cell中
连接文字   
[Initialization](#Initialization)     

在另一个MarkDown的 cell中
<a id='Initialization'></a>  
##### tst   
![jupyter link跳转]()   

### 5 主题 和 pdf导出 
详见[jupyter 安装配置](https://www.cnblogs.com/McKean/p/6249112.html)  

5、安装Jupyter themes
https://github.com/dunovank/jupyter-themes
安装命令：
    pip install jupyterthemes
安装完后，直接cmd下，使用 jt -l 查看所有 themes，使用 jt -t grade3 -T -N 启用不同的themes。

重启jupyter 生效

6、输出PDF
 a、安装pandoc
https://github.com/jgm/pandoc/releases/tag/1.19.2.1

 b、安装MiKTeX
https://miktex.org/download

 c、安装 GNU make for windows
http://gnuwin32.sourceforge.net/packages/make.htm

 d、把上面安装好的软件路径，全部添加到环境变量里面   
 e、PDF支持中文
 C:\Python27\Lib\site-packages\nbconvert\templates\latex\article.tplx
 把 \documentclass[11pt]{article} 修改为  \documentclass[11pt]{ctexart} 即可！！！

Pandoc 支持中文
pandoc infile.md -o outfile.pdf --latex-engine=xelatex -V mainfont="SimSun"(已经过时)