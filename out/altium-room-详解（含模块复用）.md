---
title: 'Altium Room 详解（含模块复用）'
date: Thu, 08 Apr 2021 06:50:17 +0000
draft: false
tags: ['Altium']
---

以下部分内容来源于[Altium官网](https://www.altium.com/documentation/altium-designer/pcb-obj-roomroom-ad?version=18.1)，由本人理解后整理如下

说明
--

Altium中Room作为设计的一种基本元素，可以使用矩形或多边形形状放置于PCB的TOP或Bottom层。绘制Room包裹住元器件或线路时，则对应的元器件或线路将自动与该Room建立关联关系。或者可以通过选择元器件对元器件创建Room，此时选中的元器件将与此Room建立关联关系

从原理图导入网表到PCB时将默认会按原理图分页对单页的器件建立一个Room并建立关联，如不需要导入此Room可在工程选项中（右键工程选择Option）将其关闭

![](http://a1024.synology.me:222/images/blog2022/room1.png)

放置
--

使用菜单**Design » Rooms »**放置矩形（快捷键DMR）或多边形Room（快捷键DMM）

### 器件关联

当绘制Room时，Room将于完全落于Room区域内部的元器件自动建立关联，若绘制的Room区域没有完全落于Room区域内部的元器件将不创建任何关联，创建或修改关联通过Component Classes和规则管理器的Room Definition进行进一步操作

规则管理
----

Room的使用典型应用为器件的限制区域或布线的区域规则使用

### 器件限制

如下图规则要求Room Defintion 37这个器件组所有器件完全放置在Room Definition内部，如果有器件超出则会报错

![](http://a1024.synology.me:222/images/blog2022/ROOM2.png)

### 区域规则限制

如下图规则要求Room区域内部按照给定的线宽或间距要求设计，如果违背则会报错

*   **TouchesRoom(RoomName)** - 对象完全位于Room区域内部，或与Room边缘有接触的器件均可
*   **WithinRoom(RoomName)** -要求对象完全位于Room区域内部.

ROOM复制（模块复用）
------------

Room的典型应用还包括相同模块的复用（布局复制、布线复制、模块应用）该命令在多通道设计中使用时特别有用，因为它允许将一个通道中的布局和布线传播到所有其他通道。

**Design » Rooms » Copy Room Formats**（快捷键DMC）先选源会依次点击目标

![](http://a1024.synology.me:222/images/blog2022/ROOM3.gif)

通过channel offset（通道偏移）方式模块复用

通过snippets的方法，模块复用[**https://v.qq.com/x/page/l03370c373r.html**](https://v.qq.com/x/page/l03370c373r.html)  
通过copy room方式模块复用[**https://v.qq.com/x/page/r0337d1ajh0.html**](https://v.qq.com/x/page/r0337d1ajh0.html)

详解内容待补充