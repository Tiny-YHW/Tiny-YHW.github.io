---
title: 'Altium在PCB Footprint（焊盘图形）中添加更多信息'
date: Tue, 08 Sep 2020 05:31:19 +0000
draft: false
tags: ['Altium']
---

添加自定义相对层
--------

PCB中可定义的层在Footprint（焊盘图形）中仍然实用[Altium 层知识](https://a1024.synology.me:1024/altium-%e5%b1%82%e7%9f%a5%e8%af%86/)

[Altium指定某层作为元器件布局边框](https://a1024.synology.me:1024/?p=1435)

定义布局边框（Courtyard）
-----------------

布局边框：代表元器件实体布局的占位区，在一些专业文档中一般称为Courtyard，对应Allegro软件的Place Bound层，在布局时一般不允许布局边框层图形交叉。布局边框一般按元器件实体（本体和引脚）占位外扩一定安全间距（0.25mm）设计

Altium中未指定布局边框层，默认按Footprint所有元素的占位的最长和最宽的占位矩形作为布局边框，这显然是不合理的，下述介绍如何在Footprint添加辅助层做布局边框图形

*   按L键打开View Configuration面板
*   在Layer区域右键选择Add Component Layer Pair
*   指定两个机械层（推荐使用M12、M17）作为布局边框层
*   在对应层绘制布局边框图形
*   在PCB中放置或更新到PCB

![](http://a1024.synology.me:222/images/blog2022/addcountyyard.gif)

![](http://a1024.synology.me:222/images/blog2022/addcountyyard2.gif)

https://v.qq.com/x/page/a3148ul7sed.html

增加装配边框和装配位号
-----------

添加装配层具体操作和增加布局边框类似不再赘述

在添加装配边框后，使用Tool->Add Designators for Assembly Drawing功能，将自动生成一个新的相对的层（Designator）代表装配位号

此功能对对当前使用的所有Pcblib生效

https://v.qq.com/x/page/t3148sc62gm.html