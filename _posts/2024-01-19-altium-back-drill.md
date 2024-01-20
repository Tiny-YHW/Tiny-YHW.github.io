---
layout: post
title: Altium Back Drill背钻应用
categories: Altium PCB
date: 2024-01-20
permalink: altium-back-drill
excerpt:
---

Altium PCB从17版本开始引入背钻支持的相关功能，而后不同版本的可能略有差异，本文使用Altium 24版本作为案例对背钻相关内容进行介绍

## 设置层叠

使用快捷键DK或菜单Design-Layer Stack Manager…打开层叠管理器，填写Thickness值与生产一致，以确保设计背钻时数据中板子厚度方向的参数与实际相吻合

## 定义背钻起止层类型

使用快捷键DK或菜单Design-Layer Stack Manager…打开层叠管理器，从层叠视图右上角点开三横杠图标选择勾选**Back Drills**则允许设计生成背钻

![](https://a1024.synology.me/images/blog/2024/image-30.png)

从层叠管理页下方的Back Drills标签页打开背钻层配置页面

从背钻孔层配置页面左上方点击Add可以增加一种背钻贯穿层，选择已有的背钻层点击Delete可以删除选择的背钻层

新增背钻孔后选择新增的背钻孔按F11键打开其属性面板，可以查看背钻孔的详细信息，从此处First Layer和Last Layer定义背钻的起止层

![](https://a1024.synology.me/images/blog/2024/image-31.png)

背钻层配置页面也将会随更改的First Layer和Last Layer值即时更新示例图

![](https://a1024.synology.me/images/blog/2024/image-44.png)

根据设计情况添加一个或多个需要背钻贯穿的层

## 设置背钻目标

打开规则管理器定位到High Speed - Max Via Stub Length(Back Drilling)规则，此项规则用于配置哪些对象需要进行背钻

### 对象

背钻的对象一般可以按网络名、网络组、通孔Pin、Via的一个或多个条件的任意组合

从规则中Where The Object Matches处指定背钻对象

以下是几个案例

直接指定几个特定的网络

```
InNet('SFPA_RX_P') or InNet('SFPA_RX_P')   
```


网络组，将需要背钻的多个网络划分到一个或多个Net Class

```
InNetClass('SFP') or InNetClass('PCIE_TX') or InNetClass('PCIE_RX')
```


以上两个案例未提及via或pin则会对via和pin均按做背钻处理，如果需要指定via或pin类型应使用“and”进行连接，以下是一个仅对SFP网络组的via背钻（pin不背钻）的案例

```
InNetClass('SFP') and  IsVia
```

### 背钻参数

从规则中Constraints处指定背钻参数

![](https://a1024.synology.me/images/blog/2024/image-32.png)

- 在Backdrill Oversize处指定背钻孔比钻孔单边外扩尺寸
- Max Stub Length用于限定最大的Stub长度值，Stub长度超过此值的将被背钻
- Top Layer和Bottom Layer勾选则代表允许从此面进行背钻

通过上述的设定，则设计中符合条件的对象将以背钻的形式显示出来

## 查看和检查背钻

### 背钻孔显示

![](https://a1024.synology.me/images/blog/2024/image-33.png)
成功生成背钻的孔会生成不同的两个半圆拼成的色环，色环的颜色与背钻的起始层和结束层颜色一样，如上图第一个图是背钻从TOP层到绿色的线的层

色环的直径与规则中BackDrill OverSize定义的值相关，色环外侧直径代表背钻孔径=孔径+2\*BackDrill OverSize

Tips：色环能否显示还和活动层和层显示状态相关，单层模式下如果活动层在无背钻的层则色环不可见；活动层在有背钻的层将显示色环。多层模式下基本和单层一致但背钻孔径小于空盘直径时，若活动层在无背钻的层，孔盘将完全覆盖色环导致色环不可见（若元素是透明状态则将显示其叠加色）

### 在 Hole Size Editor 中查看背钻

打开PCB panel选择 Hole Size Editor 项目，可以查看到[BD]开头的Layer Pairs项目为对应的背钻孔列表

![](https://a1024.synology.me/images/blog/2024/image-34.png)

### 3D视图

切换到3D视图从背钻的面去查看过孔，也可以看到背钻的结果样例

![](https://a1024.synology.me/images/blog/2024/image-38.png)

## 生产输出

### 钻孔数据（必须）

使用菜单File-Fabrication Output-NC Drill Files输出钻孔数据，输出的数据包括

- DRR文件：钻孔报告文件，包含钻孔及背钻的详细统计信息
- \*-BackDrill.TXn：背钻孔数据文件，n为系列号
- \*SlotHoles\*.TXT：槽形孔数据文件
- \*RoundHoles\*.TXT：圆形孔数据文件

### 钻孔表（非必须）

可以按下图方式打开Drill Symbols对话框，配置不同钻孔的Symbol图形

![](https://a1024.synology.me/images/blog/2024/image-39.png)

使用菜单Place-Drill Table放置钻孔表，选择放置的钻孔表使用F11打开属性面板，调整Layer Pairs选项调整钻孔表对应的贯穿层，需要多种背钻钻孔表的话可以继续放置钻孔表调整Layer Pairs分开放置多个表，并在输出数据时输出Drill Drawing层数据

![](https://a1024.synology.me/images/blog/2024/image-40.png)

![](https://a1024.synology.me/images/blog/2024/image-41.png)

由于背钻孔涉及在同一位置使用不同规格的钻头进行钻孔，钻孔符号将在这些位置堆叠显示。使用层对选择器控制当前显示的层对，如下图所示。

需注意钻孔表一般作为统计查看或说明数据使用，不能直接作为背钻数据使用

![](https://a1024.synology.me/images/blog/2024/image-42.png)

### Draftsman（非必须）

Draftsman是为您的设计创建高质量文档的理想工具。如果在设计中定义了背钻孔类型的板层对，则板层叠层图例将显示这些板层对，从而能够简单地将其快速显示。

![](https://a1024.synology.me/images/blog/2024/image-43.png)

调整好需要的图将其输出为PDF格式导出

### ODB++

针对ODB++输出，会为定义的每个背钻孔层对创建额外的钻孔文件夹。文件夹的名称如 \\drill1、\\drill2。这些文件夹包含标准的ODB钻孔文件。

### Gerber X2

尚未普及