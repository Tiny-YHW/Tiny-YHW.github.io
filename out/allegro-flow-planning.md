---
title: 'Allegro Flow Planning将设计意图表达在设计中'
date: Mon, 01 Jun 2020 08:28:16 +0000
draft: false
tags: ['Allegro', '设计技巧']
---

Allegro Flow Planning 于高速PCB 设计流程中能够大幅度的缩短评估布线空间及走线方式所花费的时间成本，并且提升设计效率。现在，搭配Allegro PCB Symphony Team Design Option 线上协同作业功能，能将Flow Planning 所规划之布线走势藉由线上多人合作来加速PCB 设计流程，快速完成PCB 设计。

以往工程师在评估PCB 布线空间以及规划走线趋势时，往往需要先考量信号品质并依照零件布排空间以及过孔小心翼翼地试着拉线，一次又一次地重复步骤，直到布线空间及走线规划呈现最合理的状态，方能进行实际走线。而在高复杂度及高密度的PCB 设计情况下，以上步骤犹如穿针引线，见缝插针，让人绞尽脑汁仍不得其所。

现在，使用Flow Planning 功能预先建立Flow Bundle，一次将群组信号呈现整束Bundle 图形来进行走线规划，并将Bundle 图形依照实际走线规范显示所需空间，快速地评估布线空间及走势。

**使用下述功能需要在Allegro中软件开启时启用Design Planing或Full GRE产品选项**

切换Flow Planning 模式
------------------

切换App Mode为Flow Planning方法有很多种选择适合自己的

*   idle（无命令）时右键菜单App Mode子选项
*   菜单栏Set up -> App Mode子选项
*   Toolbar（右下角）中的快捷选项
*   快捷图标中的IFP

![](http://a1024.synology.me:222/images/blog2022/app%20mode.png)

建立Flow Bundle
-------------

Bundle可翻译为线束，在这里理解为飞线的集合，可以通过如下三种方式创建，是一种属于Groups的对象。自动在Plan（Class）层生成

### **自动创建Bundle**

从菜单栏_FlowPlan- Auto Bundle_或右键菜单选项_Auto Bundle_ _All_程序可根据当前器件飞线的连接关系自动创建**Bundle**（并不实用，不插图了）

### **设计中手动创建Bundle**

1.  在Find中选择Ratsnets
2.  在设计中选择目标对象
3.  从菜单栏_FlowPlan- Creat Bundle_或右键菜单选项__Creat Bundle__
4.  完成创建

### **规则中创建Bundle**

打开规则管理器选择Properties _\-_ Nets - Ratsnest Bundle Properties项，从清单中选择网络创建（可从PCB或原理图中选择网络进行交互）

![](http://a1024.synology.me:222/images/blog2022/creatbun.png)

编辑**Bundle**
------------

Find中选择Groups，层开关打开Plan/All层（默认生成到此层），通过点击创建好的**Bundle**可对其进行拆分、合并、删除操作

*   Split Bundle：把一个Bundle分成多个Bundle。
*   Edit Bundle：把Bundle之外的飞线或Bundle加入进来。
*   Delete Bundle：删除Bundle，变回飞线的方式。

![](http://a1024.synology.me:222/images/blog2022/%E7%BC%96%E8%BE%91boun.gif)

**Flow的规划**
-----------

当Flow Bundle 产生出来之后，我们便可藉由针对Flow Bundle 相对宽度的设定调整来做走线空间的评估。

菜单Setup > Design Parameter Editor > Flow Planning 页面可对部分参数进行调整，如**Bundle**线的宽度（默认50%，建议100%，宽度与规则设置的线宽和间距成正相关）

### **定义Flow的走线路径**

选中Bundle，右键选择Create Flow，依次点击预布线路径上的点，完成走线路径的规划（按需设计，非必要流程）

选中Bundle，右键选择Flow Edit可以对**Flow**进行更多交互式调整或重置

### **走线**限制

选中Bundle，右键选择Bundle Properties可对该组Bundle布线的情况进行限制，情况包括允许的所在层，是否要求同层，绕线形式（如有定义了match group），是否按照规划路径布线等

更改后允许的所在层后，该组Bundle所在层会由Plan/All变为你要求的允许层

完成布线
----

根据创建好的**Flow**可以手动完成布线，或通过allegro提供的自动布线功能完成自动布线

选中Bundle右键选择

Auto Connect

[Allegro (AIBT)Auto Interactive Break Out Technology自动交互布线技术](https://a1024.synology.me:1024/allegro-aibtauto-interactive-break-out-technology%e8%87%aa%e5%8a%a8%e4%ba%a4%e4%ba%92%e5%b8%83%e7%ba%bf%e6%8a%80%e6%9c%af/)