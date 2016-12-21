##Function Debuging##
使用keli软件对程序进行debug。
实验截图：

cnt的取值

![这里写图片描述](http://img.blog.csdn.net/20161221170742306?watermark/2/text/aHR0cDovL2Jsb2cuY3Nkbi5uZXQvZGFpZGFpaGVtYQ==/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70/gravity/SouthEast)

happybuff的取值

![这里写图片描述](http://img.blog.csdn.net/20161221172204921?watermark/2/text/aHR0cDovL2Jsb2cuY3Nkbi5uZXQvZGFpZGFpaGVtYQ==/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70/gravity/SouthEast)

结果说明：
	首先启用debug功能，然后在save程序段中的pop语句上设置断点，启动全速运行，从Init初始化中可以看出cnt的变量的地址为0x20000028，因此在memory窗口中查看该地址处的值来进行监控。
	![这里写图片描述](http://img.blog.csdn.net/20161221172712944?watermark/2/text/aHR0cDovL2Jsb2cuY3Nkbi5uZXQvZGFpZGFpaGVtYQ==/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70/gravity/SouthEast)
	发现cnt到0x00000014时就进已经达到最大，因此cnt变量的最终的值为0x00000014,同时也满足我们在程序中定义好的size值20。

再在happybuf处设置断点，观察最后happybuff的取值。
![这里写图片描述](http://img.blog.csdn.net/20161221172946889?watermark/2/text/aHR0cDovL2Jsb2cuY3Nkbi5uZXQvZGFpZGFpaGVtYQ==/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70/gravity/SouthEast)

可以从寄存器窗口中看到happybuf的地址为0x20000000。因此我们可以通过查询0x20000000观察到happybuf的值。