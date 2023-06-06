---
layout: post
title: Cadence Allegro What’s New in 22.1
categories: Allegro
date: 2023-06-06
---
![Cadence-Alegro-2022.png](https://a1024.synology.me:222/images/blog2023/Cadence-Alegro-2022.png)

22.1（**2022年10月**）
==================

本文描述了Cadence Allegro PCB Editor在22.1基础版的新功能和增强功能。

版本说明
----

17.4-2019版和22.1版之间的数据库格式没有变化（除下文特别指出的情况），22.1版和17.4-2019版设计文件可以直接互开

### Structures and Vias in Mirrored Layers结构和通孔的镜像层

如果数据库在mirrored layers状态，即标记为`mirrored_layers`，数据库无法迁移到早于17.4 -2019版HotFix 028 (QIR4).的版本。

处于镜像层状态的对象是用Mirror Geometry 命令然后 mirrored 到板子另一侧的对象

通常使用Mirror Geometry命令来翻转同一层上的结构，但是在移动或复制时也可以翻转过孔，如果此类过孔是符号、模块或组的一部分，则镜像会将过孔更改为镜像层状态。

Improvement Using 3DX Canvas使用3DX Canvas提高性能
--------------------------------------------

Allegro SPB 22.1 版本附带一个新的 3DX 引擎，该引擎与 Allegro 板设计数据库整合，会对以前 3D Canvas 的性能和内存使用进行优化，以解决与大型设计相关的规模和复杂性问题。3DX Canvas**可以更快、更有效地处理大型设计。**

3DX Canvas窗口可以从_View – 3DX Canvas_菜单命令或_3DX_工具栏图标:

此功能貌似是需要使用Allegro Enterprise PCB Designer Suite产品选项才能使用

![3DXcanvas.png](https://a1024.synology.me:222/images/blog2023/3DXcanvas.png)

3DX Canvas窗口包括Visibility, Properties, Search，Component控制面板。

3DX Canvas与Allegro数据实时同步，实时交互。在Allegro中所做的任何更改都会更新到到3DX Canvas，反之亦然。

更多详情，请至帮助文件关键字“Allegro 3DX Canvas User Guide”查阅相关描述

<iframe width="720" height="405" frameborder="0" src="https://www.ixigua.com/iframe/7224396314727940648?autoplay=0" referrerpolicy="unsafe-url" allowfullscreen></iframe>

[视频演示](https://v.douyin.com/UqjJ3tQ/){:target="_blank"}

High-Speed Structure Enhancements高速结构增强
---------------------------------------

高速结构得到了改进，以加快创作速度。

此功能需要Allegro产品选项启用了High-Speed选项时使用

### Parameterized High-Speed Structures参数化高速结构

现在创建结构更快了。这是对版本17.4-2019, HotFix 013中引入的原型的增强，可基于参数生成结构。

Allegro SPB 22.1 版本可以**从画面上所选的差分对变换中直接提取结构的相关信息，**更快地创建结构。

增加一个选项：回流过孔使用与信号孔同样的padstack，启用此选项可以更快的定义一种指定的回流孔类型

![algPN_base-7.gif](https://a1024.synology.me:222/images/blog2023/algPN_base-7.gif)

差分对过孔换层需要相邻层禁布。定义禁布区时，需要匹配差分线布入或布出差分孔的方向。图层行现在有一个方向三角形来标识方向，可定义相邻层掏空形状。

![algPN_base-8.gif](https://a1024.synology.me:222/images/blog2023/algPN_base-8.gif)

选择现有差分对via提取信号via padstack，可对差分线或焊盘的相关参数进行编辑

![algPN-10.gif](https://a1024.synology.me:222/images/blog2023/algPN-10.gif)

### Differential Pair Vias Replaced by Structures通过结构替换差分过孔

在此版本中通过结构替换差分过孔已更新，可以保持不包含焊盘进入或退出走线的结构的当前布线和延迟匹配。

HotFix 028版本17.4-2019提供了通过结构替换差分过孔的功能。但如果焊盘进入或退出走线经过调整以满足时序要求，替换可能会产生替换前不存在的延迟DRC。

现在，Allegro SPB 22.1 版本**可以使用不带有进线或出线的过孔结构，**这样在替换以后，走线和延迟就可以保持不变。

### On-Canvas Structure Update and Variant Creation画布上的结构更新和变体创建

结构可以在一个设计中多次使用。可以更改一个实例，并同步更新所有相同的实例。有时，您可能需要添加或移除对象，或者为不同的情况创建稍微不同的结构变体。在此版本中可以通过Route – Structure – Redefine命令在现有结构中添加或移除对象。可以选择覆盖实例或保存到新结构中。

在不更改membership的情况下，移动或调整结构对象的现有流程仍然可以通过使用Redefine Structure命令将更新推送到所有实例。

![algPN-14.gif](https://a1024.synology.me:222/images/blog2023/algPN-14.gif)

Converting Shapes, Vias, and Pins 转换形状、过孔和引脚
--------------------------------------------

将 Gerber 或 DFX 文档转换为智能设计时，为了确保创建连接，有时需要将这些文档转换成不同的设计对象。比如，有时导进来的是铜箔，但是我们需要的却是过孔和 Pin脚，或者需要的是电气连接线但导进来的却是非电气的连接线。另外，要能依据电气线、非电气线和引脚或过孔焊盘自动生成铜箔的形状而不是手动来画。

现在，Allegro SPB 22.1 版本可以轻松解决以上需求，**只要执行 Tools-Convert 命令，在板中直接选中对象即可完成不同对象的转换，也可以实现对象的创建或替换。**

![algPN-15.gif](https://a1024.synology.me:222/images/blog2023/algPN-15.gif)

Dimensioning Update标注功能更新
-------------------------

Dimension Environment命令提供了为对象创建关联尺寸的功能，当移动标注对象时，标注尺寸会一同变更更新，但有时我们并不希望标注的尺寸同对象一起更新时，相应的操作就会比较繁琐

在这个版本中可以使用菜单Manufacture – Dimension Environment,_，_然后选择_Disband dimensions_命令将标注分离成单独的对象，以便在不删除和重新生成标注的情况下对其进行更改。

Route Keepouts Exception Use Model Enhancement（不会翻译了 使用模型增强禁止异常？）
-----------------------------------------------------------------

部分设计情况要求指定区域内可以有vias但不允许使用stacked vias

此版本增减一个VIA\_STACKING\_NOT\_ALLOWED属性，用于在VIAS\_ ALLOWED的基础上限制stacked vias

设置VIAS\_ ALLOWED和VIA\_STACKING\_NOT\_ALLOWED属性时，可以在禁止区内添加过孔，但当stacked vias出现时，会显示DRC。

![algPN_base-18.gif](https://a1024.synology.me:222/images/blog2023/algPN_base-18.gif)

![algPN-17.gif](https://a1024.synology.me:222/images/blog2023/algPN-17.gif)

![algPN-19.gif](https://a1024.synology.me:222/images/blog2023/algPN-19.gif)

Power Delivery Generator电源范围生成
------------------------------

使用Power Delivery Generator，无需手绘铜皮边界以覆盖电源连接点

使用Si Layout – Power Delivery – Power Delivery Generator功能，可以自动在对应的电源区域生成电源或接地层平面

![algPN-21.gif](https://a1024.synology.me:222/images/blog2023/algPN-21.gif)

The plane boundary can range from a flood net to cover the layer where no other plane is poured, to regions defined by a bounding shape (convex hull) surrounding pin groups, to rectangular regions such as blocks around regular clusters of pins that identify power domains inside of the chip.

随着设计的进行，您可以继续更改参数，并根据需要再生所有平面。

Performance Enhancements性能增强
----------------------------

22.1版中的增强功能加快了设计速度。此版本中的一些主要性能改进如下:

*   具有大量DRC的设计性能更佳
*   Faster Update to Smooth 铜皮批量更新性能优化
*   Better Move Performance 移动大量对象是表现更加
*   Better Performance for Shape Parameter per Layer Override 当设计影响到铜皮形状，铜皮需要更新时性能更佳
*   Restricting Command Window Messages 限制命令窗口消息，设计任务的非关键消息在命令窗口中不再可见。例如，通常在执行批量操作时，会提前显示1000多条消息。现在消息的最大数量限制为100条。
*   Faster DRC Checking on Designs with Negative Layers 对带有负片层的设计进行更快的DRC检查

Display Enhancements 显示增强
-------------------------

显示得到了增强，以简化复杂和密集设计的设计过程。以下部分描述了显示增强功能:

### Expanded GPU Support 扩展的GPU支持

在此版本中，除了现有的对NVIDIA GPUs的支持，GPU Canvas渲染还扩展到支持英特尔和AMD的现代独立或集成GPU，并具有以下增强功能:

*   平移和缩放的性能提升
*   增强的显示质量:虚拟机需要专用或集成的NVIDIA、Intel或AMD物理GPU。
*   启动布局编辑器时，会自动检测并启用最佳的GPU渲染器:
    *   要禁用GPU画布，请设置`DISABLE_GPU`中的变量_用户首选项_设置。
    *   要为会话禁用GPU Canvas，请使用`–nogpu`开关(`allegro –nogpu`).

### Normalized Forms for High Resolution Displays 高分辨率显示器的标准化形式

现在，您可以指定一个比例因子来标准化由于显示比例问题而产生部分截断形状的情况。通过调整系统变量`ALLEGRO_HIGH_DPI_ENABLED`可以让设计的各方面显示在高分辨显示器上也能有更好的表现

修复记录
----

Fixed CCRs: SPB 22.1 BASE

CCRID Product Title

QIR 1 (HotFix 001)（12-16-2022）
==============================

本文描述了Cadence Allegro PCB Editor在22.1版季度增量版(QIR) 1中的新功能和增强功能。

Allegro 3DX增强功能
---------------

引入了新的3DX引擎，该引擎与Allegro设计数据库集成，通过解决相关的规模和复杂性问题，提供了更快、更有效的大型设计处理。

该QIR为DRC环境提供了全面的增强，并简化了查看和浏览DRC的方式。该版本还为刚挠结合设计提供了额外的支持。

### 器件间隙DRC

器件到器件的间隙的DRC可用于3D model以及Place Bound 和 DFA Bound。DRC支持为单个器件和各类器件（mechanical, connector, discrete, QFN, SOP, and BGA.）设定不同的水平和垂直间隙值。

DRC标记在三维视图中可见，将光标悬停在标记上可以高亮显示DRC对象及提示信息。

3DX Canvas的搜索窗格中可以浏览DRC。

### 3DX刚挠结合

以交互方式查看和测量刚挠设计的弯曲。您可以随时进行目视器件间距检查，也可以在折弯状态下运行DRCs检查

GPU加速渲染增强
---------

GPU支持在平移和缩放以及打开或关闭图层时提供更快的响应时间，并提高图形渲染质量。

默认情况下，GPU支持是启用的，并且在Windows和Linux平台上可用。

为了获得最佳性能，可考虑使用RTX A6000级别的GPU。