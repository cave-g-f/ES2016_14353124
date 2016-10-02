#DOL开发环境配置
##1.DOL框架概述
>The distributed operation layer (DOL) is a framework that enables the (semi-) automatic mapping of applications onto the multiprocessor SHAPES architecture platform. The DOL consists of basically three parts:
* DOL Application Programming Interface
* DOL Functional Simulation
* DOL Mapping Optimization


##2.DOL配置与安装
**安装一些必要的环境**  

$ sudo apt-get update  
$ sudo apt-get install ant  
$ sudo apt-get install openjdk-7-jdk  
$ sudo apt-get install unzip

**下载文件**

$ sudo wget http://www.accellera.org/images/downloads/standards/systemc/systemc-2.3.1.tgz  
$ sudo wget http://www.tik.ee.ethz.ch/~shapes/downloads/dol_ethz.zip

**解压文件**  

新建dol的文件夹   
$	mkdir dol  
将dolethz.zip解压到 dol文件夹中  
$	unzip dol_ethz.zip -d dol  
解压systemc  
$	tar -zxvf systemc-2.3.1.tgz  

**编译systemc**

解压后进入systemc-2.3.1的目录下  
$	cd systemc-2.3.1  
新建一个临时文件夹objdir  
$	mkdir objdir  
进入该文件夹objdir  
$	cd objdir  
运行configure(能根据系统的环境设置一下参数，用于编译)  
$	../configure CXX=g++ --disable-async-updates    
$ sudo make install  
记录当前的工作路径   
$	pwd  

运行后效果图：  
![](http://i1.piimg.com/4851/4ecaac35f6ce1151.png)         

**编译DOL**  
进入刚刚dol的文件夹  
$	cd ../dol  
修改build_zip.xml文件  
找到下面这段话，就是说上面编译的systemc位置在哪里  
`<property name="systemc.inc" value="YYY/include"/>`  
`<property name="systemc.lib" value="YYY/lib-linux/libsystemc.a"/>`  
把YYY改成上页pwd的结果  
$	ant -f build_zip.xml all  
若成功会显示build successful  

运行后效果图：  
![ima](http://i1.piimg.com/4851/dcd99802d943681a.png)  

**运行第一个例子**   
$ cd build/bin/main   
然后运行第一个例子   
$ ant -f runexample.xml -Dnumber=1   
运行后效果图：  
![im](http://i1.piimg.com/4851/dcd99802d943681a.png)  

##3.实验感想##
本次实验主要是配置了dol的环境，配置过程中并没有遇到什么太大的苦难。这次接触了一种全新的文本编辑方式，markdown语言，初次使用这种
方式来编写文档感觉还是很方便的，里面各种格式可以很方便的帮助我们排版。







     
      
      
      
      










