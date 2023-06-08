---
layout: post
title: Cadence Allegro What’s New in 17.2 2016 QIR6（hotfix38）
categories: Allegro
date: 2023-06-08
---

Enhancements in Design for Fabrication Rules Dfx规则增强
----------------------------------------------------

### Design for Assembly Rules装配设计规则

新添加的Design for Assembly（DFA）约束位于Constraint Manager中的“Manufacturing”类别下。

**Outline**

检查DESIGN\_OUTLINE和CUTOUT图形边界到器件之间最小间距的规则，对于器件优先使用DFA\_BOUND其次使用PACKAGE\_BOUND

![172-algPN-73.gif](https://a1024.synology.me:222/images/172-algPN-73.gif)

**Spacing**

可以设定器件到pin pads、hole、edge fingers或paste到paste或via的间距检查

**Pastemask**

可以设定Paste到Pad间距 焊盘丢失Paste以及paste到其他类型paste的检查

### DesignTrue DFM

### Tented Vias

Analysis Modes中提供一个选项Tented Vias，将过孔加入这个list中，则这些指定的via将在Design for fabrication定义为被油墨塞住的孔而不是裸露的孔，这样可以避免部分检查时产生多余的DRC

![172-algPN-69.gif](https://a1024.synology.me:222/images/172-algPN-69.gif)

### Void Sliver checks 间隙空洞检查.

使用static or dynamic shape避孔时，避孔或形状边界可能会与铜或其他镀层材料形成窄缝隙，有可能导致制造或组装问题，即使在同一网络上发生桥接也是如此。该检查提供了一个最小间隙DRC来识别可能出现桥接问题的避孔边缘之间的位置。下图显示了通过到形状DRC。

![172-algPN-70.gif](https://a1024.synology.me:222/images/172-algPN-70.gif)

### Micro Via Stagger 微通孔交错

在HDI设计或类似技术中使用微型通孔时，通常采用锥形几何结构的激光钻孔微型通孔结构。在密集设计中，这种几何通孔结构的优点是可以减少相同网络的微型通孔之间的空间。如果一个微型通孔从第1层穿过到第2层，并连接到另一个相同网络的微型通孔，该微型通孔从第2层穿过到第3层，则钻好洞之间最小距离可以比不同网络的两个微缩图案更接近。

![172-algPN-71.gif](https://a1024.synology.me:222/images/172-algPN-71.gif)

这种情况下微通孔（交错）规则导体的最小间距和下可在_Design for fabrication_类别中定义。

![172-algPN-72.gif](https://a1024.synology.me:222/images/172-algPN-72.gif)

3D Canvas Update
----------------

在版本17.2-2016 QIR 6中，3D Canvas不再需要环境变量来启用，默认情况下可用。

此阶段引入了三个新的视觉功能shadowing, centering, and additional options。

如下图所示，电路板上的元件模型和电路板本身现在具有阴影，可以将画布上的图像从静态图像转换为电路板的逼真视图。

![172-algPN-74.gif](https://a1024.synology.me:222/images/172-algPN-74.gif)

居中功能可在弯曲操作后自动将画布上的刚柔结合设计重新居中。

符号表示现在包括两个附加选项：STEP模型，如果可用，否则Place\_Bound形状和Place\_Bound形状，如果可用，否则STEP模型。

![172-algPN-75.gif](https://a1024.synology.me:222/images/172-algPN-75.gif)

Enhancements to Sigrity Technology Driven High-Speed Signal Analysis and Checking**增强Signity技术驱动的高速信号分析和检查**
------------------------------------------------------------------------------------------------------------

在QIR 6中，通过引入Crosstalk Analysis and Return Path Analysis工作流以及新的高级ERC，该环境得到了增强。

### Crosstalk Analysis **串扰分析**

运行Crosstalk分析，设置组件模型并指定要模拟的网络（Net、XNet、Bus、差分对）。您可以使用Analysis Model Manager (AMM)来管理库和分配模型。您可以直接在此流程中使用IBIS库和模型。

在此分析中specify GeoWindow and coupling values to pre-screen filter aggressors.

You can choose to run the default _All Neighbor_ simulation or include _Each Neighbor_ results as well. In the All Neighbor simulation, worst case crosstalk is determined by holding each victim in either a high or a low state while switching the aggressors away and towards the victim state. Each Neighbor uses the All Neighbor results to find the worst aggressors based on a percentage that you define.（看不懂，请自行理解）

除了表格电子表格窗格外，Crosstalk分析结果还以网络级别的彩色编码串扰段显示在画布中。

### Return Path Analysis **返回路径分析**

使用回流路径分析来识别和查看具有回流问题的信号。要运行此分析，请指定参考网络和定向组，这些是起始元件与一个或多个终止元件之间的连接。

分析结果是一个模拟表格，列出了回流路径、网络以及起始和结束信号引脚。

### Advanced ERCs **高级ERC**

除了QIR 5中引入的负平面和在线检查支持外，返回路径ERC现在还包括DRC，用于检查以信号过孔中心为半径的针脚过孔。与其他高级ERC一样，斯stich via与Constraint Manager完全集成。

您可以将鼠标悬停在选定的过孔或网络上，以查看网络的返回路径状态，例如违规计数以及各个违规类型的细分。

STEP Model Enhancements for 3D **STEP模型3D增强功能**
-----------------------------------------------

### STEP Package Mapping

在_Device/Package STEP Mapping_对话框中选择Purge将提示一个确认框（此前版本貌似不弹提示框），点击Yes即移除此模型

![172-algPN-77.gif](https://a1024.synology.me:222/images/172-algPN-77.gif)

### STEP Export Options  STEP导出选项

输出 STEP 模型时增加一个选项_ Ignore STEP model definitions _，选中此选项可以忽略板中定义的step模型，选择不导出这些模型而是使用这些器件关联place\_bound 外形及高度

![172-algPN-78.gif](https://a1024.synology.me:222/images/172-algPN-78.gif)

### Refresh Symbol Enhancement  刷新符号增强

更新封装页面新增一个选项_Update STEP mapping data only_，可以选择仅更新STEP模型而不更新封装

![172-algPN-79.gif](https://a1024.synology.me:222/images/172-algPN-79.gif)

Dynamic Shape Quality and Performance Initiative **动态铜皮质量和性能**
--------------------------------------------------------------

要启动高性能铜皮模式请选择_Fast_模式，此模式使用基于网格的填充方法来定位复杂铜皮的区域，以便在修改设计时进行更新。性能测试结果表明，这种新方法在shape voiding显著改善。

启用此模式需设置环境变量位于_Unsupported _类别中的_shape\_rough\_gridded_

![172-algPN-80.gif](https://a1024.synology.me:222/images/172-algPN-80.gif)

然后可在_Global Dynamic Shape Parameters_对话框中选择Fast

![172-algPN-81.gif](https://a1024.synology.me:222/images/172-algPN-81.gif)

Return Path DRC Enhancements
----------------------------

### Return Path Stitch Via DRC回流地孔检查

规则管理器中允许添加一个Stitch Via Distance检查，当指定网络穿孔附近指定距离内若没有找到回流地孔，则将知识一个DRC

![172-algPN-83.gif](https://a1024.synology.me:222/images/172-algPN-83.gif)

![172-algPN-84.gif](https://a1024.synology.me:222/images/172-algPN-84.gif)

Productivity Enhancements
-------------------------

### Quickplace by Schematic Layout 按原理图位置布局

仅支持DE-HDL or System原理图关联的PCB，使用quickplace命令中Place by schematic page number选项，并启用Schematic type placement，此时可将指定页原理图中的器件按其原理图中的相对位置放置到pcb中

![172-algPN-85.gif](https://a1024.synology.me:222/images/172-algPN-85.gif)

### Place Replicate Enhancements 模块复用功能增强

模块复用可在不同层叠的板间进行复用，此时复用时将弹出一个选项让用户选择哪些层面进行匹配

![172-algPN-86.gif](https://a1024.synology.me:222/images/172-algPN-86.gif)

### Route Clearance View 布线空隙视图

在add connect命令时_Options_面板有一个名为_Clearance View_的选项，当其被启用时，对应的导体图形周边会生成一个安全距离的轮廓，可以更直观的查看布线可用空间，此视图支持两种显示模式_Spacing_ and _Channel_

使用Ctrl+Tab键可以快速切换启用或关闭此视图

![172-algPN-88.gif](https://a1024.synology.me:222/images/172-algPN-88.gif)

### Enhancements in Copy and Paste Commands 复制粘贴命令增强

可在粘贴时选择使用包含via或shape网络

移除了_Paste Anywhere_功能选项

Allegro® PCB Symphony Team Design Option
----------------------------------------

### General Task  一般任务

*   支持更多的skill函数支持
*   Z-Copy shape support 
*   3D Canvas support
*   Create bounding shape support

### User Interaction  用户交互

被移动中的对象将显示一个十字光标

![172-algPN-89.gif](https://a1024.synology.me:222/images/172-algPN-89.gif)