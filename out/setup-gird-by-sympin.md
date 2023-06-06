---
title: 'Cadence Allegro What’s New in 17.2-2016 QIR 2 (Hotfix9)'
date: Mon, 06 Dec 2021 07:33:09 +0000
draft: false
tags: ['Allegro']
---

[Find by Query按查询查找](https://a1024.synology.me:1024/?p=2991)
------------------------------------------------------------

位于“Find”窗口中的“Find By Query”功能可以让你轻松地在画布中找到指定的设计元素，查询语句支持被保存并在新设计中重复使用，所有编辑命令均支持与查询一起使用。

New 3D Canvas (Unsupported Prototype)
-------------------------------------

图形引擎升级，可在平移和缩放时带来更高质量的可视化和速度。Allegro 3D Canvas是一个新的3D Viewer介面，3D Canvas 搭配STEP File来让Allegro 3D Canvas更真实呈现PCB的样貌，并提供高品质的画面和速度，还能做结构上零件的干涉测试。

![172-algPN-330.gif](https://a1024.synology.me:222/images/172-algPN-330.gif)

原始的3D Viewer仍然是默认的3D查看器，新的_3D Canvas_作为unsupported prototype功能加入，使用此功能需要设置Setup – User Preferences – Unsupported中interactive\_3d\_canvas才可启用

从工具栏点击3D图标或从菜单View – 3D View启用，加载可能需要一段时间，具体时间受设计大小影响

### 3D Canvas Navigation 3D 画布导航

调整视图操作方法

*   使用鼠标滚轮放大或缩小视图
*   按住滚轮拖动平移视图
*   按住键盘Shift并按住滚轮拖动旋转视图

### 3D Canvas Controls 3D 画布控件

*   Visibility – 控制Etch层的Line, Pin, Shape, Via可见性。
*   Symbols – 为Top, Bottom or Embedded Component层器件控制器件是否显示出来
*   Collision – 检查器件是否存在重叠.

![172-algPN-331.gif](https://a1024.synology.me:222/images/172-algPN-331.gif)

### Basic Collision Detection

从Collision面板中检查并报告重叠器件，如下图所示。选择一个对象，单击鼠标右键，然后选择“Locate”。这将在器件附近显示蓝色定位器图形。该器件也会闪烁几次。

![172-algPN-332.gif](https://a1024.synology.me:222/images/172-algPN-332.gif)

STEP Model Mapping to Devices STEP 模型映射
---------------------------------------

Step Mapper用户界面增强

*   新的映射模式，支持按Device或Package类器件进行映射
*   新增“？”按钮，点击查看提示内容。
*   New pane for current devices in design。
*   New mapping status for package (Primary or Secondary)

![172-algPN-333.gif](https://a1024.synology.me:222/images/172-algPN-333.gif)

使用菜单Setup – User Preferences – Path – Library进行库路径设置，这样才能检索到对应的3D模型文件

*   step\_mapping\_path - 网表导入时检索的映射文件路径.
*   step\_facet\_path - 导入 STEP 映射文件时检索 STEP 文件的路径
*   steppath (old) - STEP mapping时检索的STEP 文件的路径.

Bend Editor for Flex Design Applications用于港后设计的弯曲编辑器
----------------------------------------------------

允许定义设计弯折，折弯由折弯的半径、角度和方向定义，此版本引入了折弯编辑器，您可以在其中定义表示折弯区域弧中心的折_弯_线。折弯线参数将作为特性附着到折弯线的属性指定。定义线后，将创建一个折弯区域，该区域根据折弯值直观地显示折弯的范围。还有一个选项，可以相对于折弯区域的轮廓图形添加禁布。

### Creating a Bend Definition创建

选择菜单Setup – Bend – Create将出现Create Bend Area对话框

![172-algPN-335.gif](https://a1024.synology.me:222/images/172-algPN-335.gif)

**折弯名称：**折弯区域需要 ID 或名称。每个名称必须是唯一的，不允许重复的折弯区域名称。导出和导入 IDX 文件以进行 ECAD/MCAD 协作时会引用此名称。

![172-algPN-336.gif](https://a1024.synology.me:222/images/172-algPN-336.gif)

**折弯线起点（终点）：**输入折弯线起点（终点）的 X：Y 位置。

![172-algPN-337.gif](https://a1024.synology.me:222/images/172-algPN-337.gif)

折弯线定义沿折弯半径的折弯中心，如下图所示。

![172-algPN-338.gif](https://a1024.synology.me:222/images/172-algPN-338.gif)

**折弯参数**

![172-algPN-339.gif](https://a1024.synology.me:222/images/172-algPN-339.gif)

*   **Inner side:**选择 TOP 表示折弯方向向上，而选择 BOTTOM 表示向下方向。
*   **Inner radius:**弯折半径
*   **Angle:**弯折角度
*   **Order:**弯折顺序

![172-algPN-340.gif](https://a1024.synology.me:222/images/172-algPN-340.gif)

**折弯区域选项**

![172-algPN-341.gif](https://a1024.synology.me:222/images/172-algPN-341.gif)

**Via keepout:**选中此复选框表示为折弯区域生成过孔禁布。设定Oversize值时禁布将依据弯折区域图形外扩

**Package keepout:**选中此复选框表示为折弯区域生成器件禁布。设定Oversize值时禁布将依据弯折区域图形外扩

**Create**：按参数生成弯折

![172-algPN-343.gif](https://a1024.synology.me:222/images/172-algPN-343.gif)

![172-algPN-3448f92db486d6fddf6.gif](https://a1024.synology.me:222/images/172-algPN-3448f92db486d6fddf6.gif)

折弯区域不允许重叠。如果折弯区域重叠，则新折弯区域创建将失败，命令窗口中将显示以下消息：

![172-algPN-34576f1fc4ee66335f9.gif](https://a1024.synology.me:222/images/172-algPN-34576f1fc4ee66335f9.gif)

### Editing a Bend Definition

选择Setup – Bend – Edit菜单可对已经创建好的弯折区域继续编辑

从Bend name选择要编辑的折弯区域，然后其它参数基本与创建时输入的内容一致，可按需调整参数值

![172-algPN-34769192233d6b9d1c1.gif](https://a1024.synology.me:222/images/172-algPN-34769192233d6b9d1c1.gif)

选择Delete Bend按钮可以删除对应的弯折区域定义

![172-algPN-348b5ffb466b5b30569.gif](https://a1024.synology.me:222/images/172-algPN-348b5ffb466b5b30569.gif)

Shape Application Mode Updates
------------------------------

新增多个Shape一并设置参数功能，选择多个Shape后右键选择Shape – Parameters可以同时编辑多个Shape参数

![172-algPN-3506be205e3cf5ea520.gif](https://a1024.synology.me:222/images/172-algPN-3506be205e3cf5ea520.gif)

### Add Notch Update

增加Notch在原来只有90的基础删新增了45度和135度，或者你可以定义1-179直接的任意数值

![172-algPN-3516e70d4d291345942.gif](https://a1024.synology.me:222/images/172-algPN-3516e70d4d291345942.gif)

### Slide IX/IY Support

Shape – Slide命令现在支持IX 和 IY 命令（先前是不支持的），输入 IX 100 将选定的垂直边缘定位在正 X 方向上 100 个单位。

Route Optimization (Unsupported Prototype)布线优化
----------------------------------------------

设置Setup – User Preferences – Unsupported中optimize\_in\_channel并在add connect命令时从option设置Bubble为非off勾选optimize in channel时从焊盘或过孔间穿线时，线会自动居中

![172-algPN-367.gif](https://a1024.synology.me:222/images/172-algPN-367.gif)

Via Structure Update 过孔结构更新
---------------------------

Route – Via Structure – Create支持一个新的选项cut clines by rectangle，其允许截取一部分作为过孔结构而不是整个线，这样更有助与这个过孔结构被调用

![172-algPN-368.gif](https://a1024.synology.me:222/images/172-algPN-368.gif)

Group Routing群组布线
-----------------

新的间距选项Control Trace允许可以以一侧的线为基准，其它线依靠基准线平均分布（默认模式为以中心线为基准，向两侧扩展）

群组布线时按右键从下图菜单中访问此命令

![Snipaste_2023-04-26_10-32-27.png](https://a1024.synology.me:222/images/Snipaste_2023-04-26_10-32-27.png)

![172-algPN-369.gif](https://a1024.synology.me:222/images/172-algPN-369.gif)

![172-algPN-370.gif](https://a1024.synology.me:222/images/172-algPN-370.gif)

Tab Routing Update
------------------

etch-editing命令更新增强，可以智能地保留或删除clines or segments上的tabs

![172-algPN-373.gif](https://a1024.synology.me:222/images/172-algPN-373.gif)

![172-algPN-374.gif](https://a1024.synology.me:222/images/172-algPN-374.gif)

Add RF Trace添加射频线
-----------------

Route – Unsupported Prototypes新增Add RF Trace命令

![172-algPN-375.gif](https://a1024.synology.me:222/images/172-algPN-375.gif)

*   Bend Type – 弯折类型
    *   Square – 方形
    *   Mitered – 斜角
    *   Curve – 曲线（圆弧）
*   Width Transition Mode – 线宽过渡模式
    *   None – 无过渡.
    *   Round – 圆弧过渡.
    *   Taper – 锥形过渡
*   Transition Taper Length –锥形过渡，长度锥度效果的段上没有足够的空间时实际长度会小于此值
*   Conductor Line Width – 线宽.
*   Centerline Curve Radius – 具有曲线弯曲效果的迹线的中心线弯曲半径。
*   Miter Fraction – 具有斜接折弯效果的迹线的斜接度。
*   Snap to connect point – 捕捉到连接点，该命令会尝试在布线期间捕捉到对象.
    *   Inherit Width – when Snap to connect point is checked, this field is enabled. If checked, trace width is inherited from the snapped object if possible. The field is mutually exclusive to Taper Connect to Pin.
    *   Taper Connect to Pin – when Snap to connect point is checked, this field is enabled. If checked, trace segment connecting to the snapping pin is tapered.
*   Create generic shape – 创建通用形状 – 这使通用形状编辑命令能够对添加的形状进行操作。

Convert RF Trace
----------------

shape形式的RF traces可以使用Route – Unsupported Prototypes菜单中的Convert RF Trace转换为常规shape，并允许被再次编辑

Chip on Board (COB)板载芯片
-----------------------

Chip on Board 也称为直接芯片连接，是指安装裸片、用电线电连接以及通常用硅胶或环氧基材料封装在印刷电路板上的组装过程。

针对引线键合应用的封装符号必须在Symbol Editor中使用_“Bondpad_”选项创建。PCB编辑器Wirebond应用不能直接利用现有的symbols。必须删除现有symbols上的引脚，然后使用左图所示的 _Bondpad_ 选项重新添加。此外，_“_Find f”过滤器已更新为两个新条目：Fingers and Bond wires。

![172-algPN-376.gif](https://a1024.synology.me:222/images/172-algPN-376.gif)

两个新的图形_Bond\_Top_和_Bond\_Bottom_，可用于支持包含芯片引脚的封装符号。

![172-algPN-377.gif](https://a1024.synology.me:222/images/172-algPN-377.gif)

Allegro PCB 编辑器中的wirebond命令位于_“_Route”菜单中。它们包括Add, Edit, Settings and Tack Point Move.。

![172-algPN-378.gif](https://a1024.synology.me:222/images/172-algPN-378.gif)

一个新的模式Wirebond Edit application mode可选

![172-algPN-379.gif](https://a1024.synology.me:222/images/172-algPN-379.gif)

用户定义变量中增加一系列变量，可定制不同的功能

![172-algPN-380.gif](https://a1024.synology.me:222/images/172-algPN-380.gif)

Route – Wirebond – Settings设置用于Bond Fingers的焊盘和对齐选项。

![172-algPN-381.gif](https://a1024.synology.me:222/images/172-algPN-381.gif)

选择一个或多个pin以添加wire bond，添加wire bond后，将显示引线的长度和角度。

![172-algPN-382.gif](https://a1024.synology.me:222/images/172-algPN-382.gif)

使用“Tack Point Move”命令在键合手指内重新定位导线。此命令允许支持手指边界内的多根线。

![172-algPN-383.gif](https://a1024.synology.me:222/images/172-algPN-383.gif)

Display Canvas显示画布
------------------

部分显示改善

### Toolbar Icons

工具栏图标大小可以通过用户首选项变量 _tbiconsize_ 控制大小

![172-algPN-384.gif](https://a1024.synology.me:222/images/172-algPN-384.gif)

### Fontsize字体大小

_fontsize_ 用户首选项变量控制菜单文本和表单标题的大小。默认情况下，其值设置为 9，以下示例使用值 12。

![172-algPN-385.gif](https://a1024.synology.me:222/images/172-algPN-385.gif)

### Analysis Mode Form Update 分析模式面板更新

模式类别已合并为Design, Electrical, Physical, Spacing, Same Net Spacing, and Assembly，UI显示增强

![172-algPN-386.gif](https://a1024.synology.me:222/images/172-algPN-386.gif)

Eagle PCB and Library Translator
--------------------------------

新增 Eagle CAD 的 PCB 文件转换为Allegro设计格式，从File - Import – CAD Translators菜单中访问

![172-algPN-387.gif](https://a1024.synology.me:222/images/172-algPN-387.gif)

Productivity ToolBox Updates 效率工具箱更新
------------------------------------

### PCB Design Compare PCB设计比较

允许选择两个不同的brd数据，对齐进行比较，查找差异，该命令支持两种模式

**Standard Compare标准比较**

默认模式，该模式提取差异并将其写入 HTML 报表，其中包含适用于以下内容的信息：

*   Modification of stackup (cross section)
*   Netlist and connectivity
*   Pin connectivity modifications
*   Property changes
*   Testpoint modifications (testpoint moved, renamed, and so on.)
*   Device type modification (ECO part)
*   Placement modifications
*   Renamed components

**Graphical Compare图形比较**

可以以图形的方式比较两个数据，基于IPC2581，可以比较所有或单个层。突出显示差异。

![172-algPN-388.gif](https://a1024.synology.me:222/images/172-algPN-388.gif)

Custom Variables自定义变量
---------------------

此功能允许在PCB中增加文本信息，这些文本可以使用被控制更改，方便管理，支持历史记录

![172-algPN-389.gif](https://a1024.synology.me:222/images/172-algPN-389.gif)

RF-PCB Enhancements射频PCB增强
--------------------------

### Clearance Commands间隙命令

间隙初始化和设置命令已得到增强，以支持cline and trace shapes（通过rf\_add\_trace命令添加的shape）。您可以为不同的对象(RF component, cline, and trace)设置不同的偏移值。间隙的默认值在所有图层上始终对称。下图显示 rf\_ac\_setup and rf\_ac\_init命令 的_“Options_”选项卡。

![172-algPN-390.gif](https://a1024.synology.me:222/images/172-algPN-390.gif)

添加间隙时，启用Override global clearance选项，并使用按图层查看间隙形状选项设置要添加View clearance shape by layer。

![172-algPN-391.gif](https://a1024.synology.me:222/images/172-algPN-391.gif)

对于traces，对其右键可以使用swap命令来交换asymmetrical offset values.

现在将包含symbols, clines, and clearance shapes视为一个整体。在使用move and spin命令时，作为组件一部分的所有对象将作为一个组移动或旋转。

### Via Array Command 过孔阵列命令

使用add\_bviaarray命令时，可根据“Options”选项卡中所做的选择提供准确的结果。

*   添加了在cline segment的中心线上通过阵列创建的新选项。

![172-algPN-392.gif](https://a1024.synology.me:222/images/172-algPN-392.gif)

*   Disable extending cline选项可防止 cline 扩展通过所有 cline 分支上的数组创建。

![172-algPN-393.gif](https://a1024.synology.me:222/images/172-algPN-393.gif)

*   The staggered via is centered between 2 vias of the other ring.。
*   The via-via gap for adjacent via pairs on a ring does not exceed maximum gap between 2 vias and is maintained for all adjacent via pairs。
*   通孔阵列均匀地添加到cline周围。

更多信息从Allegro User Guide: Preparing the Layout中Creating Via Arrays中查阅

### Performance Improvement性能提升

在使用RF元件的设计中，一些通用DRC会产生错误的结果。在 QIR2 中，RF PCB 命令已升级为不显示错误的 DRC。此增强功能可提高性能并缩短设计周期时间。