---
title: 'Add->RKO By Diff Vias+Pins'
date: Wed, 01 Dec 2021 09:32:47 +0000
draft: false
tags: ['TY-Skill']
---

[返回主菜单](https://a1024.synology.me:1024/?p=2217)
-----------------------------------------------

![](https://a1024.synology.me:222/images/blog2022/%E9%AB%98%E9%80%9F%E5%B7%AE%E5%88%86%E9%93%BE%E8%B7%AF%E4%BC%98%E5%8C%96%E9%98%BB%E6%8A%97%E4%BC%98%E5%8C%96%20%E6%8E%8F%E7%A9%BA%E9%93%9C%E7%9A%AE%E5%A4%84%E7%90%86.jpg)

功能说明
----

针对高速差分线，对选择的网络对象增加ShapeKeepout

增加的禁布包含VIAS\_ALLOWED和ROUTES\_ALLOWED属性，可有效减少DRC误报，如果确认不允许Vias或Routes需要从属性面板将其属性删除

这个功能已改善升级，支持用户框选多个目标对象，程序自动识别差分对，直接对差分对添加ShapeKeepout

启动命令:creatediffpairkeepout

操作说明见视频演示
---------

[抖音视频](https://v.douyin.com/FTxora2/)

手动操作说明
------

1.  从菜单或启动命令启动此功能
2.  切换Form到第二个标签页Manual Create
3.  从Find面板选择需要被过滤的对象类型Vias或Pins
4.  从弹窗选择ShapeKeepout的目标层和外扩值后点击Create
5.  从PCB中框选两个Pins或Vias（多选或少选均无效）ShapeKeepout即添加成功
6.  如果需要重新选择目标层或更改外扩值，需重新启用一些本命令，暂未支持实时修改参数

对选择的Vias添加ShapeKeepout
----------------------

![](https://a1024.synology.me:222/images/blog2022/creatediffpairkeepoutvia.gif)

对选择的Pins添加ShapeKeepout
----------------------

![](https://a1024.synology.me:222/images/blog2022/creatediffpairkeepoutpin.gif)

添加ShapeKeepout的属性
-----------------

![](https://a1024.synology.me:222/images/blog2022/creatediffpairkeepoutshuxing.gif)

[返回主菜单](https://a1024.synology.me:1024/?p=2217)
-----------------------------------------------