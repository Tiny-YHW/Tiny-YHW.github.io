---
layout: post
title: Cadence Allegro What’s New in 17.4-2019
categories: Allegro
description: 
date: 2023-06-12
---

本文描述了Cadence Allegro PCB Editor在17.4-2019基础版中的增强和改进


* * *

**关联**

*   [What’s New in 17.4 2019](https://tiny-yhw.github.io//2023/06/12/cadence-allegro-whats-new-in-17-4-2019/)
*   [What’s New in 17.4 2019 QIR1（hotfix7）](https://tiny-yhw.github.io//2023/06/12/cadence-allegro-whats-new-in-17-4-qir1-hotfix-007/)
*   [What’s New in 17.4 2019 QIR2（hotfix13）](https://tiny-yhw.github.io//2023/06/12/cadence-allegro-whats-new-in-17-4-qir2-hotfix-013/)
*   [What’s New in 17.4 2019 QIR3（hotfix19）](https://tiny-yhw.github.io//2023/06/12/cadence-allegro-whats-new-in-17-4-qir3-hotfix-019/)
*   [What’s New in 17.4 2019 QIR4（hotfix28）](https://tiny-yhw.github.io//2023/06/12/cadence-allegro-whats-new-in-17-4-qir4-hotfix-028/)
*   [BUG修复记录](https://layouto.lanzouf.com/i1LVI0tkym7i){:target="_blank"}

* * *

17.2 Database Compatibility Mode 17.2数据库兼容模式
--------------------------------------------

使用17.2兼容功能，您可以在17.4-2019版中打开17.2数据库并对其进行处理，而无需将其保存为新的17.4数据库格式

您可以更改数据库，但只能更改与17.2兼容的数据库。

即使启用了兼容模式，在当前版本中打开的17.4设计仍将保持17.4数据库格式。

在17.4-2019版本中打开的16.6版本数据库将在此模式激活时以17.2格式保存。

从用户首选项设置database\_compatibility\_mode值为17.2激活兼容模式

![174algPN_base-2.gif](https://tiny-y.asia/images/blog/2023/174algPN_base-2.gif)

在17.4-2019中打开17.2-2016版设计时，如果启用了兼容模式，将显示一个对话框，指示该模式处于活动状态。

您可以决定保持17.2数据库格式或禁用该模式以启用新版本(17.4-2019)功能，并以17.4-2019数据库格式保存设计。

![174algPN_base-3.gif](https://tiny-y.asia/images/blog/2023/174algPN_base-3.gif)

在兼容模式下打开设计时，窗口标题栏和状态栏会显示_17.2兼容模式_。

如果在17.4中打开17.2设计，禁用兼容模式，将显示一个对话框，指示数据库将更新到当前软件版本。

![174algPN_base-4.gif](https://tiny-y.asia/images/blog/2023/174algPN_base-4.gif)

Symphony Team Design Option 协同设计选项
----------------------------------

Allegro® Physical Viewer Plus可以支持Symphony Team Design，以审查和标记正在进行工作的设计

Symphony Team Design Option在以下产品中均可使用

*   Allegro PCB Designer and Allegro Venture PCB Designer
    *   PCB design, constraint management, in-circuit testing and manufacturing verification, signal integrity (SI) analysis screening
*   Allegro Physical Viewer Plus
    *   Full viewer functionality with mark-up capabilities. (Mechanical, Regulatory, Manufacturing Engineering reviews)
*   Allegro Package Designer+
    *   IC/Packaging design support
*   Allegro Sigrity SI
    *   Real-time analysis of active database as work is completed
    *   Exchange of advanced signal integrity results with PCB Designer

### 规则管理增强

*   不再需要设置用户首选项即可访问
*   允许协作者进入规则管理，其它人仍可并行设计
*   几乎所有的规则项目可以在协同模式下编辑

### 17.2 Compatibility Mode 17.2兼容模式

协同模式同样支持开启协同，加入协作时会有下面的提示，此时客户端也将处于兼容模式

![174algPN_base-5.gif](https://tiny-y.asia/images/blog/2023/174algPN_base-5.gif)

这种新模式不允许17.2版客户端连接到17.4版Symphony服务器，但会阻止将17.2版数据库更新为17.4版格式。

Hierarchical Route and Via Keepouts 分层布线和过孔禁布
---------------------------------------------

在Symbol Editor环境下增加禁布图形是新增层类别，可以对指定类别的层绘制禁布图形，这些禁布图形将在其被放入PCB中时一并映射到对应的设计层中，这些层类别包括OUTER\_LAYERS, INNER\_SIGNAL\_LAYERS, and INNER\_PLANE\_LAYERS

![174algPN_base-6.gif](https://tiny-y.asia/images/blog/2023/174algPN_base-6.gif)

Allegro Constraint Complier 规则编译器
---------------------------------

17.4-2019版本引入了Allegro Constraint Compiler (ACC)

这是一种支持将设计约束从外部来源直接自动转换到Constraint Manager的基础架构。ACC并不是约束管理器的替代品，而是一种基于制造商指南在接口级注入约束的机制。ACC用于在设计中植入初始约束信息，或更新具有现有约束的设计。在最简单的层面上，ACC使用设计的连接性(Buses, Differential Pairs, Nets, and so on)以及“数据不可知”的约束信息来为设计中的各种接口创建特定的规则。

Allegro约束编译器的优势

*   由于从设计到设计的单一来源复用，确保了一致的约束条目
*   促进规则管理器(Differential Pairs, Net Classes, Net Groups Match Groups, and expanded Constraint Rule Sets)的自动生成
*   通过使用避免手动操作_一对多_约束展开将规则向下传播到最低层，生成所有支持对象和组

IPC 2581 Spec Properties 规格属性
-----------------------------

IPC-2581是XML格式的制造数据文件，包含制造、装配和测试印刷电路板(PCB)所需的信息。IPC-2581格式允许包含可能附加到特定对象的描述性细节，例如通常显示在制造或装配图中的装配说明和/或制造注释。指令(或注解)被定义为一个规范，或者用IPC-2581术语来说，一个规范。规格作为组件的附件或通用设计数据包含在内，可用于后期设计流程。

`SPEC`是IPC-2581数据中由名称标识的XML元素(比如，`FAB NOTES`)并包含一个或多个组成`SPEC`定义。在……里_FAB笔记_例如，传统方法是向制造图添加注释，并创建图像层或文档文件(每个注释项)。这需要打开图纸或文件来查找和查看制造说明。

通过定义一个`SPEC`由制造注释组成，注释成为IPC-2581数据的一部分，并由IPC-2581查看工具直接读取，减少了定位正确的图纸或文档来读取注释的需要。

另一个例子是为要添加到零件的散热器定义装配注释。组装说明可能会指示用户先添加特定的热环氧树脂，然后在应用环氧树脂后添加散热器。

在Allegro /OrCAD PCB Editor和Allegro Package Designer+ (APD+)的17.4-2019版中，您可以定义`SPEC`元素，并将它们应用于电路板绘图、组件或特定元素。创建等级库后，可以将其导出到其他设计可以导入的等级库模板中。

Mask Defined Pin Annular Ring Check
-----------------------------------

一个新的Mask Defined Pad检查已添加到Manufacturing Annular Ring检查的设计和DesignTrue DFM向导模板文件中。当谈到阻焊层与引脚焊盘尺寸大小时，有两种常见的焊盘定义方式。第一种是metal-defined的焊盘(有时称为non-mask defined的焊盘)，阻焊层开口通常大于引脚焊盘。另一种是mask-defined的焊盘，其中阻焊层尺寸通常小于引脚焊盘。mask-defined的焊盘通常用于BGA元件，以将焊球包含在引脚焊盘内，并防止焊料流出。

![174algPN_base-7.gif](https://tiny-y.asia/images/blog/2023/174algPN_base-7.gif)

Via Array Update 阵列过孔更新
-----------------------

17.4-2019版本新增功能添加一个阵列过孔命令，用于添加、更新和删除许多不同的阵列过孔类型。屏幕动态通过让您在放置阵列之前动态调整它们，为您提供控制和反馈。新添加的视觉效果和图形使阵列易于理解，让您第一时间得到您想要的东西。

![174algPN_base-9.gif](https://tiny-y.asia/images/blog/2023/174algPN_base-9.gif)

使用Via Array命令将各种排列的过孔或结构添加到设计中。您可以轻松选择阵列的起点、位置和几何图形(对象之间的间距)。使用现有的传统控件进行预览，遵循DRCs，并扩展选择以包括网络的所有对象。之前被称为_boundary_和_matrix arrays_，以便于使用，并提供以下阵列类型:

![174algPN_base-10.gif](https://tiny-y.asia/images/blog/2023/174algPN_base-10.gif)

Contour Routing Update
----------------------

17.4-2019版本现在支持先前的增强Contour行为作为默认Contour绘制方法。除了以前支持的latching/unlatching and shoving功能之外，此版本还通过添加额外的间距控制和完全区域规则支持。使用中提供的等值线功能，精确快速地依附复杂的几何图形及其路径。

Copy/Paste Update 复制/粘贴更新
-------------------------

像其它传统软件一样，现在复制支持将存在存在一个类似剪切板的地方，可以使用粘贴命令将暂存在剪切板的图形

### Copy

Copy命令现在将选定的对象添加到缓冲区，并自动启动Paste命令来允许在画布上放置对象。

### Paste

Paste命令支持所有传统的“复制”选项以及对shape net保留的新支持。除了这些选项之外，粘贴还有两种不同的方式。

*   单一位置粘贴
    *   每次单击复制对象并粘贴到一个位置
    *   对象捕捉到单个选定对象或位置
*   多位置粘贴
    *   通过窗口选择在多个位置复制和粘贴对象
    *   对象捕捉到所有选定的对象

Via Structure Update过孔结构更新
--------------------------

17.4-2019版本中的新增功能是single unified Create Structure对话框。该对话框将以前的Standard, High Speed, and L-Comp合并为一个易于使用的对话框，同时还添加了关于如何创建每个结构的描述和使用指南。图形提供了每种结构的可视化示例，使得识别每种结构的可能用例更加容易。

![174algPN_base-11.gif](https://tiny-y.asia/images/blog/2023/174algPN_base-11.gif)

Route – Structures – Create命令支持创建以下三种不同类型的结构

*   Standard Via Structure (SVS)
    *   Supported Objects – Traces and Vias
    *   Connectivity Support – Objects can connect to up to one net
    *   Export Format – eXML
*   High Speed Via Structure (HVS)
    *   Supported Objects – Traces, Vias, Static Shapes, Route Keepouts
    *   Connectivity Support – Objects can connect to up to two nets (one primary, one return)
    *   Export Format – eXML
*   Inductance Compensation Structure (L\_Comp)
    *   Supported Objects – Traces and Route Keepouts
    *   Connectivity Support – Objects can connect to up to one net
    *   Export Format – eXML

结构灵活，适应性强。如果任何一块etch or circuit要重复使用多次，结构提供了一种快速的方式来添加、刷新和替换它们。使用示例包括但不限于以下内容:

*   Antennas
*   Coils
*   High-speed “launches”
*   HDI structures
*   BGA pin escapes
*   RF Structures

3D Canvas Update 3D画布更新
-----------------------

### Usability Improvements Associated with Cutting Plane 与切割平面相关的可用性改进

切割平面功能现在更容易使用。它的调用现在是通过一个context菜单完成的，用户可调整的设置现在位于选项窗格中。这项功能的性能也有了很大的提高。

![174algPN_base-12.gif](https://tiny-y.asia/images/blog/2023/174algPN_base-12.gif)

![174algPN_base-13.gif](https://tiny-y.asia/images/blog/2023/174algPN_base-13.gif)

Mechanical Symbol Transparency 器件透明度
------------------------------------

Setup – Preferences – Symbol Representations可以调节机械对象的透明度

![174algPN_base-14.gif](https://tiny-y.asia/images/blog/2023/174algPN_base-14.gif)

Symbol Representation Using DFA\_Bound Shapes 使用DFA\_Bound作为器件外形
----------------------------------------------------------------

将PCB设计引入3D Canvas时，如果封装外形没有映射到它的STEP模型，3D Canvas当前使用Place\_Bound以及height属性来创建三维。在17.4-2019版本中，您可以选择使用现有的Place\_Bound或新添加的DFA\_Bound。

创建DFA\_Bound作为MMC (Maxim Material Condition)允许您在3D画布中使用模型之间的最坏情况场景进行间距检查

从用户首选项Setup – User Preferences – Display – 3D中设置3D\_symbol\_include\_dfa\_bound勾选以启用此功能或者通过在3D画布中使用Setup – Preferences设置Boundary Shape Source

![174algPN_base-15.gif](https://tiny-y.asia/images/blog/2023/174algPN_base-15.gif)

Unplated Holes in Footprints 焊盘图形中的非金属化孔
----------------------------------------

现在3D画布中非金属化孔可以以非金属化的形式展示出来了（之前的版本仍然是显示金属化的）

![174algPN_base-16.gif](https://tiny-y.asia/images/blog/2023/174algPN_base-16.gif)

### STEP Models and Pastemask 锡膏厚度模型

3D模型中可以指定锡膏厚度以真实的模拟实际情况，

![174algPN_base-17.gif](https://tiny-y.asia/images/blog/2023/174algPN_base-17.gif)

通过用户首选项Setup – User Preferences – Display中的3D\_symbol\_place\_on\_pastemask设置是否使用锡膏厚度值

![174algPN_base-18.gif](https://tiny-y.asia/images/blog/2023/174algPN_base-18.gif)

### Outer Layers Only Mode仅外层模式

通过用户首选项Setup – User Preferences – Display – 3D中的3D\_canvas\_skinning设置仅显示器件的外形和PCB的外层图形，这样可以减少数据量和内存占用提供更快的运行方式