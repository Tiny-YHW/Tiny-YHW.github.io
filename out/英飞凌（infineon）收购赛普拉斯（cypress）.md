---
title: 'Edit->ZcopyPro 外扩內缩复制shape，支持多种元素'
date: Thu, 09 Apr 2020 05:38:23 +0000
draft: false
tags: ['TY-Skill']
---

功能说明
----

将设计中的Pins、Via、Clines、Lines、Shape、Void元素转换为外扩或内缩的Shape，并移动或复制到任意层。

基于设计原Zcopy的功能升级，升级功能支持多种元素的源目标支持、复制目标层多选等更多功能详见操作说明。

常用于结构设计中禁布的设计，模拟信号隔层参考处理的情况。

操作说明
----

1.  使用菜单或者命令启动后从Find面板选择操作对象
2.  从Option面板配置功能选项。
3.   主要配置功能包括要复制到的层的Class和Subclass（支持多选）、生成Shaped为静态或动态、复制（移动）到相同位置或复制（移动）其它位置、仅对高亮对象进行操作、删除源元素等，部分选项与软件自带功能重合功能一致。
4.  选择需要Zcopy的对象，支持多选和TempGroup
5.  选择目标位置（如之前勾选了Same location则无此步骤）

![](https://a1024.synology.me:222/images/blog2023/ZCopy.png)