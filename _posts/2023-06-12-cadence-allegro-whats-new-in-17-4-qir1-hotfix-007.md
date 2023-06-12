---
layout: post
title: Cadence Allegro What’s New in 17.4-2019 QIR1（hotfix007）
categories: Allegro
description: 
date: 2023-06-12
---

本文描述了Cadence Allegro PCB Editor在17.4-2019 QIR1（hotfix007）中的增强和改进


* * *

**关联**

*   [What’s New in 17.4 2019](https://tiny-yhw.github.io//2023/06/08/cadence-allegro-whats-new-in-17-2-2016/)
*   [What’s New in 17.4 2019 QIR1（hotfix007）](https://tiny-yhw.github.io//2023/06/08/cadence-allegro-whats-new-in-17-2-2016-qir-1-hotfix4/)
*   [What’s New in 17.4 2019 QIR2（hotfix013）](https://tiny-yhw.github.io//2023/06/08/cadence-allegro-whats-new-in-17-2-2016-qir-2-hotfix9/)
*   [What’s New in 17.4 2019 QIR3（hotfix019）](https://tiny-yhw.github.io//2023/06/08/cadence-allegro-whats-new-in-17-2-2016-qir-3-hotfix16/)
*   [What’s New in 17.4 2019 QIR4（hotfix028）](https://tiny-yhw.github.io//2023/06/08/cadence-allegro-whats-new-in-17-2-2016-qir-4-hotfix25/)
*   [BUG修复记录](https://layouto.lanzouf.com/i1LVI0tkym7i){:target="_blank"}

* * *

In-Design Analysis: New Flow and Enhancements 设计分析新流程改进
-------------------------------------------------------

Allegro In-Design Analysis environment融合了Allegro和Sigrity技术的精华，完全在PCB编辑器框架内为以下六种分析类型提供分析和检查功能:

*   Impedance
*   Coupling
*   Crosstalk
*   Reflection
*   Return Path
*   IR Drop

### New Design Setup Workflow 新设计设置工作流

通过设置不同检查的设计来准备分析。可以设置cross-section, DC nets, components, Xnets, and differential pairs。这些设置可以被保存并应用到其它设计中。从菜单View-Windows-Design Workfolw勾选以显示控制面板，从面板中选择你需要的项目进行设置

![algPN-136.gif](https://a1024.synology.me:222/images/algPN-136.gif)

### Define VRMs for Non-PowerTree IR Drop Analysis 为非PowerTree IR Drop分析定义VRM

在之前的版本需要PowerTree文件来运行IR Drop，此版本可以快速设置VRM，然后根据需要修改自动生成的sinks，以便在没有PowerTree文件的情况下运行IR Drop分析。

![algPN-137.gif](https://a1024.synology.me:222/images/algPN-137.gif)

Allegro Constraint Compiler Allegro规则编译器
----------------------------------------

在17.4 QIR 1版本中，进行了一些增强以提高可用性并支持新类型的规则。其中一个主要的增强是一个新的表格，支持对布线网络进行分割以驱动规则。

![algPN-138.gif](https://a1024.synology.me:222/images/algPN-138.gif)

### New Topology Table新拓扑表

一般情况下Physical and Spacing规则是被定义到整个Net或XNet上，但有时候我们可能需要对网络上个各个支段定义规则如Fanout, Pin Field, Breakout, Main Route等

![algPN-139.gif](https://a1024.synology.me:222/images/algPN-139.gif)

这个新的拓扑表允许Routing Sections在net或XNet中，用于在ObjectRule表中指定Physical, Spacing, and Electrical constraints。

按照Allegro Constraint Compiler (ACC)的逻辑，在不需要支持多个表变量的情况下，跨NetGroup, Bus, Interface等利用规则表是很重要的。为了进一步实现这一目标，拓扑表支持定义布线部分的起点/终点的器件的自动映射:

*   Component Type (Part, Discrete and Connector)
*   Component Class (IC, DISCRETE, IO)
*   XNet (Pass-through components)

拓扑表的主要好处之一是驱动网络部分的规则。为此，可以基于设计中的物理表示(Via, Width, and Region Entry/Exit transitions)来定义布线部分的开始/结束点。这些转换在画布上是可见的，它们动态地捕捉到拓扑中定义的适当位置。

![algPN-140.gif](https://a1024.synology.me:222/images/algPN-140.gif)

### ObjectRule Table对象规则表

添加了额外的列来驱动拓扑布线部分的物理、间距和电气规则。还有更多灵活的应用方式，因为ObjectRule表支持单独的规则分配、来自任何域的规则集关联以及Class到Class的间距规则。

![algPN-141.gif](https://a1024.synology.me:222/images/algPN-141.gif)

### Object Table 对象表

为了进一步实现设计独立表的目标，添加了两个新列，以根据从设计中的元件管脚提取的相关网络名称来定义组。这允许在具有公共有源器件或芯片组的设计中使用表，而不需要特定的映射别名来支持设计中的不同网络名称格式。

![algPN-142.gif](https://a1024.synology.me:222/images/algPN-142.gif)

一个新的内置函数`ByteLane`现在可用于快速生成数据字节通道组。

*   `ByteLane(x, y, z)`
    *   `x`\=字节通道号，从0开始
    *   `y`\=每个字节通道中的位数
    *   `z`\=每个位数的位数
*   示例:`ByteLane(1, 8, 2)`
    *   数字模式结果:08，09，10，11，12，13，14，15

![algPN-143.gif](https://a1024.synology.me:222/images/algPN-143.gif)

### Rule Specification Table 规则说明表

规则规格表用于捕获Physical, Spacing, and Electrical要求，以在规则管理器中创建规则集(CSet)。在许多情况下，物理和间距cset是从现有cset中派生出来的，只做了一些修改(走线宽度、间距等)。以前的版本使用默认CSet作为起点，但为了提供更大的灵活性，在表头中添加了一个新的关键字，以指定设计中的现有CSet作为起点。

![algPN-144.gif](https://a1024.synology.me:222/images/algPN-144.gif)

![algPN-145.gif](https://a1024.synology.me:222/images/algPN-145.gif)

Allegro Data Management (Version on Commit)版本管理
-----------------------------------------------

版本控制允许您在整个设计过程中捕获设计的版本快照，并为您提供一种参考或恢复到设计的先前版本的简单方法。可能的使用场景包括:

*   轻松尝试不同的设计策略
*   在网表更改前后保存数据库
*   在规则更改前后保存数据库

### Enable Data Management启用数据管理

Setup – User Preferences Unsupported category中allegro\_pulse\_enable选项勾选，使用此功能需要更改设置后重启一次

![algPN-146.gif](https://a1024.synology.me:222/images/algPN-146.gif)

启用上述选项后任务栏会有以下新的托盘图标如下图，对应File菜单也会增加几个菜单命令用于版本管理。

![algPN-147.gif](https://a1024.synology.me:222/images/algPN-147.gif)

### Embedded Mode Data Management (default)嵌入式模式数据管理(默认)

嵌入式模式中的数据管理提供了保存数据库快照的功能，该功能可以作为唯一指定的版本进行跟踪。本地区域默认为用户`Home`目录下的子文件夹名为`PULSE`.

使用File – Commit菜单命令，输入版本描述和任何相关的标签，保存设计快照及设计版本

![algPN-148.gif](https://a1024.synology.me:222/images/algPN-148.gif)

查看或恢复以前的版本可以使用File – Version Control。选择一个版本以查看详细信息和PDF预览，或者选择_反转_从弹出菜单将先前版本恢复到布局编辑器会话中。

![algPN-149.gif](https://a1024.synology.me:222/images/algPN-149.gif)

使用File – Copy_为_使用从版本1.0开始的重置版本历史从现有设计创建新设计。这通常用于“从头开始”的情况，即现有设计用作新设计的起点。

3D Canvas Update 3D画布更新
-----------------------

性能改进大大减少启动时间，对于大型设计尤其明显，减少内存使用容量提升性能

### 3D画布过滤器对话框

在运行3D Canvas时，增加一个过滤器对话框，用于设定哪些层或对象将被带入3D画布中

若希望取消此对话框可以从Setup – User Preferences – Display – 3D section设置hide\_unified\_filter\_dialog选项为不勾选

![algPN-150.gif](https://a1024.synology.me:222/images/algPN-150.gif)

### Nets Pane网络窗格

增加一个Nets面板，可以在3D画布中选择查看指定网络或指定网络组

![algPN-151.gif](https://a1024.synology.me:222/images/algPN-151.gif)

![algPN-152.gif](https://a1024.synology.me:222/images/algPN-152.gif)

选择指定的网络或网络组后，属于该网络的所有元素(clines, lines, vias, pins, and so on)将被列出来，该部分称为“元素”。可以可视化整个网络或选定网络中的单个元素。在下图中，使用新的消失亮显模式可视化了整个选定的电网。

![algPN-153.gif](https://a1024.synology.me:222/images/algPN-153.gif)

### Variable Highlighting 变量突出显示

之前在PCB中选择的元器件在3D画布中显示为选中状态(红色)，现在提供两种突出显示方式Dim and Vanish，这项设置从3D Canvas 菜单 Setup – Preferences – Appearances – Highlighting – Highlighting Modes中设置

下图展示了在PCB中选择了一个连接器时3D Canvas的展示情况

选定的元器件(连接器)为红色，所有其他元器件保持相同的颜色。

![algPN-155.gif](https://a1024.synology.me:222/images/algPN-155.gif)

Dim选定的元器件为红色，所有其他元器件为灰色

![algPN-156.gif](https://a1024.synology.me:222/images/algPN-156.gif)

Vanish选定的元器件为红色，所有其他元器件从视图中消失

![algPN-157.gif](https://a1024.synology.me:222/images/algPN-157.gif)

### Collision Detection Consistency With 2D 与2D的冲突检测一致性

算是一个错误修复，之前Place\_Bound无间距并排时，PCB不报DRC，但min\_spacing为零的3D画布中会报DRC，现在不再报了，保持和PCBDRC一致

![algPN-158.gif](https://a1024.synology.me:222/images/algPN-158.gif)

![algPN-159.gif](https://a1024.synology.me:222/images/algPN-159.gif)

Allegro ECAD-MCAD Library Creator Update（略，建库工具更新内容，需要时再继续补充）
-------------------------------------------------------------

DesignTrue DFM:New Stack Microvia over Core Via Rules 核心过孔规则上的新堆栈微孔
-------------------------------------------------------------------

核心过孔上的堆叠微孔的新规则现在在DesignTrue DFM制造设计(DFF)检查的扩展版本中可用。这些检查有助于避免整个制造过程中微孔桶破裂和通孔分层。

### Maximum Microvia over Cover Via覆盖过孔上的最大微孔数量

该规则管控在核心过孔上允许最大数量的堆叠微孔数量。该值必须是等于或大于的整数`0`.

下图显示了约束表单中的核心过孔规则上的最大微孔堆叠数为2时，DFM检查的结果

![algPN-179.gif](https://a1024.synology.me:222/images/algPN-179.gif)

![algPN-180.gif](https://a1024.synology.me:222/images/algPN-180.gif)

### Defining Core Vias定义核心过孔

没看懂原文如下

A core via is defined as any blind, buried via with a drill that passes through a dielectric layer with the Layer Function of Dielectric Core. The Layer function is set in the cross-section editor using the Layer Function drop down menu. Multiple Dielectric Cores may be defined in the cross-section.

![algPN-181.gif](https://a1024.synology.me:222/images/algPN-181.gif)

### Microvia to Microvia and Microvia Over Core Via Alignment微孔到微孔和核心过孔到微孔对准

微孔与微孔或Core Via中心对齐对于电镀稳定性至关重要，当需要在Core Via上叠微孔时，对于中心的偏移量有要求时，可以通过设置Analysis Modes – Design For Fabrication中Max uvia alignment tolerance值来限制偏移量

![algPN-182.gif](https://a1024.synology.me:222/images/algPN-182.gif)

这是一个偏移违规的示例

![algPN-183.gif](https://a1024.synology.me:222/images/algPN-183.gif)

### Enabling Microvia to Microvia and Microvia over Core Via Alignment Checks 对准检查开关

可以从规则管理器Manufacturing – Design for Manufacturing – DFF Constraint Sets – Holes中Alignment between uvias and Alignment between uvias stacked on core via打开或关闭对准检查项目是否启用

![algPN-184.gif](https://a1024.synology.me:222/images/algPN-184.gif)

Miscellaneous Updates 杂项更新
--------------------------

### Custom Icon Support for Toolbars 工具栏的自定义图标支持

可以选择本地图片格式\*.bmp, \*png, \*.jpg的图片作为指定命令的图标

![algPN-185.gif](https://a1024.synology.me:222/images/algPN-185.gif)

Find by Query Enhancements 表达式查询增强功能

Lines对象增加了一个Width属性，添加宽度有助于找到符合特定线宽值的所有线条。

![algPN-186.gif](https://a1024.synology.me:222/images/algPN-186.gif)