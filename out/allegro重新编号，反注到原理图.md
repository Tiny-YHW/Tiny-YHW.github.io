---
title: 'Allegro重新编号，反注到原理图（位号反标）'
date: Mon, 01 Mar 2021 06:47:32 +0000
draft: false
tags: ['Allegro', '设计软件']
---

**器件附上Auto\_Rename属性**
----------------------

a、执行edit->property  
b、单击控制面板find栏，只勾选Comps复选框。

![](http://a1024.synology.me:222/images/blog2022/AllegroAuto_Rename01.jpg)

![](http://a1024.synology.me:222/images/blog2022/AllegroAuto_Rename02.jpg)

c、单击左键框选器件或右键快捷菜单中Temp Group命令给部分器件赋上Auto\_Rename属性，如图所示：

![](http://a1024.synology.me:222/images/blog2022/AllegroAuto_Rename03.jpg)

**参数设置**
--------

a、打开PCB文件，选择Logic->Auto Rename Refdes->Rename命令

![](http://a1024.synology.me:222/images/blog2022/AllegroAuto_Rename04.jpg)

b、选择rename all components，点击more

![](http://a1024.synology.me:222/images/blog2022/AllegroAuto_Rename05.jpg)

c、设置编号相关参数

![](http://a1024.synology.me:222/images/blog2022/AllegroAuto_Rename06.jpg)

设置的时候注意右边区域的设置，**一定要勾选preserve current prefixes项**。  
d、设置完后点击colse回到步骤b，点击rename，完成重新编号。（**注意保存\*.brd文件**）  
e、Auto Rename 完成后在PCB当前目录产生rename.log文件，其内容包括Rename前后发生的变化，如图所示：

![](http://a1024.synology.me:222/images/blog2022/AllegroAuto_Rename07.jpg)

**反标**
------

a、编辑rename.log文件，用txt文档打开，保存成Orcad Capture可以识别的文件格式\*.swp。  
b、打开原理图，选择Tools->Back Annotate命令。  
c、弹出如下对话框，设置如下，点击确认完成回注。

![](http://a1024.synology.me:222/images/blog2022/AllegroAuto_Rename08.jpg)

d、rename.swp为步骤a修改的文件。

![](http://a1024.synology.me:222/images/blog2022/AllegroAuto_Rename09.jpg)