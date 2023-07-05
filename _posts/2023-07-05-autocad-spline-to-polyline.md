---
layout: post
title: AutoCAD 样条曲线转多段线
categories: AutoCAD
date: 2023-07-05
permalink: autocad-spline-to-polyline
excerpt: AutoCAD 样条曲线转多段线
---

由于部分PCB设计软件包括Allegro和Altium不支持样[样条曲线](https://help.autodesk.com/view/ACDMAC/2024/CHS/?guid=GUID-58316136-30EB-499C-ACAD-31D0C653B2B2){:target="_blank"}（样条曲线不是圆弧）

考虑到部分设计软件导入DXF结构图时样条曲线图形丢失问题，请按下述内容操作

## 多条

要同时转换多条样条曲线，请使用 PEDIT 命令：

1.  在 AutoCAD 的命令行中，键入 **PEDIT**。
2.  键入 **M**，表示转换多个。
3.  选择样条曲线。（PEDIT 命令不允许预先选择样条曲线）
4.  键入 **Y**，表示将直线、圆弧和样条曲线转换为多段线。
5.  指定精度 <0-99>。
6.  按 Esc 键退出命令。

或者：

1.  输入 SAVEAS 命令。
2.  以 AutoCAD R12/LT2 DXF (\*.dxf) 格式重新保存图形。

**注意：**这种较旧的文件格式不支持样条曲线，因此会自动将它们更改为三维多段线。但请注意，图形中的其他数据结构可能也会受到影响。要避免出现这种情况，请选择要转换的样条曲线，然后改用**WBLOCK**命令。

## 单条

要转换单个样条曲线，请使用 SPLINEDIT 命令：

1.  在 AutoCAD 的命令行中，键入**SPLINEDIT**。
2.  选择样条曲线（如果尚未选择）。
3.  键入**P**，表示转换为**多段线**。
4.  指定精度 <0-99>。

SPLINEDIT 之前：

![用户添加的图像](https://s3-us-west-1.amazonaws.com/help.autodesk.com/sfdcarticles/img/0EM3A0000008M4e)

SPLINEDIT 之后：

![用户添加的图像](https://s3-us-west-1.amazonaws.com/help.autodesk.com/sfdcarticles/img/0EM3A0000008M4j)

另请参见：

*   [Auto CAD SPLINEDIT（命令）](https://knowledge.autodesk.com/zh-hans/support/autocad/learn-explore/caas/CloudHelp/cloudhelp/2019/ENU/AutoCAD-Core/files/GUID-5530922C-6828-48B1-804C-EDD9053535BD-htm.html){:target="_blank"}
*   [Auto CAD PEDIT（命令）](https://knowledge.autodesk.com/zh-hans/support/autocad/learn-explore/caas/CloudHelp/cloudhelp/2019/ENU/AutoCAD-Core/files/GUID-0C422AA9-23DD-4650-AD66-68E9D7989E3F-htm.html?st=pedit){:target="_blank"}
