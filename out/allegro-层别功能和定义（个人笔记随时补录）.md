---
title: 'Allegro 层别功能和定义（个人笔记随时补录）'
date: Thu, 19 Jan 2023 08:36:11 +0000
draft: false
tags: ['Allegro']
---

以下个人总结，如有错误或补充评论区欢迎

Anti Etch 反蚀刻：使用Split Plane Create功能灌铜时，铜根据Anti Etch对应层别图形做分隔或避让。

*   TOP-Bottom ：应用于对应层别的图形
*   All：应用于所有层的图形

Board Geomety 板级图形：设计中需要增加的图形，注意与Package Geomety的区别。

*   Outline：板框图形，17.X版本定义有差异
*   Silkscreen\_TB：板中增加的丝印图形
*   Soldermask\_TB：板中增加的开窗图形

Etch 蚀刻：PCB各层蚀刻出来的图形

*   TOP-Bottom ：应用于对应层别的图形

Package Geometry Package图形：Footprint中需要的图形，注意与Board Geomety的区别。

*   Autosilk\_TB：最后出gerber的时候，自动生成的丝印层。会自动调整丝印位置，以及碰到阻焊开窗的地方，丝印会自动消失，避免露锡的地方涂上丝印。
*   Silkscreen\_TB：Footprint中的丝印图形，一般包括元器件丝印框，一脚标识，辅助标识。
*   Assembly\_TB：Footprint中的装配图形，一般包括元器件框，倒角（代表极性方向）。
*   place\_bound\_TB：Footprint中的元器件占位，包括元器件本体大小和机械允许间隙距离。

Manufacturing 制造：板子生产需要使用一些信息

*   No\_probe\_TB：禁止探针探入区域

Ref Des：

Pin：元器件pad对应的相关信息