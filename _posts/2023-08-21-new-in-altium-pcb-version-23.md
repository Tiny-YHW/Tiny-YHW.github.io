---
layout: post
title: New in Altium PCB Version 23
categories: Altium
permalink: new-in-altium-pcb-version-23
description: Altium Designer PCB 各版本更新内容
date: 2023-08-21

---

## 23.8（2023-08-15）

### Custom Paste/Solder Masks

使用此功能需要在软件设置Advanced Settings中启用 PCB.Pad.CustomMasks 时才可以使用

此功能允许您在PCB设计和PCB封装中对焊盘的Paste/Solder Masks层图形自定义形状

相应的焊盘属性面板的UI已同步更新，可以对焊盘图形进行针对性编辑

![Pnl_Properties_Pad_PadStack_TopPasteExpanded_AD23_7-450x766.png](https://a1024.synology.me:222/images/Pnl_Properties_Pad_PadStack_TopPasteExpanded_AD23_7-450x766.png)

从Shape下拉列表中选择Custom Shape，然后点击Edit按钮，即可自定义编辑对应图形

![CSPM_DefineUsingPropertiesPnl1_AD23_7-840x403.png](https://a1024.synology.me:222/images/CSPM_DefineUsingPropertiesPnl1_AD23_7-840x403.png)

![CSPM_DefineUsingPropertiesPnl2_AD23_7-840x403.png](https://a1024.synology.me:222/images/CSPM_DefineUsingPropertiesPnl2_AD23_7-840x403.png)

![CSPM_DefineUsingPropertiesPnl3_AD23_7-840x403.png](https://a1024.synology.me:222/images/CSPM_DefineUsingPropertiesPnl3_AD23_7-840x403.png)

![CSPM_DefineUsingPropertiesPnl4_AD23_7-840x403.png](https://a1024.synology.me:222/images/CSPM_DefineUsingPropertiesPnl4_AD23_7-840x403.png)

从指定层绘制一个或多个自定义图形，选中它们从鼠标右键选择Pad Actions->Add Selected Custom Masks to Pad在焊盘上自定义形状

![CSPM_DefineUsePrimitives_Paste1_AD23_7-840x403.png](https://a1024.synology.me:222/images/CSPM_DefineUsePrimitives_Paste1_AD23_7-840x403.png)

![CSPM_DefineUsePrimitives_Paste2_AD23_7-840x403.png](https://a1024.synology.me:222/images/CSPM_DefineUsePrimitives_Paste2_AD23_7-840x403.png)

![CSPM_DefineUsePrimitives_Paste3_AD23_7-840x403.png](https://a1024.synology.me:222/images/CSPM_DefineUsePrimitives_Paste3_AD23_7-840x403.png)

![CSPM_DefineUsePrimitives_Paste4_AD23_7-840x403.png](https://a1024.synology.me:222/images/CSPM_DefineUsePrimitives_Paste4_AD23_7-840x403.png)

为了支持 'pin-in-paste' and 'thru-hole reflow' 技术，如果需要对通孔焊盘增加锡膏层可在规则管理器或者使用自定义的方式定义锡膏层

![PMTH_DesignRule_Properties_AD23_7-840x363.png](https://a1024.synology.me:222/images/PMTH_DesignRule_Properties_AD23_7-840x363.png)

### Added New Special Strings

添加了几个预定义参数，可以用于PCB文档或Draftsman文档

* .BlindVia_Count
* .Board_Height
* .Board_Width
* .BuriedVia_Count
* .ComponentMixed_Count
* .ComponentSMD_Count
* .ComponentThru_Count
* .CopperInner_Weight_Max
* .CopperOuter_Weight_Max
* .Hole_Size_Min
* .Hole_Size_Num
* .Layer_Count
* .MicroVia_Count
* .PadSMD_Count
* .PadThru_Count
* .SolderMask_Bottom
* .SolderMask_Top
* .StackedVia_Count
* .Thru_Via_Count

![PCB_NewSpecStrings_AD23_8-840x534.png](https://a1024.synology.me:222/images/PCB_NewSpecStrings_AD23_8-840x534.png)

注意Draftsman特殊字符串的前缀是“ = ”而不是“ . ”

![Draftsman_NewSpecStrs_AD23_8-800x537.png](https://a1024.synology.me:222/images/Draftsman_NewSpecStrs_AD23_8-800x537.png)

### Added Ability to Keep Room Orientation

Copy Room 时增加一个 Copy Room Orientation 选项，允许带方向复制room，这样如果room方向与源不一致时，room方向不会改变到与源一致

### Draftsman Improvement

Draftsman的Board Assembly View支持沉孔，如果源PCB具有应用了沉孔特征的通孔焊盘，则这些焊盘将正确显示在Draftsman文档中PCB的板组装视图中。

![Draftsman_BAV_Counterholes_AD23_8-840x332.png](https://a1024.synology.me:222/images/Draftsman_BAV_Counterholes_AD23_8-840x332.png)

### 修订记录

* 52750	For a specific embedded board, custom pads were being incorrectly located when using the Print Preview feature and in subsequently generated PDF documentation.
* 53166	For a particular design and with a specific expansion value for a custom shaped pad's Top Paste Mask, an error would be encountered when generating IPC-2581 output.
* 54470	Added additional support for customization of padstacks. You can now define custom Paste/Solder Mask shapes. (I:2424, I:10245, I:14604)
* 55401	After closing a PCB document, not all memory was being released/freed as expected, indicative of a memory leak.
* 55520	Additional special strings (with auto-calculated values for key manufacturing parameters) now available in support of composing fabrication notes when preparing an RFQ. (I:6849, I:10853)
* 56095	For a specific design, glossing a selected odd-angle track in Rounded mode would result in an erroneous violation between the track and a neighboring pad.
* 56141	For a specific design, attempting to move a selection with the 'Component re-route' option enabled, would result in an Access Violation (in module 'ADVPCB.DLL') being encountered.
* 56212	For a particular design, interactively routing would lead to the PCB editor locking up and Altium Designer silently exiting. (BC:21185)
* 56223	Added the ability to control whether or not the rotation of the chosen source room is copied to a destination room when using the ‘Copy Room Formats’ feature. (I:8457)
* 56241	It was not possible to import a SOLIDWORKS 3D model (\*.SldPrt) created using SOLIDWORKS 2023.
* 56595	In some cases with the PCB Rules And Violations panel undocked, left-clicking on a violation entry would lead to an Access Violation (in module "ADVPCB.DLL") being encountered. (BC:21481)

## 23.7（2023-07-19）

没有功能性更新

### 修订记录

* 45932	For a specific PCB, exporting to DXF/DWG format would not include component pads rotated by 180 degrees.
* 54107	When tuning a differential pair in a specific design, it was possible to create an extra tuning pattern after previously applied tuning had already achieved the target length.
* 54909	Added support for the import of custom pad stacks (and defined thermal leg ties) defined in an Allegro board design.
* 55397	When using the outer layers (Top/Bottom) for a single layer Flex PCB, the bottom solder mask was visible for a top SMD component pad.
* 55398	When generating NC Drill output, only a single drill was being generated for each of the IPC 4761 via types.
* 55551	For a specific panelized PCB, generation of Gerber X2 data through an OutJob resulted in the PTH_Drill.gbr file containing no data. (BC:20599)
* 55908	In some cases, closing a PCB document using the Ctrl+F4 shortcut would result in an Access Violation (at address 000000015C40C523 in module 'ADVPCB.DLL') being encountered.
* 55960	When generating Gerber files from a specific PCB document, the error "Exception has been thrown by the target of an invocation" would be encountered.
* 56012	The Board Report would show "100% Routing Completion", even when some connections remained unrouted, but were hidden.
* 56036	For a specific design, the number of holes in the Drill Table for a created Embedded Board Array was not equal to the sum total of holes in the Drill Tables for source PCBs.

## Altium 23.6

### Additional Clipping Options for Silkscreen Preparation 根据焊盘裁切丝印功能

菜单Tools » Silkscreen Preparation新增一个裁切丝印的功能，可以将丝印图形落在裸露的铜皮或Solder Mask的部分去除掉

压焊盘的丝印

![SilkPreparation_OriginalState_AD23_6-840x582.png](https://a1024.synology.me:222/images/SilkPreparation_OriginalState_AD23_6-840x582.png)

移除压裸露的铜皮部分

![SilkPreparation_ClipToExposedCopper_AD23_6-840x582.png](https://a1024.synology.me:222/images/SilkPreparation_ClipToExposedCopper_AD23_6-840x582.png)

移除压Solder Mask部分

![SilkPreparation_ClipToSolderMaskOpenings_AD23_6-840x582.png](https://a1024.synology.me:222/images/SilkPreparation_ClipToSolderMaskOpenings_AD23_6-840x582.png)

### Footprint Parameters in the PCB Library PCB库中的更多参数

现在封装属性面板新增一个Footprint标签页,可以更方便的定义封装库属性，并在此基础上新增多个固定属性

封装属性页面仅在PCB library document (.PcbLib) 模式下可用，在打开某个封装库，且没有任何对象被选择时Footprint标签页显示在属性面板中

![FootprintTab_LibOptions4.png](https://a1024.synology.me:222/images/FootprintTab_LibOptions4.png)

在PCB文档中选择一个器件时，如果器件包含这些指定的属性，其也将在属性面板中可见

![Pnl_Properties_Component_Workspace_AD22_10.png](https://a1024.synology.me:222/images/Pnl_Properties_Component_Workspace_AD22_10.png)

使用表达式查询可用`FootprintParameterValue, HasFootprintParameter and HasFootprintParameterValue`筛选指定属性的元器件

Altium Designer’s Comparison engine，可以查看封装属性的差异

![Dlg_UpdateFromPCBLibraries_Parameters_AD22_10-500x497.png](https://a1024.synology.me:222/images/Dlg_UpdateFromPCBLibraries_Parameters_AD22_10-500x497.png)

更新封装时可选是否将属性内容也一同更新

![Dlg_ComponentsUpdateOptions_FootprintParameter_AD22_10-249x269.png](https://a1024.synology.me:222/images/Dlg_ComponentsUpdateOptions_FootprintParameter_AD22_10-249x269.png)

从PCB中使用Make PCB Library生成PCB库时，若器件包含这些属性，其也将被一起导出

从PCB输出Pick and Place and ODB++也支持导出这些属性值

### 修订记录

* 51719 Support for adding user-defined parameters to footprints at the PCB Library level through the Properties panel has been added.
* 52776 When glossing track entering an SMD pad in 'Rounded' mode, the track's trajectory is pulled to the corner of the pad, creating violations with nearby objects.
* 52778 When glossing odd-angle track in 'Rounded' mode, any arcs included are replaced with straight track, causing a violation with any neighboring keep-out track.
* 54567 Two additional options have been added to the Silkscreen Preparation tool, allowing you to "Clip to Exposed Copper" or "Clip to Solder Mask Openings".
* 55043 In some cases on boards containing sections separated by net class, running a DRC would sometimes flag false clearance violations between split planes.
* 55237 In some cases, an Access Violation (in module ADVPCB.DLL) would be encountered after attempting to delete a design rule created by the Rule Wizard.
* 55247 For a specific design, routing a particular section of the board would lead to the error "Infinite loop is detected" being encountered.
* 55396 A single line text string placed on a PCB when using a 30 inch monitor was being converted to multi-line text when using a 24 inch monitor.

## Altium 23.5

### Added New PCB Section View

为了更好地了解复杂PCB的布局和结构，已为PCB编辑器实现了截面视图功能。当需要显示PCB内通常不可见的细节时，使用剖面视图很有帮助。

截面视图功能可在PCB编辑器的3D布局模式下使用 (View » 3D Layout Mode, shortcut 3)选择View » Toggle Section View命令启用

![PCB_SectionView_Edit_AD23_3-840x503.png](https://a1024.synology.me:222/images/PCB_SectionView_Edit_AD23_3-840x503.png)

![PCB_SectionView_On_AD23_3-840x503.png](https://a1024.synology.me:222/images/PCB_SectionView_On_AD23_3-840x503.png)

![PCB_SectionView_Off_AD23_3-840x503.png](https://a1024.synology.me:222/images/PCB_SectionView_Off_AD23_3-840x503.png)

在“编辑”模式下，剖面显示在设计空间中。通过单击并拖动截面视图Gizmo的相应彩色箭头，可以更改每个截面平面的位置。可以在“视图配置”面板中启用剖面的显示并配置其方向和颜色。

默认设置是隐藏当前截面视图的负空间中的所有内容，即仅显示出现在横断面图正空间中的对象。

### Custom Thermal Reliefs for Pad/Via

此版本使您可以更好地控制焊盘和过孔连接到焊盘的连接方式。

热连接可以以两种模式之一应用：规则驱动或自定义。在这两种模式中，都添加了“自动”选项，该选项可自动从每个焊盘/过孔边缘的中心添加连接。可以使用“最小距离”（Min Distance）设置来控制每个连接之间的间距。

![CTR_AutoMode_AD23_5-840x508.png](https://a1024.synology.me:222/images/CTR_AutoMode_AD23_5-840x508.png)

现在，您可以通过精确指定需要连接的连接点，手动定义焊盘和过孔（焊盘的常规形状和自定义形状）的散热。所有焊盘/过孔类型都支持手动定义的散热连接，并能够根据需要为不同层制作连接点。这些点本身可以直接在PCB设计空间中进行编辑和图形化定义。

要手动定义散热连接点，请在焊盘/过孔属性中启用“ Thermal Relief ”选项，然后使用“Pad Actions/Via Actions”右键单击菜单中的命令，或单击“Properties panel”中的“Edit Points ”按钮。单击“Edit Points”按钮后，可以使用Ctrl+单击在焊盘形状沿着任意点以图形方式添加辐条，而无需从右键单击菜单中调用命令。添加、编辑或删除连接点时，它们在焊盘/过孔边缘上显示为白色十字准线。

![CTR_AD23_2-840x486.png](https://a1024.synology.me:222/images/CTR_AD23_2-840x486.png)

为焊盘或过孔手动定义热释压时，它将由“特性”面板中的“Manual ”选项和“Edit Polygon Connect Style”对话框表示，现在可以通过单击“特性”面板中“Thermal Relief ”字段中的链接来访问该对话框。如果需要，还可以通过启用“Min Distance”复选框并输入适当的值来选择导体之间的最小距离。

![CTR_ManualMode_AD23_4-840x375.png](https://a1024.synology.me:222/images/CTR_ManualMode_AD23_4-840x375.png)