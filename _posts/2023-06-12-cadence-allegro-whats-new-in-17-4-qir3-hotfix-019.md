---
layout: post
title: Cadence Allegro What’s New in 17.4-2019 QIR3 (HotFix 019)
categories: Allegro
description: 
date: 2023-06-12
---

本文描述了Cadence Allegro PCB Editor在17.4-2019 QIR3 (HotFix 019）中的增强和改进


* * *

**关联**

*   [What’s New in 17.4 2019](https://tiny-yhw.github.io//2023/06/12/cadence-allegro-whats-new-in-17-4-2019/)
*   [What’s New in 17.4 2019 QIR1（hotfix7）](https://tiny-yhw.github.io//2023/06/12/cadence-allegro-whats-new-in-17-4-qir1-hotfix-007/)
*   [What’s New in 17.4 2019 QIR2（hotfix13）](https://tiny-yhw.github.io//2023/06/12/cadence-allegro-whats-new-in-17-4-qir2-hotfix-013/)
*   [What’s New in 17.4 2019 QIR3（hotfix19）](https://tiny-yhw.github.io//2023/06/12/cadence-allegro-whats-new-in-17-4-qir3-hotfix-019/)
*   [What’s New in 17.4 2019 QIR4（hotfix28）](https://tiny-yhw.github.io//2023/06/12/cadence-allegro-whats-new-in-17-4-qir4-hotfix-028/)
*   [BUG修复记录](https://layouto.lanzouf.com/i1LVI0tkym7i){:target="_blank"}

* * *

Dynamic Shape Performance Improvements动态Shape性能改进
-------------------------------------------------

### Fast Mode Performance快速模式性能

一种新的动态shape模式称为_Fast_被添加到QIR 2中的Global Dynamic Shape参数对话框中。快速模式在交互式操作(如slide, add connect, discrete moves等)提供动态shape的快速增量更新，本版本将此模式性能进一步改进，更快更强

DesignTrue DFM Enhancements
---------------------------

### DesignTrue DFF Mask Rule Additions (Venture)

两种新的DesignTrue DFF Mask检查，用于vias和SMD pad overlapping solder masks or Coverlay。

![algPN-43.gif](https://a1024.synology.me:222/images/algPN-43.gif)

#### Allow Via-in-Pad Via Mask to SMD Mask Overlap

当选项设置为off时过孔延伸到SMD引脚阻焊层边界外部是报错，完全在阻焊图形内部是不报错

![algPN-44.gif](https://a1024.synology.me:222/images/algPN-44.gif)

当选项设置为on时上述两种情况均不报错

![algPN-45.gif](https://a1024.synology.me:222/images/algPN-45.gif)

#### Allow Same Net Via Mask to SMD Mask Overlap

当选项设置为off时相同网络过孔（包含盘）与SMD引脚阻焊层边界重合时报错

![algPN-46.gif](https://a1024.synology.me:222/images/algPN-46.gif)

当选项设置为on时相同网络过孔（包含盘）与SMD引脚阻焊层边界重合时不报错

![algPN-47.gif](https://a1024.synology.me:222/images/algPN-47.gif)

### DesignTrue DFF Hole Enhancement Hole检查增强

micro vias的厚径比算法更新，按micro vias的深度和孔径计算得出，现在厚度仅包括起始层和钻孔穿过的层，钻孔停止的末端层不再包含在总深度中

![algPN-48.gif](https://a1024.synology.me:222/images/algPN-48.gif)

这种计算方式适用于micro vias和non-standard drill 类型为 Laser的vias

![algPN-50.gif](https://a1024.synology.me:222/images/algPN-50.gif)

![algPN-51.gif](https://a1024.synology.me:222/images/algPN-51.gif)

### Component Lead Display元器件引脚显示

元器件引脚显示通过层控制Package Geometry/Component\_Lead and Pin两个层控制，像Pin number一样，必须同时打开这两个层才能显示元器件引脚图形

![algPN-52.gif](https://a1024.synology.me:222/images/algPN-52.gif)

![algPN-53.gif](https://a1024.synology.me:222/images/algPN-53.gif)

### DesignTrue DFM Wizard Enhancements向导功能增强

支持面向制造的设计(DFF)和面向装配的设计(DFA)的第2版模板文件。

#### DFF Template Enhancements 模版增强

Copper 图形和间距，现在可以在末班中为不同的层类型指定不同的规则值，这些层类型包含Internal (INT), external (EXT), plane (PLN), and All.

![algPN-55.gif](https://a1024.synology.me:222/images/algPN-55.gif)

![algPN-56.gif](https://a1024.synology.me:222/images/algPN-56.gif)

#### DFA Template Enhancements模板增强

列表中以下规则值现在可以存储在模板文件中。

DFA-Spacing

*   Trace under component
*   Via under component

Component Lead

*   Plated Thru Pin
    *   Plated thru pin lead to hole clearance
    *   Non plated thru pin lead to hole clearance
*   SMD Pin
    *   Pastemask to Lead
    *   Lead to Pad
*   Ball
    *   Diameter
*   Component Body
    *   Lead

DRC Browser Updates DRC浏览器更新
----------------------------

### Navigation Improvements导航改进

在DRC导航中，添加了右键弹出选项，可以在不同级别展开或折叠导航树。

![algPN-57.gif](https://a1024.synology.me:222/images/algPN-57.gif)

![algPN-58.gif](https://a1024.synology.me:222/images/algPN-58.gif)

![algPN-59.gif](https://a1024.synology.me:222/images/algPN-59.gif)

### Waive DRC By Group Select 批量Waive DRC

通过组合按键Ctrl或Shift或鼠标按住拖动可以从DRC列表中选择多项后通过鼠标右键选择Waive批量Waive多个DRC

![algPN-60.gif](https://a1024.synology.me:222/images/algPN-60.gif)

### Constraint Domain View Options规则Domain视图选项

在DRC浏览器的选项菜单中，可以选择两个新选项来按constraint rule or constraint domain查看DRC。

![algPN-66.gif](https://a1024.synology.me:222/images/algPN-66.gif)

![algPN-67.gif](https://a1024.synology.me:222/images/algPN-67.gif)

### Fillet DRC Behavior

此处的fillet多数情况下指的是泪滴

可以通过选项将fillet被视为一个单独的shape做DRC检查，默认fillet将作为与其关联的对象如via or pin作为对象检查，启用此选项后若Shape控制间距较大时可能导致很多情况下不能生成fillet

![algPN-68.gif](https://a1024.synology.me:222/images/algPN-68.gif)

GPU Acceleration Rendering GPU渲染加速
----------------------------------

使用以下平台的GPU将有效加速图形渲染速度

*   Quadro P500 / P520
*   Quadro P400
*   Quadro P600 / P620/ P1000
*   Quadro P2000
*   Quadro P2000 / P2200
*   Quadro P3200 / P4200 / P5200
*   Quadro P4000
*   Quadro P5000
*   Quadro P6000
*   Quadro GP100
*   Quadro GV100
*   Quadro T1000
*   Quadro T2000
*   Quadro RTX 3000
*   Quadro RTX 5000/RTX 4000
*   Quadro RTX 6000/RTX 8000
*   Tesla P4 / P6
*   Tesla P40
*   Tesla P100
*   Tesla V100
*   Tesla T4

Analysis and Constraints分析和规则
-----------------------------

### Return Path DRC回流路径DRC检查

先版本可以检查信号回流路径是否连续，设计规则允许设置一个相邻层Void间距值，当信号距离Void间距的值小于设定时报告DRC，在此版本中此功能进一步增强，检查对象包含shape void and plane edge checks

检查设置项位于规则管理器Electrical / Return Path/Adjacent Void Spacing.

![algPN-69.gif](https://a1024.synology.me:222/images/algPN-69.gif)

### Parameterized High-Speed Structures参数化高速结构

在17.4-2019 QIR2中即添加了此功能，在此版本中进一步进行升级，可以通过在画布上选择差分对过孔并将过孔padstack and spacing输入参数，从而为预先存在的布线构建替换结构。

![algPN-70.gif](https://a1024.synology.me:222/images/algPN-70.gif)

layer-specific keepouts也扩展为包括五种预定义的几何形状。

![algPN-71.gif](https://a1024.synology.me:222/images/algPN-71.gif)

Non-symmetrical keepouts, Owl and Goggles在结构创建过程中会自动翻转，以最大化焊盘entry/exit走线通过过渡进入差分对的平面参考。

![algPN-72.gif](https://a1024.synology.me:222/images/algPN-72.gif)

Symphony Team Design Improvements协同改进
-------------------------------------

### Via Structure Support

允许客户端在画布上创建和放置structures，这些structures数据将被实时更新到数据库，其他客户端可立即调用更新

![algPN-73.gif](https://a1024.synology.me:222/images/algPN-73.gif)

### In-session Component Placement Usability 在线元器件放置可用性

改进了元件放置时多用户锁定显示，避免了两个用户同时放置同一个元件。锁定在`place manual`命令相关窗口中可见。

![algPN-75.gif](https://a1024.synology.me:222/images/algPN-75.gif)

### Database Sharing Usability Improvements数据库共享可用性改进

在这个版本中，Symphony服务器增加了一个_分享_按钮。设计所有者或连接的客户可以单击_分享_按钮来生成一个链接，该链接可以粘贴到Host Name快速连接到Symphony会话。

![algPN-76.gif](https://a1024.synology.me:222/images/algPN-76.gif)

3D Canvas Updates 3D画布更新
------------------------

在此版本中，3D Canvas使PCB设计的可视化尽可能逼真，并使设计师与3D Canvas的交互尽可能简单。增加了底部等轴视图以及改进的通孔铜壁镀层厚度表示以及导入的CAD模型的真实性。

### Isometric View – Top or Bottom 顶视图和底视图

选择View – Camera – Bottom Isometric或按数字小键盘1键，多次在顶部和底部之间切换Isometric View 。

![algPN-77.gif](https://a1024.synology.me:222/images/algPN-77.gif)

![algPN-78.gif](https://a1024.synology.me:222/images/algPN-78.gif)

Realistic Plating Thickness实际孔铜厚度
---------------------------------

为了尽可能真实地显示3D画布中的PCB设计，在此版本中，电镀孔的铜壁电镀厚度已改进为更真实的电镀厚度，如下图所示。

![algPN-79.gif](https://a1024.synology.me:222/images/algPN-79.gif)

孔铜厚度默认值为`25um (microns)`。如果需要，请使用`PTH_PLATING_THICKNESS`属性更改孔铜厚度值。

![algPN-80.gif](https://a1024.synology.me:222/images/algPN-80.gif)

### Increased Model Realism增强了模型的真实感

曲面更平滑

![algPN-81.gif](https://a1024.synology.me:222/images/algPN-81.gif)

![algPN-82.gif](https://a1024.synology.me:222/images/algPN-82.gif)

### Primary and Secondary Models主要和次要模型

生成3D画布时，针对器件模型可选主要或次要模型，此选项原来位于Design Parameter对话框中

![algPN-83.gif](https://a1024.synology.me:222/images/algPN-83.gif)

此选项控制主要或次要映射3D模型的显示(如果可用)。如果首选或选定的选项未映射，则显示其他模型(如果可用)。3D models and/or Place\_Bound / DFA\_Bound shapes是否显示在3D画布中仍由3D画布中的符号表示首选项控制，如下图所示。

![algPN-84.gif](https://a1024.synology.me:222/images/algPN-84.gif)

### Model Mapper GUI with Primary and Secondary Models带有主模型和次模型的模型映射器GUI

在3D Canvas中3D Mapper标签页现在可以用于设置映射主要或次要模型，从Footprint, Device, or Mechanical tab中选择指定器件类，再选择主要或次要模型类型，之后再Model File可以查看当前器件类使用的模型名称，右侧两个按钮用于替换其它模型或删除当前指定的模型

![algPN-85.gif](https://a1024.synology.me:222/images/algPN-85.gif)

![algPN-86.gif](https://a1024.synology.me:222/images/algPN-86.gif)

![algPN-87.gif](https://a1024.synology.me:222/images/algPN-87.gif)

Module Enhancements模块设计增强
-------------------------

设计中经常使用到模块复用功能，使用place replicate命令可以快速生成非正式模块，以便在设计中快速重用重复电路。正式模块通常与已验证电路的原理图模块相关联，以便在布局活动中加以利用。

place replicate用于构建一个在其设计中使用的经过验证的重用模块库。为了保持设计意图和完整性，对重用模块流程进行了以下改进:

*   在放置过程中，模块中的动态Shape会自动转换为静态Shape，以确保一致
*   默认情况下，设计中应用的模块保持锁定，以避免意外修改
    *   右键单击选项以Unlock快速解锁模块

可以通过启用以下user preferences来更改以上默认行为，勾选这些选项则相应的操作将不按上述原则进行

*   disable\_module\_auto\_lock:防止模块自动锁定
*   disable\_module\_shape\_convert:防止动态到静态的形状转换  
    

![algPN-88.gif](https://a1024.synology.me:222/images/algPN-88.gif)

![algPN-89.gif](https://a1024.synology.me:222/images/algPN-89.gif)

Miscellaneous Enhancements杂项增强功能
--------------------------------

### Multi-Pin Scribble Support in Add Connect 布线多PIN涂鸦连接功能增强

增加智能性，现在只要大致划过需要连接的对象即可，不需要在每一个节点都点击一次鼠标

![algPN-90.gif](https://a1024.synology.me:222/images/algPN-90.gif)

### Align Vias (Update)过孔对齐功能更新

用户选择过孔对齐命令是增加一个对齐点的操作用于确定对齐基准对象，右键选择Snap Pick to for object alignment of the selected vias.

### Pulse Linked Schematic and Layout原理图和PCB即时连接

在协作时，经常会原理图和PCB并行设计，所以确保原理图和PCB即时同步非常重要，使用此功能可以在原理图更改是，可以重新导入网表，确保版本始终同步，下文成链接设计

![algPN-91.gif](https://a1024.synology.me:222/images/algPN-91.gif)

要使用链接设计，Cadence系统的管理员需要启用Pulse integration，并要求在PCB Editor中使用Pulse version control进行数据管理。

![algPN-93.gif](https://a1024.synology.me:222/images/algPN-93.gif)

通过链接的设计版本控制，PCB设计者可以找到和原理图设计者都可以从系统捕获或PCB编辑器中打开链接的设计，通过在提交表单中指定一个标签，经由Pulse发布网表。

![algPN-94.gif](https://a1024.synology.me:222/images/algPN-94.gif)

当设计不同步时链接设计会提供一个通知，提示对数据进行同步。

![algPN-95.gif](https://a1024.synology.me:222/images/algPN-95.gif)

使用链接设计，您可以:

*   跟踪链接网表
    *   确定共享公共网表的设计版本
    *   在整个设计周期中跟踪网表更新
    *   更容易找到为特定电路板版本生成网表的原理图
*   从特定设计版本导入网表
*   查看链接设计的兼容设计版本