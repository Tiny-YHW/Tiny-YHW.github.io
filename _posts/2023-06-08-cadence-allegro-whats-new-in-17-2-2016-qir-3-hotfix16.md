---
layout: post
title: Cadence Allegro What’s New in 17.2 2016 QIR3（hotfix16）
categories: Allegro
date: 2023-06-08
---

本文档介绍了Allegro® PCB Editor在17.2版季度增量版QIR3（hotfix16）中的新功能和增强功能

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

* * *


## Allegro® PCB Symphony Team Design Option 协同设计选项

此次Allegro\_17.2QIR3的Allegro PCB Symphony Team Design Option新增了几项功能，让设计人员能通过过这些新增功能更方便在Symphony Team Design Option做操作和设计PCB。

### Placement

Component swapping可转换同性质的零件功能。

### Shape Editing

新增动态铜和静态铜可以做Move、copy、change及spin功能。

### Manufacturing

新增手动加测点、delete、move测点、检查测点等功能。

### General

新增选择的物件可以进行加入或取消FIXED property功能。  
新增选择的物件可以进行copy和paste到多个目标点和支援paste按右键的Snap Pick功能。

3D Canvas Updates 3D 画布更新
-------------------------

![172-algPN-240.gif](https://a1024.synology.me:222/images/172-algPN-240.gif)

### Isometric View (Default)等轴测视图（默认）

在此版本中，对画布进行了视觉更改。默认情况下，加载的设计显示在等轴测视图中，以便更好地表达画布和设计的 3D 性质。为了便于访问，等轴测视图映射到 NumLock 键 _1_。下图显示了新的 3D 画布窗口。

![172-algPN-241.gif](https://a1024.synology.me:222/images/172-algPN-241.gif)

### Updated and New Panes更新和增加新面板

在 3D 画布中，添加了两个新窗格：Messages and Options，使用者可以从这个视窗看到PCB的信息或者是错误信息。

![172-algPN-242.gif](https://a1024.synology.me:222/images/172-algPN-242.gif)

Visibility面板现在包括图层控件，用于快速打开或关闭Conductor, Plane, Mask, and Dielectric图层。这将与2D 画布上Visibility面板基本一致。这些窗口现在都允许移动和分组

![172-algPN-243.gif](https://a1024.synology.me:222/images/172-algPN-243.gif)

### Preferences Dialog“首选项”对话框

此版本引入一个新的Preferences对话框，与PCB编辑器中的Setup – User Preferences类似

![172-algPN-243.gif](https://a1024.synology.me:222/images/172-algPN-244.gif)

*   Display显示：设定 3D 画布窗口的默认颜色。
*   Messages消息：控制新“_消息_”窗格的显示与关闭。
*   Interactive交互式：控制 3D 画布和 2D 工作区之间的通信。禁用后，在 3D 画布中对 PCB 设计所做的任何更改都不会传播回 2D 设计。

### Display of Silkscreen Text, Rectangles, and Shapes in 3D Canvas在 3D 画布中显示丝印文本、矩形和形状

在以前的版本中，silkscreen outlines (lines)是可见的。在此版本中，text (both reference designators and free text)在 3D 画布上也可见。

![172-algPN-245.gif](https://a1024.synology.me:222/images/172-algPN-245.gif)

在silkscreen图层上绘制的Rectangles现在显示在 3D 画布上。对于未定义线宽的line将使用Artwork中设置的Undefined line width作为线宽值。

对shapes的支持也是此版本的一部分，但目前，所有形状类型（filled, cross-hatched, and unfilled）在 3D 画布上显示为填充。

![172-algPN-246.gif](https://a1024.synology.me:222/images/172-algPN-246.gif)

![172-algPN-247.gif](https://a1024.synology.me:222/images/172-algPN-247.gif)

### 2D PDF and Export Dialog文件输出功能

此版本也支持了2D PDF输出功能，可以从3D Canvas 的File > Export来输出PDF文件，输出的PDF文件但内容只会是2D呈现，而且也只会是表面层资料，不会有内层资料。

![172-algPN-248.gif](https://a1024.synology.me:222/images/172-algPN-248.gif)

### 3D to 2D Move Command在3D中移动器件

此次也新增了零件移动指令，我们可以从3D Canvas里点选零件，零件就会呈现红色，然后鼠标右键可选择Move指令，此时零件会变成透明状，移动的器件会是实心状，我们移动时只能仅限于X和Y平面，当零件移动完成后会更新到Allegro PCB上，所以会有连动关系。移动时也可从Options来选择Etch的处理方式。

![172-algPN-249.gif](https://a1024.synology.me:222/images/172-algPN-249.gif)

![172-algPN-249.gif](https://a1024.synology.me:222/images/172-algPN-250.gif)

### Zone Aware 3D

此版本也新增显示叠层的厚度。此厚度是依据Allegro Cross Section Editor设定的厚度。

![172-algPN-251.gif](https://a1024.synology.me:222/images/172-algPN-251.gif)

### Miscellaneous Updates to 3D Canvas：

此版3D Canvas的介面也更新了跟Allegro PCB一致。 Status bar添加Units：这会跟Allegro 一致。 Status bar添加X、Y、Z座标：参考点为鼠标。滑鼠的操作跟Allegro的操作更新为一致。

![172-algPN-252.gif](https://a1024.synology.me:222/images/172-algPN-252.gif)

Dynamic Ratsnest动态飞线（鼠线）
------------------------

旧版本的Dynamic Ratsnest是要移动零件到一个定点后按下Done，鼠线才会更新Net Schedule，这会让使用者在操作上比较繁琐，而且无法即刻了解到Net Schedule状况。  
但新版Dynamic Ratsnest功能是当在Move零件时，鼠线就会立即跟这零件的移动而更新Net Schedule，这方便在Placement时，使用者可以即时了解Net Schedule的状况。  
但这功能还是有一些例外Net Schedule不在包含内：

*   User-defined net schedule
*   System-defined net schedule
*   Power nets
*   Ground nets
*   Nets with pin-count greater than 20
*   Components with pin-count greater than 100

![172-algPN-255.gif](https://a1024.synology.me:222/images/172-algPN-253.gif)

注意：如果要停止此功能，可以从Setup > User Preferences > Placement > General folder No\_dynamic\_ratsnest来设定。

Route Keepout Net Exceptions 例外禁布
---------------------------------

此版新增可以让Route Keepout禁制区从Constraint manager来设定加入一个Net群组，让在经过这个Route Keepout里的Net不会产生DRC

在Constraint manager创建一个PKO Group。

![172-algPN-255.gif](https://a1024.synology.me:222/images/172-algPN-254.gif)

![172-algPN-255.gif](https://a1024.synology.me:222/images/172-algPN-255.gif)

把例外的Net加入这个PKO Group

![172-algPN-256.gif](https://a1024.synology.me:222/images/172-algPN-256.gif)

![172-algPN-257.gif](https://a1024.synology.me:222/images/172-algPN-257.gif)

在禁布区增加RKO Group Assign这个属性到这个Shape里，即可加入此例外。

![172-algPN-258.gif](https://a1024.synology.me:222/images/172-algPN-258.gif)

在route keepout shape上运行“Show Element ”命令可以查看例外成员。

![172-algPN-259.gif](https://a1024.synology.me:222/images/172-algPN-259.gif)

Padstack Editor XML Import 通过XML文件导入焊盘
--------------------------------------

在某些情况下，PCB库设计人员使用内部开发的软件来创建焊盘定义。派生的padstack定义可以通过SKILL，脚本或手动传输到Padstack编辑器。

在此版本中，引入了将包含完整下载堆栈定义的 XML 文件导入 Allegro Padstack 编辑器的功能。修改内部软件以 XML 格式导出 padstack 定义提供了一种更简单的方法，可以单独或通过批处理以编程方式生成和更新 padstack 定义。

范本路径\\share\\pcb\\xml-formats\\cdn\_padstack.dtd。

关于此功能的详细介绍先略，如有需要再继续补充

![172-algPN-260.gif](https://a1024.synology.me:222/images/172-algPN-260.gif)

Import File Manager导入文件管理器
--------------------------

在设计过程中，许多文件被用作在PCB编辑器和其他工具之间交换设计数据的通信工具。在整个设计过程中，会发生各种更改，这些更改通常需要对布局设计进行逻辑和物理修改。每当发生此类更改时。PCB编辑器中新的导入文件管理器功能可检测新的或更新的导入文件，并显示弹出通知，指示文件已准备好_导入_。通知还提供了用于启动更新过程或稍后提醒的选项。

### Setup for the Import File Manager导入文件管理器的设置

在使用导入_文件管理器_之前，您需要设置导入文件的存储库。必须使用共享目录属性创建此存储库。它必须是特定于设计的，并且独立于其他设计项目。例如：

使用 IDX 格式进行 ECAD/MCAD 协作，应创建特定于当前 PCB 设计项目的共享目录，使 PCB 设计人员和 MCAD 用户能够读写 IDX 文件。此特定的共享 IDX 目录位置在导入文件管理器中定义，该管理器监视此目录中的新 IDX 文件和更新 IDX 文件。

要在布局编辑器中调用此函数，请选择Tools – Import File Manager。

![172-algPN-267.gif](https://a1024.synology.me:222/images/172-algPN-267.gif)

在Import File Manager中，指定文件类型、扩展名、共享目录的位置以及用于文件类型的导入命令。

![172-algPN-268.gif](https://a1024.synology.me:222/images/172-algPN-268.gif)

_导入文件管理器_设置将保存到文本文件中（在设计的工作目录中。`importFileManagerConfiguratoin.txt)`

定义设置后，可以随时打开导入文件管理器以快速查看导入状态。您可以检查是否有任何导入挂起，或上次导入的时间，或分析导入文件管理器报告。

在导入文件中启用更新的自动通知需要在_用户首选项编辑器_中设置两个环境变量。要在PCB编辑器中设置这些变量，请选择Setup – User Preferences – File Management – Miscellaneous。

*   _import\_file\_alarm\_enable_：重新启动PCB编辑器时激活新的导入文件检测过程。
*   _import\_file\_alarm\_interval_：输入一个以分钟为单位的数值，以定义新文件检测进程之间的时间间隔。（值为 3 表示 3 分钟）

![172-algPN-271.gif](https://a1024.synology.me:222/images/172-algPN-271.gif)

必须重新启动PCB编辑器才能应用变量设置。当PCB编辑器重新打开时， Import File Manager会根据指定的时间间隔检查共享目录中是否有新的或更新的文件。如果检测到新的或更新的文件，则会弹出导入文件警报。警报显示新的或更新的文件名以及文件可用的时间和日期。

![172-algPN-272.gif](https://a1024.synology.me:222/images/172-algPN-272.gif)

Relative Grid相对格点
-----------------

此新功能是新增在Move 指令里，使用Move功能，在Option里做Relative Grid。这功能可以设定X和Y的格点来替代PCB里的格点，这个有助于移动器件时，可以准确的放置到指定位置上。这功能可以运用在Bypass的电容要放置到BGA有电源或接地的Vias里，这里要移动往往需要变更系统的格点才能准确地摆放在正确位置，但如果有Relative Grid功能就能轻松又准确地放零件，当结束Move指令Relative Grid就会回复到原本系统的格点了。  
Relative Grid的操作：

![172-algPN-273.gif](https://a1024.synology.me:222/images/172-algPN-273.gif)

Move指令，然后在Options勾选Relative Grid，然后设定安全间距X和Y，接这在BGA上的Vias运用Snap pick to > Via，把Spacing套到Vias上，(这时会发现Grid已经改变)这样偏移的格点就改变了。

![172-algPN-274.gif](https://a1024.synology.me:222/images/172-algPN-274.gif)

![172-algPN-275.gif](https://a1024.synology.me:222/images/172-algPN-275.gif)

![172-algPN-276.gif](https://a1024.synology.me:222/images/172-algPN-276.gif)

移动器件到指定位置上

![172-algPN-277.gif](https://a1024.synology.me:222/images/172-algPN-277.gif)

![172-algPN-278.gif](https://a1024.synology.me:222/images/172-algPN-278.gif)

结束move命令，格点恢复原值

![172-algPN-279.gif](https://a1024.synology.me:222/images/172-algPN-279.gif)

Multi-Destination Paste多目标粘贴
----------------------------

在此版本中，添加了一个新的预选命令粘贴。此命令将对象复制到多个目标，并将它们捕捉到所选目标对象的中心。当使用当前的_“复制”_命令一次将对象复制到多个位置时。

copy命令尚未修改，只是所选对象现在放置在复制缓冲区中，以便将来执行paste命令。

选择Copy命令，并设置复制参考点

![172-algPN-280.gif](https://a1024.synology.me:222/images/172-algPN-280.gif)

指定对象类型

![172-algPN-281.gif](https://a1024.synology.me:222/images/172-algPN-281.gif)

设置选择方式并选择要复制粘贴的对象

![172-algPN-282.gif](https://a1024.synology.me:222/images/172-algPN-282.gif)

可选吸附到指定对象作为参考点

![172-algPN-283.gif](https://a1024.synology.me:222/images/172-algPN-283.gif)

此时选择的对象已经被存储到剪切板，直到下次试用复制命令时其一直存在

![172-algPN-284.gif](https://a1024.synology.me:222/images/172-algPN-284.gif)

可以选定对象后选择paste命令，重新调用剪切板中的内容

![172-algPN-286.gif](https://a1024.synology.me:222/images/172-algPN-286.gif)

Route Clearance View
--------------------

此功能是在拉线时会快速显示Spacing，这个Spacing是依据Constraints里的设定，这有助于在Routing时我们估计空间的规划，也能快速知道线宽的安全间距。

![172-algPN-295.gif](https://a1024.synology.me:222/images/172-algPN-295.gif)

在此版本中，路线间隙视图是不受支持的原型。要启用此功能，请从Setup – User Preferences.设置环境变量_clearance\_view_。

![172-algPN-296.gif](https://a1024.synology.me:222/images/172-algPN-296.gif)

Miscellaneous Enhancements in PCB Editor其它增强
--------------------------------------------

没什么意思，引用原文

### Pre-selection Use Model Update

Select by Lasso, Select on Path, and Select by Polygon have been enhanced to support the use of the Shift and Ctrl keys. Using these keys you can extend or toggle the selection set when in the pre-selection editing mode.

*   Shift key selection: extends the current selection set by adding newly found items to the selection set.
*   Ctrl key selection: toggles the selection set by removing found items from the selection set.
*   Selecting objects using the Ctrl key does not add items to the selection set if part of a group selection. It will only add objects selected by a single control-click.

### Inter-Layer DRC Update

The Inter-Layer (ILC) DRC spreadsheet now supports layers associated with the Manufacturing class.

### Symbol Editor Update

The THETA\_JB and THETA\_JC properties can now be added in the symbol editor.

### RF PCB Enhancements

In this release, enhancements have been made in the following area of RF-PCB.

### Via Array Commands

The via array placement commands (add\_bviaarray,add\_viaarray,and del\_viaarray)have been enhanced and now support the following:

*   Placement of via structures
*   Checks DRCs only when placing via arrays
*   An option to enable the preview of via array