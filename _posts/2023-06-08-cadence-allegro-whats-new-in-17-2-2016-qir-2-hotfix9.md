---
layout: post
title: Cadence Allegro What’s New in 17.2 2016 QIR2（hotfix9）
categories: Allegro
date: 2023-06-08
---

本文档介绍了Allegro® PCB Editor在17.2版季度增量版QIR2（hotfix9）中的新功能和增强功能

* * *

**关联**

*   [What’s New in 17.2 2016](https://tiny-yhw.github.io//2023/06/08/cadence-allegro-whats-new-in-17-2-2016/)
*   [What’s New in 17.2 2016 QIR1（hotfix4）](https://tiny-yhw.github.io//2023/06/08/cadence-allegro-whats-new-in-17-2-2016-qir-1-hotfix4/)
*   [What’s New in 17.2 2016 QIR2（hotfix9）](https://tiny-yhw.github.io//2023/06/08/cadence-allegro-whats-new-in-17-2-2016-qir-2-hotfix9/)
*   [What’s New in 17.2 2016 QIR3（hotfix16）](https://tiny-yhw.github.io//2023/06/08/cadence-allegro-whats-new-in-17-2-2016-qir-3-hotfix16/)
*   [What’s New in 17.2 2016 QIR4（hotfix25）](https://tiny-yhw.github.io//2023/06/08/cadence-allegro-whats-new-in-17-2-2016-qir-4-hotfix25/)
*   [What’s New in 17.2 2016 QIR5（hotfix31）](https://tiny-yhw.github.io//2023/06/08/cadence-allegro-whats-new-in-17-2-2016-qir-5-hotfix31/)
*   [What’s New in 17.2 2016 QIR6（hotfix38）](https://tiny-yhw.github.io//2023/06/08/cadence-allegro-whats-new-in-17-2-2016-qir-6-hotfix38/)
*   [What’s New in 17.2 2016 QIR7（hotfix48）](https://tiny-yhw.github.io//2023/06/08/cadence-allegro-whats-new-in-17-2-2016-qir-7-hotfix48/)

* * *


## New Concurrent PCB Team Design Environment 一种新的并行PCB团队设计环境

[](link){:target="_blank"}
## Create Flow (Design Planning Option)

## Introducing the New 3D Canvas (Unsupported Prototype) 3D画布

![172-algPN-303.gif](https://a1024.synology.me:222/images/172-algPN-303.gif)

原来的*3D Viewer*任然是默认的查看器，要启用新的查看器需在*Setup - User Preferences - Unsupported*中设置环境变量`interactive_3d_canvas`然后从菜单*View – 3D View*中启动即可打开新的3D画布

### 操作方法

- 滚动鼠标滚轮对界面进行缩放
- 按住鼠标滚轮并拖动对视图进行平移
- 按住 <kbd>Shift</kbd> 和鼠标滚轮并拖动对视图中3D惊醒旋转

### 控制面板

- Visibility：控制设计中Etch层中的Line, Pin, Shape, and Via 的可见性
- Symbols：控制元器件的Step Model or Placebound在Top, Bottom, or Embedded Component 层的可见性
- Collision：检查器件干涉

![172-algPN-304.gif](https://a1024.synology.me:222/images/172-algPN-304.gif)

### Basic Collision Detection 基本碰撞检测

在Collision控制面板中可以查看有重叠的symbols，选择列表中的条目则对应的器件将在3D画布生成蓝色的定为图形，对应的器件也会闪烁几次

![172-algPN-305.gif](https://a1024.synology.me:222/images/172-algPN-305.gif)

### 3D-2D Interaction 3D与2D交互

![172-algPN-306.gif](https://a1024.synology.me:222/images/172-algPN-306.gif)

在3D画布上选定的对象也会在2D画布上选定并高亮显示。

现在可以在2D画布上高亮、移动、添加或删除对象，这些操作的内容将实时更新到3D画布中

可以在2D画布上选择任何对象，例如vias, pins, components, nets等，这些对象也将在3D画布中突出显示

### Full Layer Modeling of Mask, Silk, and Dielectric Layers

![172-algPN-307.gif](https://a1024.synology.me:222/images/172-algPN-307.gif)

3D Canvas现在更接近于在逼真的渲染中更准确地表示设计的板。此版本在*Visibility*窗格中列出了阻焊层、丝网印刷层和电介质层。板和层的厚度以及板的轮廓现在可以准确地显示。

![172-algPN-308.gif](https://a1024.synology.me:222/images/172-algPN-308.gif)
![172-algPN-309.gif](https://a1024.synology.me:222/images/172-algPN-309.gif)

### File Export 文件导出

从3D Canvas中，您现在可以导出文件-导出表单中列出的六种文件类型中的五种。此版本提供的格式包括：

- HSF – Hoops Stream File
- HMF – Hoops Metadata File
- OBJ – Wavefront Format OBJ
- PLY – Polygon File Format
- STL – STereoLithography

![172-algPN-310.gif](https://a1024.synology.me:222/images/172-algPN-310.gif)

## Interactive Routing Enhancements 交互式布线增强功能

在此版本中，它们现在与 add connect 命令完全集成。这种模式下的过孔结构限于single nets and differential pairs。一旦在数据库中定义了保存的选项，它们就被应用到ECSet并映射到相应的高速网络。

### Standard Via Structure 标准通孔结构

- 菜单选项*Route – Via Structure – Create – Standard*
- 使用目标模型：Single net trace/via structures and fan-out
- 支持对象：Traces, vias
- 连通性：需要物理连接（single net）

![172-algPN-311.gif](https://a1024.synology.me:222/images/172-algPN-311.gif)

### High Speed Via Structure 高速通孔结构

- 菜单选项*Route – Via Structure – Create – High Speed*
- 使用目标模型：差分 via transitions with 回流 vias and custom plane void
- 支持对象： Traces, vias, static shapes (no voids), route keep out
- 连通性：Multi net

![172-algPN-312.gif](https://a1024.synology.me:222/images/172-algPN-312.gif)

### Via Structures in Constraint Manager

必须将过孔结构添加到规则管理器中的ECSet，从规则管理器中*Electrical Constraint Set – Routing – Vias*添加过孔结构，并将ECset分配给网络对象

![172-algPN-313.gif](https://a1024.synology.me:222/images/172-algPN-313.gif)

### Methods to add Via Structures 添加过孔结构

使用*add connect*命令时从option面板过孔清单处可以选择预定义的过孔结构

![172-algPN-315.gif](https://a1024.synology.me:222/images/172-algPN-315.gif)

添加过孔结构时如果方向不对可以从通过右键菜单选择指定方向（0、90、180、270）调整

![172-algPN-316.gif](https://a1024.synology.me:222/images/172-algPN-316.gif)

## Route Optimization (Unsupported Prototype) 布线优化

使用*add connect*或*Auto-Interactive Breakout*布线时可以选择从Option中选择optimize in channel选项，这样布线将自动平均分配在Viod间隙内

要使用本功能需要在*Setup – User Preferences – Unsupported*中定义环境变量optimize_in_channel才可使用

![172-algPN-320.gif](https://a1024.synology.me:222/images/172-algPN-320.gif)
![172-algPN-321.gif](https://a1024.synology.me:222/images/172-algPN-321.gif)

## Shape Applications

### Automatic Island Deletion自动删除孤岛

*Global Dynamic Shape Parameters*中添加了一个新的参数*Automatically delete islands*，启用此项时，在有形成的Shpe被更新Smooth时将被自动去除。


![172-algPN-322.gif](https://a1024.synology.me:222/images/172-algPN-322.gif)

### Island Void Deletion 删除孤立Void

新增一个*delete island voids*命令可以自动删除voids，这些voids一般是通过*Delete Islands*命令时产生的

### Shape Voiding Behavior

针对矩形避让的Shape将默认使用圆角

![172-algPN-323.gif](https://a1024.synology.me:222/images/172-algPN-323.gif)

若需要沿用老版本使用90度通过设置环境变量值*dv_squarecorners*来进行调整

![172-algPN-324.gif](https://a1024.synology.me:222/images/172-algPN-324.gif)

DFA Table Support for Embedded Layers（略）

## Miscellaneous Enhancements 其它增强

### Show element 显示元素

- 报告过孔是否为堆栈的一部分
- 报告keepout是否属于pin/via及其pad keepout type
- 报告pins and vias所在的区域名称（仅适用于刚柔设计）

### Show measure 测量

支持lines and clines (之前只支持线段segments)

### Prevent Opening of Database in 17.2 防止在17.2中打开旧数据库

由于无法将17.2数据库降到16.6，因此可以启用值为no的用户首选项变量`uprev_answer`，以防止在17.2中打开旧数据库。

`uprev_answer`:如果设置，则不显示主要发布设计 uprev警告但提供默认答案。 如果值为“否”那么用户无法打开旧版本的设计

### IPC2581

Net names are now associated with plated hole records

### Derive Connectivity Utility

增加一个新选项*Derive Connectivity Utility*可防止将未连接的cline恢复为line

### DBDoctor

Reports padstacks that are non-plated, but are used within the physical path of nets (pins or vias).