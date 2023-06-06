---
title: 'TB-Skill Check->Footprint Elements'
date: Mon, 26 Sep 2022 09:09:00 +0000
draft: false
tags: ['TY-Skill']
---

[返回主菜单](https://a1024.synology.me:1024/?p=2217)
-----------------------------------------------

功能说明
----

如果板中器件与其对应的封装内相应层对象的数量存在不同则输出差异数量报告，如误删丝印层一脚标识，器件Placebound等

程序将分析每个元器件及其对应的原焊盘图形（封装库），在指定的几个绘图层的元素数是否有差异，如果有差异则有概率是设计时对器件进行了非预期的操作，这些对象将被报告出来，供再次核实是否均符合预期

指定的绘图层包括以下几个

*   "BOARD GEOMETRY/OUTLINE"
*   "BOARD GEOMETRY/SILKSCREEN\_TOP"
*   "BOARD GEOMETRY/SOLDERMASK\_TOP"
*   "PACKAGE GEOMETRY/SILKSCREEN\_TOP"
*   "PACKAGE GEOMETRY/SOLDERMASK\_TOP"
*   "PACKAGE GEOMETRY/PLACE\_BOUND\_TOP"
*   "PACKAGE GEOMETRY/PASTEMASK\_TOP"
*   "REF DES/SILKSCREEN\_TOP"
*   "REF DES/DISPLAY\_TOP"
*   "PACKAGE GEOMETRY/DISPLAY\_TOP"
*   "COMPONENT VALUE/DISPLAY\_TOP"
*   "COMPONENT VALUE/SILKSCREEN\_TOP"
*   以及以上各个TOP层对应的BOTTOM层

操作说明
----

直接从菜单命令运行即生成报告文件

![](https://a1024.synology.me:222/images/blog2022/Footprint%20Elements.jpg)

*   RefDef：元素数量有差异的器件位号
*   Location：元素数量有差异的器件位置，点击坐标可跳转到器件出
*   Package：元素数量有差异的器件对应的焊盘图形（封装库）名称
*   Layer：元素数量有差异的对象所在的层
*   Num-Original：器件对应层原来的元素数（即封装库中元素数）
*   Num-Current：器件对应层现在的元素数（即当前器件中元素数）

例如：上图中U1器件在"PACKAGE GEOMETRY/SILKSCREEN\_BOTTOM"层原来有60个元素（F896这个封装"PACKAGE GEOMETRY/SILKSCREEN\_BOTTOM"层有60个元素），现在只有0个元素，这些元素都没有了

例如：上图中U15器件在"PACKAGE GEOMETRY/SILKSCREEN\_TOP"层原来有16个元素（QFN40这个封装"PACKAGE GEOMETRY/SILKSCREEN\_BOTTOM"层有16个元素），现在只有15个元素，可能是有一个元素被删除了

注意事项
----

本程序仅作为检查检查封装内元素是否正确的一个侧面的方法，不能完全作为核查封装内元素的正确性的检查依据。

Tips：如果一个Lines或Clines由多个线段组成，本程序则认为每一个线宽（没拐弯的）都是一个元素

[返回主菜单](https://a1024.synology.me:1024/?p=2217)
-----------------------------------------------