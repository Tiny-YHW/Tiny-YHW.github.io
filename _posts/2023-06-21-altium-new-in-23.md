---
layout: post
title: New in Altium Designer PCB 23
categories: Altium
description: 
date: 2023-06-21
permalink: altium-new-in-23
excerpt: 介绍Altium Designer PCB 23版本更新的功能
---

# 23.6.0
## Additional Clipping Options for Silkscreen Preparation 根据焊盘裁切丝印功能

菜单*Tools » Silkscreen Preparation*新增一个裁切丝印的功能，可以将丝印图形落在裸露的铜皮或Solder Mask的部分去除掉

**压焊盘的丝印**

![](https://www.altium.com/documentation/sites/default/files/wiki_attachments/320598/SilkPreparation_OriginalState_AD23_6.png)

**移除压裸露的铜皮部分**

![](https://www.altium.com/documentation/sites/default/files/wiki_attachments/320598/SilkPreparation_ClipToExposedCopper_AD23_6.png)

**移除压Solder Mask部分**

![](https://www.altium.com/documentation/sites/default/files/wiki_attachments/320598/SilkPreparation_ClipToSolderMaskOpenings_AD23_6.png)

## Footprint Parameters in the PCB Library PCB库中的更多参数

现在封装属性面板新增一个*Footprint*标签页,可以更方便的定义封装库属性，并在此基础上新增多个固定属性

封装属性页面仅在PCB library document (*.PcbLib*) 模式下可用，在打开某个封装库，且没有任何对象被选择时*Footprint*标签页显示在属性面板中

![](https://www.altium.com/documentation/sites/default/files/wiki_attachments/302601/FootprintTab_LibOptions4.png)

在PCB文档中选择一个器件时，如果器件包含这些指定的属性，其也将在属性面板中可见

![](https://www.altium.com/documentation/sites/default/files/wiki_attachments/302601/Pnl_Properties_Component_Workspace_AD22_10.png) ![](https://www.altium.com/documentation/sites/default/files/wiki_attachments/302601/Pnl_Properties_Component_Local_AD22_10.png)

使用表达式查询可用`FootprintParameterValue, HasFootprintParameter and HasFootprintParameterValue`筛选指定属性的元器件

Altium Designer’s Comparison engine，可以查看封装属性的差异

![](https://www.altium.com/documentation/sites/default/files/wiki_attachments/302601/Dlg_UpdateFromPCBLibraries_Parameters_AD22_10.png)

更新封装时可选是否将属性内容也一同更新

![](https://www.altium.com/documentation/sites/default/files/wiki_attachments/302601/Dlg_ComponentsUpdateOptions_FootprintParameter_AD22_10.png)

从PCB中使用Make PCB Library生成PCB库时，若器件包含这些属性，其也将被一起导出

从PCB输出Pick and Place and ODB++也支持导出这些属性值

## PCB Release Notes

* 51719	Support for adding user-defined parameters to footprints at the PCB Library level through the Properties panel has been added.
* 52776	When glossing track entering an SMD pad in 'Rounded' mode, the track's trajectory is pulled to the corner of the pad, creating violations with nearby objects.
* 52778	When glossing odd-angle track in 'Rounded' mode, any arcs included are replaced with straight track, causing a violation with any neighboring keep-out track.
* 54567	Two additional options have been added to the Silkscreen Preparation tool, allowing you to "Clip to Exposed Copper" or "Clip to Solder Mask Openings".
* 55043	In some cases on boards containing sections separated by net class, running a DRC would sometimes flag false clearance violations between split planes.
* 55237	In some cases, an Access Violation (in module ADVPCB.DLL) would be encountered after attempting to delete a design rule created by the Rule Wizard.
* 55247	For a specific design, routing a particular section of the board would lead to the error "Infinite loop is detected" being encountered.
* 55396	A single line text string placed on a PCB when using a 30 inch monitor was being converted to multi-line text when using a 24 inch monitor.
