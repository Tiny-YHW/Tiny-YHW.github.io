---
layout: post
title: Altium Designer之多图纸设计
categories: Altium PCB
date: 2023-07-22
permalink: altium-top-and-repeat
excerpt:
---

页面结构
----

### 基本概念

当进行大型工程设计时，只靠一张图纸是无法实现的，这时需要用多个图纸进行开发设计。一个多图纸设计工程是由逻辑块组成的多级结构，其中的每个块可以是原理图或是 HDL文件，在这结构的最顶端是一个主原理图图纸——工程顶层图纸。

多图纸结构一般是通过图表符（sheet symbol）形成，一个图表符对应一个子图纸；在主原理图图纸放置图标符，通过图表符与子图纸进行连接，而子图纸也可以通过图表符与更底层的图纸连接。通过点击“Place》Sheet Symbol”或 图标来放置图标符号。

![](https://tiny-y.asia/images/blog/2022/Altium%20Designer%E4%B9%8B%E5%A4%9A%E5%9B%BE%E7%BA%B8%E8%AE%BE%E8%AE%A11.png)

我们可以在“Designer”区域输入标识符，若标识符包含有Repeat关键字的语句，还能实现多通道功能（下文有详解）。而在“File Name”输入想要调用的子图纸文件名称（不分大小写），则可实现对子图纸的调用。还有其他方法能生成图表符，具体方法见下文。

当多图纸工程编译好后，各个图纸间的逻辑关系被识别并建立一个树形结构，表示各个图纸的逻辑关系

![](https://tiny-y.asia/images/blog/2022/Altium%20Designer%E4%B9%8B%E5%A4%9A%E5%9B%BE%E7%BA%B8%E8%AE%BE%E8%AE%A12.png)

### 层次结构

层次结构包含如下三种：

*   自上而下：在主原理图图纸下，通过“Design》Create sheet from symbol”、“Design》Create HDL file from symbol》Create VHDL file from symbol”与“Design》Create HDL file from symbol》Create Verilog file from symbol ”等命令创建子图纸、底层VHDL文件和底层Verilog文件。
*   在主原理图图纸下，通过“Design》Create symbol from sheet or HDL ”和“Design》Create symbol from sheet or HDL ”、“Design》Create Component  from sheet ”等命令创建图表符和顶层元件。
*   混合原理图/HDL文件层次：这种情况下，图表符通过不同的文件名称来调用HDL文件或原理图

### 层次结构维护

#### 端口与图纸入口的同步

当子图纸中的端口与图纸入口不匹配（包括名字和IO类型）时，可以通过“Design》Synchronize Sheet Entries and Ports”来同步

![](https://tiny-y.asia/images/blog/2022/Altium%20Designer%E4%B9%8B%E5%A4%9A%E5%9B%BE%E7%BA%B8%E8%AE%BE%E8%AE%A13.png)

选中不同步的端口，若想改变子图纸的端口，使其与图表符匹配，则选中间的图标（第一个）；相反就选第二个。

#### 重命名图表符对应的子图纸

若想重命名一个图表符对应的子图纸，一般的思路是先改子图纸的名称，然后再改图表符的“file name”，最后编译工程。现在AD提供了重命名子图纸的功能“Design》Rename Child Sheet”，出现浮动的十字光标，点中想重命名的图表符。

![](https://tiny-y.asia/images/blog/2022/Altium%20Designer%E4%B9%8B%E5%A4%9A%E5%9B%BE%E7%BA%B8%E8%AE%BE%E8%AE%A14.png)

我们可以根据自己的需要设置相关的选项。

### 多通道设计

在设计过程可能会重复使用某个图纸，此时我们可通过两个方法实现：

*   通过多图表符重复调用同一个子图纸
*   通过具有Repeat关键字的图表符

这里具体介绍下第二种方法：在图表符的“Designator”区域输入包含Repeat的语句，其格式如下：

```
Repeat(SheetSymbolDesignator, FirstInstance, LastInstance)
```

其中，SheetSymbolDesignator是图表符的本名，FirstInstance和LastInstance一起定义了通道数；注意FirstInstance参数必须等于或大于1，如下图所示，表示了2个filter通道。

![](https://tiny-y.asia/images/blog/2022/Altium%20Designer%E4%B9%8B%E5%A4%9A%E5%9B%BE%E7%BA%B8%E8%AE%BE%E8%AE%A15.png)

### 单个图表符调用多个子图纸

在图表符的“File Name”区域输入多个子图纸文件的名称，并用分号隔开，则能实现单个图表符调用多个子图纸的目的；而这些子图纸间的相互连接可通过跨图纸接口（off-sheet connectors）实现。

网络连通性
-----

### 各类网络标识符

由于我们使用到多图纸功能，这时需要考虑图纸间的线路连接。在单个图纸中，我们可以通过简单的网络标签“Net Label”来实现网络的连接；而在多图纸中，网络连接涉及到的网络标识符比较多，下面具体介绍：

最基本的网络标识符是网络标签（net labels）。在单个图纸内，它们可以代替导线来表示元件间的连接，在多图纸设计中，其功能未变，只能表示单图纸内部的连接。

端口（Port）既可以表示单图纸内部的网络连接（与net labels相似），也可以表示图纸间的网络连接。端口（Port）在多图纸设计中，可用于纵向连接和横向连接。横向连接时，可以忽略多图纸结构而把工程中所有相同名字的端口连接成同一个网络。纵向连接时，需和图表符、图纸入口相联系——将相应的图纸入口放到图纸的图表符内，这时端口就能将子图纸和父系图纸连接起来。

跨图纸接口（Off Sheet connectors）提供了介于端口和网络标号的作用。当一个图表符调用多个子图纸时，这些子图纸间的网络连接就可以跨图纸接口实现——在这些子图纸中放置跨图纸接口，当接口匹配时就能连接起来。注意，跨图纸接口的连接作用只限于这一组子图纸间的连接，一般情况下不要用于其他图纸结构的连接。

电源端口（也叫电源对象）完全忽视工程结构，并与所有的参与链接的图纸上匹配的电源端口连接起来。

下面简单列举各类网络标识符的区别：

*   网络标号（Net label）：一般只在单图纸内部连接网络；当选择Flat范围或Net范围设置为Global时，会水平连接到全部的匹配网络符号
*   端口（Port）：如果它和父系图表符的某图纸入口匹配，或选择了层次结构、自动范围，则起垂直连接作用。当选择了Flat或Ports Global范围时，会水平连接到全部匹配的端口
*   图纸入口（Sheet Entry）：总是垂直连接到图表符所调用的下层图纸端口
*   跨图纸接口（Off-sheet connector）：水平连接到匹配的跨图纸接口，但只限于被单个的、子图纸分割的图表符调用的图纸组之间
*   电源端口（Power Port）：全局连接到工程中所有的匹配电源端口

注：这里涉及到工程里面关于端口范围的设置，打开设置对话框（Project->Project Option，点击Option标签），在“Net Identifier Scope”区域可以选择网络标识符的作用范围，一般情况都是选择“Automatic”模式即可，AD会自动判断。其他的还有“Flat”，“Hierarchical”，“Global”模式，在特殊情况下可根据需要选择。

如果要使网络标识符表示反相模式，只需在命名网络名称的每个字符后面加一个反斜杠（如E/N/A/B/L/E）；或是在Preferences对话框中的Schematic-Graphical Editing页面内，选中“Single‘/’Negation”复选框，之后在网络标识符名称之前加个反斜杠即可（如：/ENABLE）。

### 网络连通性实例

#### 分层次设计

![](https://tiny-y.asia/images/blog/2022/Altium%20Designer%E4%B9%8B%E5%A4%9A%E5%9B%BE%E7%BA%B8%E8%AE%BE%E8%AE%A16.png)

这个原理图工程被自动识别为分层次作用域，因为其父系图纸中的图表符带有图纸入口。这时端口HP-L和HP-R通过图纸入口连接到一起；而两个子图纸中的C1和C2则不能跨越图纸连接。

#### 全局端口

![](https://tiny-y.asia/images/blog/2022/Altium%20Designer%E4%B9%8B%E5%A4%9A%E5%9B%BE%E7%BA%B8%E8%AE%BE%E8%AE%A17.png)

此工程只有端口，不存在图纸入口，因此作用域被自动设置成全局端口。工程变成平行结构，此时工程上的所有匹配端口都会连接在一起，但网络标签仍不能跨图纸连接。这时即使顶层图纸移除也不会影响工程。

#### 全局网络标号

![](https://tiny-y.asia/images/blog/2022/Altium%20Designer%E4%B9%8B%E5%A4%9A%E5%9B%BE%E7%BA%B8%E8%AE%BE%E8%AE%A18.png)

此工程没有端口和图纸入口，使得网络标签能够跨越图纸，在匹配的情况下进行全局连接；此时移除顶层图纸工程仍能正常编译。

#### 全局网络标号和端口

![](https://tiny-y.asia/images/blog/2022/Altium%20Designer%E4%B9%8B%E5%A4%9A%E5%9B%BE%E7%BA%B8%E8%AE%BE%E8%AE%A19.png)

选择Project->Project Option，点击Option标签，在“Net Identifier Scope”区域可以选择网络标识符范围模式：Global（Netlabels and ports global）；如图 9示，这时网络标签与端口为全局，它们都以水平方式，在全局范围内连接到匹配对象。

#### 跨图纸接口

![](https://tiny-y.asia/images/blog/2022/Altium%20Designer%E4%B9%8B%E5%A4%9A%E5%9B%BE%E7%BA%B8%E8%AE%BE%E8%AE%A110.png)

如图 10示，此工程有四个子图纸，图表符“Group A”调用了两个子图纸“A1.schdoc”和“A2.schdoc”，“Group B”调用了子图纸“B1.schdoc”和“B2.schdoc”。此时图纸“A1.schdoc”内部的C1、C2能够和图纸“A2.schdoc”中的C1、C2相连接，同理图纸“B1.schdoc”和“B2.schdoc”也能够实现网络的连接，但这两个组间不会进行网络连接（如图纸A1.schdoc的C1不会连接到B1.schdoc的C1）。这就是跨图纸接口的作用，能增大图表符的图纸范围。

设计实例
----

### 设计思路

现在要设计一个2.0低音功放，此时假设有一个现成的有源低通音频滤波器原理图（filter.SchDoc），一个双通道功率放大器原理图（Amplifier.SchDoc）；我们可以直接使用这两个原理图来实现此设计功能：创建一个PCB工程和原理图，将现成的两个文件添加到此工程中，然后在新建的原理图中创建两个图表符，其中一个图表符调用双通道功放，另一个通过多通道功能调用两次滤波器，之后就可以进行连线，最后编译工程。

注：filter.SchDoc原理图中要用到的信号有输入（IN），输出（OUT）；Amplifier.SchDoc原理图中要用到的信号有左输入（IN\_L），右输入（IN\_R），左输出（OUT\_L），右输出（OUT\_R）。设计前可先创建好工程的文件夹，将这两个原理图文件复制到工程文件夹中。

### 具体步骤

1)       创建PCB工程，给新工程添加新原理图toplevel.SchDoc，并将两个现成的原理图添加到工程中，之后save all。

2)       打开原理图filter.SchDoc，添加两个端口IN和OUT（分别与信号IN和OUT相连接）；打开原理图Amplifier.SchDoc，添加四个端口IN\_L， IN\_R， OUT\_L和OUT\_R（分别与信号IN\_L， IN\_R， OUT\_L和OUT\_R相连接）。

![](https://tiny-y.asia/images/blog/2022/Altium%20Designer%E4%B9%8B%E5%A4%9A%E5%9B%BE%E7%BA%B8%E8%AE%BE%E8%AE%A111.png)

3)       打开原理图toplevel.SchDoc，点击“Design->Creat Sheet Symbol From Sheet or HDL file”，在弹出的窗口中选择“Amplifier.SchDoc”文件，然后点击OK。这时软件会生成一个带有四个图纸入口的图表符，将其放置在原理图中，重命名“Designator”为“Am”，并排列好相应的图纸入口。

![](https://tiny-y.asia/images/blog/2022/Altium%20Designer%E4%B9%8B%E5%A4%9A%E5%9B%BE%E7%BA%B8%E8%AE%BE%E8%AE%A112.png)

4)        同理，点击Design->Creat Sheet Symbol From Sheet or HDL file”，在弹出的窗口中选择“filter.SchDoc”文件；之后重命名“Designator”为“repeat(FI,1,2)”，表示调用两次filter.SchDoc图纸。注意，所有子图纸的公共网络是按照正常的方式连接的，此时图表符的图纸入口名称不用修改；而子图纸都有的但又是各自独立的网络则是以总线方式引出，总线中的每一条线连接一个子图纸，此时图表符的图纸入口需修改为Repeat（端口名），如本例中的输入需改为Repeat（IN）。如下图示。网络是以在导线上放置总线名的方式（而不是以总线范围的方式）来表示。当设计被编译时，总线就会被分解为每个通道带有一个标识的独立的网络（从IN1到IN2），IN1连接到FI\_1子图纸，IN2连接到FI\_2子图纸。

![](https://tiny-y.asia/images/blog/2022/Altium%20Designer%E4%B9%8B%E5%A4%9A%E5%9B%BE%E7%BA%B8%E8%AE%BE%E8%AE%A113.png)

5)        放置其他元件，连接好线路，然后编译工程。

![](https://tiny-y.asia/images/blog/2022/Altium%20Designer%E4%B9%8B%E5%A4%9A%E5%9B%BE%E7%BA%B8%E8%AE%BE%E8%AE%A114.png)

6)       编译好之后，可以看左边的面板，发现工程变长树形结构。

![](https://tiny-y.asia/images/blog/2022/Altium%20Designer%E4%B9%8B%E5%A4%9A%E5%9B%BE%E7%BA%B8%E8%AE%BE%E8%AE%A115.png)

### 关于多通道设计的几点说明

#### 设置ROOM和标识符格式

多通道设计多次调用同一个子图纸，在编译之后，会为各个通道分配好标识符，进而映射到PCB文件中；点击“Project->Project Option”，在打开的对话框中单击“Multi-Channel”标签，在这里可以设置到通道（ROOM）和元件的命名方式。

![](https://tiny-y.asia/images/blog/2022/Altium%20Designer%E4%B9%8B%E5%A4%9A%E5%9B%BE%E7%BA%B8%E8%AE%BE%E8%AE%A116.png)

**通道（ROOM）的命名**

在Room Naming区域，选择Room Naming Style 下拉列表的选项设置ROOM的命名方式。命名方式包括了2种平行化和3种层次化类型，可根据具体情况选择；在有多级room的情况下，其命名结构为（通道前缀+通道索引）。我们可以随便选择一种命名方式，其命名情况如上图；该图片给出了一个2\*2的通道设计例子，共有6个通道，每个Bank一个，4个较低层次通道各一个。且层次化命名类型还支持通过“Level Separator for Paths”来修改分割路径信息的符号。

**元件命名**

元件命名一般包括通道名称。元件命名类型有8种，在“Designator Format”下拉列表可以选择具体的命名方式。用户还可以直接在对话框里输入自定义的元件标识符命名方式，其中可能会用到一些关键词。

*   $RoomName：name of the associated room, as determined by the style chosen in the Room Naming Style field
*   $Component：component logical designator
*   $ComponentPrefix：component logical designator prefix (e.g. U for U1) 
*   $ComponentIndex：component logical designator index (e.g. 1 for U1) 
*   $ChannelPrefix：logical sheet symbol designator 
*   $ChannelIndex：channel index 
*   $ChannelAlpha：channel index expressed as an alpha character. This format is only useful if your design contains less than 26 channels in total, or if you are using a hierarchical designator format. 

#### 关于PCB

工程被编译后，我们可以在被多次调用的子图纸界面下方看到多了一些标签。我们可以单击相应的标签查看里面元件标识符的分配情况。之后给工程添加一个PCB文件，通过“Design->Update PCB”将元件导入到PCB文件中；转换过程会自动为每个子图纸建立一组元件中，每组元件有一个room并将元件都置于room之中。对一个通道布局布线后，可通过“Design->Rooms->Copy Room Formats”来复制该通道的布局与走线到另一通道中。

![](https://tiny-y.asia/images/blog/2022/Altium%20Designer%E4%B9%8B%E5%A4%9A%E5%9B%BE%E7%BA%B8%E8%AE%BE%E8%AE%A117.png)

#### 查看通道标识符分配情况

单击“Project->View Channel”即可调出“Project Components”对话框，其中显示了每个原理图中元件标识符的分配情况。之后点击“Component Report”，弹出“Report Preview”窗口，此时可以点击“Export”按钮导出Excel格式表格（.xls文件），或是点击“Print”按钮进行打印。

![](https://tiny-y.asia/images/blog/2022/Altium%20Designer%E4%B9%8B%E5%A4%9A%E5%9B%BE%E7%BA%B8%E8%AE%BE%E8%AE%A118.png)

#### 使用Signal Harness使多图纸设计更方便

AD提供的Signal Harness功能，支持将多个导线、总线包裹在一起进行连接。在导线、总线连接较多且复杂的原理图中，我们可以使用Signal Harness将这些线路汇集在一起，结合各种网络标识符进行图纸内或跨图纸连接。一般Signal Harness系统包含有四块：Signal Harness（连线），Harness Connector（连接器），Harness Entry（入口）和Harness Definition File（定义文件）。前三者在画原理图时需用到，最后的定义文件则会自动生成（前提是使用了Harness Connector）。

![](https://tiny-y.asia/images/blog/2022/Altium%20Designer%E4%B9%8B%E5%A4%9A%E5%9B%BE%E7%BA%B8%E8%AE%BE%E8%AE%A119.png)

下面简单介绍下Signal Harness的使用：

*   点击“Place->Harness-> Harness Connector”，在放置前按“TAB”键，在“Harness Type”输入连接器的类型（本例使用“TEST”），之后点击OK放置。
*   点击“Place->Harness-> Harness Entry”，放置接口，并根据实际重命名。
*   放置端口“AUDIO”和其他的网络标签，之后进行连线；其中AUDIO需用Signal Harness连接。
*   编译工程，在左边工程面板的工程目录下的“Setting->Harness Definition Files”可以看到（\*.Harness）的文件，双击打开，可以看到里面就一个语句“TEST=WCLK,BCLK,DOUT,DIN,MCLK”，表示TEST由多个连接线组成。
*   之后可以在图纸内其他需要连接的地方再建一个Signal Harness，通过端口连接起来
*   如果需要连接的电路在其他图纸内，同样可以通过端口（port）将电路连接起来。

参考资料：

\[1\] 徐向民. Altium Designer快速入门. 北京航空航天大学出版社，2008

\[2\] [Connectivity and Multi-Sheet Design. From](https://www.altium.com/documentation/altium-designer/creating-connectivity-ad)

\[3\] [Creating a Multi-channel Design. From](https://www.altium.com/documentation/altium-designer/multi-sheet-and-multi-channel-design-ad)

\[4\] [Multi-Channel Design Concepts. From](https://techdocs.altium.com/display/ADOH/Multi-Channel+Design+Concepts)

————————————————

版权声明：本文为CSDN博主「chenzelin2009」的原创文章，遵循 CC 4.0 BY-SA 版权协议，转载请附上原文出处链接及本声明。  
原文链接：https://blog.csdn.net/chenzelin2009/java/article/details/5751251