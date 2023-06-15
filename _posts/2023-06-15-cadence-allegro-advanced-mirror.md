---
layout: post
title: Allegro PCB Advanced Mirror高级镜像功能
categories: Allegro
description: 
date: 2023-06-15
---

在这个专题中，我们将介绍在该套件下的一个Toolbox选项组件下的Advanced Mirror高级镜像功能。

![](https://www.u-c.com.cn/uploads/editor/2019/12/04180900753.png)

1、 在Allegro PCB17.2的版本里面有个Allegro Productivity Toolbox可选高级组件，勾选该复选框就可以使用该须选件下的各种高级功能，其中Advanced Mirror高级镜像功能就在这个组件中。

 ![](https://www.u-c.com.cn/uploads/editor/2019/12/04180921321.png)

2、 Allegro Productivity Toolbox高级组建所带来的众多高级命令，都相当于是Allegro PCB软件里面的旷世奇功。组件本身相当于少林寺的藏经阁，他藏了很多很实用的武功秘籍，用户利用这些秘籍可以让PCB设计和信号分析提高效率，大大的缩短设计周期。今天我们就来一起学习这些奇功里面的Advanced Mirror高级镜像功能，该功能可以支持将整体PCB电路板或者部分选择电路板进行镜像、移动、旋转等操作。操作命令对Symbols、Vias、Clines、lines、Shape、Text都有效，能够支持同时对器件、电气线、非电气线、铜皮、字符的操作。

 ![](https://www.u-c.com.cn/uploads/editor/2019/12/04180948662.png)

3、 选择Edit—Advanced Mirror 菜单即可进入该命令状态。

![](https://www.u-c.com.cn/uploads/editor/2019/12/04181005728.png)

  

4、 Advanced Mirror命令在右侧的Options和Find两个选型卡中，都是有关的命令参数需要设置。

【1】 Options选项卡中，Mirror Type是命令执行的类型，None不执行镜像。Geometry and Layer对几何图形和电气层都执行镜像操作，对电气层来说，TOP层会镜像到BOTTOM层。BOTTOM层会镜像到TOP层，依次方式和原理图，内层也会跟着进行镜像，相当于将这个电路板进行了物理反转。Geometry only 仅执行几何图形的镜像，执行后TOP层对应的对象（器件，过孔，电气线，非电气线，铜皮，字符）还在TOP层对应的对象上，只是它们发生了左右、上下、角度的旋转，但是其所在的层不改变。Mirror via padstacks 表示仅镜像过孔焊盘，Mirror text表示仅镜像字符文字，smart spin 2-pin devices表示智能旋转2个引脚以上的器件。Mode是命令操作的模式，可以选择是复制还是移动。Rotation用来旋转操作的对象，可以旋转按照一定的角度旋转，也可以设置按照一定的增量来旋转。

【2】 Find选项卡用来设置命令支持操作的对象类型，共计有6种的类型可以被复选。

只针对Symbols,Vias,Clines,lines,Shape,Text都有效，可以通过勾选实现该类型的选择操作。

 ![](https://www.u-c.com.cn/uploads/editor/2019/12/04181046602.png)

5、 选择Geometry and Layer和Copy执行命令后的效果，大家可以看到，这个PCB的层和图形都进行了镜像操作（器件，过孔，电气线，非电气线，铜皮，字符都进行了镜像）。

![](https://www.u-c.com.cn/uploads/editor/2019/12/04181106389.png)

6、 选择Geometry only，Mirror via padstacks，Mirror text，smart spin 2-pin devices，copy，执行命令后的效果。大家可以看到，这个PCB图形都进行了镜像（包括器件、过孔、电气线、非电气线、铜皮、字符都进行了镜像），但其所在的层都没有变化。

![](https://www.u-c.com.cn/uploads/editor/2019/12/04181123400.png)

7、 选择Geometry only，复选Mirror via padstacks，执行命令后的镜像效果。

![](https://www.u-c.com.cn/uploads/editor/2019/12/04181140747.png)

8、 过孔属性显示。查看被镜像后的过孔属性情况，可以看到过孔属性提示进行了镜像操作。

 ![](https://www.u-c.com.cn/uploads/editor/2019/12/04181219341.png)

10、选择Geometry only，不勾复选命令的情况下，执行命令后的效果，可以看到过孔没有执行镜像命令。

 ![](https://www.u-c.com.cn/uploads/editor/2019/12/04181228277.png)

11、选择Geometry only，复选Mirror Text，执行命令后的镜像效果，可以看到字符执行了镜像操作。 

 ![](https://www.u-c.com.cn/uploads/editor/2019/12/04181335604.png)

12、选择Geometry only，不勾复选功能，执行命令后的镜像效果，可以看到字符没有进行镜像操作。

 ![](https://www.u-c.com.cn/uploads/editor/2019/12/04181349409.png)

13、选择Geometry only，smart spin 2-pin devices执行命令后的镜像效果，可以看到器件、铜皮、字符、都执行了镜像操作。

![](https://www.u-c.com.cn/uploads/editor/2019/12/04181358627.png)

总结

通过上面的学习让我们看到了Allegro Productivity Toolbox高级镜像功能使用方法，可以利用这个功能对已经设计完成的电路板中的器件，过孔，电气线，非电气线，铜皮，字符进行整体或者部分的镜像操作。给已经完成布局、布线、层叠、模块等PCB设计工程师提供了一种可以直接镜像的功能方法，从而大大的减少了工程师重复手动操作的次数和难度。该方法相对于其他方法来说，操作简单，功能强大。对于提升设计效率以及设计的准确性都有很大的帮助，阅读完这篇文章的小伙伴可以自己去试一试这个新功能，为己所用提高工作效率。

本文摘录于 https://www.u-c.com.cn/w/news/technical/63.html