---
title: 'Allegro Gloss优化命令详解'
date: Thu, 17 Sep 2020 08:38:34 +0000
draft: false
tags: ['Allegro']
---

当PCB板设计完成后，无论是手工布线还是采用SPECCTRA进行自动布线，总会产生一些布线效果不好、多余过孔等问题。此时可以利用Allegro提供的Gloss命令对设计进行优化和调整，这样不仅可以提高设计的美观和可生产性，并且可以降低制造成本，提高产品可靠性。

**一、优化前的准备工作**
--------------

  
在进行优化工作之前，先检查设计以确定是整个板子都需要进行优化还是只对某个区域或者某些网络进行优化。

如果某些网络有特殊要求，我们就应该对其进行设置以保护在优化过程中不改变这些网络的特殊性。保护网络不在优化过程中改变的俄方法就是给网络增加NO\_GLOSS 或者FIXED属性。

如果要保护设计中的某个区域不被优化，则应设置一个NO\_GLOSS的多边形。NO\_GLOSS的多边形应该设置在MANUFACTURE层，它的子层可以是NO\_GLOSS\_TOP、NO\_GLOSS\_BOTTOM、NO\_GLOSS\_ALL或NO\_GLOSS\_INTERNAL。

Allegro还提供了几种不同的优化命令可以针对不同的优化区域进行操作，分别为优化菜单中的Design、Room、Window、Highlight和List。Design用于对整个设计进行优化，Room用于对选定的room进行优化，Window用于对选定的窗口进行优化，Hightlight用于对高亮显示的当个网络或者元件进行优化，List用于对所设定的列表项目进行优化。

**二、项目和参数设置**
-------------

选择菜单命令Route/Gloss/Parameters，弹出如图1所示对话框。

