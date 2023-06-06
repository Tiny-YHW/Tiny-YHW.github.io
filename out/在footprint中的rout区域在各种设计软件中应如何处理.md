---
title: '在Footprint中的Rout区域在各种设计软件中应如何处理'
date: Thu, 02 Apr 2020 06:34:55 +0000
draft: false
tags: ['Footprint(焊盘图形)']
---

铣切图形 与实体铣切区等大

ROUT标识  字号与脚标号大小一致

KeepOut  比实体单边外扩 10mil（0.25mm）

Library Expert
--------------

铣切图形：放在装配层TOP，线的中心距与实体等大，注意如果使用矩形工具长宽需要多加一个线宽，LE中不能做倒角，转到设计软件需要再次编辑倒角。

KeepOut：比实体单边外扩 10mil（0.25mm）

Altium Designer
---------------

铣切图形：Mechanical1和Drill Drawing层

ROUT标识：Mechanical1和Drill Drawing层

*   调整装配层铣切图形与实体等大，包括倒角
*   将调整后的图形分别复制到Mechanical1和Drill Drawing层
*   在Mechanical1和Drill Drawing层铣切图形区域增加ROUT文本标识

Cadence Allegro
---------------

铣切图形：BG/Outline

ROUT标识：BG/Outline

*   调整装配层铣切图形与实体等大，包括倒角
*   将调整后的图形复制到BG/Outline层
*   在BG/Outline层铣切图形区域增加ROUT文本标识

Mentor Pads
-----------

铣切图形：Drill Drawing层

ROUT标识：Drill Drawing层和顶层丝印层

*   调整装配层铣切图形与实体等大，包括倒角
*   将调整后的图形复制到Drill Drawing层
*   在Drill Drawing层和顶层丝印层铣切图形区域增加ROUT文本标识

Mentor Xpedition
----------------

铣切图形：Contour层

ROUT标识：Text/Silkscreen Mount层

*   在PadEditor中Holes标签新建一个直径0.12mm的非金属化Hole：Rnd .12 Non-Plated
*   在Cell Edit中调整装配层铣切图形与实体等大，包括倒角
*   复制装配层铣切图形到Contour层，选择Hole Name（这里理解为线宽）为刚新建的Rnd .12 Non-Plated

Keepout

LE输出到Mentor Xpedition KeepOut可能不会有效转换，需查看禁布是否有生成。禁布图形放置到Route Obstruct/All层

相关问题
----

[Pads中如何设置圆弧倒角](https://zhidao.baidu.com/question/1738513900317196227.html)

Xpedition如何设置圆弧倒角：选中图形顶点从属性面板Polygon中调整