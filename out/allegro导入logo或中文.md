---
title: 'Allegro导入Logo或中文'
date: Mon, 29 Mar 2021 08:03:57 +0000
draft: false
tags: ['Allegro']
---

由于Allegro软件的种种限制，在PCB中直接添加图像文件或者中文字符是十分不友好的，本文提供几种方式导入Logo图像或者中文字符

导入图片和中文思路类似，都是通过自己制作包含中文文本的文件后以图像的方式导入设计

中文字符的图片可以通过直接在画图工具中写入文本另存为图片或者在Word等文本工具写好字符截图另存的方式获得

将图片用画图工具打开另存为[单色位图](https://www.iiiff.com/article/318042)的bpm文件，因为我们设计图纸里面的图形信息只有有和无没有颜色或透明度的概念所以单色位图才是有效文件

Rata工具
------

1、解压下载后的[文件](https://layouto.lanzous.com/iqsrxnfuuha)，双击RATA.exe运行软件  
2、选择左下角的1-Select BMP file，导入单色位图文件

![](http://a1024.synology.me:222/images/blog2022/logo1.jpg)

3、选择设定，2-Settings；  
      Lines Thick：默认线宽，结合PCB制板工艺，丝印最小线宽一般是4mil；  
      Scale：1 Pixel is \[\] Mils：一个像素是多少mil的比例；默认  
      Pick Color：颜色（需要部分颜色一般为黑色），先点击颜色后在图片上拾取

4、点击3-Make out.plt，生产out.plt文件；默认在软件所在当前文件夹

5、点击4-Bye，结束转换。

6、启动allegro打开需要导入的设计  
7、选择命令File/Import/IPF,选择out.plt文件，放到合适的位置如图

![](http://a1024.synology.me:222/images/blog2022/logo2.png)

8、如果大小导入对象的大小不合适需要重新制作图形文件或者修改上述3步骤的Scale值调整图形大小，或使用Allegro的Crete  Detail命令调整对象大小

软件自带功能
------

Allegro16.6d额某个补丁及之后的版本增加了对导入logo的支持，在创建Sym的时可使用此功能（brd是没有的），可通过创建sym后放入或者在sym中使用sub-drawing导入brd

![](http://a1024.synology.me:222/images/blog2022/logo3.png)

需注意通过此功能导入的logo只有图形的线条轮廓（空心的），可以继续使用Crete  Detail功能将其转换为实心图形

Skill方式
-------

[罗老师的skill](http://www.allegro-skill.com/forum.php?mod=viewthread&tid=2660) 文件已不提供公开下载，联系我活着罗老师索取文件

[电路精灵](http://www.jiloukeji.com/index.html) 有直接放入中文功能，无需自己做文本字符的图像