---
title: 'Allegro 新的绘图能力'
date: Thu, 04 Jun 2020 03:26:10 +0000
draft: false
tags: ['Allegro', '设计技巧']
---

Allegro新增一系列绘图能力功能，大大增强了在机械结构图的设计上的编辑处理能力，对应的命令可在菜单Manufacture > Drafting的子菜单访问，也可以在_General Edit _App模式时，鼠标指向对应的对象时通过右键访问Drafting

![](http://a1024.synology.me:222/images/blog2022/draft1.png)

这几个命令都相对比较简单，不做详细说明了，自己点点功能就玩明白了

Extend Segments 扩展并闭合线段
-----------------------

![](http://a1024.synology.me:222/images/blog2022/draft2.png)

Trim Segments修建线段
-----------------

![](http://a1024.synology.me:222/images/blog2022/draft3.png)

Delete by Line切割线
-----------------

![](http://a1024.synology.me:222/images/blog2022/draft4.png)

Delete by Rectangle矩形切割
-----------------------

![](http://a1024.synology.me:222/images/blog2022/draft5.png)

Offset Copy 偏移复制
----------------

![](http://a1024.synology.me:222/images/blog2022/draft6.png)

Offset Move 偏移移动
----------------

同上，只是不保留原对象

Add Perpendicular Line 添加垂直线
----------------------------

Add Parallel Line 添加平行线
-----------------------

**Add Tangent Line** 添加切线
-------------------------

**Relative Copy** 图形镜像复制（支持旋转）
------------------------------

**Relative Move** 图形镜像移动（支持旋转）
------------------------------

**Connection Lines** 创建连接线
--------------------------

在两条已有的线的基础上创建过渡连接线。选择命令后，依次选择需要连接的两条线，然后根据给出虚线提示选择目标线作为结果

Add Arc Prototype 添加圆弧
----------------------

提供更多种绘制圆弧的方式，从菜单_Add_ - _Unsupported Prototypes_ - Arc进入命令。

![](http://a1024.synology.me:222/images/blog2022/draft7.png)