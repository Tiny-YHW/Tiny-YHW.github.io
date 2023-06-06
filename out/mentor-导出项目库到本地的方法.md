---
title: 'Mentor 导出项目库到本地的方法'
date: Tue, 06 Jul 2021 08:57:23 +0000
draft: false
tags: ['Mentor']
---

本文内容由网友daoshuailx发布于此处

本文介绍的方法适用于用netlist创建的工程，用中心库的工程行不通

首先导出 Symbol
-----------

   1. 用DXDesigner 打开原理图。  
   2.按下图步骤操作

![](http://a1024.synology.me:222/images/blog2022/mentorlib1.jpg)

3.选择保存路径后，Symbol 就导出了，导出后的 Symbol，会按不同的文件夹保存。

导出 Cell
-------

 1.用 Xpedition layout 打开pcb文件,依次点击 Setup -> Libraries -> Library Services 弹出如下 对话框

![](http://a1024.synology.me:222/images/blog2022/mentorlib13.jpg)

2.分别在 Padstacks \\ Cells \\ Parts 选项卡 下面 选择 Export 和 Padstack data file \\ Cell data file \\ Part data file 来导出相应数据  
   以 导出 Padstacks 为例，导出步骤如下图所示

![](http://a1024.synology.me:222/images/blog2022/mentorlib12.jpg)

说明：以上导出的所有数据可以通过 Library Manager 中的 Library Services 导入，然后就可以在其它项目中使用了