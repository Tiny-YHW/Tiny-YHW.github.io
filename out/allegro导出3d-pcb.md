---
title: 'Allegro导出3D PCB'
date: Fri, 02 Apr 2021 09:19:45 +0000
draft: false
tags: ['Allegro', '设计资料/文档']
---

Allegro支持多种导出3D的方法

step out
--------

使用此功能需要Allegro 16.6 QIR 4(HotFix16)及之后的版本

注意输出路径不能有中文，否则文件不能成功生成

此功能将从Allegro PCB中生成3D STEP，可以包含板框、线路、焊盘、通孔、元器件等，一般元器件外形按PlaceBound层shape的形状生成，高度为PACKAGE\_HEIGHT\_MAX的值，如果设计中元器件制定了3D模型，可以通过选择选项Parts withSTEP models将3D模型替换PlaceBound导出，如果没有指定PACKAGE\_HEIGHT\_MAX值，其将被指定为一个默认高度。

通过菜单 _File - Export - STEP_ 或 使用step out 命令 从Allegro PCB导出3D STEP文件

![](http://a1024.synology.me:222/images/blog2022/stepout.png)

*   Output file name 指定导出文件的文件名 按需设置
*   Output units 指定导出文件的单位 按需设置
*   STEP Protocol 指定导出文件的类型 见下文 按需设置
*   Parts with/without STEP models 当设计用的元器件有使用3D模型时是否导出此3D模型 按需设置
*   Mechanical holes 勾选代表导出机械孔 一般默认勾选
*   External copper (Traces, Pads, Shapes) 是否导出 ETCH/TOP ETCH/BOTTOM 层的 线 盘 铜（高版本可同时输出内层） 按需设置
*   Highlighted parts only 仅导出被选择高亮的器件 按需设置
*   Bare board 勾选代表输出裸板（不包含元器件） 按需设置
*   Compress outfile file(.zip) 输出文件被压缩为zip压缩包 按需设置

选择Export则在brd所在目录（除非你指定了其它位置）生成对应的文件

![](http://a1024.synology.me:222/images/blog2022/stepouttu.png)

### STEP Model 的套用与设定

STP是一种符合STEP国际标准（ISO 10303）的CAD文件格式，是一种独立于系统的产品模块的3D交换格式文档，因此获得了大多数工程软件的支持。

*   Creo Parametric（Pro/ENGINEER）
*   Solidworks
*   Autodesk Inventor
*   AutoCAD
*   U-G
*   Blender

STEP AP214 AP203均支持的实体、面的输入和输出。

他们的区别是：

*   AP203定义机械零件和组件的实体模型的几何，拓扑和配置管理数据。此文件类型并不管理颜色和图层。
*   AP214拥有AP203档包含的所有内容，但增加了颜色，图层，几何尺寸和容差以及设计意图。AP214被认为是AP203的延伸。
*   AP 203主要应用在航空航天和国防工业，AP 214主要应用在汽车工业中。
*   AP 242 为最新规范 , 并含括203与214 的所有功能。

idf\_out
--------

整体与step out类似

![](http://a1024.synology.me:222/images/blog2022/IDFOUT1.png)

通过菜单 _File - Export - IDF_ 或 使用idf\_out 命令 从Allegro PCB导出3D文件，导出的格式及文件如下

**File Name Type**

Board File

Library File

PTC

\*.emn

\*.emp

SDRC

\*.out

\*.pro

IDF

\*.bdf

\*.ldf

Default package height可以对未指定高度的元器件指定一个默认高度

Filter可以选择过滤指定对象被输出或不输出

选择Export则在brd所在目录（除非你指定了其它位置）生成对应的文件，此类文件有一定限制，部分3D软件不能浏览，目前已知Proe可以支持浏览，或者也可能只能用Proe打开

3D Canvas
---------

使用此功能需要Allegro 17.2及之后的版本，详见[链接](https://a1024.synology.me:1024/allegro-step-model%e5%9c%a8pcb-editor%e4%b8%8a%e7%9a%84%e5%ba%94%e7%94%a8/)