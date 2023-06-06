---
title: 'Class（类）SubClass（子类）层功能介绍'
date: Wed, 02 Dec 2020 00:46:46 +0000
draft: false
tags: ['Allegro']
---

在Allegro工具中，绘图元素的类别称为类Class。 类代表设计中所有可见项目的类型。每个类中图形的各个部分称为子类SubClass。 每个类可以包含许多子类，包括用户定义的一些子类。

类和子类的绘图元素包含了设计中使用的个元素。子类允许进一步分类，从而使该工具可以更具体地处理数据。 例如，ETCH / CONDUCTOR具有两个与其关联的预定义子类：顶部和底部（因此消除了通过层号引用元素类型的必要性）。

在PCB板的设计中，同样的图形或者符号代表的内容往往是不同的，比如同样是一个矩形，它可能代表PCB板的板框，也可以表示布线区等。因此Allegro将设计中的内容按照其所表达的意义分成不同的类，以及进一步细分的子类。在Allegro添加的任何内容必定属于某个Class/Subclass.Class与Subclass是Allegro中非常重要的一个概念，

Geometry
--------

### Board Geometry

在板子上的图形，在板子上添加的标识、说明、注释等信息应添加到该类的子类上

*   Assembly-Detail和Assembly-Note的使用与装配有关.Assembly\_Detail用于指示装配细节，比如器件在PCB上进行固定的规程等.Assembly\_Note可以标注装配的注意事项.
*   Both\_Rooms，Bottom-Room，Top-Room，Place-Grid-Bottom，Place-Grid-Top与自动布局有关，具体可以参见自动零件摆放的说明。
*   Silkscreen-Bottom和Silkscreen-Top分别为Bottom层和Top层丝印，某些情况下比如需要在PCB板标注某个电位器的含义，以方便调试或操作时，可以此层添加对应图形
*   Constraint-Area用于在设计中指定特殊的布线区，在这些布线区中可以设定特殊的布线规则
*   Dimension用于标注设计中的有关尺寸.
*   Off Grid\_Area用于指示设计中不使用栅格的区域。
*   Outline用于绘制PCB的外形（板框）.
*   Plating-Bar用于指示设计中需要电镀的地方，比如很多采用金手指的设计中可以用Plating-Bar来指示需要镀金的金手指条
*   Soldermask\_Bottom和Slodermask\_Top用于设计在Bottom层和Top层添加阻焊窗，即添加不需要俗称绿油的区域.
*   Switch\_Area Bottom和Switch\_Area-Top用于指示可以将区域内零件的摆放进行交换的区域。
*   Tooling-Corners用于指示某些需要加工的转角等。例如在某些设计中，在PCB的外形中有拐内角的地方，虽然设计中是一个直角，但加工完成后则是一个圆弧角。如果设计中没有考虑这个尺寸余量将导致零件无法装配.

### Package Geometry

在焊盘图形中的图形，在焊盘图形中添加的标识、说明、注释等信息应添加到该类的子类上

*   ASSEMBLY-TOP和ASSEMBLY-BOTTOM是与装配相关的内容，表示的是零件的外形和方向。
*   PLACE-BOUND-TOP和PLACE-BOUND-BOTTOM表示的是零件在Top层和Bottom层各自占位大小，在同一层中如果两个零件的PLACE，BOUND区域有交叠将发生DRC错误。
*   PIN-NUMBER用于表示零件的引脚号的显示。

### Manufacturing

*   PHOTOPLOT-OUTLINE用于指示在生成Gerber文件时的指定区域，区域外的将不做输出
*   NO\_GLOSS\_ALL，NO\_GLOSS\_BOTTOM，NO\_GLOSS\_TOP，NO\_GLOSS INTERNAL.分别用于指示所有层、Bottom层、Top层、内层（非Bottom层和Top层）禁止使用GLOSS功能.
*   NCDRILLFIGURE用于指示设计中钻孔（包括通孔，盲孔和埋孔）。对于不同规格的钻孔NCDRILL-FIGURE用不同的符号标识.NCDRIL-LEGEND用于统计NCDRIL FIGURE标识的各种规格钻孔的Class型与数量.NCDRILL\_FIGURE和NCDRIL LEGEND相结合可以指导钻孔的加工.
*   AUTOSILKTOP和AUTOSILK BOTTOM指的是在Allegro中通过Auto Silkscreen命令生成的丝印
*   NO-PROBE-TOP和NO-PROBE-BOTTOM，以及PROBE-TOP，PROBE-BOTTOM分别为Top层，Bottom层禁止飞针测试区和Top层，Bottom层飞针测试区.

Drawing Format
--------------

用于在设计中添加技术说明，以告诉制版厂其他的一些加工信息，如叠层结构、板厚的容差等

Stack-Up
--------

DRC：设计中的错误报告显示  
ETCH：导体蚀刻层，与设计层数相关，代表PCB各层的导体图形  
Anti-ETCH：与ETCH相对，与设计层数相关，当使用split plane create命令时，如果此层有图形，则生成的Shape将避开对应的图形，常用作Plane层面的分割  
Pin：焊盘图形中的引脚相关内容  
Via：PCB和焊盘图形中通孔的内容

Components
----------

Refdes：元器件显示字符，对应到原理图对元器件定义的位号属性  
ComponentValue：  
Device Type  
Tolerance  
User PartNumber

Areas
-----

Route Keepin：允许布线区  
Route Keepout：禁止布线区  
Via Keepout：禁止放置Via区  
Package Keepin：允许布局区  
Package Keepout：禁止布局区