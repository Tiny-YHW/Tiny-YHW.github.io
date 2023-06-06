---
title: 'Altium Smart Component Placement 智能元器件放置'
date: Fri, 11 Jun 2021 02:32:48 +0000
draft: false
tags: ['Altium']
---

Altium 16及之后的版本开始支持元器件智能放置功能，主要包含一个元器件间避让或推挤以及一个元器件对齐动态捕捉的功能

动态对齐
----

器件放置移动器件时允许用户通过按住热键Ctrl和Shift激活对齐功能，当元器件与周围器件有对齐关系时，会出现绿色指示线，此时放置器件其与周边元器件对齐。

按住Ctrl键时为器件边界相关的对象引导对齐

按住Shift键时为元器件焊盘对象引导对齐

使用**Shift**和**Ctrl**将元件按相邻元件或相邻元件的焊盘对齐。

放置模式
----

当移动器件放置时可以通过按热键R切换元器件的放置方式为以下几种模式

*   忽略障碍：元器件按指定位置放置，不避让其它器件
*   推挤障碍：元器件按指定位置放置，如果有其它器件与其干涉，将推荐其它器件（除被锁定的器件外）
*   避让障碍：元器件按指定位置放置时如果与其它器件与它冲突，将会避让此器件被推挤到合适的位置

使用**R**热键在放置模式之间循环。请注意R6已锁定，无法在推障碍模式下移动。

交换器件
----

选择一对器件右键选择Component Actions » Swap Components可以很方便的交互两个器件的位置

元器件对齐
-----

此内容不是AD16的新功能，各版本都有，本处作为相关内容编写在这里

选择多个目标器件后通过鼠标右键选择Align选择相应功能，也可通过键盘按键A直接访问，或直接使用对应的快捷键。

![](http://a1024.synology.me:222/images/blog2022/AltiumAlign.png)

*   Align 对齐选项
*   Align Left 左侧对齐
*   Align Right 右侧对齐
*   Align Left (Maintain Spacing) 左侧等距对齐
*   Align Right (Maintain Spacing) 右侧等距对齐
*   Align Horizontal Centers 水平（垂直方向）居中对齐
*   Distribute Horizontally 水平方向等距分布
*   Increase Horizontal Spacing 水平间距增加
*   Decrease Horizontal Spacing 水平间距减少
*   Align Top 上侧对齐
*   Align Bottom 下侧对齐
*   Align Top (Maintain Spacing) 上侧等距对齐
*   Align Bottom (Maintain Spacing) 下侧等距对齐
*   Align Vertical Centers 垂直（水平方向）居中对齐
*   Distribute Vertically 处置方向等距分布
*   Increase Vertical Spacing 垂直间距增加
*   Decrease Vertical Spacing 垂直间距减少
*   Align to Grid 将选择器件的圆心置于当前的格点上
*   Move All Component Origins to Grid 将所有器件的圆心置于当前的格点上