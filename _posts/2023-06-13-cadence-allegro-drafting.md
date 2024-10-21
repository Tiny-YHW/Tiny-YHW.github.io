---
layout: post
title: Allegro Drafting 新的绘图能力
categories: Allegro
description: 
date: 2023-06-13
---


Allegro新增一系列绘图能力功能，大大增强了在机械结构图的设计上的编辑处理能力

此功能在Allegro16.6的补丁版本新增，在各个补丁号中多次进行更新，本文描述功能基于QIR 8(HotFix38)进行介绍，在之前的版本可能缺少部分功能或需要从菜单*Manufacture - Drafting*处访问

对应的命令可在菜单Manufacture > Drafting的子菜单访问，也可以在*General Edit App*模式时，鼠标指向对应的对象时通过右键访问Drafting

![](https://tiny-y.asia/images/blog/2022/draft1.png)

这几个命令都相对比较简单，不做详细说明了，自己点点功能就玩明白了

### Extend Segments 扩展并闭合线段

可以将线段或圆弧段延伸到交点，使用命令再分别选择两个线段

![](https://tiny-y.asia/images/blog/2022/draft2.png)

### Trim Segments修建线段

以删除超出指定交点的线段和圆弧段的部分，使用命令再分别选择两个线段，第一个线段是要修建的线段

![](https://tiny-y.asia/images/blog/2022/draft3.png)

### Delete by Line切割线

删除定义剖切线一侧的线段或圆弧段，使用命令再点击两点画一条剖切线，系统提示选择要移除的一侧，点击确认执行

![](https://tiny-y.asia/images/blog/2022/draft4.png)

### Delete by Rectangle矩形切割

删除位于用户指定的剪切矩形内的线、圆弧、线段和过孔部分，使用命令再点击两点定义一个矩形，则矩形内的对象被切割掉

![](https://tiny-y.asia/images/blog/2022/draft5.png)

### Offset Copy 偏移复制

此命令允许您制作多个从原始对象偏移特定X和/或Y值的各种对象的副本。

![](https://tiny-y.asia/images/blog/2022/draft6.png)

### Offset Move 偏移移动

同上，只是不保留原对象

### Add Perpendicular Line 添加垂直线

### Add Parallel Line 添加平行线

### Add Tangent Line 添加切线

### Relative Copy 图形镜像复制（支持旋转）

### Relative Move 图形镜像移动（支持旋转）

### Connection Lines 创建连接线

在两条已有的线的基础上创建过渡连接线。选择命令后，依次选择需要连接的两条线，然后根据给出虚线提示选择目标线作为结果

### Add Arc Prototype 添加圆弧

提供更多种绘制圆弧的方式，从菜单*Add-Unsupported Prototypes- Arc*进入命令。

![](https://tiny-y.asia/images/blog/2022/draft7.png)