---
title: 'Allegro DesignTrue DFM可制造性设计解决方案'
date: Fri, 21 Oct 2022 02:49:44 +0000
draft: false
tags: ['Allegro']
---

传统的PCB设计制造流程是在设计结束时创建制造数据，然后将其发送给制造商。几个小时或几天后，制造商会回复一份需要解决的问题清单。这些问题得到纠正之后，数据创建周期重复进行，导致了设计到制造阶段的时间浪费。

为了缩短制造周期，设计增加DFx验证检查以减少制造验证数据与设计数据之间的循环反复

PCB DesignTrue DFM 技术允许在设计过程中提供即时、线上的有关制造性设计的检查，为了却把DFM 最后验收阶段，PCB 设计者能确保他们的设计符合制造规范要求，让设计和制造两个环节更顺畅衔接。

该创新技术提供2000 多个进阶检查项目可以轻松配置应用制造规范。Allegro DesignTrue DFM 技术支持DFM 规则的导入和导出，可重复使用。它采用全新、更易使用的DRC 浏览器，能够一次性处理一类错误。Constraints 可灵活配置来启用、禁用群组和整个类别的规则或单个规则。规则可被应用于Etch模式、Non-Etch模式和Stackup模式。新的浏览器可图形化描述DRC，按类型描述DRCs，并提供DRC 计数图表。使用者可以快速排序、浏览和查看，也能放弃或保留DRCs。

DFM规则类型
-------

打开规则管理器，定位到应用及制造的Manufacturing规则，此处包含三种规则项目

*   Design for Fabrication用于设定PCB裸板的设计规则
*   Design for Assemby是用于设定PCB元器件装配的设计规则
*   Design for Test是用于PCBA测试的设计规则（本文不做介绍）

![](https://a1024.synology.me:222/images/blog2022/DFM1.png)

在每个项目下包含两个子项目，和Physical规则类似，这里DFF Constraint Set用于创建规则模版，Design用于将制定的规则模版应用到设计中，可配置的规则项目包含以下几个类型

### Fabrication

*   Outline：部分元素到板边或者板内铣切区（Cutout）的间距设置
*   Mask：阻焊相关检查
*   Annular Ring：环宽检查
*   Holes：（略）
*   Copper Features：导体图形检查
*   Copper Spacing：导体间距检查
*   Silkscreen：丝印检查

### Assembly

*   Outline:设置器件、助焊到板边/铣切区域的最小距离。
*   PkgtoPkg Spacing:设置器件到器件最小安装距离规则。
*   Spacing：设置器件/助焊到孔、焊盘、金手指最小间距规则。
*   Pastemask:设置助焊到焊盘最小距离，丢失助焊检查等规则。

创建一个CSet（规则模版）
--------------

![](https://a1024.synology.me:222/images/blog2022/DFM2.png)

选择你需要设定的一个规则类型，可以从右侧列表中查看到改类型规则具体可以配置的项目，这里有横排和竖排两种显示方式，点击Create new或New CSET弹出对话框，上边一行设定一个你能识别的名称，下边一行代表此规则应用于那个对象类型，此处包含三种

*   Etch：所有导体层包含正片和负片
*   Non-Etch：所有非导体层如丝印、阻焊等
*   Stackup：板结构相关，板框、钻孔等

在对应的规则项目指定需要的临界值

应用一个Cset（规则模版）
--------------

![](https://a1024.synology.me:222/images/blog2022/DFM3.png)

选择规则项目的Design子项，从子项中选择你已经创建过规则类型的项目，在这个表中你可以选择哪些层或者对应的项目需要使用你设定的规则模版，不同的层或项目也可以选择不同的规则模版

部分包含子项目的箭头双击可以打开所有子项目，如上图Condutor大空翼打开左右正片层，用于对不同的层分配不同的规则模版

在对应的层或项目下方的Referenced DFF CSet行选择你需要使用的规则模版名称即应用成功

### 丝印和阻焊

由于需要用的丝印和阻焊层是不固定的，所以对于这两个项目应用规则时应先设置需要检查的层再调用规则

从规则区右键创建一个层组，起一个名字，从光绘叠层中或者从class subclass界面选择需要使用的丝印层点击应用则层创建完成

再对创建的层应用创建的规则

![](https://a1024.synology.me:222/images/blog2022/DFM6.png)

启用或关闭规则项目
---------

![](https://a1024.synology.me:222/images/blog2022/DFM4.png)

从规则管理器菜单选择Analysis->Analysis Mode，打开规则分析管理窗口，找到你设定规则的对应项目，将你需要检查分析的项目选择On项勾选（这些项目在一个新板中默认全部是关闭的）

DRC检查和处理
--------

和其它DRC检查一样，规则设置好生效后，再更新DRC则有悖于设定规则的设计将被标识DRC标志，查看DRC标识的信息，可以查看对应的冲突项目和具体信息

同样也可以在各种DRC清单或者DRC浏览器中浏览所有DFM相关的项目

当你在实时设计中如果出现有悖于悖于设定规则的情况，这些DRC也将实时被显示出来

DFM规则的导出和复用
-----------

![](https://a1024.synology.me:222/images/blog2022/DFM5.png)

从规则管理器中选择File->Export->Constraints，从窗口底部选择你需要的部分，如果你只需要DFM规则则只选择上图中红框的选项，如果有其它需要请自行决策

导出的Constraints可以在其它的设计中被复用通过菜单File->Import->Constraints导入进行复用

注意导出导入的规则一般只强调使用Cset（规则模版）因为每个设计各有不同，所有Design子项关系规则模版的复用不能保证一一对应需要再次核查是否套用成功