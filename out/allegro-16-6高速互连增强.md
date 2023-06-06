---
title: 'Allegro 16.6高速互连增强'
date: Thu, 04 Jun 2020 02:00:35 +0000
draft: false
tags: ['Allegro', '设计软件']
---

使用下述功能需在软件启动时，启用High-Speed产品选项

Differential Pair Return Path Vias 差分回流过孔
-----------------------------------------

回流过孔，也称为_接地参考过孔，_提供回流路径，以最大程度地减少过孔过渡期间PCB和封装互连中的信号衰减。电流必须始终返回其源极，因此，当信号使用通孔从一层转移到另一层时，返回电流将沿着阻抗最小的路径返回到源极。

使用方法：在Add connect命令时右键选择菜单Return Path Vias (Prototype)选择Setup设置回流过孔的参数包括，Setup标签页的过孔选择、网络选择和Spacing标签页的对应回流过孔类型的间距位置等参数，应用后再打孔时回流过孔会同时生成

![](http://a1024.synology.me:222/images/blog2022/highspped1.png)

Fiber Weave Effect - Zig-Zag Routing 锯齿形布线
------------------------------------------

可将平行布线转换为锯齿形（斜角）路线。通过此种布线方式，可以最大程度地减少PCB玻璃纤维编织对高速信号路由的影响。此功能同时可用于差分对和单端网络。可以指定所需的曲折角度和最大线段长度，以及用于转换完整线段或定义起点和终点的选项。

![](http://a1024.synology.me:222/images/blog2022/highspped2.png)

使用方法：见动图

![](http://a1024.synology.me:222/images/blog2022/highspeed3.gif)

[等长线处理AiDT AiPT **Timevision**](https://a1024.synology.me:1024/?p=1797)
-----------------------------------------------------------------------

Remove Tuning移除等长绕线
-------------------

将进行过Delay tune(等长绕线)的Cline，移除绕线的蛇形部分恢复直连，通过菜单中Route - Remove Tuning访问