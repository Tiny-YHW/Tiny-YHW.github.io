---
title: 'Altium PCB 位号重排'
date: Thu, 13 May 2021 01:09:40 +0000
draft: false
tags: ['Altium']
---

按PCB
----

从菜单选择**Tools » Re-Annotate**命令，从此对话框选择对应选项

![](https://www.altium.com/documentation/sites/default/files/wiki_attachments/295914/Positional_Re-Annotate_AD18.png)

*   **编号方向**\-选择重新编号的顺序。可用的选项有：
    *   `1 By Ascending X Then Ascending Y`
    *   `2 By Ascending X Then Descending Y `
    *   `3 By Ascending Y Then Ascending X `
    *   `4 By Descending Y Then Ascending X `
    *   `5 Name from Position`

选择对应的选项上述窗口右侧图像将显示排列位号的顺序方式

*   **编号范围**\-指定器件或焊盘的重新编号范围。 
    *   器件
        *   顶面，然后底面 
        *   仅顶面
        *   仅底面 
        *   仅选择
    *   焊盘
        *   自由焊盘

*   **保护锁定器件**\-允许在重新编号并忽略被锁定的组件。
*   **比较阈值**\-更改重新便函方向的位置距离阈值。
*   **起始索引**\-指定重新编号的起始索引。例如，考虑具R1，R2，R3，R4的四个电阻器。用10的开始索引重新编号会更改为R10，R11，R12，R13（并根据定义的其他选项）。此选项仅适用于前四个编号方向选项。

点击ok后位号将按选项设置重排位号

使用菜单**Design » Update Schematics in xxx**命令，可将重排后的位号反标回原理图。

为位号加前缀或后缀
---------

Altium PCB在功能上并不支持此项操作，可通过灵活使用编辑PCB List的方法实现此项操作，步骤如下

*   选择需要加前缀或后缀的元器件，打开PCB List窗口
*   从PCB List窗口上端左侧处分别调整为Edit、Selected objects、Display Only Component
*   选择Designator位号右键选择Copy（不要更改PCB List中对象的排列方式）
*   将复制的数据粘贴到Excel中并操作做出一列带前缀或后缀且排序一致的数据，选择数据复制
*   回到Altium重新选择PCB List窗口Designator列或者最上方一个数据，右键选择粘贴，则元器件位号将更改为带前缀或后缀的位号

同时可以使用[Altium Smart Edit](https://a1024.synology.me:1024/altium-smart-edit/)的功能更加方便的完成此番操作

从原理图
----

待补充