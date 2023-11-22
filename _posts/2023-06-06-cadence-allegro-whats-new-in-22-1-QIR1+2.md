---
layout: post
title: Cadence Allegro What’s New in 22.1 QIR1&2
categories: Allegro
date: 2023-06-06
---

本文档介绍了Allegro® PCB Editor在22.1版季度增量版（QIR）2中的新功能和增强功能

<!--

SPB22.1/Allegro Package Designer Plus/Allegro Layout Eidtors:Whats New in Release

-->

* * *

**关联**

*   [What’s New in 22.1](https://tiny-yhw.github.io//2023/06/06/cadence-allegro-whats-new-in-22-1/)
*   [What’s New in 22.1 QIR1&2（hotfix4）](https://tiny-yhw.github.io//2023/06/06/cadence-allegro-whats-new-in-22-1-QIR1+2/)

* * *


![Cadence-Alegro-2022.png](https://a1024.synology.me/images/blog/2023/Cadence-Alegro-2022.png)

---
# QIR 1 (HotFix 001)（12-16-2022）

## Allegro 3DX增强功能

引入了新的3DX引擎，该引擎与Allegro设计数据库集成，通过解决相关的规模和复杂性问题，提供了更快、更有效的大型设计处理。

该QIR为DRC环境提供了全面的增强，并简化了查看和浏览DRC的方式。该版本还为刚挠结合设计提供了额外的支持。

### 器件间隙DRC

器件到器件的间隙的DRC可用于3D model以及Place Bound 和 DFA Bound。DRC支持为单个器件和各类器件（mechanical, connector, discrete, QFN, SOP, and BGA.）设定不同的水平和垂直间隙值。

![221-algPNQIR1-2.gif](https://a1024.synology.me/images/blog/2023/221-algPNQIR1-2.gif)

DRC标记在三维视图中可见，将光标悬停在标记上可以高亮显示DRC对象及提示信息。

3DX Canvas的搜索窗格中可以浏览DRC。

### 3DX刚挠结合

以交互方式查看和测量刚挠设计的弯曲。您可以随时进行目视器件间距检查，也可以在折弯状态下运行DRCs检查

![221-algPNQIR1-3.gif](https://a1024.synology.me/images/blog/2023/221-algPNQIR1-3.gif)

## GPU加速渲染增强

GPU支持在平移和缩放以及打开或关闭图层时提供更快的响应时间，并提高图形渲染质量。

默认情况下，GPU支持是启用的，并且在Windows和Linux平台上可用。

为了获得最佳性能，可考虑使用RTX A6000级别的GPU。

---

# QIR 2 (HotFix 003)

## New 3DX Canvas DRCs 新的3DX Canvas DRC

此版本引入了三个新的3DX DRC，可用于创建和检查模型、PCB和刚柔结合对象之间的物理冲突。这些检查在Allegro 3DX Canvas中可用。

在Constraint Manager的3D工作表中设置新DRC。

![221algPNQIR2-2.gif](https://a1024.synology.me/images/blog/2023/221algPNQIR2-2.gif)

与其他Constraint Manager检查一样，可以从Analysis Modes对话框中启用或禁用这些检查。

![221algPNQIR2-3.gif](https://a1024.synology.me/images/blog/2023/221algPNQIR2-3.gif)

此版本中添加了以下DRC：

- Component to Component: 根据元器件的models或shapes检查器件干涉。下图说明了DRC的一个实例：

![221algPNQIR2-4.gif](https://a1024.synology.me/images/blog/2023/221algPNQIR2-4.gif)
![221algPNQIR2-5.gif](https://a1024.synology.me/images/blog/2023/221algPNQIR2-5.gif)

- Component to Board: 元器件到PCB板,如元器件引脚相对于钻孔进行检查。

![221algPNQIR2-6.gif](https://a1024.synology.me/images/blog/2023/221algPNQIR2-6.gif)

如下图中，DRC表示已经为引脚设置了一个距离PCB或钻孔至少 0.05 mm的规则，但实际值为 0.021 mm 。

![221algPNQIR2-7.gif](https://a1024.synology.me/images/blog/2023/221algPNQIR2-7.gif)

增大孔径、使用更细引脚的元器件、更改允许的规则值可修正以上错误

- Component to Rigid-Flex:元器件到刚柔结合板的距离

![221algPNQIR2-8.gif](https://a1024.synology.me/images/blog/2023/221algPNQIR2-8.gif)

如下图中，规则值设置为2mm，实际值为1.27mm

![221algPNQIR2-9.gif](https://a1024.synology.me/images/blog/2023/221algPNQIR2-9.gif)

- Component to Board Edge:元器件到PCB板边缘或铣切区距离

![221algPNQIR2-10.gif](https://a1024.synology.me/images/blog/2023/221algPNQIR2-10.gif)

如下图中，规则值设置为1mm，实际值为0.92mm

![221algPNQIR2-11.gif](https://a1024.synology.me/images/blog/2023/221algPNQIR2-11.gif)

3DX DRCS使用封装CAD模型或Shape（Place_Bound或DFA_Bound）进行间隙检查。如下图中的“Component to Component”检查所示，可以指定要检查的几何图形的任意组合。在该示例中，对于SOP与SOP的检查和Lcd_Ea_8081-A3 n-b与外壳的检查，3D CAD模型与3D CAD模型的检查。

![221algPNQIR2-12.gif](https://a1024.synology.me/images/blog/2023/221algPNQIR2-12.gif)

可以指定单个组件以对照其他单个组件或DFA开发程序包类进行检查

![221algPNQIR2-13.gif](https://a1024.synology.me/images/blog/2023/221algPNQIR2-13.gif)

## Enhancements in Zone Creation and Editing 分区创建和编辑功能增强

可以在PCB中定义各种分区，以简化创建需要不同层叠的Rigid-Flex设计。可以定义软板和硬板所在的区域，不同的区域允许使用不同的规则约束，

### Creating Nested Zones 创建嵌套分区

当前版本中可以创建嵌套分区，其中一个分区完全放置在PCB中的另一个分区中，如下图所示，其中Zone 2嵌套在Zone 1中：

![221algPNQIR2-14.gif](https://a1024.synology.me/images/blog/2023/221algPNQIR2-14.gif)

### Editing Zone Boundaries 编辑分区边界

从此版本开始，可以编辑分区边界，与编辑形状边界类似。区域边界是静态未填充的Shape可任意编辑修改

## Performance Enhancements 性能增强

### Faster Cline Editing in Designs Containing 100,000 or More Attributes

针对类似*Add Connect, Move, Copy, and Delete*等命令操作众多对象时，性能优化。

### Increase in Stream Out Speed

*stream out*命令速度更快

### Faster Gerber/Artwork Generation

Gerber/Artwork生成更快，对于大型设计尤为明显

## Enhancements to Vias and Structures

新的封装设计完整性检查*High-Speed Structure Connectivity*现在可用于查找和修复高速结构连接网络继承相关的问题。

![221algPNQIR2-15.gif](https://a1024.synology.me/images/blog/2023/221algPNQIR2-15.gif)

新选项*Use Original pads on bottom*将结束层焊盘复制到过孔定义的新端，而不是原始焊盘堆栈中最后一层上的焊盘。

![221algPNQIR2-16.gif](https://a1024.synology.me/images/blog/2023/221algPNQIR2-16.gif)

## Ignoring FIXED Objects During Copy and Paste

使用复制或粘贴命令时选项面板增加一个*Ignore FIXED objects*选项

![221algPNQIR2-17.gif](https://a1024.synology.me/images/blog/2023/221algPNQIR2-17.gif)

## Enhancements to Degassing

从静态铜皮转换为动态铜皮时可以保留Degassing（气孔，避让的Void）或重新控制一个避让距离

### Preserving Degassing Holes保持气孔

通过设置`SHAPE_CONVERT_KEEP_DEGASSING`环境变量，可以使从静态铜皮转换为动态铜皮时可以保留Degassing

![221algPNQIR2-18.gif](https://a1024.synology.me/images/blog/2023/221algPNQIR2-18.gif)

### Controlling Void Spacing During Degassing

可以使用Degassing对话框的*Void Spacing Constraints*中的*Shape void*选项控制空隙间距

![221algPNQIR2-19.gif](https://a1024.synology.me/images/blog/2023/221algPNQIR2-19.gif)

# (HotFix 005)

## Managed Modular Design: Physical Reuse 托管模块化设计：设计复用

借助Allegro® Pulse的全新管理模块化设计功能，您可以在原理图和PCB中同时设计和复用模块，提高效率。

[![algPNHF005-2.gif](https://a1024.synology.me/images/blog/2023/algPNHF005-2.gif)](https://a1024.synology.me/image/8af3)

可以import and place modules published and shared 设计中的模块。

[![algPNHF005-3.gif](https://a1024.synology.me/images/blog/2023/algPNHF005-3.gif)](https://a1024.synology.me/image/8LZm)

您可以更新导入的模块，以反映Allegro System Capture中所做的最新更改。您还可以选择将导入的模块回滚到任何以前的版本。您对放置的模块所做的任何更改都可以提交到Pulse服务器。所有版本控制和共享操作都可以通过直观的脉冲模块管理器执行。

[![algPNHF005-4.gif](https://a1024.synology.me/images/blog/2023/algPNHF005-4.gif)](https://a1024.synology.me/image/8rHO)

您必须安装22.1版HotFix 005或更高版本的客户端应用程序Allegro System Capture和Allegro PCB Editor以及服务器应用程序Allegro Pulse，才能使用托管模块。