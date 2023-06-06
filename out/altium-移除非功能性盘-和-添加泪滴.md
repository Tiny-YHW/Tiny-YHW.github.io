---
title: 'PCB设计中的非功能性盘'
date: Sat, 05 Jun 2021 03:08:10 +0000
draft: false
tags: ['Allegro', 'Altium', '技术讨论', '设计技巧', '设计经验']
---

多层板设计时通孔Pin(Pad)和Via均是设计PCB的重要组成部分，它实现了让元器件引脚穿过 PCB 的不同层进行连接，一般通孔Pin(Pad)和Via会在设计中占据较大空间，甚至会导致高速信号的阻抗不匹配，设计或生产时针对此类情况，会涉及各种设计方式或生产方式如埋盲孔、背钻、去除非功能性焊盘，添加泪滴等，本文主要介绍去除非功能性焊盘

非功能性盘
-----

非功能性盘 英文non-functional pads (NFP) ，对于金属化通孔内层或表层，那些没有连接到对应层的金属环如下图红色部分金属环称为非功能盘，下图右侧即为去除非功能盘后的效果

![](http://a1024.synology.me:222/images/blog2022/NFPS.png)

**移除的好处**

*   移除非功能性盘可以减少钻头磨损延长钻头的使用寿命（钻穿基板比钻穿铜更容易），并在电路板上产生更好的通孔
*   非功能性焊盘可能对高速信号不友好[产生影响阻焊带来插入损耗](https://www.doc88.com/p-9035260735512.html)，移除非功能性盘可以在一定情况下改善此问题，高速电路要求过孔为尽可能短并且没有任何不必要的铜柱，这些会改变信号传输线的阻抗。也可能产生有问题的信号反射。
*   移除非功能性焊盘可以为设计更多的布线空间如下图左侧为移动了非功能性焊盘的相对右侧的空间情况。

![](http://a1024.synology.me:222/images/blog2022/pIYBAF1wpSmADZsKAACePPyMc48919.jpg)

**保留的好处**

*   大多数物质在加热时会膨胀，在冷却时会收缩，但是不同的材料有不同的导热系数和不同的热膨胀系数，因此，它们不会以均匀的方式膨胀或收缩。保留非功能盘有助于解决由于热膨胀系数（CTE）问题而导致的电路板Z轴膨胀问题。由于热膨胀系数（CTE）的问题。然而，随着较新的材料被用于无铅组装，这种担忧似乎已经减少。装配，这种担忧似乎已经减弱。
*   非功能盘对PCB孔壁加工过程中的沉铜效果有较大改善，在放置孔铜脱落、孔壁裂纹等质量问题上有一定功效

![](http://a1024.synology.me:222/images/blog2022/o4YBAF1wpOKADut1ABvcshXMtGA245.gif)

以下引用一个国外网站的说明

![](http://a1024.synology.me:222/images/blog2022/Snipaste_2021-06-07_11-28-51.png)

原文如下

#### WHY REMOVE UNUSED PADS?

*   “The drill bit will not easily be hurt and cause hole-wall roughness. (The non-functional inner layer pads are also always drilled even when the via and via hole size is small. The drill bit is also small and may easily be damaged if the copper remains for each layer.)”
*   “We minimize drill wear by removing them, especially on high layer counts with thick copper.”
*   “Drill life is reduced if all layers have unused lands. Drill breakage is also a concern.”
*   “Removal of unused lands in wiring plane with tight registration of line to land requirements.”
*   “To protect the drill bit from damaging and produce clean hole wall free of nodules.”
*   “We remove them to reduce the opportunity of creating shorts especially in a BGA area where typically trace/space is already fairly dense and to reduce the drill wear. The more copper we drill through, the more heat is generated reducing the possible hit count and having cleaner holes.”
*   “To enhance the drill hole quality, we prefer to drill through as little metal as possible. The effect of the unused pads is to wear the drill bit more rapidly, which shows up as gouging and poor drill quality.”
*   “Non-functional pads are normally removed to eliminate the possible misregistration perception by end user.”
*   “We remove them because it allows for a better product after etching.”
*   “For hole wall support on rigid product to reduce drill wear.”

#### WHY LEAVE UNUSED PADS?

*   “In our case, concern for accidental removal of a functional pad.” However, I began in business at TI and we always removed nonfunctional pads because our concern was bond strength of the electroless copper to the internal surface copper. If you didn’t need the copper, remove it. Also less chance for shorting in plane areas for nonfunctional pads.
*   “We believe that they anchor the hole and improve reliability. However, we have begun questioning this and have a DOE in progress to investigate.”
*   “The more copper that can be retained on any layer, the better the dimensional stability will be. Providing a complete pad stack (with the exception of plane layers) has improved registration and allows for proper DPA (destructive part analysis). With this ability to verify registration or misregistration anywhere within the product panel provides a great benefit. The additional copper also allows for better chip evacuation and prevents or greatly reduces clogged flutes.”
*   “Primarily electrical test shorts and AOI call outs for shorts”

#### SUMMARY OF RESPONSES

In all cases, remove or leave, the primary reason was to improve the respective fabricators process and yields. The companies that remove the unused pads do so primarily because they want to extend drill bit life and produce better vias in the boards, which they consider the primary reliability issue. For those that keep the unused pads, the primary reason is that they believe it acts as a multi-flanged rivet to combat interlayer damage within the PB. Such delamination is the result of non-homogeneous Z-axis expansion of the board due to differences in the Coefficient of Thermal Expansion (CTE) of the disparate materials.

设计师可以根据设计的实际情况选择是否保留非功能性盘，关于非功能性盘可以在设计阶段（PCB）或输出数据（Output）时甚至在Gerber（CAM）阶段均可以移除。后面分别介绍在Allegro和Altium PCB中如何去除非功能盘。

Altium
------

Altium中可以在设计时或输出Gerber时去除非功能盘

在设计时移除非功能盘可以在设计中实时看到设计情况，若过孔的间距规则与pad的间距规则有余量的情况可以有更大的布线空间，可以更大程度上优化布线

在输出时移除非功能盘仅代表去掉内层没有连接的盘，不能实时查看设计情况，也不能有优化布线的空间

### 在设计时移除

需要软件版本为14及之后版本，一般去除非功能盘在设计完成后进行，从菜单选择**Tools » Remove Unused Pad Shapes**

![](http://a1024.synology.me:222/images/blog2022/Unused_Pad_Shape20-460x242.png)

*   **Scope**移除范围
    *   **Vias** - 仅移除Vias的非功能性盘.
    *   **Pads** - 仅移除Pads的非功能性盘
    *   **Both **\- 同时移除Via和Pads的非功能性盘.

*   **Operation**
    *   **Remove unused **\- 移除非功能盘.
    *   **Restore unused** - 重置（恢复）非功能盘.
    *   **Update unused** - 更新非功能盘.

*   **Selected only** - 仅移除被选择的，使用此功能需在打开本菜单之前先选择目标对象
*   **Preserve pads on start and end layers** - 保留起始和结束层（一般指顶底层除非埋盲孔）的非功能盘

点击ok后将自动执行非功能性盘被移除、重置或更新

一般非功能盘移除后设计汇总布线空间有有所改变需要重新更新所有铜皮，甚至可以优化部分线路的布线路径。

### 在输出时移除

在输出Gerber光绘数据时，下方有可选项**Include unconnected mid-layer pads**，按选项输出对应结果的Gerber数据

![](http://a1024.synology.me:222/images/blog2022/Snipaste_2021-06-07_13-46-28.png)

此选项默认为不勾选代表移除（不保留）非功能盘；勾选时代表不移除（保留）非功能盘

Allegro
-------

Allegro中可以在设计时或输出Gerber时去除非功能盘

在设计时移除非功能盘可以在设计中实时看到设计情况，若过孔的间距规则与pad的间距规则有余量的情况可以有更大的布线空间，可以更大程度上优化布线

在输出时移除非功能盘仅代表去掉内层没有连接的盘，不能实时查看设计情况，也不能有优化布线的空间

Allegro中若需要使用去除非功能盘选项时需要在pad的库中开启使能选项（默认为开启的），否则即便设计中设置了移除也能不能被成功应用，对应的设置项如下图处勾选

![](http://a1024.synology.me:222/images/blog2022/Snipaste_2021-06-07_14-00-25.png)

### 在设计时移除

**16.X及以下**从菜单_Setup - Unused Pads Suppression_进入设置项

![](http://a1024.synology.me:222/images/blog2022/Snipaste_2021-06-07_13-59-16.png)

勾选Pins和Vias列的勾分别代表在对应的层具有非功能盘的Pins和Vias将被移除

_Dynamic unused pads suppression_ - 在设计中动态（实时）显示非功能盘的去留情况

**17.X**及之后的版本以上设置项已被集成到层叠管理的窗口中，从_Setup -_ Cross Section访问，从下图出设置对应选项

![](http://a1024.synology.me:222/images/blog2022/Snipaste_2021-06-07_14-04-12.png)

### 在输出时移除

在输出光绘时有可选项**Suppress unconnected pads**，按选项输出对应结果的Gerber数据

![](http://a1024.synology.me:222/images/blog2022/Snipaste_2021-06-07_13-58-44.png)

此选项默认为不勾选代表不移除（保留）非功能盘；勾选时代表移除（不保留）非功能盘