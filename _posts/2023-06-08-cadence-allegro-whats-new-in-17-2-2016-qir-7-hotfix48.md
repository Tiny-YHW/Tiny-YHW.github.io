---
layout: post
title: Cadence Allegro What’s New in 17.2 2016 QIR7（hotfix48）
categories: Allegro
date: 2023-06-08
---

本文档介绍了Allegro® PCB Editor在17.2版季度增量版QIR7（hotfix48）中的新功能和增强功能

* * *

**关联**

*   [What’s New in 17.2 2016](https://tiny-yhw.github.io//2023/06/08/cadence-allegro-whats-new-in-17-2-2016/)
*   [What’s New in 17.2 2016 QIR1（hotfix4）](https://tiny-yhw.github.io//2023/06/08/cadence-allegro-whats-new-in-17-2-2016-qir-1-hotfix4/)
*   [What’s New in 17.2 2016 QIR2（hotfix9）](https://tiny-yhw.github.io//2023/06/08/cadence-allegro-whats-new-in-17-2-2016-qir-2-hotfix9/)
*   [What’s New in 17.2 2016 QIR3（hotfix16）](https://tiny-yhw.github.io//2023/06/08/cadence-allegro-whats-new-in-17-2-2016-qir-3-hotfix16/)
*   [What’s New in 17.2 2016 QIR4（hotfix25）](https://tiny-yhw.github.io//2023/06/08/cadence-allegro-whats-new-in-17-2-2016-qir-4-hotfix25/)
*   [What’s New in 17.2 2016 QIR5（hotfix31）](https://tiny-yhw.github.io//2023/06/08/cadence-allegro-whats-new-in-17-2-2016-qir-5-hotfix31/)
*   [What’s New in 17.2 2016 QIR6（hotfix38）](https://tiny-yhw.github.io//2023/06/08/cadence-allegro-whats-new-in-17-2-2016-qir-6-hotfix38/)
*   [What’s New in 17.2 2016 QIR7（hotfix48）](https://tiny-yhw.github.io//2023/06/08/cadence-allegro-whats-new-in-17-2-2016-qir-7-hotfix48/)

* * *



## DesignTrue DFM

增加诸多可检查项

[Allegro DesignTrue DFM可制造性设计解决方案](https://tiny-yhw.github.io//2023/06/08/cadence-allegro-designtrue-dfm/){:target="_blank"}


## Component Lead Editor in Allegro PCB Editor 器件引脚编辑

现在，使用Allegro PCB Editor或Allegro Symbol Editor中的新Lead Editor添加元件引线接触区域信息。

- Define lead type 定义引线类型
- Define lead physical details 定义引线物理详细信息
- Position the lead in the symbol 确定器件引线位置
- View the lead contact area graphically 以图形方式查看引线与焊盘接触区域
- Enable DFM lead checks 启用DFM与引线相关的检查项

### Component Lead Editor in Allegro Symbol Editor

使用菜单*Setup – Lead Editor*编辑引脚信息，从*Assign Pin Leads*中编辑详细信息。

![172-algPN-11.gif](https://a1024.synology.me:222/images/172-algPN-11.gif)

1. 选择需要添加引脚信息的引脚号
2. 选择引脚类型
3. 选择引脚与焊盘连接的图形

![172-algPN-12.gif](https://a1024.synology.me:222/images/172-algPN-12.gif)

完成后封装汇总将显示定义的引脚信息图形，如果位置有偏差可以使用offsets将其放到正确的位置

![172-algPN-13.gif](https://a1024.synology.me:222/images/172-algPN-13.gif)
![172-algPN-14.gif](https://a1024.synology.me:222/images/172-algPN-14.gif)

定义引脚信息完成后*Assign Pin Leads*将被关闭，对应的图形将在封装中显示，对应的层为*Package Geometry/Component_Lead*

![172-algPN-15.gif](https://a1024.synology.me:222/images/172-algPN-15.gif)

### Component Lead Editor in Allegro PCB Editor

基本与Allegro Symbol Editor中类似

使用菜单*Setup – Lead Editor*编辑引脚信息，从*Assign Pin Leads*中编辑详细信息。

![172-algPN-16.gif](https://a1024.synology.me:222/images/172-algPN-16.gif)
![172-algPN-17.gif](https://a1024.synology.me:222/images/172-algPN-17.gif)

## DesignTrue DFM Ecosystem DesignTrue DFM生态系统

需要在线连接Cadence官网，略

## Allegro® PCB Symphony Team Design Option

[Allegro PCB Symphony Team Design实时协同设计](https://tiny-yhw.github.io//2023/06/10/2023-06-10-cadence-allegro-symphony-team-design/){:target="_blank"}

增加更多功能或命令支持

**Interactive Routing**

- Create Fanout and Copy Fanout support
	+ Quickly fanout devices and copy to similar devices
- Spread between Voids
	+ Spread traces between adjacent plane layer voids
	

**General Task**

- Property edit support
	+ Addition and modification of user-defined and standard object properties
	+ Properties that trigger additional actions are not supported in Symphony, such as Propagation delay are not available.
- Define lists
	+ Generate text file lists for nets, reference designators, and so on in the design
- Import and export sub-drawing support (Clipboard)
	+ Export supports all objects
	+ Import is limited to clines, vias, and shapes
- Create canvas image
	+ Capture canvas display and save it to Bitmap image (.bmp) and Portable Network Graphics (.png) file
	
## Return Path DRC Enhancements

定义参考层支持以Table的方式定义参考层面

![172-algPN-24.gif](https://a1024.synology.me:222/images/172-algPN-24.gif)

当选择Table方式时，会弹出一个*Edit RTP Reference Layers for Design*的对话框，用于对指定层定义参考层

![172-algPN-25.gif](https://a1024.synology.me:222/images/172-algPN-25.gif)
![172-algPN-26.gif](https://a1024.synology.me:222/images/172-algPN-26.gif)

## Sigrity Technology-Driven High-Speed Signal Analysis and Checking Enhancements 高速分析和检查增强

新增Reflection Analysis and IR Drop Analysis 工作流

### Reflection Analysis 反射分析

反射分析SI仿真工作流程，在Allegro中惊醒设置和建模要求与串扰分析所用的相同。设置包括分配元件模型和指定要仿真的网络（Net、XNet、Bus、Differential Pair）。可以使用分析模型管理器（AMM）管理库和指定模型。还可以在这个流中直接使用IBIS库和模型。

![172-algPN-27.gif](https://a1024.synology.me:222/images/172-algPN-27.gif)

仿真结果生成几个波形质量和延迟测量。这些测量包括回铃、过冲和切换/建立延迟。

除了表格式电子表格窗格之外，还可以选择反射分析结果中的一个测量结果，以在画布中显示为网络级的彩色编码段。

### IR Drop Analysis IR 压降分析

IR压降分析是PI仿真工作流程，用于识别构成电力输送网络的互连中的潜在压降问题。运行分析所需的设置基于PowerTree技术。

分析结果是一个列出结果的表格，如果在PowerTree中添加了可选的公差阈值，则该表格可以指示通过/失败状态。IR Drop视觉可以显示为电压或IR Drop颜色编码梯度。

![172-algPN-28.gif](https://a1024.synology.me:222/images/172-algPN-28.gif)

## Backdrill Enhancements 背钻增强

### Backdrill Clearance – Anti-Pads and Route Keepouts

User Preferences Editor中*Manufacturing – Drilling*新增一个环境变量`BACKDRILL_OVERSIZE_OPTION

![172-algPN-31.gif](https://a1024.synology.me:222/images/172-algPN-31.gif)

启用此选项将在*Backdrill Setup and Analysis*窗口增加两束新选项

- Disable oversize antipads: 使用焊盘参数中的*BACKDRILL_CLEARANCE ANTI PAD*值而不使用antipads
- Disable oversize keepouts: 禁止基于焊盘堆参数中的*BACKDRILL_CLEARANCE Keep-Out*值生成 Route Keepout
- 
![172-algPN-32.gif](https://a1024.synology.me:222/images/172-algPN-32.gif)

## Component Group Move with DFA Feedback 带DFA反馈的多元器件移动

QIR7之前只移动单器件时可以带DFA反馈，此版本增强了此功能，可以通过多种方法选择多个组件，并在器件移动器件实时反馈DFA间距问题

![172-algPN-33.gif](https://a1024.synology.me:222/images/172-algPN-33.gif)

## 3D Canvas Update 3D画布更新

### 2D Window Select

可选在3D画布中仅显示在2D窗口选择的对象，对于大型设计，更方便快捷的查看指定区域的3D

![172-algPN-34.gif](https://a1024.synology.me:222/images/172-algPN-34.gif)
![172-algPN-35.gif](https://a1024.synology.me:222/images/172-algPN-35.gif)

### Reverse Cutting Plane 反向切割

在使用*Cutting Plane*功能时，如果显示的可是区域是反向的，可以通过*Reverse Cutting Plane*切换切割的一侧或另一侧

![172-algPN-36.gif](https://a1024.synology.me:222/images/172-algPN-36.gif)
![172-algPN-37.gif](https://a1024.synology.me:222/images/172-algPN-37.gif)

### View 视图

自从引入3D Canvas以来默认视图一直是透视图。在此版本中，还提供了第二个选项“Orthographic view（正交视图）”。

透视图模仿您站在组装板的中心上方。正交视图允许您查看设计的每一个方面-特别是孔-就好像您正站在每个对象的正上方，如图所示。

![172-algPN-38.gif](https://a1024.synology.me:222/images/172-algPN-38.gif)

### STEP Models without Specified Colors 没有指定颜色的STEP模型

在早期版本中，如果STEP模型没有指定颜色，则会指定默认的粉红色。在此版本中，如果STEP模型没有指定颜色，则可以使用*Device/Package STEP Mapping*对话框指定颜色，3D Canvas将识别新指定的颜色。

![172-algPN-39.gif](https://a1024.synology.me:222/images/172-algPN-39.gif)

### Negative Space 负空间

将实际板中的空洞部分切割掉，如孔或铣切区或板外的丝印，这样3D更接近现实

![172-algPN-40.gif](https://a1024.synology.me:222/images/172-algPN-40.gif)
![172-algPN-41.gif](https://a1024.synology.me:222/images/172-algPN-41.gif)

### Layer Transparency Setting 图层透明度设置

颜色主题中各层可以使用单独的滑块在透明（0%）和不透明（100%）之间的任何位置设置可见性。

![172-algPN-42.gif](https://a1024.synology.me:222/images/172-algPN-42.gif)
![172-algPN-43.gif](https://a1024.synology.me:222/images/172-algPN-43.gif)

### Measure Closest Distance 测量最近距离

增加一个新的菜单命令*Measure Closest Distance*，使用此命令可以显示选择物体的最小距离

![172-algPN-44.gif](https://a1024.synology.me:222/images/172-algPN-44.gif)
![172-algPN-45.gif](https://a1024.synology.me:222/images/172-algPN-45.gif)

## Place Vision 放置可视化

Place Vision是一个图形化环境，旨在通过各种元件放置策略提高效率。虽然这一概念类似于Timing Vision，但Place Vision提供了以下方面的指导：

- XNet rat filtering XNet
- Timing driven placement
- Component association

选择菜单*View - Vision Manager* 并选择Placement Vision启动此功能

![172-algPN-46.gif](https://a1024.synology.me:222/images/172-algPN-46.gif)

### Vision Options 视觉选项

- XNets: 忽略Xnet器件的飞线并直接显示Xnet的两端的互联飞线，这样会减少混乱，因为一般Xnet器件可随意调整位置不会影响线序

![172-algPN-47.gif](https://a1024.synology.me:222/images/172-algPN-47.gif)

- Ratsnest Timing:对于设置了等长但net组，飞线将显示不同的颜色以显示线长差值

![172-algPN-48.gif](https://a1024.synology.me:222/images/172-algPN-48.gif)

- Associated Comp: 需要在原理图中指定的Associated Components，并仅限于旁路电容，此类器件在移动时会显示一个圆，引导将器件放置到其关联的器件附近

![172-algPN-49.gif](https://a1024.synology.me:222/images/172-algPN-49.gif)
