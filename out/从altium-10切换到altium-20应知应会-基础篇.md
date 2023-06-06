---
title: 'PCB设计从Altium 10切换到Altium 20应知应会-基础篇'
date: Wed, 13 Jul 2022 06:51:45 +0000
draft: false
tags: ['Altium']
---

![](https://a1024.synology.me:222/images/blog2022/AD10-AD20.jpg)

为什么写这篇文章
--------

得益于Altium软件（后文可能称呼其为阿腾）最近几年其工程师对其软件大改特改，在我看来这个软件现在已经变得非常好用了。大概10年前我刚入行时学习使用的是阿腾和Allegro（后文可能称呼其为阿狗），那时候我们使用的阿狗都是16.3版本；阿腾使用的是10版本，几乎所有同时使用这两款软件的人都是认为阿狗比阿腾好用的多，我们会更喜欢用阿狗做PCB设计。

时过境迁现在阿腾已经进化到了22版本，阿狗进化到了17.4版本，我经历这两款进化过程中的各个阶段，用的时间久了，夸张的讲我会感觉阿腾软件越来越像一个PCB设计软件；阿狗则更像一个绘图工具，不知道会不会有人更我有同样的感觉。

本次文章的主角是阿腾同学，阿腾同学最近几年的进步非常明显，尤其是16->17,17->18这两次大版本功能迭代做出的重要改变，不得不说这两次迭代功能性都强了很多，但有一部分改变还是让我有一些不舒服，都过去了具体不再赘述了。后边18->22版本于我而言更大的意义在于其版本优化和功能完善，到了22版本我在使用过程中几乎不再有不舒服的感觉了，至此我会推荐所有已经熟悉阿腾但至今仍停留在17及之前版本的的同学都可以尝试切换升级到21及之后的版本了，熟悉了之后的版本后相信你会由衷的感受到阿腾同学是真的棒！

我给身边很多使用阿腾的人推荐过让其切换升级到新版本，但经常收到的回复是“不会用”、“用不习惯”、“很多命令或功能找不到”等等一些负面的答复，所有本文应运而生，我将基于我的设计习惯整理出Altium10到Altium 20一些跨度较大的一些逻辑功能及UI设计的改动点，解决这些“不会用”、“不习惯”、“找不到”的问题，本次文章将着重讲述有改变的基础功能，希望通过本次文章的学习能让你无缝切换到高版本的使用中，而更多进阶性的功能则需要你自行探索或者从我发表的其它文章或视频来进行了解。

本文部分动图来源于阿腾官网，默认只播放一次，需要再次观看，鼠标指向其右键选在在新标签中打开图片，可再次观看。

选择和过滤
-----

选择过滤器有利于让我们更灵活的选择特定类型的对象，在进行任何选择操作时应注意选择过滤器的设置，只有被选择过滤器对应类型元素被开启允许选择时才能使用选择选择到指定对象。

### 选择过滤器

选择过滤器可以从两个位置访问

**属性面板**

当设计面板没有任何命令且没有任何对象被选择时，可以从属性面板（通过键盘快键键F11打开或关闭）顶端Selection Filter处进行访问

![](https://a1024.synology.me:222/images/blog2022/1selectionfilter.png)

*   All-On处按钮可以切换所有对象开启，所有对象关闭，用户自定义三种选择状态
*   对象类型按钮为蓝色时代表其被允许选择

**PCB绘图界面**

PCB绘图界面顶端靠近中间位置第一个图标为选择过滤器，具体功能同上

![](https://a1024.synology.me:222/images/blog2022/2selectionfilter.png)

### 选择对象

**简单选择**

将鼠标悬停在需要被选对象处，通过鼠标单击选择对象，再次单击对象取消对应的选择

默认选择对象不是累计的，单击另一对象时之前的选择将被清除，若要保持原选择需要按住键盘Shift键再进行选择或取消选择

**选择控制**

按住Alt选择：选择且仅选择Connection（飞线）对象

按住Ctrl选择：选择器件的模式为选择元器件的子对象如元器件的焊盘、位号但元器件不被选择（调丝印是批量移动对象非常好用），不按Ctrl选择器件则选择的是元器件而不是元器件子对象

按住Shift选择：对对象进行加选或减选，选择为范围选择时统一识别为加选，点击指定对象时则切换为加选或减选

无命令时按键盘X键访问取消选择相应的命令，可在已经多选的对象的基础上进行减选

**选择矩形区域**

要选择一个区域多个对象时可以通过按住鼠标左键并进行拖动选择一个矩形区域的多个对象，使用选择矩形进行选择的行为取决于拖动的方向——从左到右或从右到左决定是选择区域内部或选择接触

![](https://a1024.synology.me:222/images/blog2022/selectrec.png)

![](https://www.altium.com/documentation/sites/default/files/wiki_attachments/270571/PCBSmartDragSelectionEx.gif)

**任意形状选择**

无命令时按键盘S键可以访问多种选择命令，Lasdo Select是一个新增的选择方式，允许用户通过按住（不按住也可以）鼠标左键并进行拖动选择一个跟随鼠标绘制路径的任意形状区域，选择行为与选择矩形区域是一样的

![](https://www.altium.com/documentation/sites/default/files/wiki_attachments/270571/PCBLassoSelectEx.gif)

**选择记忆**

原理图和 PCB 编辑器中提供了八个选择存储器，可用于存储和调用原理图或 PCB 上多达八组对象的选择状态。选择您要记住的对象，然后将它们存储起来以便以后快速调用。

提供以下选择记忆选项：

*   存储在内存中（**Ctrl**  + 数字**1**到**8**）
*   添加到内存（**Shift**  + 数字**1**到**8**）
*   从内存中调用（**Alt**  + 数字**1**到**8**）
*   从内存中调用和添加（**Shift**  + **Alt** + 数字**1**到**8**）
*   应用内存作为设计空间过滤器（**Shift**  + **Ctrl**  + 数字**1**到**8**）。

您还可以使用**Edit » Selection Memory**子菜单访问选择记忆。

或者，使用通过按**Ctrl+Q** 打开的“_选择内存”_对话框。单击 **STO**按钮以存储选择或单击**RCL**以调用选择。控制面板底部的过滤选项将决定选择的显示方式。

**Select Next**

这个神级命令我还没想到一个配的上这个功能的名字，暂且叫它联想选择吧，使用快捷键Tab访问

在设计中选择初始对象后，此命令用于扩展选择以包括基于逻辑层次结构的下一个更高级别的对象（或多个对象）。

![](https://www.altium.com/documentation/sites/default/files/wiki_attachments/270571/SelectNextMultipleNetsEx.gif)

联想选择的联想逻辑参考如下，需要实际体验一下，效果极佳

*   _Track Segment_ ---> _All Connected (Contiguous) Track on the Same Layer_ ---> _All Connected Copper_ ---> _All Electrical Objects in the Associated Net_
*   _Connected Pad_ _\---> All Connected (Contiguous) Track on the Same Layer ---> All Connected Copper_ _\---> All Electrical Objects in the Associated Net_
*   _Unconnected Pad_ ---> _All Electrical Objects in the Associated Net_
*   _Via_ ---> _All Connected (Contiguous) Track on Layers Associated with Via ---> All Connected Copper_ _\---> All Electrical Objects in the Associated Net_
*   _Copper (Region/Polygon Pour/Fill)_ ---> _All Connected Copper_ _\---> All Electrical Objects in the Associated Net_
*   _Free Pad/Via ---> All Connected (Contiguous) Track on the Same Layer as Pad, or on Layers Associated with Via---> All Connected Copper_ _\---> All Electrical Objects in the Associated Net._

### 后选择过滤器

当被选择的对象包含多种类型元素时，如果希望通过属性面板修改其中一种类型元素的参数时，可以通过后选择过滤器完成类似操作，以下是一个修改一个网络连接线线宽的示例

![](https://a1024.synology.me:222/images/blog2022/houselect1.gif)

Snap吸附，光标捕捉
-----------

PCB 编辑器是一个基于网格的设计环境 - 设计对象一般放置在用户指定的格点上，除了捕捉格点外还包括许多额外的捕捉功能，旨在帮助您准确定位和对齐设计对象。这些功能统称为_统一光标捕捉系统_。

“光标捕捉”是鼠标光标在屏幕上时操作对象将会按照一定逻辑指定到鼠标附近的一个位置而不一定是鼠标的显示位置，比如仅开启格点时，对象坐标将识别为离鼠标最近的一个格点；开启吸附对象时，对象坐标将识别为距离鼠标最近的一个吸附对象的坐标

当设计面板没有任何命令且没有任何对象被选择时，可以从属性面板（通过键盘快键键F11打开或关闭）顶端附近Snap Option处进行访问光标捕捉的相应设置

另外可以从PCB设计界面顶端第二个磁铁图标或者使用键盘快捷键Ctrl+E调取后对其进行设置

![](https://a1024.synology.me:222/images/blog2022/snap.png)

*   **Grids**\- 用于切换光标是否将捕捉设计格点。启用此选项后，光标将拉动或捕捉到最近的捕捉网格位置。
*   **Guides** - 用于切换光标是否捕捉到手动放置的线性或点捕捉参考线。
*   **Axes**\- 用于切换光标是否将轴向对齐（在 X 或 Y 方向）到启用的对象以进行捕捉。**轴捕捉范围**定义了 X 或 Y 轴对齐触发的距离。当从当前光标位置到轴向对齐的对象捕捉点（热点）实现对齐时，将显示动态对齐引导线。
*   **Snapping**：选择被吸附对象所在层。使用快捷键Shift+E可以循环切换这三种模式
    *   All layers：位于所有层的可见对象允许被吸附；
    *   Current：仅位于当前活动层的可见对象允许被吸附；
    *   Off：关闭吸附
*   **Objects for snapping**：选择开启或关闭哪些对象允许被捕捉，较早的版本圆弧中心是不能吸附的，后面增加了这个对象方便多了，当然还有一些其它的选项自行探索一下吧。
*   **Snap Distance**：当光标在距启用的对象捕捉点的此距离内时，光标将捕捉到该点。
*   **Axis Snap Range**：当光标轴向对齐并且距启用的对象捕捉点在此距离内时，将显示一条动态引导线以指示已实现对齐。

捕捉行为仅在显示编辑光标（十字准线）时发生，例如在对象放置或移动期间。

捕捉行为发生时，如果不希望吸附任何对象，可按住键盘Ctrl键临时关闭所有吸附

跳转下面这个链接查看视频演示

[https://www.altium.com/documentation/sites/default/files/wiki\_attachments/305408/Snap\_Demo\_AD21\_0.mp4](https://www.altium.com/documentation/sites/default/files/wiki_attachments/305408/Snap_Demo_AD21_0.mp4)

板信息
---

当设计面板没有任何命令且没有任何对象被选择时，从属性面板Snap Option下方查看，这里包含了板子的基础信息包括板长、宽、（长宽来源于定义板框的最长和最宽值，而不是任意机械层的图形尺寸）器件占面积、器件密度、器件数、pin数、网络数等

![](https://a1024.synology.me:222/images/blog2022/boardinfot.png)

属性面板
----

上面三个段落介绍了改版后几个关于设计PCB的基础设置和信息，这些信息在老版本中位于各个不同的对话框中，在新版本中这些信息都被集中到了此处，用户可在一个窗口对其进行设置和查看，上述三个段落都是在无命令且没有对象被选择时属性面板的状态。

熟悉使用高版本后，一般属性面板都是常驻在设计界面中的，它集中管理着板基础设置和信息（上面三个段落）、当前设计命令的的参数设置和被选对象的属性信息

### **属性面板命令参数**

当PCB使用任何带参数的命令时如布线，放置字符，布铜皮等，每当此类命令在PCB编辑界面被使用时属性面板都会立即变更为对应命令的参数，按Tab键后可对对应参数进行调整，再次按Tab键恢复PCB编辑界面继续操作

### 对象属性信息

PCB中有任何对象被选中时，属性面板状态将变更为对应选择对象的属性参数，可以通过修改参数值修改对象

当仅有同一种类型的对象被选择时，属性面板将显示此类对象的所有可选参数

当选中多种对象类型时，属性面板将仅显示被选对象具有相同参数的项，如同时选择一个导线和过孔时，则仅有net属性和位置信息。而单独选择导线是还有宽度、层等属性，单独选择过孔时还有孔径盘径等属性

当选中多种对象类型，但仅需要更新某一种多少量几种对象的属性时可通过上文后选择过滤器进行过滤后再进行参数调整

当选择被选择过滤的多个对象某个属性值全都相同时，对应的属性值将显示为实际数值；当属性值不全部相同时，对应的属性值将显示为“\*”，不管其为数值或“\*”，只要需要修改，均可以通过重新填入你需要的值，改变这个对象的属性

**神级功能assign net**

属性面板新增一个给选择的对象赋予网络功能，通过选择PCB上的导体，再点击属性面板网络名右侧的吸管工具，再从PCB上选择一个带有你目标网络名的物理即可

![](https://a1024.synology.me:222/images/blog2022/assignnet.gif)

功能设计非常完美，如果你经常使用这个功能可以对其指定一个快键键，这个功能对应的命令为“Assign Net”

差分线规则
-----

在老版本中若要定义差分线规则，需要分别在线宽规则中设置线宽，在差分规则中设置间距，新版本中更改为线宽和间距规则均在差分线规则中进行设置，更为简单明朗

![](https://a1024.synology.me:222/images/blog2022/diff.png)

Polygon铜皮的更改与更新
---------------

老版本中完成第一次Polygon后再次修改其轮廓较为繁琐，新版本主要使用如下两种方式改变铜皮轮廓

选中铜皮后其轮廓描点会被显示出来，直接拖拽描点或描点所在的边即可直接更改

选择铜皮后右键选择Plygon Action->Modify Polygon Border然后选择边缘上一个点后重新绘制一条新边缘取代原来的一部分边缘

![](https://www.altium.com/documentation/sites/default/files/wiki_attachments/296870/Modify_Polygon_Border_AD18.gif)

关于铜皮的更改操作可以查阅这个[链接](https://www.altium.com/documentation/altium-designer/editing-polygonal-shaped-pcb-design-objects)

至于铜皮被修改后铜皮的更新是遵循软件首选项设置的，勾选黄框内两个选项则铜皮或与其相关的对象被更改后铜皮会直接重新生成，若这两个勾均没有被勾选（默认如此）则铜皮或与其相关的对象被更改后铜皮不会有任何改变，若需要重新生成某个或某几个铜皮可选中铜皮后通过Plygon Action->Repour Selected（键盘快捷键为YR）或者Repour All更新选中的铜皮或所有铜皮

![](https://a1024.synology.me:222/images/blog2022/polyxiugai.png)

View Configuration
------------------

新板层显示控制采用了一个全新的UI设计，部分逻辑稍有改变

**Layer&Colors标签页**

原来Sigal Layers和Plane Layers分属两个部分显示，现其统一到一个部分，按层叠顺序排列

![](https://a1024.synology.me:222/images/blog2022/viewconfiguraa.png)

Component Layer Pairs包含原来的Mask Layer和Silk Layer两个部分，并将Top和Bottom划分为左右两个区域方便区分查看

Component Layer Pairs还允许用户添加更多的用于对称的机械层，如3D实体，布局边框等，当定义好对称的层叠后若镜像对象操作时对应的对称层叠也会一起到对称的层面，和丝印层的逻辑一样

![](https://a1024.synology.me:222/images/blog2022/viewconfiguraa2.png)

在Component Layer Pairs或Mechanical Layers选中层右键菜单可以选择增加Component Layer Pairs或Mechanical Layers层或者删除选中的层

**View Option**

View Option页面如下图Configuration处可以对常用层显示定义保存模版，方便再次调用，此设置跟随软件设置，不根据PCB板而改变

从Configuration选框处选择系统定义或自定义层显，则预设的层显将被再次被调用，Configuration选框右侧三个按钮分别为新建、保存、删除用于管理预设层显

![](https://a1024.synology.me:222/images/blog2022/viewconfiguraa3.png)

Object Visibility替代原Show/Hide指定元素的标签页，眼睛控制开关，Draft控制草图模式，右侧Transparency处滑块控制对应元素的透明度

![](https://a1024.synology.me:222/images/blog2022/viewconfiguraa4.png)

其它个别问题
------

### 问题：叠层不能做不对称层叠，对称层叠不能指定不同的內缩值

解释：在新版叠层管理对话框其属性面板有个Stack Symmetry（层叠对称），如果这个选项为勾选则所有层叠一定要求对称且参数一致，如下图L3，L4层不能分别为Singal和Plane；L2和L5的Pullback distance（平面內缩值）是联动更改的，若要使用不对称层叠或者对称层需要不同的参数时需要选择去掉这个Stack Symmetry勾选，这个选项默认是勾选的

![](https://a1024.synology.me:222/images/blog2022/cengdie.png)

### **问题：不能做单层禁布图形**，导线压禁布不报错

老版本可以选择单层元素对象，修改其属性增加keepout则对象将被视为keepout

新版本中不再支持这样操作，如果需要单层禁布需要选择菜单命令Place->Keepout->选择禁布图形样式，在对应层绘制图形，且新版本禁布可区分不同类型的禁布对象，可按需选择

![](https://a1024.synology.me:222/images/blog2022/keepout.png)

### 问题：老版本中的Single Layer Mode怎样启用

从View Configuration中按住键盘Ctrl键单击图层前面的眼睛，眼睛被一个方框框起来，这种状态的图层被打开时，在单层模式时也仍然可突出可见

### 问题：为什么选择器件原理图与PCB不交互

PCB与原理图交互在软件设置里面设置，交互选项默认是关闭的，可以通过下图进行详细设置

![](https://a1024.synology.me:222/images/blog2022/Crossselection1.png)

*   Cross Selection:是否启用交互的总开关，勾选代表启用交互，切换快捷键位Ctrl+Shift+X
*   Dimming、Zooming:当选择对象交互时突出交互对象、根据交互对象缩放到合适的视图
*   Resposition:开启此选项时，若从原理图选择一个器件，再回到PCB窗口，器件会出于鼠标处且出于移动命令状态，可以直接将器件放置到你需要的位置，初布局时可以用用。
*   右边Comp、Nets、Pins：允许交互对象的开启和关闭

### 问题：是否存在跨版本问题

跨版本问题不能一概而论，理论上阿腾6.3及之后的版本都是PCB Binary V6.0格式，本不应该存在版本差异的，但实际因为新功能的增加或者一些意外情况，有可能会出现跨版本问题，本处将罗列我已知的跨版本问题

阿腾14开始针对差分线线宽线间距一齐设置，切换版本时，规则管理对于此项处理逻辑不一样，需重新定义线宽使用规则

阿腾15开始支持xSignals如果 从15及之后版本规则管理器设置了此功能，使用15之前的版本开设计修改时，因DRC会判断无效程序一直报错，可以通过删除此类规则解决此问题（本条规则应该对所有高版本支持的规则类目语法有效，举一反三）

有时候PCB用不同版本保存时，尤其是高版本保存后，再用低版本打开时会出现PCB像是出现Bug了一样，所有元器件不能被选中，视图显示残缺不完整这类问题，可以尝试使用阿腾17版本打开保存一下，再用更低版本查看一般能解决这类问题