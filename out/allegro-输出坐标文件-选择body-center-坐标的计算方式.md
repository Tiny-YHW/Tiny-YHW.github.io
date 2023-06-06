---
title: 'Allegro 输出坐标文件 选择Body Center 坐标的计算方式'
date: Tue, 28 Feb 2023 07:11:25 +0000
draft: false
tags: ['未分类']
---

个人笔记，内容来自于[Cadence官方论坛](https://community.cadence.com/cadence_technology_forums/pcb-design/f/pcb-design/35912/body-center-calculation-in-export-placement)

The Body Center calculation is based on the following priority:

1.  Text String location on Package Geometry/Body\_Center
2.  Centroid of the Shape defined on Package Geometry/Place\_Bound\_Top
3.  Centroid of the Shape defined on Package Geometry/Dfa\_Bound\_Top, if Place\_Bound\_Top shape does not exist
4.  Centroid of the gathering of pins in the symbol, If Dfa\_Bound\_Top and Place\_Bound\_Top shapes do not exist

For odd shaped components you may want to define a Text String on Package Geometry/Body\_Center in your symbol to ensure that the Body Center calculation is what you expect.  If you want to see where Allegro thinks the Body Center of a symbol is located you could move the symbol with the "Point" set to "Body Center" under the Options tab.  You could then delete the shapes mentioned above and move the symbol again to see how the Body Center calculation changes.

Symbol Origin is the 0,0 inside of the symbol, nothing more, and not to be confused with Body Center.  In most cases SMD symbols will have the Symbol Origin at the Body Center of the component, as mentioned on another post

Body Center计算基于以下优先级：

*   Package Geometry/Body\_Center 上的Text位置
*   在 Package Geometry/Place\_Bound\_Top 上定义的形状的质心
*   如果 Place\_Bound\_Top 形状不存在，则在 Package Geometry/Dfa\_Bound\_Top 上定义的形状的质心
*   符号中引脚聚集的质心，如果 Dfa\_Bound\_Top 和 Place\_Bound\_Top 形状不存在

对于奇形怪状的器件，您可能需要在符号中的 Package Geometry/Body\_Center 上定义一个文本字符串，以确保 Body Center 计算符合您的预期。 如果您想查看 Allegro 认为符号的主体中心所在的位置，您可以在“选项”选项卡下将“点”设置为“主体中心”的情况下移动该符号。 然后您可以删除上面提到的形状并再次移动符号以查看身体中心计算如何变化。

Symbol Origin 是符号内部的 0,0，仅此而已，不要与 Body Center 混淆。 在大多数情况下，SMD 符号的符号原点位于组件的主体中心，如另一篇文章所述