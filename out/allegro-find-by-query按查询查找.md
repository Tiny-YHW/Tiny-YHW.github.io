---
title: 'Allegro 17.2 Find By Query按查询查找'
date: Wed, 19 Oct 2022 01:40:53 +0000
draft: false
tags: ['Allegro']
---

需要17.2-2016 QIR1 (Hotfix4)及之后版本

位于“Find”窗口中的“Find By Query”功能可以让你轻松地在画布中找到指定的设计元素，查询语句支持被保存并在新设计中重复使用，所有编辑命令均支持与查询一起使用。

视频演示地址：[片段1](https://www.ixigua.com/7159482072200184356)、[片段2](https://www.ixigua.com/7159484170048274974)、[片段3](https://www.ixigua.com/7159486131522929189)

抖音视频地址：[片段1](https://v.douyin.com/M4nMsjQ/)、[片段2](https://v.douyin.com/M4nybWJ/)、[片段3](https://v.douyin.com/M4nV4sU/)

配置选项卡
-----

配置创建查询时可用的设计元素/对象。在下图中，所有对象都在“Configure”选项卡中选中，这意味着它们在“Objects”选项卡中都是可见和可选择的。如果你有需要可以通过去掉某些勾选项，使其不可见且不可被选择。

![](https://a1024.synology.me:222/images/blog2022/algPN-353.gif)

按查询查找
-----

通过将元素从“Objects”选项卡移动到“Fields”窗格来创建查询。随着对象被添加到“Fields”窗格，它们会展开以显示它们独有的属性。然后通过将属性从“Fields_”_窗格移动到“Filters”窗格来创建和优化查询。随着项目被添加到Filters窗格，设计中与查询匹配的项目将显示在Matching Objects窗格中。

可以通过以下三种方式将元素从一个窗格添加到另一个窗格：

*   用鼠标双击一个元素
*   用鼠标从一个窗格拖放到另一个窗格
*   选择对象后，使用左/右箭头按钮

从“Objects”选项卡选择你需要查询的一个或多个元素种类，将这些元素种类添加到“Fields_”_窗格，让其作为可以用作查询的一部分

添加到“Fields_”_窗格中的所有元素种类，可以打开对象左侧的小三角形，查看或隐藏可用属性。

![](https://a1024.synology.me:222/images/blog2022/algPN-354.gif)

从“Fields_”_窗格选择你需要使用的元素种类或者需要的指定属性，将其添加到“Filters”窗格，用于创建查询

在添加到添加到“Filters”窗格之前选择“AND”或“OR”按钮将会创建不同的表达式，AND用于取交集，OR用于取并集

![](https://a1024.synology.me:222/images/blog2022/algPN-356.gif)

添加Filters时，与其匹配的对象将会被添加到Matching Objects窗格中。

![](https://a1024.synology.me:222/images/blog2022/algPN-359.gif)

如果你需要指定属性值的元素，可以通过双击Filters窗格中的属性行，从Filters Setting窗格过滤指定属性值，过滤器支持通配符（如下图所示，带有将查询所有封装名包含soic的Symbols”）。

![](https://a1024.synology.me:222/images/blog2022/algPN-362.gif)

从Matching Objects通过选择对应的行来选择你需要操作的对象，通过按住Ctrl可以对对象进行加选或减选，通过按住Shift或使用鼠标拖动对对象进行连续选择，通过单击表格左上空白块或键盘Ctrl+A或在表格右击选择_Select All_，可以选择所有符合表达式的对象

然后就可以对这些选择的对象执行你需要的操作命令了

Tips:只有在Find面板中勾选的对象类型可以被选择到，如果有符合表达式但为在Find面板中勾选的对象cammand中将提示：\*\*\* selection is not appropriate at this time

保存和调用表达式
--------

![](https://a1024.synology.me:222/images/blog2022/findbyquery1.png)

创建好一个表达式后点击Save Query按钮可以将表达式以文件的形式进行存储，文件对应的后缀为qfnd，

TIPS:所有Allegro中需要调用文件存储的内容时均需要指定路径配置到才能被调用到，qfnd文件存储路径的配置变量与导dxf识别的cnv文件为同一个变量，变量值在User Preferences Eidtor中Paths->Library->miscpath进行设置

command栏输入echo $miscpath可以查看已经配置的可被调用的路径

Load Query选项可以选择以文件的形式进行存储好的表达式，对其进行再次调用

从Find窗口勾选By Saved Query,也可以在下拉菜单中选择存储好的表达式，PCB画布选择需要应用此表达式的对象范围，则该区域内符合表达式的对象将被选择

![](https://a1024.synology.me:222/images/blog2022/findbyquery2.png)