---
title: 'Cadence Allegro What’s New in 17.2-2016 QIR 5 (Hotfix31)'
date: Thu, 11 May 2023 02:38:59 +0000
draft: false
tags: ['未分类']
---

Return Path DRC Updates
-----------------------

在此版本中，您可以在在线模式下启用回流路径DRC的电气分析模式。在线模式可使DRC标记保持最新状态，无需进行Batch DRC更新。此外，回流路径DRC检查还可识别负平面层反焊盘几何形状和平面切割/分割。

### Return Path DRC Vision

新面板Vision Manager可在_View_菜单中Vision Manager打开，新增一个_Return Path DRC _可以对设定了Return Path规则的违规情况实时反馈到PCB线上

单击Modify Selection按钮以选择指定的Net，选择的Net将以指定颜色显示违规或不违规，点击Clear Selection将清除选择

![172-algPN-96.gif](https://a1024.synology.me:222/images/172-algPN-96.gif)

### Graphical Overlays

如下图展示了实际Vision的显示模式，将鼠标悬停到对象上，datatip显示返回路径约束值和实际值的详细信息

![172-algPN-97.gif](https://a1024.synology.me:222/images/172-algPN-97.gif)

![172-algPN-98.gif](https://a1024.synology.me:222/images/172-algPN-98.gif)

[DesignTrue DFM](https://a1024.synology.me:1024/?p=3030)
--------------------------------------------------------

新增大量DFM支持的检查项目

3D Canvas Updates
-----------------

![172-algPN-99.gif](https://a1024.synology.me:222/images/172-algPN-99.gif)

### Wire Bonds  焊线

3D画布现在支持Chip-On-Board（COB）设计。 3D画布显示了从COB芯片到板设计上的焊盘的简单线缆表示。 还支持包含空穴的板设计。 与其他2D和3D交互类似，可以选择、移动或路由线缆，并在同时打开3D画布和设计画布的并排分割视图模式中实时更新。

![172-algPN-100.gif](https://a1024.synology.me:222/images/172-algPN-100.gif)

### Additional Export Formats 导出更多格式

*   ACIS files (`*.sab,*.sat`)
*   ACIS assembly files (\*.`asat`)
*   IGES files (\*.`iges`, \*.`igs`)
*   PDF 3D (\*.`pdf`)
*   STEP files (\*.`step`, \*.`stp`)

![172-algPN-101.gif](https://a1024.synology.me:222/images/172-algPN-101.gif)

Allegro and OrCAD PCB Editor Canvas Enhancements
------------------------------------------------

从QIR5版本开始，Allegro和OrCAD PCB Editor画布正在进行许多新功能和更改的转换，使新用户更容易使用Allegro和OrCAD PCB Editor并改进设计方法。此版本中包含的新功能包括：

*   Start Page
*   Workflow Pane
*   Quick Access to frequently used icons  
    快速访问常用图标
*   Customizable Design Canvas  可定制的设计画布
*   Improved Graphic Response time  
    改善图形响应时间
*   Modern command pane

### Start Page  起始页

编辑器画布现在有一个新的“起始页”选项卡，可以访问最佳实践文件、迁移信息和技巧，并提供对最近打开设计的便捷访问。

![172-algPN-102.gif](https://a1024.synology.me:222/images/172-algPN-102.gif)

### Design Workflow Pane  设计工作流窗格

设计工作流程面板，以协助新用户。该面板可用于指导用户执行基本任务，并消除了搜索必要菜单、工具栏图标或知道命令的需要。单击工作流程面板中的任何选项都会弹出相应命令的对话框。

![172-algPN-103.gif](https://a1024.synology.me:222/images/172-algPN-103.gif)

工作流是基于XML的，您可以创建自己的自定义流程。例如，库创建流程、内部QC检查表或用于制造可交付成果。

默认工作流文件位于 `<installation_directory>/share/pcb/text/workflows` 文件夹。PCB编辑器的工作流文件作为 `workflow.xml`

![172-algPN-104.gif](https://a1024.synology.me:222/images/172-algPN-104.gif)

![172-algPN-105.gif](https://a1024.synology.me:222/images/172-algPN-105.gif)

### Frequently-Used Icons 常用菜单

_View – Customize Toolbar_中_Customize_允许自定义_ContextMenu_，可以将常用的命令添加到里面

在ToolBars便签页勾选_ContextMenu_以启用此菜单

从画布上右键则定义的菜单命令将展示在最上侧，最多允许定义16个命令

![172-algPN-106.gif](https://a1024.synology.me:222/images/172-algPN-106.gif)

### Customizable Design Canvas  可定制的设计画布

![172-algPN-107.gif](https://a1024.synology.me:222/images/172-algPN-107.gif)

### Improved Graphic Response Time **改善图形响应时间**

![172-algPN-108.gif](https://a1024.synology.me:222/images/172-algPN-108.gif)

![172-algPN-109.gif](https://a1024.synology.me:222/images/172-algPN-109.gif)

![172-algPN-110.gif](https://a1024.synology.me:222/images/172-algPN-110.gif)

### Modernized Command Pane  现代化的命令窗格

新增一个enable\_command\_window\_history环境变量，默认值为勾选，勾选时代表使用更新的命令窗格，去掉勾选可恢复为之前的命令窗格

新的命令窗格输入命令栏使用单独的输入框，支持模糊匹配（命令自动完成）以及最近使用命令的历史记录，不同的消息类型使用不同的颜色区分标识

*   正常消息显示为黑色
*   Warnings消息为橙色
*   Error 信息以红色显示

![172-algPN-111.gif](https://a1024.synology.me:222/images/172-algPN-111.gif)

Route Vision (Segment Suppression in Pads)
------------------------------------------

增加一个选项ignore Seg in Pads，勾选此项将不对完全焊盘内部的线段进行Route Vision分析

![172-algPN-113.gif](https://a1024.synology.me:222/images/172-algPN-113.gif)

Timing Vision Update (Static Phase at Vias)
-------------------------------------------

更新后的Timing Vision分析线长时将对via前后两端的线长单独分析，对不等长的部分单独显示

![172-algPN-114.gif](https://a1024.synology.me:222/images/172-algPN-114.gif)

Productivity Enhancements
-------------------------

### DFA Update

`move` 命令已集成到DFA应用程序中。之前，DFA间隙反馈仅限于 `place manual` 命令和Placement Edit应用模式。

![172-algPN-115.gif](https://a1024.synology.me:222/images/172-algPN-115.gif)

### Assign Net to Via

现在可以将网络分配给过孔。将鼠标悬停在单个过孔上或选择多个过孔，右键单击，然后选择“_Assign Net to Via_”选项。

### Via Label Enhancement

随着HDI趋势的不断增加，通过标签成为识别设计中使用的埋孔/盲孔开始/结束层的重要方式。标签按顺序编号，从顶部（作为第1层）到底部（作为第N层）。这种排序并不总是与实际图层名称同步，并迫使设计师创建矩阵以了解映射关系。。

在QIR 5版本中，可以在“_Visibility_”选项卡中启用新选项“_Show Layer Numbers _号”。此选项可有效显示标签与其导体图层的同步。

![172-algPN-116.gif](https://a1024.synology.me:222/images/172-algPN-116.gif)

### Padstack Editor

*   圆环焊盘，在17.2基础版本中引入，现在支持Mask层。
*   复制和粘贴功能已得到改进。现在可以在design层和 mask 层之间复制和粘贴层信息。
*   Auto-scrolling within the working grid has been improved.

### File Locking

“ _File Properties_ ”对话框现在支持五种数据锁类型。它们包括 _Manufacturing, Database, Logic, Constraints,_ and _MCAD/ECAD_。如果选择了特定选项，则禁用属于该组的导出命令。例如，启用“制造”（Manufacturing）选项将禁用 2581, ODB++, artwork, stream out, DFx check, drill legend, NC Drill, NC Route, and Variant 选项的导出。

![172-algPN-117.gif](https://a1024.synology.me:222/images/172-algPN-117.gif)

Allegro PCB Symphony Team Design Option
---------------------------------------

支持更过可使用命令及交互（略）

支持使用只读skill程序

[Allegro Symphony Team Design模式下使用Skill](https://a1024.synology.me:1024/?p=2802)

Miscellaneous Enhancements
--------------------------

### Associated Components Support for Bypass Capacitors**旁路电容器的关联器件支持**

新版Allegro System Capture原理图可以传递一些属性到PCB设计，定义关联和旁路电容器与父组件的电源引脚之间的最大距离。根据这些属性值，PCB Editor在放置或移动旁路电容时会显示一个圆形视觉指南。

`place manual`: 旁路电容器始终显示为“放置”（Placement）对话框中父元件下的子元件。在元件的最近电源引脚周围会显示一个圆圈，作为连接到同一网络的旁路电容引脚的视觉指南。圆的半径是指定电容器的引脚与其父级引脚之间的最大距离的属性的值。

`move` ：与手动放置旁路电容器类似，在移动过程中会显示一个圆圈作为视觉指导。当移动旁路电容器时，最近的父引脚可能改变，并且圆圈相应地与新引脚一起示出。

`quickplace` ：如果启用了“将关联元件放置在父引脚上”选项，则 `quickplace `命令现在会在其父元件的电源引脚之间平均分配旁路电容。例如，具有10个电源引脚的元件连接到5 V，并且20个旁路电容与之关联。电容连接在5 V和GND之间。在这种情况下，quickplace过程在10个电源引脚之间平均分配旁路电容。因此，两个旁路电容器被放置在距离10个电源引脚中的每一个相等的距离处。下图显示了一个示例。

![172-algPN-125.gif](https://a1024.synology.me:222/images/172-algPN-125.gif)

![172-algPN-126.gif](https://a1024.synology.me:222/images/172-algPN-126.gif)