---
title: 'Allegro中放置射频器件（天线，蚊香线圈等）'
date: Thu, 02 Dec 2021 06:27:18 +0000
draft: false
tags: ['Allegro']
---

射频器件
----

Distributed Components 分布式器件 常用于射频设计和微波领域，平时可能我们能比较常见的就是天线和蚊香线圈这种

![](https://a1024.synology.me:222/images/blog2022/5ab5c9ea15ce36d3ad2b57473af33a87e950b19e.jpg)

![](https://a1024.synology.me:222/images/blog2022/src%3Dhttp___file2.dzsc.com_data_18_10_27_9207_135508168.jpg%26refer%3Dhttp___file2.dzsc.jpg)

天线这种学名可能是叫Meander Trace，更多知识可以参考[2.4G天线在PCB板上的设计资料](https://blog.csdn.net/qq_42792038/article/details/82024555)

![](https://a1024.synology.me:222/images/blog2022/pcb_spiral_inductor.jpg)

![](https://a1024.synology.me:222/images/blog2022/Coil8-9.png)

蚊香线圈这种学名可能是叫MDS Microstrip Round（Rectangular） Spiral Inductor

还有更多的此类图形可以统称为射频器件，更多此类器件可以参考[这个网站](https://edadocs.software.keysight.com/pages/viewpage.action?pageId=5693357)或者[这个资料](https://layouto.lanzouo.com/irqfux4wnmj)

Allegro中添加射频器件
--------------

打开Allegro软件启用Analog/RF产品选项

![](https://a1024.synology.me:222/images/blog2022/Snipaste_2021-12-02_13-55-26.png)

进入菜单RF-PCB->Add Component从Option面板选择对应的器件类型

![](https://a1024.synology.me:222/images/blog2022/Snipaste_2021-12-02_13-58-26.png)

选择不同类型的元器件鼠标放回PCB绘图区可以预览图形形状

蚊香线圈位于Miscrostrip类型如下图几种类型

![](https://a1024.synology.me:222/images/blog2022/Snipaste_2021-12-02_14-12-19.png)

天线位于Miscellaneous类型如下图几种类型

![](https://a1024.synology.me:222/images/blog2022/Snipaste_2021-12-02_14-14-58.png)

将APP Mode切换到RFeidt，选择对应的射频器件，右键选择Show/Hide GUI可以调出对应射频器件的可调参数，输入合适的参数，射频器件创建完成

![](https://a1024.synology.me:222/images/blog2022/Snipaste_2021-12-02_14-18-35.png)

关于更多其它的器件类型如果感兴趣自己可以逐个查看，本文不做介绍