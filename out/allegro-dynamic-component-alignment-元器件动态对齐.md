---
title: 'Allegro Dynamic Component Alignment 元器件动态对齐'
date: Mon, 17 Oct 2022 09:03:17 +0000
draft: false
tags: ['Allegro']
---

[视频地址](https://www.ixigua.com/7159868099616113188)

![](https://a1024.synology.me:222/images/blog2022/Dynamic%20Component%20Alignment1.png)

功能版本号17.2-2016 QIR4 (Hotfix25)引入

Allegro可以让元器件被移动时，使用吸附准线让元器件对齐，功能类似于Microsoft PowerPoint等程序。设计人员可以实时执行放置和对齐两个元器件，从而提高效率。

_在_move命令时，可以为元器件原点、place bound边界线、飞线作为引导线参考点。您还可以为指示可用捕捉点的线条选择颜色。此设置位于“_Color_”对话框的_“Display”_中。

![](https://a1024.synology.me:222/images/blog2022/Dynamic%20Component%20Alignment2.png)

在移动命令是可以使用下面的命令定义快捷键开启或关闭动态对齐元器件功能

```
pop dyn_option_select 'Options@:@Dynamic Alignment@:@Enable'
```