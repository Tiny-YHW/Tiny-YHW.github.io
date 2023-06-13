---
layout: post
title: Cadence Allegro What’s New in 16.6-2015
categories: Allegro
description: 
date: 2023-06-13
---

本文描述了Cadence Allegro PCB Editor在17.4-2019基础版中的增强和改进

## Auto-Interactive Delay Tune (AIDT) - High Speed Product Option 自动等长高速选项

“High Speed”模块，新增“Auto-Interactive Delay Tune”命令，简称Aidt，可以实现自动对走线进行时序调节，从而大大减少绕等长所需的时间。其操作对象
为clines或者clines segments，可以对单独或者多个对象进行调节。

## Slide Overhaul 移线命令大修

16.6 版本对走线的*Slide*操作进行了很大的改进，改版后操作起来更加灵活、顺畅、可预测。该命令简化了使用模型，整合了任意角度和圆弧角度的滑动方式，并且提供了新的选项，以提高效率。

## Offset Routing
允许用户在布线过程中采用非标准角度如15度进行布线，以使在玻璃纤维介质中走线时最大程度的降低阻抗的不连续性。
在使用Route-Connect命令布线时从Option面板勾选Route offset启用此功能
![route_offset.png](https://a1024.synology.me:222/images/route_offset.png)

## Smart Layer Behavior for Add Connect 布线智能图层选择

当使用Route-Connect命令布线时，Option 控制面板中的布线起始层会自动匹配Visibility控制面板中的唯一的可见层。

![smart_layer.png](https://a1024.synology.me:222/images/smart_layer.png)

## Disable Open Space Routing

当使用Route-Connect命令布线时，16.6之前的版本允许直接点击PCB中的空白区域进行随意布线，16.6 User Preference Editor的Route - Connect中新增环境变量“acon_disable_nullnet_route”，当设置后，用户不能再在空白区域进行布线。

## Line Width Retention during Add Connect 布线线宽重用

当使用Route-Connect命令布线时，线宽默认使用之前用户指定的线宽，并在Option中使用蓝色的线宽值显示，如需使用规则中指定的值，在此处切换为Constraint回复规则中指定的线宽值

![line_width_retention.png](https://a1024.synology.me:222/images/line_width_retention.png)

## Fix Cline Segments 锁定线段

16.6 版本支持对cline segments进行Fix操作。

## Copy/Move Cline Segments

16.6 版本支持对Cline segs和Other segs进行复制/移动操作。

## Unsupported Prototype Menu 不支持的原型菜单

16.6 版本在Route 菜单下新增“Unsupported Prototype”子菜单，新增几个功能

### Auto Interactive Convert Corner (AiCC)

该命令用于批量切换（改变）走线拐角的角度（Arc、45、90）。其操作对象可以为Nets、Clines和Cline Segments

![aicc.png](https://a1024.synology.me:222/images/aicc.png)

## Productivity Enhancements

### Component Alignment updates 元器件对齐

针对横向对齐或纵向对齐，可以设置不同的对齐方式，如左对齐、右对齐、上对齐、下对齐。针对对齐时元器件的间距，可以设置不同的间距值，如Option 控制面板中，Off 代表当前间距；Use DFA constraints 表示采用DFA 间距；Equal spacing 表示用户设置等间距。

![align.png](https://a1024.synology.me:222/images/align.png)

### Place Replicate support of Text

模块复用时与元器件关联的Text也将同时被复用

### Symbol Instance Refresh 刷新器件

16.6 版本支持在布局模式（Placement edit）下对单个元器件的更新操作，例如我们会经常将元器件的文本或者器件边框不慎删除，以往的操作方法是通过Place-Update Symbol 来进行恢复，16.6 版本可以直接将鼠标放置某元器件上，右键下拉菜单选择“Refresh symbolinstance”命令来实现，操作更为简单。

![Snipaste_2023-06-13_15-02-35.jpg](https://a1024.synology.me:222/images/Snipaste_2023-06-13_15-02-35.jpg)

### Parameterized Cornering for Rectangular Shapes 倒角矩形

16.6 版本在执行“Shape-Rectangular”命令时，可以在Option 控制面板中设置自动将矩形的四个角进行倒角（chamfer）或圆弧角（Round）操作。

![rectangle.png](https://a1024.synology.me:222/images/rectangle.png)

### Shape Expansion/Contraction Shape的外扩和內缩

在General Edit 模式下，鼠标放在Shape 上，右键下拉菜单中新增“Expand/Contract”命令，用于改变Shape 的大小。

![shape_1.png](https://a1024.synology.me:222/images/shape_1.png)

### Add Circle - Ease of Use Improvements

16.6 版本在选择“Add-Circle”或“Shape-Circle”命令后，添加圆形Shape 时，可以在Option 控制面板中设置圆形Shape 的相关参数（半径、中心坐标）：

![Snipaste_2023-06-13_15-09-43.jpg](https://a1024.synology.me:222/images/Snipaste_2023-06-13_15-09-43.jpg)

### Change Radius of Line Drawn Circle 改变圆形半径

在General Edit 模式下，对于通过线绘制的圆形，16.6 版本支持通过右键下拉菜单中的“Change Arc/Circle”或“Change Radius”命令来改变圆形的大小。

![Snipaste_2023-06-13_15-09-49.jpg](https://a1024.synology.me:222/images/Snipaste_2023-06-13_15-09-49.jpg)

### Shape Updating

在“Shape-Global Dynamic Parameters”中，新增命令“Force Update”，用于对Shape 进行强制更新操作。

![shape_update.png](https://a1024.synology.me:222/images/shape_update.png)

### Embedded Net Names   嵌入的网络名称

16.6 版本支持在走线、引脚、铜皮上显示其所在的网络名称。

![embedded_netname.png](https://a1024.synology.me:222/images/embedded_netname.png)

该功能只能在OpenGL 开启情况下实现，用户还可以通过“Setup-Design Parameters”来控制走线（Clines）、铜皮（Shape）和器件引脚（Pins）上是否显示网络名称。

![Snipaste_2023-06-13_15-14-17.jpg](https://a1024.synology.me:222/images/Snipaste_2023-06-13_15-14-17.jpg)

### Show Measure Support for Dual Units 显示对双单位的测量支持

16.6 版本在执行“Display-Measure”命令时支持两种单位的显示，如毫英寸和毫米。通过环境变量showmeasure_altunits 来设置第二显示单位。

![show_measure.png](https://a1024.synology.me:222/images/show_measure.png)
![Snipaste_2023-06-13_15-16-50.jpg](https://a1024.synology.me:222/images/Snipaste_2023-06-13_15-16-50.jpg)

### Multiple Constraint Region Assignments

16.6 版本支持对单个或多个约束区域（Constraint Region）执行“Assign to Region”命令。

### Move Lines and Text outside Existing Class Structure

16.6 版本支持将线段（Lines）或文字（Text）信息转移到其他的类（Class）或子类（Subclass）
中，通过选择线段或文字，右键下拉菜单中的“change class/subclass”命令来实现。

### "Snap Pick to" updates

在执行“Edit-Vertex”命令时，右键下拉菜单中新增“Snap Pick to”命令。
Snap Pick to的对象增加几项

- Rectangle Edge Vertex  矩形边顶点
- Rectangle Edge Midpoint  矩形边中点
- Rectangle Edge  矩形边
- Shape Center  形状中心
- Symbol Center  符号中心


### Select by Lasso or Path

16.6 版本鼠标右键下拉菜单Selection set 中新增两个命令“Select by lasso”和“Select by Path”。

![lasso.png](https://a1024.synology.me:222/images/lasso.png)

- Select by Lasso：以索套的方式选择对象；
- Select by Path：以鼠标经过的路径的方式选择对象，鼠标经过哪些对象则选取哪些对象。

### Highlight Nets associated with Component 高亮与器件关联的网络

16.6 版本支持在对元器件进行高亮显示的同时，将该元器件关联的网络一并进行高亮。操
作方法：选择元器件，右键下拉菜单中选择“Highlight associated nets”命令。

指定了DC Voltage属性的网络将被忽略

### Split Plane Association

通过“Edit-Split Plane”创建铜皮时，网络与铜皮的对应关系会保存至数据库中。当重新分
割铜皮时，网络分配对话框会显示与当前Shape 默认的关联网络，

![Snipaste_2023-06-13_15-30-33.jpg](https://a1024.synology.me:222/images/Snipaste_2023-06-13_15-30-33.jpg)

点击“OK”确认该网络。如果需要选择其他网络，则选择“\*”来选择其它网络。当选择“Cancel”
后，弹出如下提示框：

![Snipaste_2023-06-13_15-30-42.jpg](https://a1024.synology.me:222/images/Snipaste_2023-06-13_15-30-42.jpg)

点击“OK”：系统自动关联铜皮和网络；

点击“Cancel”：所有铜皮没有任何网络属性（dummy nets）。

### Replace Padstack Enhancements

16.6 版本在执行“Tools-Padstack-Replace”命令时，Option 控制面板中新增两个选项：

![padstack.png](https://a1024.synology.me:222/images/padstack.png)

Ignore FIXED property：在进行焊盘的替换时，支持忽略FIXED 属性；
Pin #：支持批量替换引脚，例如输入2-8，即只替换编号为2-8 号的引脚。

### Artwork / Film Records Enhancements

- 在“Artwork Control Form”设置框中通过单击“Domain Selection”可以本将光绘文件的输出设置四种方式Artwork、IPC2581、PDF、
Visibility是否可用
- 中新增选项“Draw Holes Only”，即输出只包含引脚 或过孔的光绘文件。添加底片时须添加Pin Class 或Via Class 的信息；
- RS274X 数据格式支持有重叠的铜皮数据的输出；
- 光绘文件名称由之前的最大17 个字节增加至47 个；
- 光绘文件输出时支持删除未用到的焊盘；
- 如果有值为0 的线宽，输出日志（Photoplot.log）中会有警告；
- 光绘文件的单位默认与PCB 板采用相同单位；

### NC Route Enhancements

16.6 版本进行NC Route 操作时，支持将金属化与非金属化的钻孔区分开。

![Snipaste_2023-06-13_15-42-48.jpg](https://a1024.synology.me:222/images/Snipaste_2023-06-13_15-42-48.jpg)

### Associative Dimensioning Updates

在执行“Manufacture-Dimension Environment”命令，进行线性标注（Linear Dimension）时，
Option 控制面板有如下改进：

[![Snipaste_2023-06-13_15-45-08.jpg](https://a1024.synology.me:222/images/Snipaste_2023-06-13_15-45-08.jpg)](https://a1024.synology.me:222/image/0tmR)

Text：可以在该栏内输入文字，其优先级高于尺寸文本，如输入“XYZ”，则尺寸标注的结果只显示XYZ.

[![Snipaste_2023-06-13_15-45-13.jpg](https://a1024.synology.me:222/images/Snipaste_2023-06-13_15-45-13.jpg)](https://a1024.synology.me:222/image/05B5)

为配合尺寸标注，Text 栏中支持以下格式的输入：
%v：标注结果为实际尺寸；

[![Snipaste_2023-06-13_15-45-19.jpg](https://a1024.synology.me:222/images/Snipaste_2023-06-13_15-45-19.jpg)](https://a1024.synology.me:222/image/036P)

%u：标注结果为单位；

[![Snipaste_2023-06-13_15-45-27.jpg](https://a1024.synology.me:222/images/Snipaste_2023-06-13_15-45-27.jpg)](https://a1024.synology.me:222/image/0kVK)

例如：

[![Snipaste_2023-06-13_15-45-39.jpg](https://a1024.synology.me:222/images/Snipaste_2023-06-13_15-45-39.jpg)](https://a1024.synology.me:222/image/0WPa)

[![dim.png](https://a1024.synology.me:222/images/dim.png)](https://a1024.synology.me:222/image/0EkS)

## Database & Misc Enhancements

### Net Group Constraint Object

在约束管理器中新增概念Net Group，来代替之前的Bus，Bus 可以通过编辑属性的方式来添加。

### New Design Defaults

16.6 版本支持用户设置默认的单位/精度等基本参数，通过“Setup-User Preferences”中的环境变量“new_units”“new_accuracy”来进行设置。这样每新建一个设计，都会遵循默认的单位/精度。

### Find Filter update

Find 控制面板中新增多种查找对象（Match group, Net group, Net class, Pin pair, Diff Pair,Region）。

### Symbol Export

16.6 版本“File-Export”支持元器件电子表格（Symbol Spreadsheet）的输出，可以输出元器件引脚编号、名称、引脚连接的网络名称等信息，支持XML、TXT、CSV 三种格式，输出文件默认保存在当前工作路径下。

### Dump Libraries

以往版本中输出库时，默认保存在当前工作路径下，16.6 版本可以通过设置变量“dump_library_directory”来定义库的输出路径。