![](http://a1024.synology.me:222/images/blog2022/Gloss1.jpg)

图1 Route/Gloss/Parameters

对话框中的Application栏列出了可进行优化操作的所有选项，单击任一选项前面的按钮可进入到该选项的参数设置对话框，选中某项后面的Run，再单击对话框中的“Gloss”按钮即可进行相关项目的优化。如果一次选中多个选项，优化时就按照这些选项的排列顺序依次进行。

该对话框中可进行的优化项目包括：

*   Line And via cleanup：走线和过孔的清除
*   Via eliminate：减少过孔、多余过孔删除
*   Line smoothing：将弯折线变平滑
*   Center lines between pads：将两焊盘之间的走线放置在中间
*   Improve line entry into pads：优化走线进入焊盘的角度
*   Line fattering：增大线宽
*   Convert conner to arc：将走线方角变为圆弧
*   Pad and T connection filter：焊盘和T行联接处理
*   Dielectric generation：产生绝缘体

下面分别对常用的几种功能进行介绍。

### Line And via cleanup

这项功能将走线和过孔清除后重新布线。单击该项前面的按钮可进入参数设置对话框，如图2所示。

![](http://a1024.synology.me:222/images/blog2022/gloss2.jpg)

图2

对话框中的参数设置分为3部分。  
第一部分是关于Line的参数设置，主要选项功能如下

*   Jog Size Limit：用于设定在清除过程中可增加的斜线段个数，值为-1时表明该项没有限制。
*   Etch Length/Via：用于设定为了减少过孔而增加的布线长度，值为-1时表明该项没有限制。
*   Net Length Limit：用于设定线网的长度超过该设定值时才对其进行清除和重新布线，值为-1时表明该项没有限制。
*   Maximum 45 Length：用于设定45度角的水平边或者垂直边的长度。
*   复选框Slip Slide：用于设定在清除布线时是否可以应用推挤功能。
*   第二部分为关于Via的参数设置，主要选项功能介绍如下。
*   复选框Retry：用于设定清除连线后布线器是否进行进行重新布线，一般情况下选中该复选框。
*   Number of Executions：用于设定执行操作的次数，推荐选择多次运行。
*   Cleanup All：用于设定清除的对象，选择Lines只清除连线，选择Lines and Vias则清除连线和过孔，选择Lines，Vias，and Missing Connecs则清除连线和过孔，对后对清除的连线以及设计中没有连接的线网进行连线。

### Via eliminate

这项主要用来减少整个设计所用过孔数量。单击该选项前面的按钮，弹出如图3所示参数设置对话框。

![](http://a1024.synology.me:222/images/blog2022/gloss3.jpg)

图3

*   Eliminate Used Pin Escapes：用来设定是否减少有用的扇出过孔。选中后，当两个SMD类型焊盘各通过一个扇出孔引出后又通过其他层走线相连时，系统会尝试将这两个过孔删除，用同样线宽的表层走线来实现两个SMD焊盘的连接。
*   Eliminate Unused Pin Escapes：用来设定是否减少无用的扇出过孔。选中后，当一个SMD焊盘通过一个扇出孔引出后又通过表层走线实现了和另一个SMD焊盘的连接时，系统会删除这个没有起作用的过孔。
*   Eliminate Stand Alone Vias：用来设定是否删除没有网络属性的孤立过孔。
*   Eliminate Regular Through Vias：用来设定是否删除正规的多余通孔。
*   Jog Size：用来设定在执行Via Eliminate时可用的最大的拐线尺寸，缺省值为-1，表明没有拐线尺寸方面的限制。

设置完成之后单击“Ok”，在图1所示界面中选择Via eliminate选项，单击“Ok”开始进行Via eliminate的优化操作。

### Line smoothing

用来删除设计中额外的连接线段或者拐线，是连接线变得平滑，每次执行Line smoothing命令时只对设计中的每个线网检查一遍，所以最优的情况是将该命令执行多次，单击选项前面的按钮，弹出如图4所示的设置对话框。

![](http://a1024.synology.me:222/images/blog2022/gloss4.jpg)

图4

*   Eliminate：用于设定能被删除的对象。
*   Bubbles：用来设定是否删除一个90度走线后的45度走线。
*   Jogs：用来设定是否删除多余的拐线，将两段拐线合并为一段。
*   Dangling Lines：用来设定是否删除两头没有连接的孤立线段。
*   Line Segments：用来设定线段的一些参数。
*   Convert 90 to 45：用来设定是否将设计中的90度的拐角转换成45度的拐角
*   Extend 45：用来设定是否延长连接一个水平线段和一个垂直线段的45度连接线，这样就可以将水平线段和垂直线段删除。
*   Maximum 45 Length：用来设定45度连接线的最大长度，缺省值为-1，表明对该项没有限制。
*   Length Limit：用来设定进行平滑处理的连接线的长度，缺省值为-1，表明没有限制，任何长度的连接线都要进行平滑处理。
*   Corner Type：用来设定是45度的拐角还是90度的拐角，缺省为45。
*   Number of Executions：用来设定Line smoothing命令的执行次数，推荐多次使用该命令。

### Center lines between pads

用来调整连接线使之与相邻管脚保持相同的距离。单击选项前面按钮，弹出如图5所示的设置对话框。

![](http://a1024.synology.me:222/images/blog2022/gloss5.jpg)

图5

*   Minimum move size：用来设定移动连接线的最小距离，缺省值为两个设计单位。当一组连接线中任意连接线的移动距离小于该值，这一组中所有的连接线都不进行移动。
*   Adjacent pad tolerance：用来设定两个相邻管脚水平方向或者垂直方向上中心到中心的最大距离。
*   Corner Type：用来设定采用的是45还是90度拐角，缺省为45。
*   Line spacing：用来设定划分线间距的种类。选择Minimum是说明按照线到线的最小间距分配布线空间，最外面的连接线和管脚之间的声誉间距保持平均分配，如果有DRC错误产生，就不将连线移动到中间。选择Even是保持每一条连接线和管脚之间的间距都是相等的，如果有DRC错误产生，则应用Minimum规则重新移动连接线。
*   单击Gloss layer按钮可进入图6所示的对话框。

![](http://a1024.synology.me:222/images/blog2022/gloss6.jpg)

图6

在这个对话框中可从现有板层中添加或删除进行Gloss处理的叠层，单击Add按钮可以添加新层（可选的层都是已经定义的并且类型设置为Conductored的层），单击Delete可以删除后面的层，右边的文本输入框用来设定有效的aroute生成的连接线上的拐线个数，由于Allegro中aroute不能用，此处可以忽略。

设置完成之后单击Ok推出设置对话框，在图1所示界面中选择Center lines between pads选项，单击Gloss开始进行Center lines between pads的操作。

### **Improving line entry into pads**

从焊盘走出的线，线和焊盘的边缘有时会有锐角产生，这可能导致成品率的下降。这个步骤就是消除这些锐角。

### **Line fattening**

在不产生DRC的前提下，可以分别把某一层的走线转变成某一特定的宽度。注意很有可能是某一局部的走线变宽了，而不是整个Net。

### **Convertting corner to arc**

这个功能可以把45°或是90°的走线变成圆弧线，在参数设置中可以指定圆弧的最大和最小曲率

### **Fillet and tapered trace**

添加泪滴和渐变线，很常用

### **Dielectric generation**

基本无用，不做介绍