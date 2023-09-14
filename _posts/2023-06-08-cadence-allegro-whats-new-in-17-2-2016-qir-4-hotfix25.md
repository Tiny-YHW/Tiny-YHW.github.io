---
layout: post
title: Cadence Allegro What’s New in 17.2 2016 QIR4（hotfix25）
categories: Allegro
date: 2023-06-08
---

本文档介绍了Allegro® PCB Editor在17.2版季度增量版QIR4（hotfix25）中的新功能和增强功能

* * *

**关联**

*   [What’s New in 17.2 2016](https://tiny-yhw.github.io//2023/06/08/cadence-allegro-whats-new-in-17-2-2016/)
*   [What’s New in 17.2 2016 QIR1（hotfix4）](https://tiny-yhw.github.io//2023/06/08/cadence-allegro-whats-new-in-17-2-2016-qir-1-hotfix4/)
*   [What’s New in 17.2 2016 QIR2（hotfix9）](https://tiny-yhw.github.io//2023/06/08/cadence-allegro-whats-new-in-17-2-2016-qir-2-hotfix9/)
*   [What’s New in 17.2 2016 QIR3（hotfix16）](https://tiny-yhw.github.io//2023/06/08/cadence-allegro-whats-new-in-17-2-2016-qir-3-hotfix16/)
*   [What’s New in 17.2 2016 QIR4（hotfix25）](https://tiny-yhw.github.io//2023/06/08/cadence-allegro-whats-new-in-17-2-2016-qir-4-hotfix25/)
*   [What’s New in 17.2 2016 QIR5（hotfix31）](https://tiny-yhw.github.io//2023/06/08/cadence-allegro-whats-new-in-17-2-2016-qir-5-hotfix31/)
*   [What’s New in 17.2 2016 QIR6（hotfix38）](https://tiny-yhw.github.io//2023/06/08/cadence-allegro-whats-new-in-17-2-2016-qir-6-hotfix38/)
*   [What’s New in 17.2 2016 QIR7（hotfix48）](https://tiny-yhw.github.io//2023/06/08/cadence-allegro-whats-new-in-17-2-2016-qir-7-hotfix48/)
*   [BUG修复记录](https://layouto.lanzouf.com/i1LVI0tkym7i){:target="_blank"}

* * *



[Allegro DesignTrue DFM可制造性设计解决方案](https://tiny-yhw.github.io//2023/06/08/cadence-allegro-designtrue-dfm/){:target="_blank"}
--------------------------------------------------------------------------

[Allegro DRC Browser DRC浏览器](https://a1024.synology.me:1024/?p=2986)
--------------------------------------------------------------------

[Allegro Dynamic Component Alignment 元器件动态对齐](https://a1024.synology.me:1024/?p=2982)
-------------------------------------------------------------------------------------

Sigrity Technology Driven High-Speed Signal Analysis and Checking Sigrity 技术驱动的高速信号分析和检查
----------------------------------------------------------------------------------------

![172-algPN-161.gif](https://a1024.synology.me/images/blog/2023/172-algPN-161.gif)

Allegro® Integrated Analysis and Checking是一个新的、独特的环境，将Allegro®和Sigrity™技术融合在一起，在PCB Editor框架内提供完全的分析和检查能力。对于规则检查，DRC和ERC功能仍然依赖于Constraint Manager作为单一管理器。

### Impedance Analysis Workflow阻抗分析工作流程

该分析工作流程基于Sigrity分析提供阻抗数据反馈，可以通过运行分析或加载预先存在的Sigrity分析结果来实现。阻抗分析可以是基于_Net Based_ - Net, XNet, Bus, Differential Pair - or _Directed Group_ - connections between a start component and end component(s)。 分析结果显示迹线段或子段画布颜色编码反映阻抗值。此外，提供了一个带有滑块的阻抗颜色渐变条以过滤画布上的阻抗值，并提供了详细的阻抗结果表格以按网名和阻抗值进行过滤/排序。

![172-algPN-162.gif](https://a1024.synology.me/images/blog/2023/172-algPN-162.gif)

### Workflow Manager  工作流管理器

要切换到Impedance Analysis模式，请选择_Analyze – Workflow Manager_，然后从下拉菜单中选择_Impedance Workflow_。

![172-algPN-163.gif](https://a1024.synology.me/images/blog/2023/172-algPN-163.gif)

有两种分析模式可用于选择要分析的对象：

*   Net Based  基于网络
*   Directed Groups  定向组

![172-algPN-164.gif](https://a1024.synology.me/images/blog/2023/172-algPN-164.gif)

**Net Based Analysis Mode** **基于网络的分析模式**

红色X表示没有选择网络进行分析。选择Select Nets链接以添加用于阻抗分析的网络。

![172-algPN-165.gif](https://a1024.synology.me/images/blog/2023/172-algPN-165.gif)

XNet/Net Selection对话框允许您查看、筛选。或者选择平面（网络）或分层对象，如netgroups, differential pairs, and XNets，然后将它们移到“选定的XNet/Nets”窗格中或从“选定的XNet/Nets”窗格中移出。

![172-algPN-166.gif](https://a1024.synology.me/images/blog/2023/172-algPN-166.gif)

您还可以选择查看/过滤/选择分层对象（网络组、差分对和Xnet），并将它们移到选定的XNet/Nets窗格中或从其中移出。

![172-algPN-166.gif](https://a1024.synology.me/images/blog/2023/172-algPN-167.gif)

单击“XNet/Net Selection”对话框中的“OK”按钮后，“Select Nets”链接旁边的绿色复选框将激活“Start Analysis”链接。

![172-algPN-166.gif](https://a1024.synology.me/images/blog/2023/172-algPN-168.gif)

点击_Start Analysis_链接开始阻抗分析。Analysis部分下会出现一个进度表，模拟完成后，“Start Analysis”（开始分析）旁边会显示一个绿色复选框，并且“View Results”（查看结果）部分下的链接将启用。

![172-algPN-166.gif](https://a1024.synology.me/images/blog/2023/172-algPN-169.gif)

如果差分对是仿真的一部分，您可以选择在 the Table and the Vision中显示_Single Ended_结果或_Diff Pair_阻抗结果。

![172-algPN-166.gif](https://a1024.synology.me/images/blog/2023/172-algPN-170.gif)

**Impedance Table  阻抗表**

点击_Impedance Table_链接以显示可停靠的电子表格。模拟结果窗格包括摘要表部分，其中列出了所选网络的所有结果。此数据可以通过选择任何列标题进行排序。在摘要表中选择一行会填充详细表部分，以进一步对该网络的特定跟踪数据进行排序。您可以在详细表部分中选择行来缩放或将画布居中于阻抗差异以供调查。

![172-algPN-166.gif](https://a1024.synology.me/images/blog/2023/172-algPN-171.gif)

**Impedance Vision  阻抗视图**

点击_Workflow Manager_下的_Impedance Vision_链接，以显示反映阻抗值的信号线或线段画布颜色编码。要获取更详细的阻抗信息，可以将鼠标指针悬停在迹线段上。

![172-algPN-166.gif](https://a1024.synology.me/images/blog/2023/172-algPN-172.gif)

带有滑块的颜色渐变条可用于画布上的阻抗过滤。 在这种情况下，显示较低的参考平面表明迹线在平面分割上运行，这会改变阻抗值。

![172-algPN-166.gif](https://a1024.synology.me/images/blog/2023/172-algPN-173.gif)

更多分析模式暂略，需要时继续补充

Differential Pair DRC Enhancements差分对DRC检查增强
--------------------------------------------

Allegro约束规则系统检查差分对进行优化。有时标准设计规则不适用于差分对，这要求它们与非差分对进行不同的检查。改进已经针对静态相位计算方式进行了优化。现在，在返回驱动引脚和特定间距限制时，它包括过孔转换以控制差分对成员之间过孔最小间距。

### Static Phase Control at Via Transitions**过孔过渡处的静态相位控制**

过去默认静态相位DRC从接收器引脚到其指定的驱动器引脚计算相位长度。当超过静态相位约束值时，将在驱动器引脚处报告DRC标记。现在可以通过每个差分对返回到其指定的驱动器引脚来执行静态相位长度计算，并在超出约束值时报告DRC标记。只要差分对成员从同一层转换，就会检查任何via类型转换、thru, bb via, and micro。

**使用说明**

要激活新检查，打开“Analysis modes”表单并展开“All differential pair checks”，然后“Enable static phase at vias options”以更改静态相位DRC的检查方式（默认是关闭的）。DRC更新完成后当静态相位违反约束值时，在过孔位置处生成DRC标记，检查返回到驱动器引脚。Constraint Manager DRC工作表将在“对象”列中包含-Via作为后缀，用于从过孔过渡检查回的相位违规。

![172-algPN-189.gif](https://a1024.synology.me/images/blog/2023/172-algPN-189.gif)

鼠标悬停在DRC标记上将在datatip窗口中报告当前的差值及要求的差值。

![172-algPN-190.gif](https://a1024.synology.me/images/blog/2023/172-algPN-190.gif)

将过孔前后的差分线分别等长以消除DRC

### Intra-Differential Pair Spacing Rule差分对内部间距规则

Physical Domain _–_ Net and Region工作区新增一个_Referenced Spacing CSet_列，可以分配特定的间距规则，从而限制差分过孔的最小间距，该规则不影响差分线之间的间隔

![172-algPN-1912b0d58242414ae61.gif](https://a1024.synology.me/images/blog/2023/172-algPN-1912b0d58242414ae61.gif)

### Return Path DRC  回流路径DRC

用于在信号线参考层面变化时生成一个DRC标记

此功能不能做Online DRC，只能在Batch模式时进行检查，所以需要通过DBDoctor进行DBcheck时进行此项DRC检查

![172-algPN-194c14a440cc3cffe27.gif](https://a1024.synology.me/images/blog/2023/172-algPN-194c14a440cc3cffe27.gif)

打开规则管理器Electrical规则选择Return Path项目，此规则可以应用于Net/XNet或者网络组对象

![172-algPN-1958da2b7bbbb464364.gif](https://a1024.synology.me/images/blog/2023/172-algPN-1958da2b7bbbb464364.gif)

Reference Layer  参考层：为DRC系统提供指导，以确定在布线层上检索哪个层作为的平面参考。

Table表格：允许通过一个表的形式定义设计层面，从而确定特定布线层应在何处找到其参考平面

Ignore Layer(s)  忽略图层：进行检查时，不检查的图层

Length Ignore  忽略长度：阻抗不联系的最大允许长度

Max Pad Gap ：当信号线连接到通孔焊盘时，允许的最大焊盘间隙

**示例 1**

Closest参考层将基于电路板层叠关系确定信号线选取更近的平面用于回流路径检查

Pad Gap的值代表线到达指定参考层之前的线长

![172-algPN-1961ab6433ddc4faab5.gif](https://a1024.synology.me/images/blog/2023/172-algPN-1961ab6433ddc4faab5.gif)

DRC标记在PCB上生成，并在Constraint Manager中报告详细的分析结果。

![172-algPN-197804fa14ddf8a89f8.gif](https://a1024.synology.me/images/blog/2023/172-algPN-197804fa14ddf8a89f8.gif)

**示例2**

Dual参考层将根据电路板的层叠关系缺东信号线参考其上下相邻的的平面层用于回流路径检查

![172-algPN-19844f5590306b52832.gif](https://a1024.synology.me/images/blog/2023/172-algPN-19844f5590306b52832.gif)

DRC标记在PCB上生成，并在Constraint Manager中报告详细的分析结果。

![172-algPN-199922c0dd6fe6e5fbc.gif](https://a1024.synology.me/images/blog/2023/172-algPN-199922c0dd6fe6e5fbc.gif)

Routing Applications
--------------------

本版本新增一个新面板Vision Manager可在_View_菜单中Vision Manager打开

### Route Vision

![172-algPN-20052e15703f2f34c19.gif](https://a1024.synology.me/images/blog/2023/172-algPN-20052e15703f2f34c19.gif)

Lisence需要Allegro Venture PCB Designer产品选项

从Vision Manager选择Route Vision，可在面板中配置一些检查项目

*   Parallel Gap Less Than Preferred：平行线间距小于指定值
*   Non-Optimized Segs：Optimized segments have minimum line-to-line spacing and maximum pad-to-line spacing
*   Uncoupled Diff-Pair Segs：标识差分线不耦合的地方
*   Non-Ideal Pad Entry：对焊盘内拐角，或者焊盘出线不理想的线进行标识
*   90 Degree Corners：对存在直角的线进行标识
*   Min Miter/Corner Size：最小斜接/拐角尺寸-标识斜接/拐角尺寸小于用户指定的最小值的拐角段。
*   Min Seg/Arc Length：最小分段/弧长-标识长度小于用户指定的最小值的分段。
*   Min Arc Radius：最小圆弧半径-标识小于用户指定的最小值的圆弧半径。
*   Non-Arc：非圆弧角-标识非圆弧角。

检查是实时执行的，点击Viewlog按钮可以打开报告，结果可以在报告中查询

![172-algPN-201ad6970bd71639b57.gif](https://a1024.synology.me/images/blog/2023/172-algPN-201ad6970bd71639b57.gif)

![172-algPN-202.gif](https://a1024.synology.me/images/blog/2023/172-algPN-202.gif)

### L-Comp Structures

几乎不会用（略）

### Route Optimization布线优化

![172-algPN-204c750bf40c2293ff5.gif](https://a1024.synology.me/images/blog/2023/172-algPN-204c750bf40c2293ff5.gif)

在_Add Connect_命令时从options面板勾选_Optimize in channel_，则在拉线在焊盘或过孔中间时，线路会自动对齐在间隙中心

Productivity Enhancements
-------------------------

### Dynamic Component Alignment元器件动态对齐

### Place Replicate Module Locking模块复用锁定

新的环境变量Place Replicate Lock Modules在启用时会在Place Replicate Apply过程中自动锁定位置复制模块。这可以防止编辑符号和布线。要解锁模块，请使用 `property edit` 删除锁定的属性。

### Place Replicate-Apply Enhancement模块复用应用增强

以往的模块复用必须通过mdd文件进行，现在创建后的模块将直接存储与database中

![172-algPN-207.gif](https://a1024.synology.me/images/blog/2023/172-algPN-207.gif)

在“Placement Edit” application mode下，可以通过Show Element查看group名称，其他模块要对其复用，在右键菜单中选择From Database中对应的名称即可

![172-algPN-208.gif](https://a1024.synology.me/images/blog/2023/172-algPN-208.gif)

### Create Bounding Shape根据边界生产shape

从APD/SiP移植了基于边界的形状生成功能。使用“创建边界形状”命令，现在可以选择pins, vias, fingers, and clines来创建一个或多个基于所选对象的边界自动生成的形状。形状创建可以同时发生在classes/subclasses上。

![172-algPN-212.gif](https://a1024.synology.me/images/blog/2023/172-algPN-212.gif)

3D Canvas Updates
-----------------

### Rigid-Flex Transformation (Bending)**刚柔转换（弯曲）**

允许在3D视图中对软区进行弯曲，以匹配真实视图

![172-algPN-217.gif](https://a1024.synology.me/images/blog/2023/172-algPN-217.gif)

### Color Themes  颜色主题

![172-algPN-218.gif](https://a1024.synology.me/images/blog/2023/172-algPN-218.gif)

从3D Canvas中查看设计时，可以从3D Canvas_Setup – Preferences_对话框中设置_Color Themes_切换集中颜色主题，支持几种默认的颜色主题，用户也可以自定义几种颜色主题进行切换

![172-algPN-218.gif](https://a1024.synology.me/images/blog/2023/172-algPN-219.gif)

### Measure Path  测量路径

3D Canvas中可以在模型的表面或点之间测量距离，通过在画布上右键鼠标选择Measure Path命令启用此功能

![172-algPN-218.gif](https://a1024.synology.me/images/blog/2023/172-algPN-222.gif)

在此功能状态下当光标放在设计对象上时，可选的设计面或对象将高亮显示

![172-algPN-218.gif](https://a1024.synology.me/images/blog/2023/172-algPN-224.gif)

通过选择两个对象测点测量距离

![172-algPN-218.gif](https://a1024.synology.me/images/blog/2023/172-algPN-225.gif)

### Cutting Plane (Cross Section) Views剖面图

![172-algPN-227.gif](https://a1024.synology.me/images/blog/2023/172-algPN-227.gif)

在3D Canvas中选择_Setup–Preferences_中的_Cutting Plane_可以打开或关闭很镜面功能和设置一个横截面参数

![172-algPN-226.gif](https://a1024.synology.me/images/blog/2023/172-algPN-226.gif)

### Stackup Zones (Visibility Pane)**堆叠区域（可见性窗格）**

3D Canvas Visibility窗格现在与PCB Editor一致。为了提供类似的用户体验，包括层堆叠下拉菜单，当设计具有多个堆叠时，该下拉菜单可用。

![172-algPN-231.gif](https://a1024.synology.me/images/blog/2023/172-algPN-231.gif)

Allegro PCB Symphony Team Design Option
---------------------------------------

[Allegro PCB Symphony Team Design实时协同设计](https://tiny-yhw.github.io//2023/06/10/2023-06-10-cadence-allegro-symphony-team-design/){:target="_blank"}

新增部分功能的支持

### Placement Tasks

*   Place Replicate support
    *   Create, Update, and Apply place replicate group
    *   Apply place replicate groups created by other clients (design instance) without the need of a local place replicate (.`mdd`) file
*   Component Alignment 
    *   Allows alignment in the horizontal and vertical direction and using a particular alignment edge
    *   Spacing could also be adjusted based on DFA constraints and using entered values under the _Options_ tab
*   Pin Swap Support 
    *   Swap pins to improve routing flow into devices by selecting pins or ratsnest closest to swappable pins
    *   Back annotation of pin swaps to the schematic is not supported in the concurrent design environment but the Symphony session can be paused to allow back annotation to occur

### Interactive Routing Task

*   Diff Pair Phase Tune
    *   Allows the addition of single line or arc timing bumps by selecting a signal of a differential pair
    *   Bump length and height can be defined in the _Options_ tab to add an exact size timing bump to meet phase

### Integrated Analysis and Checking

*   Impedance Vision: Canvas cline color coding to identify and troubleshoot impedance related issues.
    *   Impedance DRC Vision: Color code clines driven by Impedance Rule requirements applied to the Nets. (DRC Marker alternative – Ideal plane)
    *   Impedance Analysis Vision: Color code sections of a cline driven by Impedance analysis of select nets or by loading analysis results from past simulations. Enhanced table reporting/navigation with vertical color bar for canvas display filtering (Complex plane aware)

### General Tasks

*   Add Line, Arc w/Radius, 3pt Arc, Circle and Text commands
*   Text Edit command

### Symphony Server  Symphony

*   Pause Session Support
    *   Allows an exclusive single-client access to the server database to perform activities outside of the concurrent design environment such as import netlist, IDX import, pin swapping, and back annotation
    *   The client who pauses gains full functionality of the layout editor leaving other connected clients in review mode only until the session is resumed
*   New multi-threaded communication architecture improves performance by dividing server related tasks into multiple threads