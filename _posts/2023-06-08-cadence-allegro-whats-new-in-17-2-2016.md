---
layout: post
title: Cadence Allegro What’s New in 17.2 2016
categories: Allegro
description: gertert
date: 2023-06-08
---

本文描述了Cadence Allegro PCB Editor在17.2基础版的新功能和增强功能。


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

17.2（除非单独声明否则包括之后版本）windows版本仅支持64位操作系统安装，（Win7-Win11均可），XP将不再被支持

![](https://tiny-y.asia/images/blog/2023/blog2022/Snipaste_2022-10-21_16-24-17.png)

Cadence® Allegro® 17.2-2016软件是过去十年中发布的最大版本，于2016年4月下旬发布

打开Cadence17.2的相关应用程序，可以不再使用切换器切换成对应版本也可用exe文件打开应用程序，若希望双击指定后缀文件如brd、dsn等打开指定版本还是需要使用switchversion.exe切换的

[Shape Operations](https://a1024.synology.me:1024/?p=2998)
----------------------------------------------------------

[Padstack Overhaul焊盘编辑器大修](https://a1024.synology.me:1024/?p=4156)
------------------------------------------------------------------

Layer support for Dynamic Shape Properties动态铜皮分层连接属性
----------------------------------------------------

对于动态铜的Pin/Via连接及隔离设定，在新的版本中能够分层来做细化的定义。

![172-algPN-410.gif](https://tiny-y.asia/images/blog/2023/172-algPN-410.gif)

支持的属性包括

*   Dyn\_clearance\_oversize\_array
*   Dyn\_clearance\_type
*   Dyn\_fixed\_therm\_width\_array
*   Dyn\_max\_thermal\_conns
*   Dyn\_min\_thermal\_conns
*   Dyn\_oversize\_therm\_width\_array
*   Dyn\_thermal\_best\_fit
*   Dyn\_thermal\_con\_type

### Cross Section Overhaul

新的层叠编辑器提供了所有功能的设置，如按区域设置层叠，动态处理未使用的焊盘和埋入式元器件设计。定义层叠特征时，可堆叠窗口中显示堆叠结构的动态图形。层叠图形中包括设置和显示反钻方向的功能。网格编辑功能允许您添加图层对或用户定义的图层数量

重新设计的叠构编辑设定，充分运用表格式的方法来进行相关设定。  
新的界面整合了Unused Pad Suppression与Embedded Component设定还有支持了非电气层的部分，如：Solder mask, Paste, Coverlay…等；另外对于Material的字段长度也扩展到250个字符。

![172-algPN-411.gif](https://tiny-y.asia/images/blog/2023/172-algPN-411.gif)

### Physical/All Tabs

获取横截面电子表格的缩小视图。支持的列是通常用于物理设计的列包括Objects, Layer Types, Thickness and Tolerances, Physical, Layer ID, Material name, Negative Artwork and Unused Pad Suppression.

选择All以包括“Physical”以及Signal Integrity and Embedded Component Design列出的所有内容。

### Functional Tabs

*   Info：显示总厚度和层数（Etch + Plane）
*   Lock：防止在电子表格中添加图层或更改值方面的编辑
*   Embedded Layers Setup：嵌入式组件设计的_设置_表单。以前位于设置 – 嵌入式组件设置中。
*   Unused Pads Suppression：非功能盘的设置表单。以前位于菜单Setup – Unused Pads Suppression中。
*   Refresh Materials：用于刷新materials.dat文件中的参数。

![172-algPN-412.gif](https://tiny-y.asia/images/blog/2023/172-algPN-412.gif)

### Multi-Cross Section Support for Rigid-Flex Design 支持定义刚柔结合板

横截面编辑器已得到增强，可支持多个堆叠，每个堆叠都能够支持导体和非导体层，例如阻焊层和覆盖层。横截面编辑器根据累积导体层提供每个堆叠的总厚度，以及包含掩模层厚度的选项。

首次启动时，编辑器仅显示一个选项卡“Primary”，默认堆叠显示在“Primary”选项卡中。

![172-algPN-415.gif](https://tiny-y.asia/images/blog/2023/172-algPN-415.gif)

使用菜单View – Multi-Stackup启用多堆叠模式

![172-algPN-416.gif](https://tiny-y.asia/images/blog/2023/172-algPN-416.gif)

*   所有堆叠选项卡 – 构成堆叠组合的所有导体和非导体层的位置
*   主选项卡 – 包含所有导体层（如导体和平面）的默认堆叠。它用于非区域应用程序，也用于表示要运行的放置/快速放置应用程序的设计大纲之外的区域。
*   用于添加新堆叠的控件 – 有两种方法可以添加新堆叠：
    *   点击顶部横幅上的 _+_
    *   单击主单元格右侧的Add Stackup单元格

![172-algPN-417.gif](https://tiny-y.asia/images/blog/2023/172-algPN-417.gif)

每个堆叠都支持复选框来控制相应堆叠的图层意图。

*   Primary Stackup – 由于此堆叠代表最大数量的导体层，并且被认为是“默认”堆叠，因此只能打开或关闭非导体层。如果必须删除导体图层，请单击所有堆叠选项卡并删除该列中的条目。
*   Rigid-Flex Designs - 主堆叠很可能是由最多导体层组成的刚性堆叠。创建额外的堆叠以支持柔性截面或较低数量的刚性截面。这些额外的堆栈映射到物理区域。可能没有必要为被视为主要部分创建物理区域。
*   Material Inlay - 初级堆叠很可能是PCB的主要部分。为镶嵌部分创建物理区域，使用不同的材料进行射频/模拟。

![172-algPN-419.gif](https://tiny-y.asia/images/blog/2023/172-algPN-419.gif)

### Cross Section Support for Non-Conductor Layers 非导体层的横截面支持

因为软硬结合板设计，支持非导体层的设定，如一般的mask及其他表面涂层皆能在新版本中设定。

![172-algPN-420.gif](https://tiny-y.asia/images/blog/2023/172-algPN-420.gif)

### Rigid-Flex Physical Zone Management刚柔结合物理区域管理

新增物理区域来分别定义软板或硬板的区域范围。

![172-algPN-425.gif](https://tiny-y.asia/images/blog/2023/172-algPN-421.gif)

New Database Classes and Subclasses新的数据库类和子类
--------------------------------------------

### Rigid Flex and Surface Finish Classes

Rigid Flex and Surface Finish Classes 刚柔和表面光洁度等级，新的子类可以更好地标识用于特定目的的子类组。这些类也被数据库中的其他函数（如堆叠）识别为具有特殊用例和应用程序的类。

*   Rigid Flex
    *   Zones
        *   Stack-up zones
        *   Transition zones
    *   Contains common subclasses for flex and rigid flex technology
        *   Masks
        *   Adhesives
        *   Bend geometry
    *   Additional user-defined subclasses may be added
    *   Mask layers may be recognized by stackup
    *   Layer types can be linked through the mask layer site file
*   Surface Finishes
    *   Represents the different materials and masks used for standard PCBs as well as rigid, and rigid-flex designs
        *   Precious metals plating
        *   OSP
    *   Additional user-defined subclasses may be added
    *   Metal mask layers may be recognized by Stack-up but there is no DRC checking for connectivity.
    *   Layer types can be linked through the mask layer site file

PCB编辑器数据库现在原生支持以下新的类结构，不仅支持刚柔结合设计，还支持标准刚性。新类/子类的结构化列表包括：

![172-algPN-427.gif](https://tiny-y.asia/images/blog/2023/172-algPN-426.gif)

### Design\_Outline and CUTOUTS subclasses

对于Board Geometry新加入了Design\_Outline及CUTOUTS的subclass用于指定板框外形和铣切区。

OUTLINE 子类仍可用于定义轮廓，因为不要求轮廓是闭合多边形，尽管它一直是首选。

部分功能将按这些层定义的板外形进行识别

*   Enhanced DRC capabilities – Object to board outline checks
    *   pad to board edge
    *   mask to cutout and/or board edge
    *   cutout to board edge
*   Rigid-flex support – Zone creation
    *   trimming of zone edges to DESIGN\_OULTINE edge
*   ECAD/MCAD collaboration
    *   Independent management of board outline and cutouts
    *   Eliminates determining what is an outline and/or cutout from other objects
    *   Enhanced STEP Export of outline and cutouts
*   Manufacturing
    *   Eliminates determining what is an outline and/or cutout from other objects

IDX 和 IDF 接口都识别并采用新的 DESIGN\_OUTLINE 和 CUTOUT 子类的使用。导入 IDF 或 IDX 时，电路板轮廓几何图形将映射到DESIGN\_OUTLINE子类。铣切区将映射到Cutouts子类。

IDF 导出将首先检查DESIGN\_OUTLINE和 CUTOUT 子类上是否存在几何图形，并使用这些几何图形导出电路板轮廓数据。如果DESIGN\_OUTLINE子类上没有几何图形，请在用户首选项设置中设置环境变量_allegro\_legacy\_board\_outline_以使用传统的电路板BOARD GEOMETRY – OUTLINE。

如果没有识别到电路板轮廓，IDX\_Out和 IPC-2581\_Out 将失败

![172-algPN-427.gif](https://tiny-y.asia/images/blog/2023/172-algPN-427.gif)

16.X版本brd用17.X打开时将自动将原BOARD GEOMETRY – OUTLINE层图形复制到DESIGN\_OUTLINE 和 CUTOUT 子类中，但会存在一些局限性

*   图形数据库中只能存在一个DESIGN\_OUTLINE几何图形
*   转换为DESIGN\_OUTLINE时，轮廓几何图形必须能够转换为形状。间隙、重叠和交叉几何将无法转换。
*   电路板轮廓内的OUTLINE图形被复制到 CUTOUT 子类
*   电路板轮廓之外的OUTLINE图形将被忽略.
*   文本和非连续的lines将被忽略.

Visibility Pane - Access to Mask Layers and Zones 面板增加层
-------------------------------------------------------

Visibility面板增强，允许设计人员更快、更高效地访问和控制图层内容。Visibility现在允许您快速访问，以轻松配置和查看不同的区域堆叠，而不是单一的堆叠方法。此窗格现在具有能够控制导体以外的图层。您现在可以轻松切换到单层视图并快速查看保存的各个图层。

### Layer Stackup

Cross Section创建的所有stackups在Layer stackup中均可见

### Masks

新的Visibility图层包含所有mask层，方便查看和切换

![172-algPN-428.gif](https://tiny-y.asia/images/blog/2023/172-algPN-428.gif)

### Dynamic Zone-based Placement

对于不同叠构层面的软硬结合板，其中顶部或底部可能因区域而异。现在PCB编辑器的放置功能是区域感知的，可识别最顶层或最底层，在摆放零件时能够依照所属的区域将零件摆放到正确的层面上。

![172-1.6.gif](https://tiny-y.asia/images/blog/2023/172-1.6.gif)

Enhanced Contour Routing 增强Contour布线功能
--------------------------------------

菜单Route – Unsupported Prototype – Enable Enhanced Contour用于在添加布线时通过遵循现有线路径。此功能在旧版 Contour 功能的基础上得到了改进，删除了连续的对话框弹出窗口，引入了简单的基于画布的双状态单击使用模型，并启用了现有连接线的推挤。non-contoured布线和contoured布线之间的过渡将针对线或圆弧拐角进行平滑处理。能让我们只许要在选择好物件之后点选要依附的目标及目的即能将走线快速完成。

![172-algPN-429.gif](https://tiny-y.asia/images/blog/2023/172-algPN-429.gif)

Shape Update 布设铜皮更新
-------------------

### Adding Dynamic XHatch Shapes增加动态网络铜

软硬结合板经常在布设铜皮是选用网络铜形式，这样铜重量更轻，材料弯曲时不易开裂。在 17.2 版本中，添加网格铜更方便，可以直接在增加铜皮时从option中type选择

![172-algPN-430.gif](https://tiny-y.asia/images/blog/2023/172-algPN-430.gif)

### Layer-based Property Settings

和新增的焊盘与铜皮的连接方式一样，铜皮同样增加相应的属性，可以分层设置相关的铜连接方式

![172-algPN-431.gif](https://tiny-y.asia/images/blog/2023/172-algPN-431.gif)

Inter Layer Checks for Rigid-Flex Design刚柔结合设计的层间检查
---------------------------------------------------

软硬结合板设计因分别拥有不同的mask及表面涂层，并且对于软板部分还会有弯折的区域，所以要能够确实做到相对的检查以避免设计因生产组装时发生错误，就能通过Inter Layer Checks制定相关检查条件。

### Understanding Inter Layer Check Rules了解层间检查规则

使用规则管理器Spacing – Inter Layer – Spacing打开层矩阵

![172-algPN-432.gif](https://tiny-y.asia/images/blog/2023/172-algPN-432.gif)

![172-algPN-433.gif](https://tiny-y.asia/images/blog/2023/172-algPN-433.gif)

层间检查不检查项目:

*   信号层（分层导体）间对象的检查，如TOP层和BOTTOM层
*   同一个层面上的物体间距检查.
*   不对Cline和Shape进行区分，其本质都是导体铜

未包含在层间检查中的其他类、子类和对象如下所示：

*   Drawing format
*   Analysis
*   DRC
*   Text (on any subclass)
*   Board geometry outline
*   Silk screen layers
*   Named dielectric layers

功能面板提供了一个过滤器用于方便选择特定类别的图层

![172-algPN-434.gif](https://tiny-y.asia/images/blog/2023/172-algPN-434.gif)

选中指定的层间检查项目如，可以在规则表中查看对应设置的规则项目

![172-algPN-435.gif](https://tiny-y.asia/images/blog/2023/172-algPN-435.gif)

规则表定义以下内容：

*   Layer 1：选择为第 1 层的子类名称
*   Layer 2：选择为第 2 层的子类名称
*   Type：要定义的特定检查类型。下拉列表提供了可能检查的列表
    *   Gap：所选子类图层上两个对象之间的最小间距值。
    *   Overlap：所选子类图层上两个对象之间的最小重叠值。

Gap 弯折区对Pin和Via的检查

![172-algPN-436.gif](https://tiny-y.asia/images/blog/2023/172-algPN-436.gif)

Overlap

![172-algPN-437.gif](https://tiny-y.asia/images/blog/2023/172-algPN-437.gif)

*   1 inside 2:定义为层 1 的子类上的几何必须包含在定义为层 2 的子类上的几何中。
*   2 inside 1:定义为层 2 的子类上的几何必须包含在定义为层 1 的子类上的几何中。

![172-algPN-438.gif](https://tiny-y.asia/images/blog/2023/172-algPN-438.gif)

*   Value:间距值
*   Enabled:启用或关闭此项检查
*   DRC Label:此字段允许您为第二个字符添加自己的 DRC 标记标签。第一个字符保留字符“I”用于层间检查。第二个字符可以是a-z、A-z、0-9
*   DRC Subclass:定义 DRC 标记的显示层。下拉菜单列出了可在其上显示规则的 DRC 标记的可用子类。在 DRC 类下添加了一个新的 INTER\_LAYER 子类，以帮助将层间 DRC 与其他 DRC 区分开来。
*   Description:可以添加规则的注释或说明以供参考。此描述只能在约束管理器中的规则表窗体中看到。
*   Delete:在“删除”列中选择“X”将删除规则条目。

![172-algPN-439.gif](https://tiny-y.asia/images/blog/2023/172-algPN-439.gif)

### Enabling On-line Inter-Layer Checking启用在线层间检查

从Analysis Modes访问，其默认是关闭的，需要时将on-line inter layer checks设置为On或Batch

![172-algPN-440.gif](https://tiny-y.asia/images/blog/2023/172-algPN-440.gif)

Manufacturing Prep - Rigid-Flex Design制造准备 - 刚柔结合设计
---------------------------------------------------

### Multiple Stackup Table多层层叠表

Manufacture – Cross Section Chart可以生成一个层叠表，该表支持所有导体和非导体层、材料和厚度的条目。

![172-algPN-441.gif](https://tiny-y.asia/images/blog/2023/172-algPN-441.gif)

### Dynamic Fillets

可以分层控制Dynamic fillets（一般是泪滴），控制设置位于Cross Section Editor的Physical中

### Missing Tapers Report

可输出一个新报告，报告线宽变化处缺少Tapers的地方

Embedded Component Design Updates嵌入式器件设计更新
------------------------------------------

*   “复制”命令现在支持嵌入的package symbols。
*   现在可以在dummy components上使用“Swap Components”命令。
*   现在支持嵌入式Soldermask subclasses（类似于Pastemask）。
*   16.6-2015 ISR 中提供了对嵌入式组件的 Extracta 支持。

![172-algPN-442.gif](https://tiny-y.asia/images/blog/2023/172-algPN-442.gif)

Backdrill Overhaul背钻大修
----------------------

使用方法详见[Allegro 17.2 Back Drill背钻应用](https://a1024.synology.me:1024/?p=3000)

[Shape Edit Application Mode](https://a1024.synology.me:1024/?p=4139)
---------------------------------------------------------------------

[Color Dialog Enhancements颜色对话框增强功能](https://a1024.synology.me:1024/?p=1075)
----------------------------------------------------------------------------

Tabbed Routing
--------------

Tabbed routing是新的布线方式，主要针对高速讯号在Breakout的平行走线间加入梯型的Shape在其走线上面做为控制阻抗(Impedance)及减低在开阔区域的远场串扰(Crosstalk)问题。

更多介绍参考[Allegro Tabbed Routing 梯形凸块布线](https://a1024.synology.me:1024/?p=1928)

![172-algPN-487.gif](https://tiny-y.asia/images/blog/2023/172-algPN-487.gif)

![172-algPN-488.gif](https://tiny-y.asia/images/blog/2023/172-algPN-488.gif)

High Speed Interconnect Enhancements高速互连增强功能
--------------------------------------------

return path vias在16.6版本中被引入，允许对差分对应用，在此版本中增加对单线的应用，在Add Connect命令时从右键菜单选择Return Path Vias (Prototype)启用此功能

![172-algPN-484.gif](https://tiny-y.asia/images/blog/2023/172-algPN-484.gif)

![172-algPN-485.gif](https://tiny-y.asia/images/blog/2023/172-algPN-485.gif)

从下面面板选择设置相应的参数即可自动添加固定的回流地孔

![172-algPN-486.gif](https://tiny-y.asia/images/blog/2023/172-algPN-486.gif)

Via Structures过孔结构
------------------

create via structure命令允许您创建两种类型的通孔结构 - 标准和高速。还有一个选项可用于自动导出XML文件，该文件可用于通过其他PCB / SiP数据库和Sigrity 3DEM（仅限高速）中的结构定义导入/导出。

Standard Via Structure标准通孔结构

*   菜单：Route – Via Structure – Create – Standard
*   目标使用模型：单一信号的Trace / Via以及Fan-out
*   支持的对象：Traces, Vias
*   连接性：需要所有的Via都有连接(单一信号)

![172-8.4.gif](https://tiny-y.asia/images/blog/2023/172-8.6.gif)

High Speed Via Structure高速通孔结构

*   菜单： Route – Via Structure – Create – High Speed
*   目标使用模型：Differential pair via搭配Return Path Vias及custom plane voids
*   支持的对象：Traces, Vias, Static Shapes (no voids), Route Keep out
*   连接性：多信号

![172-algPN-489.gif](https://tiny-y.asia/images/blog/2023/172-algPN-489.gif)

定义和增加过孔结构

![172-8.3.gif](https://tiny-y.asia/images/blog/2023/172-8.3.gif)

![172-8.4.gif](https://tiny-y.asia/images/blog/2023/172-8.4.gif)

![172-8.4.gif](https://tiny-y.asia/images/blog/2023/172-8.5.gif)

Acute Angle Detection锐角检测
-------------------------

对于锐角的检查，使用者可以通过定义锐角角度来将以下四种情况进行确认。

• Line to Pad  
• Line to Shape  
• Shape Edge to Edge  
• Line to Line

更多介绍见[Allegro 17.2 actue angle detection 锐角检测](https://a1024.synology.me:1024/?p=3150)

Drill Hole DRC 钻孔 DRC
---------------------

透过Check holes within pads的设定，无论Hole有无Pad都会按照CM Spacing内Hole的间距设定执行检查。（16.6及之前的版本有pad的hole是不做规则中定义的hole检查的）

此选项默认为off模式，即和之前的版本是一样的，若需使用需可以打开才行

![172-algPN-496.gif](https://tiny-y.asia/images/blog/2023/172-algPN-496.gif)

![172-algPN-497.gif](https://tiny-y.asia/images/blog/2023/172-algPN-497.gif)

IDX Enhanced Features 增强功能
--------------------------

17.2 版本在 EDMD 架构 （IDX） 中公开了增强的功能支持。这些功能受 IDX 格式支持，但您的环境中的特定 MCAD 工具可能不支持这些功能。

支持的增强功能集包括：

*   User Preference Settings
*   IDX Properties
*   Component Symbol Support
*   User Defined Layer and External Copper layer Support
*   Hole/Slot support
*   IDX Compare Utility

详情（略）基本不会用到，需要时再进行详细编写

Database and Misc Enhancements数据库和其他增强功能
----------------------------------------

### Refresh Symbol – Maintain Padstacks

选择更新封装时如果勾选Keep design padstack names for symbol pins那么在Refresh Symbol时能够选择是否要保留现在设计中的Padstack名称而不被刷新。

![172-algPN-508.gif](https://tiny-y.asia/images/blog/2023/172-algPN-508.gif)

### Performance Improvements

CPU效能提升10-20%。  
Import logic对于有很多Pin数的Device(>2k pins)条件时，处理速度比以往都要快。

### New Properties新属性

*   BOARD\_THICKNESS\_TOLERANCE\_PLUS - Adjusts the overall board thickness in the IDX flow.
*   IDX\_OTHER\_OUTLINE - Allows a bi-directional exchange of the shape if the user-defined shape is not originally defined in the MCAD tool.
*   PACKAGE\_OFFSET\_TOP and the PACKAGE\_OFFSET\_BOTTOM - Uses a value that offsets the component height across the surface of the board to account for pastemask thickness.
*   NO\_PCB\_BUNDLE - Set on a NetGroup/bus object, it prevents creating/updating bundles and visibility objects. The property is controlled by Constraint Manager – Properties – Ratsnest Bundle Property table, Disable Automatic Ratsnest Bundle column. On option selected for a group implies that the property is set.
*   IGNORE\_SHAPE\_ISLAND - Applied to etch rectangles or shapes to suppress their reporting in the shape island report or the delete island command.
*   BONDFINGER\_DRC\_DISABLED - Applied at design level in ICP designs (.mcm and .sip) to disable bondfinger DRC checks.
*   DOGBONE\_FANOUT - Set to an Allegro component and forces Specctra to apply dogbone fanout pattern to it. This property is usually applied to BGAs with irregular pin matrix.
*   PKG\_PIN1\_ORIENTATION - Used in the IDX flow. This property can be assigned to a pin in the symbol editor. It defines pin 1 to the MCAD system. By default, Allegro PCB Editor uses the pinOneCfg.txt to identify pin 1 by its name.
*   MARKING\_USAGE - Applied to rectangle, filled rectangle, shape, figure, and line. This property is used in IPC2581 Export and indicates the marking usage for the package geometry.
*   ASI\_MODEL - Applied to component instance and definition, this property is used to pass model assignments to Cadence Sigrity applications through new integrated translator.
*   DYN\_FILL\_XHATCH\_CELLS - Controls how aggressive dynamic shapes fill partial crosshatch opens. Normally this is set via the global dynamic shape dialog or on the instance base shape dialog.
*   DYN\_FIXED\_THERM\_WIDTH\_ARRAY - Allows by layer control of a pin or via’s thermal line width. This property suppresses Min Line Width DRC errors for thermal clines in dynamic shapes.
*   DYN\_OVERSIZE\_THERM\_WIDTH\_ARRAY - Allows by layer control of thermal width overrides. This property specifies the width of the connect lines added as thermal relief. The width of the reliefs should be less than or equal to the width of the hatch line to which they connect.
*   DYN\_FIXED\_THERM\_WIDTH\_ARRAY - Allows by layer control of a pin or via’s thermal line width. This property suppresses Min Line Width DRC errors for thermal clines in dynamic shapes.
*   DYN\_CLEARANCE\_OVERSIZE\_ARRAY - Allows by layer control of a pin or vias dynamic shape voiding. This property overrides the value in the Oversize values field in the Clearances tab in the Shapes Instance Parameters dialog, and increases the clearance around the specified element. The value is a positive design unit. Negative oversize is not supported.
*   REVISION\_ID - Set on the root design, symbol definition and padstack. This property is added for future work and currently is not in use.
*   ADJACENT\_LAYER\_KEEPOUT\_ABOVE - Applies to pins and vias this property works in conjunction with the adjacent keepout pad type built into padstacks. The property controls the number of layers above the start of a pin or via that a route keepout should be generated.
*   ADJACENT\_LAYER\_KEEPOUT\_BELOW - Applies to pins and vias this property works in conjunction with the adjacent keepout pad type built into padstacks. The property controls the number of layers below the end of a pin or via that a route keepout should be generated.
*   PINS\_ALLOWED - Applies to shapes or filled rectangles that are route keepouts this property permits pins within the keepout.
*   NODRC\_SYM\_SHAPE\_SOLDERMASK - Applies to root design, symbol instance and symbol definition. When present, inhibits mask to shape DRC against any shape within a symbol. Suggested model is to assign it in the symbol editor to its design root, so that it inhibits these DRCs when the symbol is placed in a design.
*   PIN\_GLOBAL\_FIDUCIAL - Applies to pin that uses a fiducial padstack. This property indicates that a pin is a global fiducial and is used in IPC25281 output to meet the standard.
*   IDX\_FEATURE\_MODE - Applies to a root design, this property specifies the mode of the IDX export as STANDARD or ENHANCED.

### Modified Properties修改的属性

*   DYN\_OVERSIZE\_THERM\_WIDTH - Cannot be applied to pins or vias now. DYN\_OVERSIZE\_THERM\_WIDTH\_ARRAY replaces this property for pins and vias.
*   DYN\_FIXED\_THERM\_WIDTH - Cannot be applied to pins or vias. DYN\_FIXED\_THERM\_WIDTH\_ARRAY replaces this property for pins and vias.
*   DYN\_THERMAL\_CON\_TYPE - Can now be applied by layer or layer type.
*   DYN\_THERMAL\_BEST\_FIT - Can now be applied by layer or layer type.
*   DYN\_MIN\_THERMAL\_CONNS - Can now be applied by layer or layer type.
*   DYN\_MAX\_THERMAL\_CONNS - Now applies to subclass design unit array.
*   LIBRARY\_PATH - Supports padstacks in addition to symbols. If it is not set, either the padstack was created in pre-17.2 Allegro PCB Editor or was created within the design (brd, mcm, sip or dra).
*   NODRC\_SYM\_PIN\_SOLDERMASK - Can now be applied to symbols to suppress soldermask DRCs. The use model is to build it into the footprint - apply at design level in symbol editor.
*   NODRC\_SYM\_PIN\_PASTEMASK - Can now be applied to symbols to suppress pastemask DRCs. The use model is to build it into the footprint - apply at design level in symbol editor.
*   DYN\_CLEARANCE\_TYPE - Can now be applied by layer or layer type.
*   DYN\_CLEARANCE\_OVERSIZE - Not supported on pins or vias. DYN\_CLEARANCE\_OVERSIZE\_ARRAY replaces this property.
*   VERSION\_ID - Can now be applied to padstacks.
*   DYN\_FIXED\_THERM\_WIDTH - Not supported on pins or vias. DYN\_FIXED\_THERM\_WIDTH\_ARRAY replaces this property.
*   VOID\_SAME\_NET - Can now be supported on etch shapes and etch filled rectangles.
*   IC\_DESIGN\_NET\_NAME - Can now support rectangle, fill rectangle, and shape.
*   IDX\_EXCLUDE - Can now support Generic groups.
*   PKGDEF\_ALT\_STEP\_FILE - Can now be applied to component definition and symbol instance defines the mapped STEP model for the package
*   PKGDEF\_ALT\_STEP\_TRANSFORMATION - Can now be applied to component definition and symbol instance defines 3D transformation between the mapped STEP model and the package.

RF PCB Enhancements射频 PCB 增强功能
------------------------------

### RF Status Display Enhancements射频状态显示增强功能

要查看原理图和布局之间RF元件的任何变化，status命令已得到增强，可在“Status”对话框中显示RF Status。

“Status”对话框中添加了一个新的“RF Status”选项卡，该选项卡仅在启用“RF/Analog”选项时才可见。

![172-algPN-519.gif](https://tiny-y.asia/images/blog/2023/172-algPN-519.gif)

使用此新选项，您可以比较原理图和物理设计数据并查看更改。如果单击颜色框，将显示每个更改的详细报告。

### Clearance Initialization Enhancements间隙初始化增强功能

在 17.2 中，间隙初始化设置已与初始化命令集成。rf\_ac\_init命令中还提供了一个新选项，用于启用全局间隙设置的编辑。

![172-algPN-520.gif](https://tiny-y.asia/images/blog/2023/172-algPN-520.gif)

### Cross-probing between Schematic and Layout Enhancements

rf\_autoplace and rf\_change 命令现在支持在元件选择阶段对原理图和布局进行交互。

通过单击原理图画布选择元件或引脚时，也会在布局编辑器和“Options”选项卡中选择相应的符号。

![172-algPN-521.gif](https://tiny-y.asia/images/blog/2023/172-algPN-521.gif)