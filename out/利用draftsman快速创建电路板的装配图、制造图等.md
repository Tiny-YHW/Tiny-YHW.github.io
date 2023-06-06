---
title: '利用Draftsman快速创建电路板的装配图、制造图等'
date: Tue, 07 Apr 2020 08:35:03 +0000
draft: false
tags: ['Altium', '设计技巧']
---

摘抄自Altium官网：[传送门](https://www.altium.com.cn/blog/%E5%88%A9%E7%94%A8draftsman%E5%BF%AB%E9%80%9F%E5%88%9B%E5%BB%BA%E7%94%B5%E8%B7%AF%E6%9D%BF%E7%9A%84%E8%A3%85%E9%85%8D%E5%9B%BE%E3%80%81%E5%88%B6%E9%80%A0%E5%9B%BE%E7%AD%89)

我们在完成PCB的设计之后，通常需要生成用于生产的各类图纸，比如装配图纸、制造图纸、和相关的BOM等文件。这些文件虽然都可以通过PCB设计软件的相关菜单获得，但是寻找相应的菜单和逐一生成各类文件都要花费时间不说，文件生成之后还需要将其整理并存放到一起以备后续使用，这个过程相当繁琐。那么有没有方法，可以将这些图纸都生成在一个文件中，并且可以对不同的图纸进行标注，从而将设计人员从创建和整理生产文件的繁琐手续中解脱出来，使其有更多的时间专注于更有挑战性的PCB设计呢？

答案是肯定的，Altium Designer提供了Draftsman扩展程序，专注于创建电路板设计产品的图形文档。Draftsman 作为传统的PCB生产文档的替代品，它可以根据需要自动放置装配和制造图纸，并包含各种手动绘图工具，还可用于添加重要细节和标注关键尺寸。

Draftsman的主要功能包括：

*   从源PCB文档中自动提取绘图数据；
*   创建多页文档；
*   将单独的模板应用于文档的每个页面；
*   从自定义模板自动生成图纸；
*   常用和附加的工程视图都可用（装配视图，制造视图，剖面视图或钻孔绘制视图）；
*   装配视图，包括从3D模型生成的图形（无需特殊PCB层）；
*   可自定义的板层堆栈图例（Layer Stack Legend），具有添加详细板层信息的选项；
*   BOM表，可以显示所有板项目或仅显示所选装配视图的项目；
*   放置标注以指出BOM项位置或备注清单中的条目；
*   支持装配变量；
*   打印和导出为PDF输出；
*   包含在OutJobs中，可将Draftsman PCB图形文件添加为新的文档输出。

Draftsman的功能这么多，是不是很想试试看呢？我们就先从生成Draftsman文档开始，对其一些主要功能及使用方法进行说明。

**创建新文档**
---------

首先打开一个设计项目，项目中要包含已经完成的PCB文档（本文中以Altium的示例项目DB46 Xilinx Virtex4-XC4VSX35   为例）。使用菜单命令File » New » Draftsman Document ，在Altium Designer中创建一个新的Draftsman文档，如下图所示。

![](https://www.altium.com.cn/blog/sites/cn.blog/files/19022712.png)

Draftsman 创建菜单

![C:\Users\CAIXIA~1.SON\AppData\Local\Temp\1540108254(1).png](https://www.altium.com.cn/blog/sites/cn.blog/files/19022714.png)

从指定项目的PCB创建一个空白或基于模板的Draftsman文档

**添加各类绘图和标记**
-------------

Draftsman应用程序允许将一系列用于PCB生产的绘图直接放置在Draftsman文档上。可以从Place主菜单中选择要放置的绘图类型，或是从编辑器的活动栏图标集中选择，如下图所示

![C:\Users\ROBERT~1.HUX\AppData\Local\Temp\SNAGHTML92622e.PNG](https://www.altium.com.cn/blog/sites/cn.blog/files/19022713.png)

Draftsman的活动栏图标集

1 装配视图及其属性

使用菜单Place » Board Assembly View ，或点击活动栏中的第一个图标，可以将对应PCB项目的装配图放置到文档中。

![](https://www.altium.com.cn/blog/sites/cn.blog/files/19022716.png)

![](https://www.altium.com.cn/blog/sites/cn.blog/files/19022715.png)

装配视图菜单（左）及对应的活动栏图标（右）

![C:\Users\CAIXIA~1.SON\AppData\Local\Temp\1540109408(1).png](https://www.altium.com.cn/blog/sites/cn.blog/files/19022718.png)

![C:\Users\CAIXIA~1.SON\AppData\Local\Temp\1540110294(1).png](https://www.altium.com.cn/blog/sites/cn.blog/files/19022717.png)

装配视图（左）及其属性面板（右）

上面的装配视图显示了带有孔和元件图形的电路板轮廓。我们只需在属性面板中对相应的属性进行设置，就可以移动、缩放、从不同方向查看已经放置的电路板装配视图。

属性面板的装配视图模式提供以下属性设置：

*   Scale –视图的缩放比例，默认值是1:1。
*   Title – 视图的标题名称、标题字体、颜色和标题位置。
*   Style – 电路板和元件的轮廓线的颜色、线宽、样式。
*   Properties – 其他属性，包括：
    1.  View Side – 查看视图的方向（例如从顶部看，得到的是顶部视图）。
    2.  Display holes – 过孔的显示。可设置为显示所有孔（All），仅显示孔径比最小孔径大的孔（Minimum diameter Only）或不显示过孔（None）等。
    3.  Minimum Diameter – 最小孔径。
    4.  Variation – 如果PCB项目中存在装配变量，则选择PCB项目中要显示的装配变量，没有被选择的变量元件不显示或标识为彩色网格。
    5.  Component Caption – 元件的标识名称，可以是元件标号(Designator)。

请试着操作一下，您将发现更多的属性参数及其功能。

**2 制造视图及其属性**
--------------

使用菜单Place » Board Fabrication View ，或点击活动栏中的第二个图标，可以将对应PCB项目的制造视图放置到文档中。

![](https://www.altium.com.cn/blog/sites/cn.blog/files/19022722.png)

![](https://www.altium.com.cn/blog/sites/cn.blog/files/19022720.png)

制造视图菜单（左）及对应的活动栏图标（右）

![C:\Users\CAIXIA~1.SON\AppData\Local\Temp\1540111442(1).png](https://www.altium.com.cn/blog/sites/cn.blog/files/19022727.png)

![C:\Users\CAIXIA~1.SON\AppData\Local\Temp\1540111478(1).png](https://www.altium.com.cn/blog/sites/cn.blog/files/19022723.png)

制造视图（左）及其属性面板（右）

上面的制造视图显示了电路板顶层的走线和过孔。我们只需在其属性面板中对相应的属性进行设置就可以移动、缩放、显示PCB加工视图的不同板层，并使用实心或轮廓铜填充进行渲染。

属性面板的制造视图模式下提供以下属性设置：

*   Scale – 视图的缩放比例，默认值是1:1。
*   Title – 视图的标题名称、标题字体、颜色和标题位置。
*   Style – 电路板轮廓线的颜色、线宽和样式。
*   Properties – 其他属性，包括：
    1.  Layer – 显示哪个板层。
    2.  View Side – 查看视图的方向（比如从顶部或底部查看）。
    3.  Drawing Mode – 板层上焊盘和走线的显示方式：实心填充（Full），或仅画出焊盘的轮廓并用细线表示连接的走线（Simplified）。
    4.  Polygon Fill Mode – 敷铜的显示方式： 实心（Filled），阴影填充（Hatched）或轮廓（Outline）。
    5.  Show Out of Board Copper - 显示位于电路板板外围的敷铜。

**3 细节展示视图**
------------

有一些器件由于本身体积较小或是视图的缩小比例较大，而无法在视图中清晰显示，这个时候可以在现有视图中添加一些细节展示图来清晰显示这些器件的情况。使用菜单Place » Additional Views » Board Detail View，即可在Draftsman文档的现有视图上放置细节展示视图。

![](https://www.altium.com.cn/blog/sites/cn.blog/files/19022725.png)

![](https://www.altium.com.cn/blog/sites/cn.blog/files/19022728.png)

细节展示视图菜单（左）及对应的活动栏图标（右）

![C:\Users\CAIXIA~1.SON\AppData\Local\Temp\1540126485(1).png](https://www.altium.com.cn/blog/sites/cn.blog/files/19022730.png)

![C:\Users\CAIXIA~1.SON\AppData\Local\Temp\1540112746(1).png](https://www.altium.com.cn/blog/sites/cn.blog/files/19022732.png)

细节展示视图（左）及其属性面板（右）

Draftsman文档的细节展示视图允许将视图的局部区域显示为其细节的放大视图，并可以在其属性面板中配置细节展示视图的放大比例、标注和线属性。

细节展示视图的放置过程如下：

1.  单击图形上的某个点，指定细节展示视图的目标区域中心。
2.  移动鼠标并单击，指定视图区域的半径（细节展示视图的数据源）。
3.  再次单击以确定细节展示视图扩展的位置。
4.  使用Properties面板中的Properties和Style部分设置细节展示视图与源区域的关联方式。
5.  细节展示视图可以添加到多种视图上：装配视图、 制造视图、剖面视图和钻孔视图。

**4 剖面视图**
----------

从PCB装配视图的指定切割线获取的截面图也称为剖面图，有助于详细展示装配视图。可以使用菜单 Place » Additional Views » Board Section View，或活动栏图标，创建PCB装配视图的剖面视图。

![](https://www.altium.com.cn/blog/sites/cn.blog/files/19022734.png)

![](https://www.altium.com.cn/blog/sites/cn.blog/files/19022736.png)

剖面视图菜单（左）及对应的活动栏图标（右）

![C:\Users\CAIXIA~1.SON\AppData\Local\Temp\1540113260(1).png](https://www.altium.com.cn/blog/sites/cn.blog/files/19022738.png)

![C:\Users\CAIXIA~1.SON\AppData\Local\Temp\1540113301(1).png](https://www.altium.com.cn/blog/sites/cn.blog/files/19022740.png)

剖面视图（左）及其属性面板（右）

Draftsman扩展程序从当前PCB获取可用的3D数据，来创建与指定切割线对齐的独立剖面图。可以从装配视图创建任意数量的剖面视图，并且可以在其属性面板中配置剖面视图的放大比例、切割线样式和放置模式（水平、垂直）。

创建剖面视图的步骤如下：

1.  将光标定位在装配视图上，其中垂直切割线将跟随光标移动 - 使用空格键在垂直和水平切割线之间切换。
2.  点击以设置切割线的位置
3.  将光标移动到线的两侧，设置视图方向（如切割线箭头所示），然后单击以确定方向。
4.  将新的剖面视图拖放到期望的位置。

**5 等轴测视图**
-----------

等轴测视图具有形象、逼真、富有立体感等特性，可以弥补普通视图过于平面化、无法展示立体结构的缺点，有助于深入理解PCB产品的实际结构。可以使用Place » Additional Views » Board Isometric View ，将对应PCB项目的等轴测视图放置到文档中。

![](https://www.altium.com.cn/blog/sites/cn.blog/files/19022704.png)

等轴测视图菜单

![](https://www.altium.com.cn/blog/sites/cn.blog/files/19022702.png)

![C:\Users\CAIXIA~1.SON\AppData\Local\Temp\1540122590(1).png](https://www.altium.com.cn/blog/sites/cn.blog/files/19022703.png)

等轴测视图（左）及其属性面板（右）

可以在其属性面板对已放置的等轴测视图进行设置：使用Face Side 下拉菜单选择视图的视角；如果存在设计变量的话，还可使用Variants下拉菜单指定显示的设计变量。

**6\. 写实视图 （该功能是AD19 的新增功能）**
-----------------------------

写实视图是一种单独且可以配置的视图，它提供了当前电路板设计的可缩放3D渲染视图，并可以根据PCB编辑器中当前视图的样式更新写实视图。使用菜单 Place » Additional Views » Board Realistic View，或活动栏图标，可以创建PCB的写实视图。

![](https://www.altium.com.cn/blog/sites/cn.blog/files/19022704.png)

![](https://www.altium.com.cn/blog/sites/cn.blog/files/19022705.png)

写实视图菜单

![C:\Users\CAIXIA~1.SON\AppData\Local\Temp\1548814979(1).png](https://www.altium.com.cn/blog/sites/cn.blog/files/19022706.png)

![C:\Users\CAIXIA~1.SON\AppData\Local\Temp\1548815376(1).png](https://www.altium.com.cn/blog/sites/cn.blog/files/19022707.png)

写实视图（左）及其属性面板（右）

在属性面板的写实视图模式下，选择View 区域的 Custom 选项后，以下两个按钮会变为可选择状态：

*   Take Current Camera Position：按照当前PCB编辑器中3D视图的视角更新写实视图。
*   Take Current View Conguration：按照当前PCB编辑器中3D视图的样式更新写实视图。

这两项的具体用法如下：

点击Take Current Camera Position按钮，写实视图会按照PCB编辑器中电路板视图的当前角度进行调整（操作前，请确保PCB编辑器处于3D视图模式下）。下面是点击该按钮之后，PCB编辑器中电路板的3D视图与写实视图的对比。

![](https://www.altium.com.cn/blog/sites/cn.blog/files/19022708.png)

![C:\Users\CAIXIA~1.SON\AppData\Local\Temp\1548826097(1).png](https://www.altium.com.cn/blog/sites/cn.blog/files/19022709.png)

PCB编辑器中电路板的3D视图（左）与更新后的写实视图（右）

点击Take Current View Configuration 按钮，写实视图会按照PCB编辑器中电路板当前视图的配置进行调整（操作前，请确保PCB编辑器处于3D视图模式下）。下面是点击该按钮之后，PCB编辑器中电路板的3D视图与写实视图的对比。

![C:\Users\CAIXIA~1.SON\AppData\Local\Temp\1548816423(1).png](https://www.altium.com.cn/blog/sites/cn.blog/files/19022710.png)

![](https://www.altium.com.cn/blog/sites/cn.blog/files/19022711.png)

PCB编辑器中电路板的3D视图（左）与更新后的写实视图（右）

**注释和绘图工具**
-----------

1.尺寸

Draftsman文档上除了可以放置各种视图之外，还可以对视图上的对象轮廓进行标注，以指示对象轮廓的长度、大小和角度，或指定对象之间的距离。要标注对象的尺寸，可以从Place的下拉菜单或从活动栏图标中选择所需的尺寸类型。

![](https://www.altium.com.cn/blog/sites/cn.blog/files/19022719.png)

![](https://www.altium.com.cn/blog/sites/cn.blog/files/19022721.png)

尺寸菜单（左）及对应的活动栏图标（右）

其中，使用最多的是以下三种尺寸：线段尺寸（Linear Dimension）；直径尺寸（Radial Dimension）和角度尺寸（Angular Dimension）。

尺寸标注非常简单：首先选择要放置的尺寸类型，并将光标移动到要标注的对象上；在对象变成橙色后，点击并按住对象，然后拖动鼠标，即可出现相应类型的尺寸标注，如下图所示。

![C:\Users\CAIXIA~1.SON\AppData\Local\Temp\1540136431(1).png](https://www.altium.com.cn/blog/sites/cn.blog/files/19022724.png)

![C:\Users\CAIXIA~1.SON\AppData\Local\Temp\1540136574(1).png](https://www.altium.com.cn/blog/sites/cn.blog/files/19022726.png)

![C:\Users\CAIXIA~1.SON\AppData\Local\Temp\1540136651(1).png](https://www.altium.com.cn/blog/sites/cn.blog/files/19022729.png)

线性尺寸 径向尺寸 角度尺寸

2\. 物料清单（BOM）

Draftsman扩展程序允许将物料清单、钻孔表、数据表放置在同一文档上，表中数据均直接来自项目中的PCB文件。它提供了一种简单、直观的方式来显示PCB制造和装配过程的关键信息。

物料清单（Bill of Materials）、钻孔表（Drill Table）、数据表（Table）的放置选项位于主菜单Place下，也可以使用活动栏上的相应图标。

![](https://www.altium.com.cn/blog/sites/cn.blog/files/19022731.png)

![](https://www.altium.com.cn/blog/sites/cn.blog/files/19022733.png)

表单菜单（左）及对应的活动栏图标（右）

只要点击所需表单的菜单，即可在文档上放置相应的表单，操作起来非常的简单！下图给出了放置到Draftsman文档上的物料清单及其属性，同时钻孔表和数据表也可以通过类似的操作进行放置。此外，我们还可以使用BOM属性面板的Columns选项卡管理表中的数据列。但是，列的分组和内容将取决于BOM本身的配置方式。

![C:\Users\CAIXIA~1.SON\AppData\Local\Temp\1540137900(1).png](https://www.altium.com.cn/blog/sites/cn.blog/files/19022735.png)

![C:\Users\CAIXIA~1.SON\AppData\Local\Temp\1540140330(1).png](https://www.altium.com.cn/blog/sites/cn.blog/files/19022737.png)

物料清单（左）及其属性面板（右）

以上都是Draftsman的一些常用功能，除此之外，它还具有很多额外功能，比如对图纸进行注释、标注等，这里就不一一说明了。

大家肯定还存在疑惑：毕竟一个文档的大小是有限的，Draftsman文档上能放置这么多的图纸和表单吗？如果一页不够的话，怎么添加多页呢，是跟添加原理图一样的方法吗？

Draftsman文档添加图纸跟原理图添加的方法还是不太一样的，不过也非常简单。可以使用菜单Tools » Add Sheet ，或右键点击文档的空白处并选择Add Sheet，实现添加文档页面。

![](https://www.altium.com.cn/blog/sites/cn.blog/files/19022739.png)

![](https://www.altium.com.cn/blog/sites/cn.blog/files/19022701.png)

Tools主菜单添加页（左）或右键单击菜单添加页（右）

文档输出

Draftsman文档与Altium Designer中的其他文档（原理图、PCB等）具有相同的打印或导出方式。要将此文档导出为单个或多个页面的PDF文件（由文档结构确定），可以从主菜单中选择File » Export to PDF，然后根据提示进行设置即可。