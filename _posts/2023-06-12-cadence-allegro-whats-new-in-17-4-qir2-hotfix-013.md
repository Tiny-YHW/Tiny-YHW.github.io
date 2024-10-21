---
layout: post
title: Cadence Allegro What’s New in 17.4-2019 QIR2（hotfix013)
categories: Allegro
description: 
date: 2023-06-12
---

本文描述了Cadence Allegro PCB Editor在17.4-2019 QIR2（hotfix013）中的增强和改进


* * *

**关联**

*   [What’s New in 17.4 2019](https://tiny-yhw.github.io//2023/06/12/cadence-allegro-whats-new-in-17-4-2019/)
*   [What’s New in 17.4 2019 QIR1（hotfix7）](https://tiny-yhw.github.io//2023/06/12/cadence-allegro-whats-new-in-17-4-qir1-hotfix-007/)
*   [What’s New in 17.4 2019 QIR2（hotfix13）](https://tiny-yhw.github.io//2023/06/12/cadence-allegro-whats-new-in-17-4-qir2-hotfix-013/)
*   [What’s New in 17.4 2019 QIR3（hotfix19）](https://tiny-yhw.github.io//2023/06/12/cadence-allegro-whats-new-in-17-4-qir3-hotfix-019/)
*   [What’s New in 17.4 2019 QIR4（hotfix28）](https://tiny-yhw.github.io//2023/06/12/cadence-allegro-whats-new-in-17-4-qir4-hotfix-028/)
*   [BUG修复记录](https://layouto.lanzouf.com/i1LVI0tkym7i){:target="_blank"}

* * *

主要更新
----

Allegro 布线速度和效能提升  
全新 3D Model Mapping 功能，可一键完成对齐的模型资料。  
动态铜箔增强功能，大大提高了在拉线时动态铜箔的更新效能。

Dynamic Shape Enhancements动态铜皮增强
--------------------------------

### Dynamic Shape Layer Parameters 分层动态铜皮参数

新增一个动态铜皮层管理界面，从菜单Shape-Layer Dynamic Params……访问

该功能允许分别对不同的设计层定制不同的默认铜皮参数，选定指定层设置对应的参数，则对应层的铜皮将按指定参数进行更新

![algPN-96.gif](https://tiny-y.asia/images/blog/2023/algPN-96.gif)

### Dynamic Fill Mode “Fast” 动态铜皮Fast模式

“Fast”替代原“Rough”模式，此模式下铜皮更新的效率更高（超级高，在进行大批量更新时，效能提升明显），建议优选此模式

![algPN-97.gif](https://tiny-y.asia/images/blog/2023/algPN-97.gif)

3D Canvas Update 3D画布更新
-----------------------

### Model Mapper Functionality 模型映射器功能

新的映射器包含之前的STEP - Package Mapping的所有功能，但做了以下增强

*   支持更多CAD文件格式
*   由于使用了更详细的模型，提高了精确度
*   3D画布的加载时间更快
*   大多数情况下可以实现一键(自动)映射
*   支持按x/y/x坐标点和角度对齐模型
*   更简单的将模型映射到PCB的top or bottom层
*   Ability to quickly add and position mechanical models to a PCB using the same GUI
*   Ability to manually move/position models using a manipulator controller
*   快速按x/y/x轴旋转模型
*   支持从电路板或GUI列表中选择封装、器件或机械模型
*   能够使用Full Board view or a Device Only (postage stamp)视图查看板映射

使用3D Mapper需要设置首选项设置Setup – Preferences – Appearance – Symbol Representation，并在3DCanvas首选项中设置红框的选项是才可使用

![algPN-98.gif](https://tiny-y.asia/images/blog/2023/algPN-98.gif)

如果选择第一个或第五个选项将收到以下提示

![algPN-99.gif](https://tiny-y.asia/images/blog/2023/algPN-99.gif)

Model Mapper Tab
----------------

在3D画布中提供一个新的3D Mapper选项面板

下图是dra模式对应的选项

![algPN-100.gif](https://tiny-y.asia/images/blog/2023/algPN-100.gif)

稀土是brd模式对应的选项

![algPN-101.gif](https://tiny-y.asia/images/blog/2023/algPN-101.gif)

选择一个需要映射的器件分类形式Footprint, Device or Mechanical.

![algPN-102.gif](https://tiny-y.asia/images/blog/2023/algPN-102.gif)

从清单中可以看到当前设计包含的所有器件类型

![algPN-103.gif](https://tiny-y.asia/images/blog/2023/algPN-103.gif)

选择从整板查看或仅单器件查看的方式映射器件

![algPN-104.gif](https://tiny-y.asia/images/blog/2023/algPN-104.gif)

### Model Mapper GUI Functionality模型映射器GUI功能

3D映射文件(`.map`)可以通过点击_导入_或者通过单击Import导入 or export导出已经映射好的map文件

![algPN-105.gif](https://tiny-y.asia/images/blog/2023/algPN-105.gif)

可选将模型指定为主要和次要

![algPN-106.gif](https://tiny-y.asia/images/blog/2023/algPN-106.gif)

从设计属性编辑面板设置在3D画布使用主要或次要模型，这个选项仅在此版本中出现在此处，之后被更新到3D画布的启动对话框中了

![algPN-107.gif](https://tiny-y.asia/images/blog/2023/algPN-107.gif)

被指定的映射模型名称将出现在下图字段，如果没有模型则显示为空，选择……可以对其增加或替换模型，支持所有主流3D文件格式

![algPN-108.gif](https://tiny-y.asia/images/blog/2023/algPN-108.gif)

使用下方控制按钮对齐模型，AUTO用于自动对齐，若未能成功可继续使用手动按钮继续对齐

![algPN-109.gif](https://tiny-y.asia/images/blog/2023/algPN-109.gif)

选择MAN后将出现一个3D操纵器控制器，然后单击拖动操纵器的末端，即可沿三个方向中的任意一个方向移动模型。

选择TOP或BTM后在模型上选择一个面，模型将按选定的面与焊盘图形铜表面或底面对齐。

XY用于将指定的模型面对齐到平面上指定点，Z用于将指定的模型面对齐到Z轴指定点

![algPN-110.gif](https://tiny-y.asia/images/blog/2023/algPN-110.gif)

通过调整坐标值调整模型的位置

![algPN-111.gif](https://tiny-y.asia/images/blog/2023/algPN-111.gif)

通过调整旋转角度调整模型的方向

![algPN-112.gif](https://tiny-y.asia/images/blog/2023/algPN-112.gif)

DesignTrue DFM Enhancements DFM增强功能
-----------------------------------

经常我们需要独立使用DRC而不使用DFM检查，此版本允许从多个位置启用或禁用DFM检查，DRC优先与DFM，如果关闭DRC则DFM也将被一同关闭

### Global Manufacturing Tolerance 全局制造公差

DFM规则可以找到在制造公差范围内的违规。例如，假设线间距设置为5，两条平行走线以弧线或角度转弯。由于各种数据库条件，线间距不再是5，而是4.99。0.01的差异小于制造商的公差，但仍会被DFM间距检查报告为违规。在一个设计中可能有许多这样的条件。

全局制造公差的设定可以指定一个可接受的公差限制以避免此类DRC报告的生成，在本例中如果全局制造公差值设置为0.05，则只会报告小于4.95间距的值。

从Setup – Constraints – Modes命令打开Analysis Modes

![algPN-113.gif](https://tiny-y.asia/images/blog/2023/algPN-113.gif)

选择Design for Fabrication中Manufacturing Tolerance Allowance

![algPN-114.gif](https://tiny-y.asia/images/blog/2023/algPN-114.gif)

分别对导体间距和Mask指定允许的制造公差值

![algPN-115.gif](https://tiny-y.asia/images/blog/2023/algPN-115.gif)

点击OK或Apply对应的公差值即设置成功

![algPN-116.gif](https://tiny-y.asia/images/blog/2023/algPN-116.gif)

### Tented Via List Enhancements

增加两种检查项目用于定义不需要盖绿油的via名称，允许特定的via忽略检查via是否包含solder mask

Example 1:  
Via21-Tent-top 焊盘中没有定义 SOLDERMASK\_TOP. Via21-Tent-top这个名称定义到了Top tented via list, 此时由于忽略了这个via的检查所有不会报DRC  
Example 2:  
Via21-Tent-top 焊盘中没有定义 SOLDERMASK\_BOTTOM . Via21-Tent-top这个名称没有定义到了Bottom tented via list, 此时检查会报DRC

从Setup – Constraints – Modes命令打开Analysis Modes

![algPN-117.gif](https://tiny-y.asia/images/blog/2023/algPN-117.gif)

选择Design for Fabrication中的Top Tented Via list或Bottom Tented Via list

![algPN-118.gif](https://tiny-y.asia/images/blog/2023/algPN-118.gif)

添加需要忽略检查的via，将其添加到右侧窗口点击ok即添加成功

![algPN-119.gif](https://tiny-y.asia/images/blog/2023/algPN-119.gif)

DesignTrue DFM Rule Aggregator DFM规则聚合器（模版）
-------------------------------------------

使用系统命令（Win+R运行，或者启动cmd）"consmgr.exe -dfmAggr"启动DFM规则聚合器

![algPN-120.gif](https://tiny-y.asia/images/blog/2023/algPN-120.gif)

使用File – Import Technology Files导入模版文件

![algPN-121.gif](https://tiny-y.asia/images/blog/2023/algPN-121.gif)

模版文件中的值即被成功应用

![algPN-122.gif](https://tiny-y.asia/images/blog/2023/algPN-122.gif)

当PCB制造商使用从DesignTrue DFM门户网站获得的规则时，使Group – Auto Group All。自动分组基于存储在technology file中的属性，并组合具有相同铜重量、制造类别等属性的规则。

对于非DesignTrue DFM Web门户技术文件，请使用以下手动过程:

1.  选择要分组的CSets(以绿色突出显示)。
2.  右键单击并选择_创建组_.

![algPN-123.gif](https://tiny-y.asia/images/blog/2023/algPN-123.gif)

创建组时，会创建聚合CSet，并用每个DFM规则的最保守值输入。通过在组中选择不同的值，然后右键选择_Override_选项。所选值现在被放置在聚合的CSet中，并突出显示以指示选择了被覆盖的值。

![algPN-124.gif](https://tiny-y.asia/images/blog/2023/algPN-124.gif)

设置好的规则文件可以通过File – Export – Aggregated CSet导出供再次调用使用

包含CSet的technology file可以导入设计中以创建DFF集，并将其指定给设计层。

EDMD (IDX) 4.0 Support
----------------------

该版本支持EDMD于2020年6月批准的IDX模式4.0版。

IDX版本4包含以下增强功能:

*   折弯线/区域的折弯序号
*   图形类型标签:标识图形意图，例如board outline, hole, and via.
*   主要引脚标识:表示引脚一或极性引脚的位置。
*   文件时间/日期戳和修改时间/日期戳:定义原始文件的创建时间。对文件的修改将包括修改发生的时间和日期。

当您在设计过程开始时导入baseline file并将文件标记为版本4.0时，PCB Editor将导入该版本，而没有任何设置要求。所有后续导入和导出将默认为该数据库的版本4.0。

如果PCB编辑器启动创建初始baseline或重新baseline的过程，PCB编辑器默认为3.0版。要启用IDX 4.0，您必须在用户首选项编辑器中指定版本，路径为_Interfaces – IDX – idx\_version_

![algPN-125.gif](https://tiny-y.asia/images/blog/2023/algPN-125.gif)

一旦将数据库设置为4.0版，无论用户首选项编辑器的设置如何，数据库都不会导出到早期版本。

IPC-2581 Revision C Support IPC-2581修订版C支持
------------------------------------------

IPC-2581的C版于2020年7月获得批准。修订版C对现有项目进行了一些增强，并包含更多数据以支持更多技术和这些技术的制造数据。

有关更多详细信息，请参考IPC-2581修订版C规范。

### Enhancements to IPC-2581 Export User Interface 导出用户界面的增强

修订版C现在还不是默认选择，因为大多数人在准备支持修订版C的时候仍然支持修订版B。

当在导出表中选择输出修订版IPC2581-C时，这些表之间存在一些差异。修订版c中还增加了三种新的功能模式BOM, STACKUP, and STENCIL

功能模式的不同提供了专注于整个制造过程某些方面的特定数据，以帮助用户保护产品知识产权。有关功能模式的更多信息，请参考IPC-2581 C版文件。

### Layer Mapping Changes for Revision C 版本C的图层映射更改

在此版本中，图层映射结构发生了变化。制图类型从5层增加到7层。您可能需要调整设计的图层映射。

**Earlier Releases**

*   Artwork Film
*   Outer Copper Layers
*   Inner Layers
*   Documentation Layers
*   SolderMask SolderPaste Layers
*   Miscellaneous Image Layers

**Current and newer releases**

*   Artwork Film
*   Outer Copper Layers
*   Inner Copper Layers
*   Documentation Layers
*   SolderMask Layers
*   SolderPaste Layers
*   Silkscreen (Legend) Layers
*   Miscellaneous Fab Layers

Command Line Enhancements 命令行增强
-------------------------------

新的命令行选项(`-x`)已被添加以支持层映射配置。此选项需要配置文件的路径作为其值。

```
-x %CDSROOT%\share\pcb\text\IPC2581_LayerMappingCfg.txt
```

IPC-2581图层映射配置文件是一个文本文件，文件格式为`<film name>,<IPC Layer Category>.`

示例图层映射配置文件

TOP, OUTER\_COPPER\_LAYERS  
BOTTOM, OUTER\_COPPER\_LAYERS  
INNER1, INNER\_COPPER\_LAYERS  
INNER2, INNER\_COPPER\_LAYERS  
SS\_TOP, SILKSCREEN\_LEGEND\_LAYERS  
SS\_BOT, SILKSCREEN\_LEGEND\_LAYERS  
PASTE\_TOP, SOLDERPASTE\_LAYERS  
PASTE\_BOT, SOLDERPASTE\_LAYERS  
SM\_TOP, SOLDERMASK\_LAYERS  
SM\_BOT, SOLDERMASK\_LAYERS  
ASY\_TOP, MISCELLANEOUS\_FAB\_LAYERS  
ASY\_BOT, MISCELLANEOUS\_FAB\_LAYERS  
FAB\_PTH, DOCUMENTATION\_LAYERS

### User Preferences Changes for Revision C 版本C的用户首选项更改

IPC-2581修订版c增加了两个新的用户首选项。

ipc2581\_enable\_artwork\_filename\_affixes:为IPC\_out设置，为非导体图形图层名称添加前缀和后缀。  
当在图形控制表单的一般参数选项卡中定义prefix and/or suffix时，前缀和后缀将被添加到层叠定义中未定义的项目的层名称中。

![algPN-127.gif](https://tiny-y.asia/images/blog/2023/algPN-127.gif)

例如，前缀为`CDNS_ `后缀为` _Rev_3`，IPC-2581图层名称为Artwork film名称`TOP_ASSEMBLY`将使用`CDNS_TOP_ASSEMBLY_REV_3`.

ipc2581\_output\_square\_hole\_as\_slot:为ipc2581\_out设置以将方孔导出为槽孔。  
对于任何定义为方形钻孔的钻孔，该钻孔将从钻孔数据中省略，并移动到slot data for different tooling。

Allegro PCB Symphony Team Design协同设计
------------------------------------

### “In-session” Component Placement “会话中（实时在线）”元件放置

现在，Symphony客户端可以直接将组件从placement list放置到画布上，并将数据传输到Symphony服务器数据库。不用再停止协同操作此项内容

![algPN-128.gif](https://tiny-y.asia/images/blog/2023/algPN-128.gif)

Symphony clients can place components with the required symbol data sent to all clients and Symphony server:

*   Components by Reference Designator or Net Group association
*   “Schematic Driven” Module instances
*   Alternate Symbol definitions
*   All symbol associated Padstacks, Shape and Flash Symbols
*   Mechanical and Format Symbols

Allegro Constraint Compiler Allegro约束编译器
----------------------------------------

在此版本中，进行了几项增强以提高可用性，并允许导入CSV Constraint Tables and XML Constraint Data Set.

*   常用的编译器选项移到了主对话框
*   通过消除不同的编译器模式，仅替换模式，简化了流程
*   界面优化，带有一个简单的Import按钮和一个“Report Only (Validate)”

![algPN-129.gif](https://tiny-y.asia/images/blog/2023/algPN-129.gif)

*   简化使用模型选择XML Constraint Data set来导入约束
    *   无需提取ZIP文件内容并导航至设计。可扩展标记语言

![algPN-130.gif](https://tiny-y.asia/images/blog/2023/algPN-130.gif)

*   在导入过程中，约束表利用别名占位符替换设计特定名称，这允许在设计之间重用约束数据。为了进一步实现这一目标，当设计关联的别名丢失时，编译器将自动生成映射表，以便可以修改设计映射表。
    *   `cds_missing_alias.csv`:接口内缺少别名映射
    *   `cds_missing_name.csv`:缺少整个接口的名称映射

Parameterized High-Speed Structures 参数化高速结构
-------------------------------------------

在设计画布上使用High-Speed Structures高速结构，有时跨越多个层，生成可复用的高度结构会方便很多，本版本新增一种基于参数生成这些结构的功能

新的创建结构将根据输入的参数，为单端或差分对创建包含回流过孔的结构，这些参数包含

*   孔名称和差分孔间距
*   特定层的Pad Entry and Exit布线图形样式

![algPN-131.gif](https://tiny-y.asia/images/blog/2023/algPN-131.gif)

回流孔分布样式

![algPN-132.gif](https://tiny-y.asia/images/blog/2023/algPN-132.gif)

特定层的禁布大小

![algPN-133.gif](https://tiny-y.asia/images/blog/2023/algPN-133.gif)

使用这些结构可以将其导入Sigrity进行仿真和分析或添加到规则管理中并在布线过程中访问