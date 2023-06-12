---
layout: post
title: Cadence Allegro What’s New in 17.4-2019 QIR4 (HotFix 028)
categories: Allegro
description: 
date: 2023-06-12
---

本文描述了Cadence Allegro PCB Editor在17.4-2019 QIR4 (HotFix 028）中的增强和改进


* * *

**关联**

*   [What’s New in 17.4 2019](https://tiny-yhw.github.io//2023/06/12/cadence-allegro-whats-new-in-17-4-2019/)
*   [What’s New in 17.4 2019 QIR1（hotfix7）](https://tiny-yhw.github.io//2023/06/12/cadence-allegro-whats-new-in-17-4-qir1-hotfix-007/)
*   [What’s New in 17.4 2019 QIR2（hotfix13）](https://tiny-yhw.github.io//2023/06/08/cadence-allegro-whats-new-in-17-2-2016-qir-2-hotfix9/)
*   [What’s New in 17.4 2019 QIR3（hotfix19）](https://tiny-yhw.github.io//2023/06/12/cadence-allegro-whats-new-in-17-4-qir3-hotfix-019/)
*   [What’s New in 17.4 2019 QIR4（hotfix28）](https://tiny-yhw.github.io//2023/06/12/cadence-allegro-whats-new-in-17-4-qir4-hotfix-028/)
*   [BUG修复记录](https://layouto.lanzouf.com/i1LVI0tkym7i){:target="_blank"}

* * *

DesignTrue DFM Enhancements增强功能
-------------------------------

### Expanded Same Net Via Checks新增同网络过孔检查

之前的版本仅能检查非同网络via，先增加对同网络via间距的检查

![samenetvia.png](https://a1024.synology.me:222/images/blog2023/samenetvia.png)

### Region-Based DFA Rules基于区域的DFA规则

可以在设计中创建一个或多个区域，然后对这些区域应用一组新的DFA间距规则。

要创建区域或指定先前创建的区域，右键单击要为其创建区域或为其指定区域的图层，然后选择Create Region创建新区域或Layer Regions分配已经创建的区域。

![algPN-3.gif](https://a1024.synology.me:222/images/blog2023/algPN-3.gif)

可以将CSets指定给创建的区域。在下面的示例中，有三个不同的DFA CSets应用于`TOP`层，一个(默认CSet)，DFAPKGCS\_RGN1，用于整个层，其余两个用于两个不同的区域。

![algPN-4.gif](https://a1024.synology.me:222/images/blog2023/algPN-4.gif)

基于区域的规则需要考虑以下因素:

*   跨越电路板不同区域的器件将按器件原点所在区域划分区域规则。
*   原点跨在区域形状边缘上的器件被视为在区域形状边缘内。
*   基于区域的规则仅适用于同一层上的器件。这些检查不会跨越层，也不会检查不同层上的器件。

Package Design Integrity Checks没读懂此处引用原文
----------------------------------------

Opens and shorts might remain undetected in a package design database that defines openings for connectivity using pad geometries in named dielectric layers instead of drill definition in padstack. As the current functionality uses drill to define connectivity between the pads in a padstack, connectivity between pads is assumed even if the value of drill diameter is defined as zero.  
With this release, new Package Design Integrity checks are added to identify the potential opens or shorts for padstacks that have the value of drill diameter set to zero. These checks are specifically for using geometries, instead of drill, on named dielectric layers to define connectivity.

![algPN-5.gif](https://a1024.synology.me:222/images/blog2023/algPN-5.gif)

Manufacturing Enhancement: Dynamic Backdrill动态背钻
------------------------------------------------

![algPN-8.gif](https://a1024.synology.me:222/images/blog2023/algPN-8.gif)

之前的版本，被选信息需要选择更新背钻命令时才会自动更新焊盘尺寸在背钻孔路径上添加禁布区，现动态背钻版本次方案得到增强，可以实时更新和显示背钻结果

![algPN-6.gif](https://a1024.synology.me:222/images/blog2023/algPN-6.gif)

要启用改功能需在User Preferences Editor 中 Manufacture – Drilling category勾选backdrill\_enable\_dynamic，此时在Backdrill Setup and Analysis框中会有一个新的选项Enable dynamic backdrill勾选以启动动态不钻功能

![algPN-7.gif](https://a1024.synology.me:222/images/blog2023/algPN-7.gif)

Padstack Editor Enhancements焊盘编辑器增强
-----------------------------------

### Multi-Drill Enhancements多钻孔功能增强

之前的版本允许在焊盘中增加行列矩阵的过孔，现增加一种polar极坐标排列或自定义排列的的多钻孔形式以匹配各种不同的多钻孔需求

![algPN-9.gif](https://a1024.synology.me:222/images/blog2023/algPN-9.gif)

### Keepout Enhancements禁布增强

Keepout支持Flash Symbol（特殊外形）

![algPN-10d15fcb246dbc1e9e.gif](https://a1024.synology.me:222/images/blog2023/algPN-10d15fcb246dbc1e9e.gif)

Keepout支持设定例外条件，即这些对象可以画在禁布中而不产生DRC

![algPN-11.gif](https://a1024.synology.me:222/images/blog2023/algPN-11.gif)

Constraints Enhancement规则管理增强
-----------------------------

### Expanded Spacing Hole to Hole Checks 扩展hole到hole的检查

此版本对不同类型的via进行分类，可以分别设置这些种类的hole到hole的间距规则，这些种类包括thru via holes, blind/buried holes, micro via holes, and pin holes，在规则管理中点击hole的间距规则时会跳出一个新的窗口用于设定不同种类的hole间距规则

![Snipaste_2023-04-07_14-07-20.png](https://a1024.synology.me:222/images/blog2023/Snipaste_2023-04-07_14-07-20.png)

这个规则在Net、Class-Class、Region、Same net等处均可使用

Differential Pair High-Speed Structures差分对高速结构
----------------------------------------------

通过在画布上选择窗口，用差分对结构替换现有的差分对结构。这种替换程序需要一个垂直差分对结构，在保持连接的同时适当旋转和调整。还包括一个选项，用于在需要大量返工时，将差分对结构转换为独立的差分对过渡过孔。

使用此功能需要先设定User preference-Interactive-dp\_via\_replace\_with\_struct勾选

在此版本中，提供了一种自动方法，选择已有结构替换板中现在使用的结构，选择Differential Pair Vias模式并设定新的结构，PCB上的对应的结构将被一同

![algPN-13.gif](https://a1024.synology.me:222/images/blog2023/algPN-13.gif)

Allegro Constraint Compiler Updates约束编译器更新
------------------------------------------

Allegro Constraint Compiler (ACC)越来越多地被用来驱动外部生成的约束，以便导入到Constraint Manager中。根据用户反馈，在此版本中，提供了几个对象表增强功能，以支持选择引脚和网络之外的对象，可选列可灵活地在表中包括可选网络，以及一个字节通道差分对计算器。一个新栏目_可选择的_现在添加了，以便在表中灵活地包括可选的网络，如果没有找到网络，允许编译器继续。还包括一个字节通道差分对计算器。此外，ObjectRule表得到了增强，以支持基于元件、网络和引脚的约束驱动规则，如背钻桩要求和引脚延迟。

3D Canvas Updates 3D画布更新
------------------------

### Symbols支持透明度设置

所有模型现在都可以应用透明度。**3D Canvas – Preferences – Symbol Representation – Transparency**可以更改Symbols模型的可见或透明度状态。

![algPN-1934607b9fa92c57a9.gif](https://a1024.synology.me:222/images/blog2023/algPN-1934607b9fa92c57a9.gif)

通过选定器件可以对其应用指定的设定状态

![Snipaste_2023-04-06_15-09-44.png](https://a1024.synology.me:222/images/blog2023/Snipaste_2023-04-06_15-09-44.png)

如上图搜索过滤也是一个新增功能，支持使用通配符的形式查找指定类型的器件

### Separate Colors for Selection and Collision设置选择对象和冲突对象的颜色

3D Canvas Preferences对话框如下图，可以为_Selection_状态或Collision状态的模型设置不同的颜色。

![algPN-22.gif](https://a1024.synology.me:222/images/blog2023/algPN-22.gif)

Overlay Mode覆盖模式
----------------

为了提高定位选定模型的能力，增加一种新的Overlay模式

![algPN-23.gif](https://a1024.synology.me:222/images/blog2023/algPN-23.gif)

在具有多层和重叠元件的密集PCB上，很难找到选定的元件。如以下示例所示，使用新的Overlay模式，两个选定的IC被突出显示出来，这样更容易找到选定的组件。

![algPN-24.gif](https://a1024.synology.me:222/images/blog2023/algPN-24.gif)

### Coloring Models using Bulk Selection使用批量选择对模型着色

在3D映射器选项卡中可以根据给定的器件分组footprints or devices，然后通过安装SHIFT or CTRL多选多种器件后点击color对话框，对选择的器件类型批量着色，在器件模型被着色的同时footprints and devices也将显示为指定的颜色。

![algPN-25.gif](https://a1024.synology.me:222/images/blog2023/algPN-25.gif)

### 3D模型内嵌在DRA或BRD中

在之前的版本使用3D Step是通过调用本地路径step文件应用的，这将导致我们传递设计文件时如果没有一同传递step文件，这将可能导致3D step不能正确显示，现在3D step被导入后将直接存储到database中，不再依赖于本地库，以保证文件传递的正确和便捷

### Representation of Planes Split Across Zones跨区分割平面显示

此版本引入了跨不同叠层/区域的平面分割，以使3D画布尽可能真实。正如您在下图中看到的那样`ADHESIVE_TOP` mask层不是叠层的一部分，`D`。还要注意`TOP`导体层不在叠层中`C`。这使得叠层B和C的厚度不同。

![algPN-26.gif](https://a1024.synology.me:222/images/blog2023/algPN-26.gif)

在下图所示的设计中ADHESIVE\_TOP跨越了BCD

![algPN-27.gif](https://a1024.synology.me:222/images/blog2023/algPN-27.gif)

You can see the new realistic outcome when looking at the design in 3D Canvas. The ADHESIVE\_TOP shape, selected in the previous image, is shown in zone/stackup B. The same ADHESIVE\_TOP shape in zone/stackup C is lower than B due to the missing TOP conductor layer in zone C. Further, you can see that the ADHESIVE\_TOP shape is completely missing from zone/stackup D because the ADHESIVE\_TOP layer is not part of zone/stackup D as depicted in the Cross-section Editor image. Shapes that cross zones/stackup areas are now represented realistically.（看不懂）

![algPN-28.gif](https://a1024.synology.me:222/images/blog2023/algPN-28.gif)

### Z-Origin Visualization and Controlz原点可视化和控制

通过选项3D Canvas – Setup – Preferences – Z0 Position可以控制Z原点打开或关闭，以及Z0的位置

![algPN-29.gif](https://a1024.synology.me:222/images/blog2023/algPN-29.gif)

从3D画布中导出文件时，也会识别Z0位置。

### Silkscreen Layer Representation丝印层显示控制

丝印层在画布中的显示可选使用Package\_Geometry – Silkscreen\_xxx layers, Board\_Geometry – Silkscreen\_xxx layer and Components – RefDes – Silkscreen\_xxx layers,或Manufacturing – Autosilk\_xxx layers

![algPN-32.gif](https://a1024.synology.me:222/images/blog2023/algPN-32.gif)

Miscellaneous Enhancements杂项增强功能
--------------------------------

部分感知度较低的功能不做详细介绍了，需要了解的自行去查看What’s New文档

### Constraint Region Support for Flow Lines and Vias 对Flow Lines and Vias约束增加区域支持（略）

### Create Zigzag on Shape Edges 在Shape边缘创建锯齿形（略）

### Display Layer ID in the Visibility Pane Visibility显示图层ID

### Advanced Non-standard Fillets高级非标准Fillets（略，特别的泪滴时可以使用）

### Import GDS Structures导入GDS结构（略）

通过Color Dialog (Display – Color/Visibility)对话框，勾选如下图Show layer IDs后在Visibility控制面板层名前会增加一个Layer序号，因为不怒Label信息如背钻显示埋盲孔等使用的都是 layer ID而不是层名称，这样便于查看序号对应的层别。

![algPN-39.gif](https://a1024.synology.me:222/images/blog2023/algPN-39.gif)

![Snipaste_2023-04-07_14-31-25.png](https://a1024.synology.me:222/images/blog2023/Snipaste_2023-04-07_14-31-25.png)

Reduce Design Extent to Fit Geometry 自动缩小画布范围适配设计图形
---------------------------------------------------

如果设计大于适合几何图形所需的大小，设计文件会占用更多的磁盘空间，DRC计算等操作对设计来说会更慢，现在可通过Setup – Design Parameters中Shrink Extents to Design Contents命令自动缩小设计范围优化设计画布

![algPN-40.gif](https://a1024.synology.me:222/images/blog2023/algPN-40.gif)

### 部分Allegro Package Designer Plus的新增功能或增强（略）