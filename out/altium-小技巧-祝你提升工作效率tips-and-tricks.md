---
title: 'Altium 小技巧 祝你提升工作效率(Tips and Tricks)'
date: Mon, 13 Jul 2020 02:49:50 +0000
draft: false
tags: ['Altium', '设计技巧']
---

版本功能发布
------

### [Altium Designer17 新功能](https://a1024.synology.me:1024/?p=3764)

### [Altium Designer20 新功能](https://a1024.synology.me:1024/?p=656)

### [Altium指定某层作为元器件布局边框](https://a1024.synology.me:1024/?p=1430)

软件设置
----

### [Altium Preferences](https://a1024.synology.me:1024/?p=625)

**快捷键**
-------

### 元器件布局

[智能元器件放置功能](https://a1024.synology.me:1024/?p=1955)

排列布局在区域内      IL/TOL  
依次放置选择的元器件  IC/TOC

### [Altium Designer中的快捷键](https://a1024.synology.me:1024/?p=715)

### [Altium自建查询语句，打包为命令](https://a1024.synology.me:1024/?p=885)

PCB Filter
----------

按F12调出Filter面板，输入下面语法Enter查询

[Altium 常用语法笔记](https://a1024.synology.me:1024/?p=329)

规则设置
----

### 通过规则设置阻焊塞孔

过孔上绿油常规方法:布线完成后用选择所有过孔，调出属性，加上solder tented属性，弊端操作完成后，新加过孔需重新编辑新加过孔。

过孔上绿油规则设置:开窗规则设置，新建规则，设置isvia  开窗值设为负数，负数代表开窗相对过孔焊盘内缩值，内缩值超过焊盘半径即代表阻焊塞孔，值自己设置。注意需开窗的过孔需单独设置过孔变为pad属性，或自行调整开窗。

![](http://a1024.synology.me:222/images/blog2022/Altium_Soldermask006.jpg)

![](http://a1024.synology.me:222/images/blog2022/altiumsoldervia.png)

低版本可以用负值，高版本可以在规则中增加Tented属性

### BGA空管脚扇孔误报处理

BGA的IO口经常会有很多用不到，在设计时会以空（无网络）管脚的状态呈现，有时我们为了设计完成后可能存在调试时管脚飞线或者为了方便后期增加网络到空的IO口时会需要把这种空管脚做扇孔处理，一般呈现结果如下图

![](http://a1024.synology.me:222/images/blog2022/Altium_BGAnonet_sp190610_105016.png)

对于强迫症患者这是无法忍受的，这时我们可以通过在规则中建立允许短路规则，来消除此类报错，效果如下

![](http://a1024.synology.me:222/images/blog2022/Altium_BGAnonet_sp190510_095432.png)

具体应用的的规则设置如下，非常简单，两句话解决

```
not InAnyNet and IsPad
not InAnyNet and IsTrack
```

![](http://a1024.synology.me:222/images/blog2022/Altium_BGAnonet_sp190610_105119.png)

大孔径Pad隔离增大
----------

孔径大于等于2mm的Pad，隔离规则设置为1mm

AsMM(HoleSize) >= 2

孔径大于等于4mm的Pad，隔离规则设置为2mm

AsMM(HoleSize) >= 4

以此类推

![](http://a1024.synology.me:222/images/blog2022/holesizeplaneclearance.png)

操作
--

### 为对象增加网络

**知识点内容：**Altium Designer通过属性面板为自由对象快速编辑属性值

**自由对象：**在PCB设计过程中由用户根据设计要求添加到设计中的可编辑的元素（与网表导入的对象相对应，比如pin的Net Name，元器件的Footprint Name这些，常规情况下是不允许用户编辑修改的）

**以下以为铺铜皮的对象增加网络为例介绍，更多应用自己引申，举一反三**

**操作步骤：**

1.  添加自由对象，此处指铜皮
2.  选择与自由对象有相同属性的非自由对象，安装Shift键才能选中
3.  安装Shift双击对象，或按键盘F11键调出属性窗口
4.  直接编辑需要更改的属性值，此处指Net

![](http://a1024.synology.me:222/images/blog2022/Altium%E7%BB%99%E8%87%AA%E7%94%B1%E5%AF%B9%E8%B1%A1%E5%8A%A0%E7%BD%91%E7%BB%9C.gif)

功能逻辑如下解释：  
因为在2中增加选择了一个非自由对象，所以当选择网络属性时软件默认给出一个值，这个会根据优先级，优先给出的非自由对象的值，即我们的目标值。通过此方式替代编辑属性值时从大量信息中寻找目标，而是直接指定好目标给予对象即可。

![](http://a1024.synology.me:222/images/blog2022/%E5%90%B8%E7%AE%A1%E7%BD%91%E7%BB%9C.png)

高版本可以通过选择对象后从属性面板选择吸管工具，再点击PCB中对应网络的对象为选择的对象增加网络

Moving and Snapping
-------------------

对象的位置调整

指定坐标

相对移动：坐标运算 !+1

格点阵列

吸附对象 Ctrl+E

### [Altium PCB中添加图形](https://a1024.synology.me:1024/?p=643)

[PCB Footprint添加更多信息](https://a1024.synology.me:1024/?p=1187)
-------------------------------------------------------------

动态铜皮编辑
------

[抖音视频链接](https://v.douyin.com/YywLkSd/) [https://v.douyin.com/YywLkSd/](https://v.douyin.com/YywLkSd/)

布局神器交叉选择元件放置
------------

可能我们最常用的命令就是ArrangeWithin Rectangle 就是框选原理图一堆器件，在pcb中画一个框聚拢  
下面介绍另外一种方法原理图和PCB之间的交叉选择和元件放置  
交叉选择元件布局，可以在原理图上有序地选择特定元件，然后在PCB板中有序地放置。这能使您的设计井井有条，易于编辑。如图

使用方法

1.  按住Shift键，在原理图上依次单击想要放置在电路板中的所有元件。
2.  切换到PCB文档，选择Tools> Component Placement > Reposition Selected Components。（toc）
3.  单击PCB板，放置选中的元件。

放置在PCB上的元件会遵从在原理图中选中的顺序，从而保持设计的一致性和协调性。

如果常用此方法可以直接将Reposition

Selected Components设为快捷键，按住CTRL点击此命令即可