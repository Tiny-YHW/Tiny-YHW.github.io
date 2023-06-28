---
layout: post
title: Cadence Allegro What’s New in 16.6-2015
categories: Allegro
description: 
date: 2023-06-13
---

<!--Help\Allegro PCB Editor\Allegro PCB Editor  What's New in 16.6-->

本文描述了Cadence Allegro PCB Editor在17.4-2019基础版中的增强和改进

<iframe width="720" height="405" frameborder="0" src="https://v.qq.com/txp/iframe/player.html?vid=w0975lb6c1m" allowFullScreen="true"></iframe>

视频演示内容包含如下
- Component Alignment 元器件对齐和等距分布
- Place Replicate support of Text 模块复用包含元器件位号
- Symbol Instance Refresh 刷新器件
- Parameterized Cornering for Rectangular Shapes 倒角矩形
- Embedded Net Names 嵌入的网络名称
- Select by Lasso or Path 套索或路径选择
- Show Measure Support for Dual Units 显示对双单位的测量支持
- Associative Dimensioning Updates 关联尺寸更新

## [Allegro Drafting Prototypes ](https://tiny-yhw.github.io//2023/06/13/cadence-allegro-drafting/){:target="_blank"}

Allegro新增一系列绘图能力功能，大大增强了在机械结构图的设计上的编辑处理能力

## Design Planning Option （Flow）

### [Flow Planning](https://tiny-yhw.github.io//2023/06/15/cadence-allegro-flow-planning/){:target="_blank"}

将设计意图表达在设计中

### [Auto Interactive Break Out Technology](https://tiny-yhw.github.io//2023/06/15/cadence-allegro-aibt/){:target="_blank"}

自动交互布线技术


## High Speed

### [Auto-Interactive Delay Tune (AIDT) 自动等长高速选项](https://tiny-yhw.github.io//2023/06/15/cadence-allegro-aidt/){:target="_blank"}

用于自动调整一组设好match group的clines，使clines延时匹配

### [Auto-Interactive Phase Tune (AiPT)](https://tiny-yhw.github.io//2023/06/15/cadence-allegro-aipt/){:target="_blank"}

QIR 2（HotFix6）引入，用于自动调整一对或多对设好差分对内等长的差分线，使差分相位匹配

### [Timing Vision 等长长度实时可视化显示](https://tiny-yhw.github.io//2023/06/15/cadence-allegro-timevision/){:target="_blank"}

QIR 2（HotFix6）引入，将等长组的线长关系，以可视化的颜色表现出来，十分有利于等长调整时使用

