---
title: 'Altium指定某层作为元器件布局边框'
date: Sat, 28 Nov 2020 01:26:05 +0000
draft: false
tags: ['Altium', '设计技巧']
---

[Altium在PCB Footprint（焊盘图形）中添加更多信息](https://a1024.synology.me:1024/altium%e5%9c%a8pcb-footprint%e4%b8%ad%e6%b7%bb%e5%8a%a0%e6%9b%b4%e5%a4%9a%e4%bf%a1%e6%81%af/)

单击并选择一个元器件时，将显示选择布局边框。新（AD18及以后）版本中默认的边界框行为是使用包围该组件中所有基本体的最小矩形，但不包括字符和注释等。

为了更好地支持更复杂的组件形状，添加了PCB.ComponentSelection 属性，[高级设置](https://www.altium.com/documentation/altium-designer/workspacemanager-dlg-sysprefsform-generalsystem-general-ad?version=20.1)（ 在_“首选项”_对话框的_[System – General](https://www.altium.com/documentation/altium-designer/workspacemanager-dlg-sysprefsform-generalsystem-general-ad?version=20.1)_页面上单击“****Advanced Settings****_”_）。通过此选项，设计人员可以控制用于定义边界框的图层。 在“_高级设置”_对话框中更改 PCB.ComponentSelection值后，需要重新启动Altium 才能使更改生效。[](https://www.altium.com/documentation/altium-designer/workspacemanager-dlg-sysprefsform-generalsystem-general-ad?version=20.1)

高级选项支持三种模式（输入值0，1或2，默认模式是2）：

*   0-legacy mode-使用除指定符和注释字符串以外的所有层的所有几何图形。
*   1-by layer mode-使用下面列出的包含对象的的几何图形，其优先级如下：
    1.  Courtyard Layer（由“层类型”属性定义，而不是机械层名称，请[显示图像](https://www.altium.com/documentation/sites/default/files/wiki_attachments/300330/Dlg_EditLayerPair.png)）
    2.  3D Body层（STEP模型存储在3D主体对象中，该对象的大小与容纳模型的最小矩形棱镜相同。使用的是3D主体，而不是STEP模型的形状）
    3.  Silkscreen Layer plus Copper Layers
    4.  Copper Layers
*   2-by graphic mode-此模式使用Courtyard层上的几何图形；或者不存在该层时，将试用“Silkscreen”+“ 3D Body”+“Copper”层上的几何组合图形作为布局边框。字符串被排除在外。

[![](https://www.altium.com/documentation/sites/default/files/resize/wiki_attachments/300330/LegacySetting_AD191-250x234.jpg)](https://www.altium.com/documentation/sites/default/files/wiki_attachments/300330/LegacySetting_AD191.jpg)

** 0 - legacy  **

[![](https://www.altium.com/documentation/sites/default/files/resize/wiki_attachments/300330/LayerSetting_AD191-250x237.jpg)](https://www.altium.com/documentation/sites/default/files/wiki_attachments/300330/LayerSetting_AD191.jpg)

** 1- by layer    **

[![](https://www.altium.com/documentation/sites/default/files/resize/wiki_attachments/300330/GraphicSetting_AD191-250x233.jpg)](https://www.altium.com/documentation/sites/default/files/wiki_attachments/300330/GraphicSetting_AD191.jpg)

**2 - by graphic**

*   如果组件包括3D模型，则将实际3D模型的形状用于冲突检查，而院子图层上的形状用于选择框。
*   机械图层对象从选择边界框中排除，但是当未定义3D实体或Courtyard图层对象时，它们将包含在碰撞检查边界框中。.Designator和.Comment文本字符串是例外，它们始终被排除。了解有关[使用机械层的](https://www.altium.com/documentation/altium-designer/working-with-mechanical-layers-ad?version=20.1)更多信息。
*   零部件选择边界框用于计算零部件面积，了解有关[零部件面积的](https://www.altium.com/documentation/altium-designer/pcb-prop-componentcomponent-properties-ad?version=20.1#component_area)更多信息。