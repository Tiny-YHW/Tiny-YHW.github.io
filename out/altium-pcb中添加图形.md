---
title: 'Altium PCB中添加图形&LOGO'
date: Thu, 14 May 2020 01:00:20 +0000
draft: false
tags: ['Altium', '设计技巧']
---

[官方链接](https://www.altium.com/documentation/altium-designer/including-barcodes-and-logos-ad)

Altium Design软件的PCB编辑器可以将条形码符号直接放置在PCB的任何层上，从而可以在制造过程中轻松将条形码印在PCB上。此外，编辑器还支持将图形图像添加到PCB设计的多种方法-非常适合在板上添加公司Logo！.

Altium Designer 21 放置图片
-----------------------

直接使用Place->Graphics功能放置图片

https://v.qq.com/x/page/x3215m445nc.html

添加条形码
-----

条形码通常用于标记和识别PCB，例如通过使用自动扫描机来简化库存跟踪。条形码作为配置的[String对象](https://www.altium.com/documentation/altium-designer/pcb-obj-stringstring-ad)放置在PCB文档中。使用[Place»String命令](https://www.altium.com/documentation/pages/viewpage.action?pageId=250856#place_string)开始放置。

要使用条形码字体，请首先选择字符串对象以通过“ [属性”面板](https://www.altium.com/documentation/altium-designer/pcb-prop-stringstring-properties-ad)访问其属性。然后，只需将**Font Type**设置为BarCode，并在下面的区域中根据需要定义显示选项。支持条形码ISO **代码39**（美国国防部标准）和**代码128**（全球贸易识别标准），并且还可以通过启用“ **显示文本”**选项来显示条形码所源自的实际文本字符串。

显示文本时，选择要使用的TrueType字体，并相应地设置文本的高度。

![](https://www.altium.com/documentation/sites/default/files/wiki_attachments/301395/Barcode_Example.png)

示例条形码下面带有原始（可读）文本。

使用所需的总宽度或最小的条形码元素宽度来指定条形码的高度和宽度，以控制尺寸。无论使用哪种方法，请确保使用能使条形码适合相应扫描仪读取的尺寸！

通过使用条形码和反向文本字符串的组合以及必要时的填充，可以在板上定义一个不错的条形码区域，在文本上提供的信息比仅通过原始条形码文本提供的信息要多，如下所示。

![](https://www.altium.com/documentation/sites/default/files/resize/wiki_attachments/301395/Barcode_AdditionalInvertedStrings-576x103.png)

使用反向条形码和其他反向文本字符串的示例。

添加图形
----

通常，在制造电路板时，所有者公司（即设计电路板并希望从其商业可用性和成功中获得可观利润的公司）会想“盖章”其所有权。当然，这可以通过在丝网印刷层上使用简单的文本来实现，但通常，该公司的徽标是一种更为醒目且有效的替代方法。为满足此要求，该软件的PCB编辑器支持几种将图形图像添加到PCB设计文档的方法。

有一种使用PCB Logo Creator插件脚本导入的方法，本文不做介绍，具体方法可通过关键字“PCB Logo Creator”查询到

### 将图形作为字体放置

可以创建一个自定义的TrueType字体，其中包含一个图形作为字形（字体中的字符之一），然后在使用该字体的PCB板上放置一个字符串。除了易于使用之外，此方法的另一个重要优点是，如果从矢量图形图像创建字体字形，则可以精确缩放它们。

PCB设计中使用的许多标准符号的字体-包括：无铅，可循环利用，对静电敏感，接地，C-Tick，UL，CE，FCC以及许多其他符号-已由Altium设计的领先专家之一创建。设计软件-Mooretronics的Darren Moore。该字体可在[此处](https://www.altium.com/documentation/sites/default/files/wiki_attachments/248056/2015Jun24-Font-Truetype.zip)下载（日期为2015年6月），您也可以查看[相关论坛主题](https://forum.live.altium.com/#posts/61899)，以获取最新帖子中的最新版本。

该字体被许可为Cardware，请参考`Readme.txt`下载ZIP中包含的字体以了解使用条件。自述文件还包括可用图形的列表。请注意，有许多文本或不文本可用，首选版本通过使用大写或小写字母选择。下图显示了该字体中可用图形的示例。

![](https://www.altium.com/documentation/sites/default/files/wiki_attachments/301395/Mooretronics_Font.png)

Mooretronics字体中的一些有用图形的示例。

![](http://a1024.synology.me:222/images/blog2022/PCBMark.png)

#### LED字体

另附一个[LED字体](https://a1024.synology.me:222/images/blog2022/LED.zip)如有需要自行

![](https://a1024.synology.me:222/images/blog2022/LED%E5%AD%97%E4%BD%93%E7%A4%BA%E4%BE%8B.png)

### 从Windows剪贴板粘贴图片

直接导入的图片仅支持单色位图，可使用画图工具存储为单色位图，单位位图只有两种颜色，黑和白，导入Altium PCB后黑被转为由图形填充，白被转换为无图形填充（空隙）

若原始图形为彩色，转换为单色位图时非预期（深色转换为黑，浅色转换为白），可使用PS调整色阶功能，转换深色和浅色。

对于以黑白两种颜色绘制的Logo，PCB编辑器支持使用标准Windows **Ctrl + V**粘贴命令将图元文件直接从Windows剪贴板粘贴到当前PCB层上。支持的图元文件数据包括位图，线，弧，简单填充和真实类型的文本-使您可以轻松粘贴徽标和其他图形符号。

请注意，并非所有图像编辑器都将图像数据作为图元文件数据放置到剪贴板中。确保发生这种情况的一种方法是，首先将图像粘贴到Microsoft Word中，然后从那里复制并将其粘贴到Altium Design软件中。去做这个：

1.  将所需的徽标图像（BMP或PNG格式）粘贴或插入到Microsoft Word文档中。 
2.  选择图形复制。
3.  在Altium设计软件中打开所需的目标PCB文档。
4.  从剪贴板粘贴图像（**编辑»粘贴**，或**Ctrl + V**）。
5.  图像将漂浮在光标上，只需单击工作区中的所需位置即可进行放置。

导入的数据将采用您为该层选择的颜色放入当前层。在粘贴过程中创建的PCB对象将自动添加到联合。粘贴后，可以使用Union的编辑手柄来微调粘贴图像的大小。粘贴后生成的并集也可以随时使用右鼠标菜单中的“ [调整](https://www.altium.com/documentation/pages/viewpage.action?pageId=250671#resize_union)并集[大小”命令](https://www.altium.com/documentation/pages/viewpage.action?pageId=250671#resize_union)来[调整大小](https://www.altium.com/documentation/pages/viewpage.action?pageId=250671#resize_union)（在启动“ **调整**并集**大小”**命令后单击以选择所需的并集）。

在**从其他应用程序粘贴**选项，在[PCB编辑器-常规页面](https://www.altium.com/documentation/altium-designer/pcb-dlg-systemoptions-framepcb-editor-general-ad)中的[首选项对话框](https://www.altium.com/documentation/altium-designer/client-dlg-alloptionsformpreferences-ad)，用于将设置**首选格式**，以图元文件或文本。对于图形，此选项没有影响-图形中的每个独立形状都将转换为区域对象。粘贴文本字符串时，如果将选项设置为Metafile，则每个字符都将转换为文本字符串，而如果将选项设置为Text，则将整个字符串粘贴为Altium Design Software字符串。

![](https://www.altium.com/documentation/sites/default/files/wiki_attachments/301395/PasteGraphic.png)

放置为OLE对象
--------

也可以将以BMP格式存储的图形作为OLE对象放置在活动的PCB文档上。这是通过PCB编辑器中的**对象链接和嵌入**（OLE）技术实现的。

首先，在要放置OLE对象数据的层上创建活动层，即工作区。启动命令（“ **放置”»“文件中的对象”**）后，将出现标准的“ Windows _选择文件”_对话框。使用此对话框浏览到所需的B MP图像文件。单击“ **打开”后**，所选文件中的数据将浮动在光标上。根据需要在工作空间中定位，然后单击或按**Enter键**以进行放置。

![](https://www.altium.com/documentation/sites/default/files/wiki_attachments/301395/bar_code.gif)

将BMP图像（作为OLE对象）放置在PCB文档上。

### 转换工具

链接: [https://pan.baidu.com/s/1cmrlocZHelN3jjLb7v62dg](https://pan.baidu.com/s/1cmrlocZHelN3jjLb7v62dg) 提取码: bpd4

[如何在您的PCB大作上添加二维码？](https://www.altium.com.cn/blog/%E5%A6%82%E4%BD%95%E5%9C%A8%E6%82%A8%E7%9A%84pcb%E5%A4%A7%E4%BD%9C%E4%B8%8A%E6%B7%BB%E5%8A%A0%E4%BA%8C%E7%BB%B4%E7%A0%81%EF%BC%9F)