### Offset Routing
允许用户在布线过程中采用非标准角度如15度进行布线，以使在玻璃纤维介质中走线时最大程度的降低阻抗的不连续性。
在使用Route-Connect命令布线时从Option面板勾选Route offset启用此功能
![route_offset.png](https://a1024.synology.me:222/images/route_offset.png)

### Fiber Weave Effect - Zig-Zag Routing 锯齿形布线

(HotFix51)新增功能
可将平行布线转换为锯齿形（斜角）路线。通过此种布线方式，可以最大程度地减少PCB玻璃纤维编织对高速信号路由的影响。此功能同时可用于差分对和单端网络。可以指定所需的曲折角度和最大线段长度，以及用于转换完整线段或定义起点和终点的选项。

![](http://a1024.synology.me:222/images/blog2022/highspped2.png)

使用方法：见动图

![](http://a1024.synology.me:222/images/blog2022/highspeed3.gif)


### Differential Pair Return Path Vias 差分回流过孔

回流过孔，也称为接地参考过孔，提供回流路径，以最大程度地减少过孔过渡期间PCB和封装互连中的信号衰减。电流必须始终返回其源极，因此，当信号使用通孔从一层转移到另一层时，返回电流将沿着阻抗最小的路径返回到源极。

(HotFix51)新增功能

使用方法：在Add connect命令时右键选择菜单Return Path Vias (Prototype)选择Setup设置回流过孔的参数包括，Setup标签页的过孔选择、网络选择和Spacing标签页的对应回流过孔类型的间距位置等参数，应用后再打孔时回流过孔会同时生成

![](http://a1024.synology.me:222/images/blog2022/highspped1.png)


### Remove Tuning移除等长绕线

将进行过Delay tune(等长绕线)的Cline，移除绕线的蛇形部分恢复直连，通过菜单中Route - Remove Tuning访问


### Auto Interactive Convert Corner (AiCC)

该命令用于批量切换（改变）走线拐角的角度（Arc、45、90）。其操作对象可以为Nets、Clines和Cline Segments
菜单：Route->Unsurpported Prototypes->Auto-interactive Convert Corner

![](http://a1024.synology.me:222/images/blog2022/Aicc.gif)


## Route Interconnect 布线交互

### Slide Overhaul 移线命令大修

16.6 版本对走线的*Slide*操作进行了很大的改进，改版后操作起来更加灵活、顺畅、可预测。该命令简化了使用模型，整合了任意角度和圆弧角度的滑动方式，并且提供了新的选项，以提高效率。

QIR 3(HotFix13) 更新在option中增加*Extend Selection*并提供三个选项

- Segments:将选择范围扩展到相邻线段。默认情况下，此选项处于选中状态。
- Vias:将选择范围扩展到相邻过孔。
- Segments and Vias:将选择扩展到相邻线段和过孔。

QIR 7 (HotFix32)更新允许在使用Slide命令时改变拐点的角度

此选项默认在Slide命令中不可见，可以通过*Design Parameter Editor*对话框中*Route*标签页勾选使其可用

![new_seg_angle.png](https://a1024.synology.me:222/images/new_seg_angle.png)

下图是使用此功能的一个案例

![new_seg_angle1.png](https://a1024.synology.me:222/images/new_seg_angle1.png)

### Smart Layer Behavior for Add Connect 布线智能图层选择

当使用Route-Connect命令布线时，Option 控制面板中的布线起始层会自动匹配Visibility控制面板中的唯一的可见层。

![smart_layer.png](https://a1024.synology.me:222/images/smart_layer.png)

### Disable Open Space Routing

当使用Route-Connect命令布线时，16.6之前的版本允许直接点击PCB中的空白区域进行随意布线，16.6 User Preference Editor的Route - Connect中新增环境变量“acon_disable_nullnet_route”，当设置后，用户不能再在空白区域进行布线。

### Line Width Retention during Add Connect 布线线宽重用

当使用Route-Connect命令布线时，线宽默认使用之前用户指定的线宽，并在Option中使用蓝色的线宽值显示，如需使用规则中指定的值，在此处切换为Constraint回复规则中指定的线宽值

![line_width_retention.png](https://a1024.synology.me:222/images/line_width_retention.png)

QIR 3(HotFix13) 更新增加一个新的环境变量*acon_no_width_override_retain*，允许启用或关闭此功能

### Fix Cline Segments 锁定线段

16.6 版本支持对cline segments进行Fix操作。

### Copy/Move Cline Segments

16.6 版本支持对Cline segs和Other segs进行复制/移动操作。

### Scribble Mode Routing 涂鸦模式布线

QIR 3(HotFix13)引入，而后进行多次更新

个人感觉有点鸡肋，没什么用途，在Add connect命令时通过右键菜单选择Scribble Mode激活此布线模式

![](http://a1024.synology.me:222/images/blog2022/scribble_mode_routing.png)

### Contour Routing 按轮廓布线

(HotFix51)中新增功能

软硬结合设计软区经常使用圆角，若布线路径预软区圆角路径一致可以获得更优质的布线空间

在Add connect命令时右键选择Contour，调整依附轮廓和间距参数，顺着轮廓描摹即可

![](http://a1024.synology.me:222/images/blog2022/highspped5.png)


## ToolBox

使用下述功能需启用Allegro Productivity Toolbox产品选项，可在软件启动时选择或File-Change Editor选择。

<iframe width="720" height="405" frameborder="0" src="https://v.qq.com/txp/iframe/player.html?vid=p0975ttcv0e" allowFullScreen="true"></iframe>

视频演示内容包含如下

- Advanced Mirror 高级镜像
- Change Width 批量修改线宽
- Cross Copy 跨Class类复制或移动
- Class颜色
- polar grid 极坐标格点的使用

### [Advanced Mirror 高级镜像](https://tiny-yhw.github.io//2023/06/15/cadence-allegro-advanced-mirror/){:target="_blank"}

说明：将多个对象按同面进行图形镜像或按镜像面镜像

使用方法：选择菜单Eidt - Advanced Mirror，调整Option，选择对象

### Change Width 批量修改线宽

说明：修改指定区域内某值线宽的Clines改变线宽

使用方法：选择菜单Eidt - Change Width，调整Option，选择目标层（可以是多个），选择区域

### Cross Copy 跨Class类复制或移动

说明：将一个Class的对象复制或移动到另一个Class（Change命令不能跨Class Change）

使用方法：选择菜单Eidt - Cross Copy，调整调整Option，选择对象

### Class颜色

说明：对用户定义过额Net Class标记一种颜色显示

使用方法：选择菜单DisPlay - Class Color，调整对话框并应用。

### [位号调整 Label Tune](https://tiny-yhw.github.io//2023/06/15/cadence-allegro-label-tune/){:target="_blank"}

位号自适应大小并居中

### [查看板中的过孔Via类型或焊盘Padstack类型](https://tiny-yhw.github.io//2023/06/15/cadence-allegro-padstack-finder/){:target="_blank"}

Padstack Finder使用户可以搜索设计中的各个Padstack进行查看。

## 3D Step

- 支持Step模型导入和导出
- 支持将Step模型映射到sym文件或pcb文件中
- 3D Viwer支持从PCB中查看真实的3D模型

### [Allegro PCB 导出3D Step](https://tiny-yhw.github.io//2023/06/15/cadence-allegro-pcb-3d-step/){:target="_blank"}

### [Allegro STEP Model在PCB Editor上的应用](https://tiny-yhw.github.io//2023/06/15/cadence-allegro-step-model/){:target="_blank"}

## Place Replicate 模块复用

### Place Replicate support of Text

模块复用时与元器件关联的Text也将同时被复用
见文章开头视频演示

### Placement Replication support for component level pin properties 支持管脚属性复用

模块复用（.mdd）时默认不会改变复用模块的管脚属性，在QIR2（Hotfix6）中新增一个环境变量*User Preference Editor - Placement - General - plc_rep_copy_attr*通过设置此变量，可以使模块复用时管脚属性被一起复用

## Shape操作

### [Shape Edit Application Mode](https://tiny-yhw.github.io//2023/06/15/cadence-allegro-shape-edit-application-mode/){:target="_blank"}

（HotFix51）新增功能,主要用于提高编辑shape的效率

### Shape Updating

在“Shape-Global Dynamic Parameters”中，新增命令“Force Update”，用于对Shape 进行强制更新操作。

![shape_update.png](https://a1024.synology.me:222/images/shape_update.png)

### Parameterized Cornering for Rectangular Shapes 倒角矩形

16.6 版本在执行“Shape-Rectangular”命令时，可以在Option 控制面板中设置自动将矩形的四个角进行倒角（chamfer）或圆弧角（Round）操作。

![rectangle.png](https://a1024.synology.me:222/images/rectangle.png)

### Shape Expansion/Contraction Shape的外扩和內缩

在General Edit 模式下，鼠标放在Shape 上，右键下拉菜单中新增“Expand/Contract”命令，用于改变Shape 的大小。
QIR2（Hotfix6）中更新对Void的支持，如果Shape内部存在手动的Void则其也将一同被外扩或內缩

![shape_1.png](https://a1024.synology.me:222/images/shape_1.png)

### Net assignment to multiple shapes

QIR2（Hotfix6）中*General Edit or Etch Edit*模式时支持对多个shapes一起增加网络，通过选择多个shape后右键选择*Assign Net*执行

### VOID_SAME_NET Dynamic Shapes

QIR 5（HotFix22)中新增VOID_SAME_NET属性对同网络shape的支持，相同网络shape有重叠时若包含VOID_SAME_NET则两个Shape会相互避让

![dynamic_shape.png](https://a1024.synology.me:222/images/dynamic_shape.png)

### Unassigned Shapes Update

在QIR 7 (HotFix32)中the NC pins assigned fillets will no longer be reported in the Shapes Without an Assigned Net report. This report is displayed when you choose Unassigned shapes button in the Status (Display - Status) dialog box.

### Lower Shape Priority  降低的形状优先级
（HotFix51）当铜皮存在交叉时选择指定铜皮右键选择提高或降低优先级来调整交叉部分的覆盖关系

![image063.png](https://a1024.synology.me:222/images/image063.png)


## Export 输出
### Artwork / Film Records Enhancements

- 在“Artwork Control Form”设置框中通过单击“Domain Selection”可以本将光绘文件的输出设置四种方式Artwork、IPC2581、PDF、
Visibility是否可用
- 中新增选项“Draw Holes Only”，即输出只包含引脚 或过孔的光绘文件。添加底片时须添加Pin Class 或Via Class 的信息；
- RS274X 数据格式支持有重叠的铜皮数据的输出；
- 光绘文件名称由之前的最大17 个字节增加至47 个；
- 光绘文件输出时支持删除未用到的焊盘；
- 如果有值为0 的线宽，输出日志（Photoplot.log）中会有警告；
- 光绘文件的单位默认与PCB 板采用相同单位；

### Artwork Control Form update

QIR 5（HotFix22）中Artwork Control Form中新增一个字段*PDF Sequence*，通过此字段可以控制生成PDF文件时Artwork各层的相对页码位置，如果此字段值相同则按Artwork层明字母排序确定顺序

![artwork_16.64.png](https://a1024.synology.me:222/images/artwork_16.64.png)

### Allegro PDF Publisher

QIR 5（HotFix22）输出PDF功能增加一个新选项*Filter Header/Footer and Filter Drawing Origin*

### NC Route Enhancements

16.6 版本进行NC Route 操作时，支持将金属化与非金属化的钻孔区分开。

![Snipaste_2023-06-13_15-42-48.jpg](https://a1024.synology.me:222/images/Snipaste_2023-06-13_15-42-48.jpg)


## Snap 和 Select 吸附和选择

### "Snap Pick to" updates

在执行“Edit-Vertex”命令时，右键下拉菜单中新增“Snap Pick to”命令。
Snap Pick to的对象增加几项

- Rectangle Edge Vertex  矩形边顶点
- Rectangle Edge Midpoint  矩形边中点
- Rectangle Edge  矩形边
- Shape Center  形状中心
- Symbol Center  符号中心

### Relative Snapping

QIR 5（HotFix22）中新增相对偏移吸附功能，可以让对象放到吸附点指定偏移值的位置

![relative_snapping.png](https://a1024.synology.me:222/images/relative_snapping.png)


### Select by Lasso or Path 套索或路径选择

16.6 版本鼠标右键下拉菜单Selection set 中新增两个命令“Select by lasso”和“Select by Path”。

![lasso.png](https://a1024.synology.me:222/images/lasso.png)

- Select by Lasso：以索套的方式选择对象；
- Select by Path：以鼠标经过的路径的方式选择对象，鼠标经过哪些对象则选取哪些对象。


### Persistent Snap and Selection 延续吸附和选择

之前默认的吸附对象或选择对象模式都是单一的，每次需要特殊的选择或者吸附时都需要重新选取，在（HotFix51）
版本中新增一种可以用于延续的功能

![image061.png](https://a1024.synology.me:222/images/image061.png)

从上图右键菜单指定对应的Persistent snap或Persistent Select模式后则此选项将被延续，后续使用所有命令的吸附或选择时，指定模式将一直存在，直到你主动切换模式


## Measure and Dimension 测量和标注

### Show Measure Support for Dual Units 显示对双单位的测量支持

16.6 版本在执行*Display-Measure*命令时支持两种单位的显示，如毫英寸和毫米。通过环境变量showmeasure_altunits 来设置第二显示单位。

![show_measure.png](https://a1024.synology.me:222/images/show_measure.png)
![Snipaste_2023-06-13_15-16-50.jpg](https://a1024.synology.me:222/images/Snipaste_2023-06-13_15-16-50.jpg)

### Display-Measure support of angle between two objects 显示两个对象的角度

在QIR 2（HotFix6）更新了*Display-Measure*命令，当测量两个对象时会列出两个对象的角度

![image009_2.png](https://a1024.synology.me:222/images/image009_2.png)

### Dimensioning   尺寸标注

QIR 6 (HotFix27)中在标注尺寸时运行使用*Mirror Text*命令标注镜像的文本

### Associative Dimensioning Updates 关联尺寸更新

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

## New Reports 新报告

在QIR 2（HotFix6）新增报告

- **Film Area:**各个artwork层叠中图形占比
- **Vias per net:**列出每个网络的过孔数量和过孔类型。
- **Vias per layer per net:**分层列出每个网络的过孔数量和过孔类型。

## Productivity Enhancements

### Component Alignment updates 元器件对齐

在Placement Eidt模式下选择元器件，右键选择Align Componment，调整Option

针对横向对齐或纵向对齐，可以设置不同的对齐方式，如左对齐、右对齐、上对齐、下对齐。针对对齐时元器件的间距，可以设置不同的间距值，如Option 控制面板中，Off 代表当前间距；Use DFA constraints 表示采用DFA 间距；Equal spacing 表示用户设置等间距。

![align.png](https://a1024.synology.me:222/images/align.png)

更多见文章开头视频演示

### Symbol Instance Refresh 刷新器件

16.6 版本支持在布局模式（Placement edit）下对单个元器件的更新操作，例如我们会经常将元器件的文本或者器件边框不慎删除，以往的操作方法是通过Place-Update Symbol 来进行恢复，16.6 版本可以直接将鼠标放置某元器件上，右键下拉菜单选择“Refresh symbolinstance”命令来实现，操作更为简单。

![Snipaste_2023-06-13_15-02-35.jpg](https://a1024.synology.me:222/images/Snipaste_2023-06-13_15-02-35.jpg)

此命令使您可以刷新PCB中已经放置的symbol。 该命令将恢复与symbol有关的数据。 例如，丝印框或文本。 

注意：此命令不会刷新库中的symbol，仅对PCB中选中器件生效。

应用：设计检查时发现的元器件某元素误删，可使用此功能恢复

#### 不完全测试结果

**Move对象**

- Line属性所有对象将被重置
- Shape属性所有对象将被重置
- Pinnumber对象将被重置
- 除Pinnumber对象外所有Text将被不会被重置

**Del对象**

- 所有被删除的对象将被重置

**总结**

- 除Pinnumber对象外所有被移动或改变Text不会被重置，其它所有对象将被重置


### Refresh Symbol Update

使用*refresh_symbol*命令时新增一个选项以保留与设计中的引脚相关联的焊盘堆栈名称，使其不被更新。

![image059.png](https://a1024.synology.me:222/images/image059.png)

### Add Circle - Ease of Use Improvements

16.6 版本在选择“Add-Circle”或“Shape-Circle”命令后，添加圆形Shape 时，可以在Option 控制面板中设置圆形Shape 的相关参数（半径、中心坐标）：

![Snipaste_2023-06-13_15-09-43.jpg](https://a1024.synology.me:222/images/Snipaste_2023-06-13_15-09-43.jpg)

### Change Radius of Line Drawn Circle 改变圆形半径

在General Edit 模式下，对于通过线绘制的圆形，16.6 版本支持通过右键下拉菜单中的“Change Arc/Circle”或“Change Radius”命令来改变圆形的大小。

![Snipaste_2023-06-13_15-09-49.jpg](https://a1024.synology.me:222/images/Snipaste_2023-06-13_15-09-49.jpg)


### Embedded Net Names   嵌入的网络名称

16.6 版本支持在走线、引脚、铜皮上显示其所在的网络名称。

![embedded_netname.png](https://a1024.synology.me:222/images/embedded_netname.png)

该功能只能在OpenGL 开启情况下实现，用户还可以通过“Setup-Design Parameters”来控制走线（Clines）、铜皮（Shape）和器件引脚（Pins）上是否显示网络名称。

![Snipaste_2023-06-13_15-14-17.jpg](https://a1024.synology.me:222/images/Snipaste_2023-06-13_15-14-17.jpg)


### Multiple Constraint Region Assignments

16.6 版本支持对单个或多个约束区域（Constraint Region）执行“Assign to Region”命令。

### Move Lines and Text outside Existing Class Structure

16.6 版本支持将线段（Lines）或文字（Text）信息转移到其他的类（Class）或子类（Subclass）
中，通过选择线段或文字，右键下拉菜单中的“change class/subclass”命令来实现。

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


### Highlight/Assign Color to Vias

在QIR 2（HotFix6）更新了*Highlight* and *Assign Color* 命令支持对Vias操作

### DRC marker - Link to Constraint Manager DRC标记连接到规则管理器

QIR 2（HotFix6）更新在*General Edit*模式时，将鼠标悬停在DRC标记上右键选择*Display DRC*将打开规则管理器并指向定位到该DRC。

### Ref-Des Layer Visibility Control

QIR 4(HotFix16) 当移动器件时默认显示元器件的ref-des的assembly text层文本，通过修改环境变量User Preference Editor - Display - General 中*display_refdes_subclass*可以指定让其显示
其它层的文本内容

![refdes.png](https://a1024.synology.me:222/images/refdes.png)

### Split Views分割视图

QIR 5 (HotFix22)引入，QIR 6 (HotFix27)有更新

将当前显示界面分割为两个部分，分别对焦不同的设计区域，当进行较长的布线时，可以直观清晰的看到连接两端的状态，通过菜单View-Split View访问

![](http://a1024.synology.me:222/images/blog2022/split_view16.66.png)

### Move Component with Slide Etch

QIR 6 (HotFix27)中新增移动器件时同时Slie与其相连的Etch的功能，这样在移动器件后器件的连接仍然保持不变


## Database & Misc Enhancements

### Net Group Constraint Object

在约束管理器中新增概念Net Group，来代替之前的Bus，Bus 可以通过编辑属性的方式来添加。

### New Design Defaults

16.6 版本支持用户设置默认的单位/精度等基本参数，通过*Setup-User Preferences*中的环境变量*new_units*和*new_accuracy*来进行设置。这样每新建一个设计，都会遵循默认的单位/精度。

### Find Filter update

Find 控制面板中新增多种查找对象（Match group, Net group, Net class, Pin pair, Diff Pair,Region）。

### Symbol Export

16.6 版本“File-Export”支持元器件电子表格（Symbol Spreadsheet）的输出，可以输出元器件引脚编号、名称、引脚连接的网络名称等信息，支持XML、TXT、CSV 三种格式，输出文件默认保存在当前工作路径下。

### Dump Libraries

以往版本中输出库时，默认保存在当前工作路径下，16.6 版本可以通过设置变量“dump_library_directory”来定义库的输出路径。

### Logo Import (Symbol Editor only)

在QIR 2（HotFix6）Symbol Editor 中新增导入单色位图.bmp文件的支持，通过菜单*File - Import*访问，默认图形被导入*Board Geometry - Silkscreen_Top*层

### Default Gerber Zero Line Width

(HotFix51)中新增环境变量*artwork_undef_line_width*可以定义一个全局的未定义线宽值

## 杂七杂八

- Add Connect选择其中一个飞线时可选让其它飞线隐藏
- 可对字号定义名称，更方便识别，而不是只叫1234
- 背钻功能增强（还差很多，有必要请使用17.2及以上版本）
- 尺寸标注关联到对象实时更新
- Find过滤器新增可过滤对象
- 新增重新编号符号引脚功能

## Find by Query（略）不好用而后在17.X中被完全更新
## RF PCB Enhancements（略） 我用的很少
## IPC2581 Enhancements（略） 我用的很少