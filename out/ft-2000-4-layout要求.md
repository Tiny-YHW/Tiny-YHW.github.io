---
title: 'FT-2000/4 Layout要求'
date: Wed, 31 Mar 2021 05:37:17 +0000
draft: false
tags: ['设计资料/文档']
---

内容引用自[FT-2000／4 硬件设计指导手册](https://www.phytium.com.cn/Uploads/20200706/FT-2000%EF%BC%8F4%20%E7%A1%AC%E4%BB%B6%E8%AE%BE%E8%AE%A1%E6%8C%87%E5%AF%BC%E6%89%8B%E5%86%8C[1].pdf)

FT2000/4 可以根据实际应用需求，设计出不同的硬件配置。如图所示，给出了一种典型 FT-2000/4 硬件平台方案。具体设计可以根据需求裁剪、添加、替换外设模块。用户可以根据具体应用灵活调整。

![](http://a1024.synology.me:222/images/blog2022/FT-200041.jpg)

FT-2000/4硬件平台框图

低速IO 接口
-------

### I2C 接口

CPU的I2C 接口为1.8V 的IO 电平类型，若外接的设备不兼容1.8V 电平，需使用I2C 专用电平转换芯片进行电平转换。

### QSPI布线要求

信号

布线建议

QSPI\_SCK

布线长度小于7 inch

QSPI\_SO\_IO0 、QSPI\_SI\_IO1 、QSPI\_WP\_IO2 、QSPI\_HOLD\_IO3 、QSPI\_CSN\[3:0\]、

与QSPI\_SCK 布线偏差建议小于1inch

QSPI 接口布线建议

### LPC 布线要求

时钟由外部供给33Mhz 时钟，同一时钟可分别给CPU 和LPC 设备,如图LPC 连接方式所示。

![](http://a1024.synology.me:222/images/blog2022/FT200042.png)

LPC 连接方式

如 上图所示， 时钟到设备与时钟到CPU 之间的边沿的偏差△t=|T2\_clk\_delay-T1\_clk\_delay|。数据线（包括Frame、LAD\[3:0\]、SerIrq、LDrq）延迟为T\_Data。

需要满足：△t<1ns、△t<T\_Data<Tclk（Tclk 为时钟周期，时钟频率为33Mhz 时，Tclk 约为33.3ns）

双向管脚到电平转换芯片间需要加 50 欧姆电阻进行保护，防止方向切换时存在电源到地的短路径。

### SPI信号布线要求

信号

布线建议

SPI\_SCK、SPI\_SI

布线长度小于7 inch

SPI\_SO、SPI\_CSN\[3:0\]

与SPI\_CLK布线偏差建议小于1 inch

SPI 接口布线建议

### RGMII布线要求

为了保证 RGMII 接口与 PHY 能正常通信，建议按照下表中的参数进行设计。布线阻抗控制为50Ω±10%

信号

建议等长

GTX\_CLK  
TXD\[3:0\]  
TX\_CTL

TXD\[3:0\]、TX\_CTL与GTX\_CLK相差-250mils到250mils

RX\_CLK  
RXD\[3:0\]  
RX\_CTL

RXD\[3:0\]、RX\_CTL与RX\_CLK 相差-250mils到250mils

MDC  
MDIO

MDIO与MDC相差-250mils到250mils

SPI 接口布线建议

PCIe接口
------

### CPU校准电阻要求

CPU外电阻值为3.01KΩ，接精度为1%的校准电阻。外部校准电阻要求尽可能靠近CPU 引脚，走线避开高速信号等干扰源。

![](http://a1024.synology.me:222/images/blog2022/FT200043.png)

外部校准电阻

### 阻抗要求

差分数据信号阻抗：85Ω±10%  
芯片扇出部分走线阻抗可不做严格控制，但是建议尽量缩短扇出线部分的走线长度。

### 耦合电容摆放要求

PCIe需要在发送端和接收端之间放置交流耦合电容。对于主板来说，TX差分对上的AC耦合电容摆放在主板上，RX上的AC耦合电容摆放在相应的PCIe设备端。

![](http://a1024.synology.me:222/images/blog2022/FT-200044.jpg)

耦合电容摆放示意图

### 走线间距要求

PCIe差分对之间的走线间距（走线边缘距离）S≥Max(4W,4H)，W为线边缘间距，H为走线距离最近参考平面的高度。尽量远离开关电源的开关管和电感等噪声源。TX和RX建议走在不同层，或者隔开尽可能远的距离（50mil以上）。

### 走线等长要求

从布线长度考虑，差分对P和N两条布线总长度之差不能超过4mils。建议扇出时，对较短的走线进行一定的等长补偿。两种等长绕线的参考如图所示。

![](http://a1024.synology.me:222/images/blog2022/FT200045.png)

等长绕线参考

### 信号过孔要求

信号如果需要打孔换层，建议在换层孔附近添加回流孔，回流孔尽量靠近信号孔。如果使用过孔换层，需考虑过孔残桩，残桩长度应小于100mils。

![](http://a1024.synology.me:222/images/blog2022/FT-200046.jpg)

回流孔摆放参考

### 走线参考要求

走线参考GND，保证参考平面完整，不允许有跨平面分割的情况。如果设计中无法避免跨平面参考，建议在跨平面分割处用旁路电容将回流信号连接起来。

信号

建议等长

GTX\_CLK  
TXD\[3:0\]  
TX\_CTL

TXD\[3:0\]、TX\_CTL与GTX\_CLK相差-250mils到250mils

RX\_CLK  
RXD\[3:0\]  
RX\_CTL

RXD\[3:0\]、RX\_CTL与RX\_CLK 相差-250mils到250mils

MDC  
MDIO

MDIO与MDC相差-250mils到250mils

SPI 接口布线建议

![](http://a1024.synology.me:222/images/blog2022/FT-200047.jpg)

跨平面参考处理

DDR4内存接口
--------

FT-2000/4支持RDIMM/UDIMM/SODIMM/板载颗粒等内存形式。

### PCB布局

FT-2000/4 芯片两个 DDR4 通道的引脚分布如图 所示（红色和蓝色标注的引脚）。两个内存通道布线可以根据芯片 ball map 设计分别对称布在芯片两侧；也可布在芯片同一侧。

![](http://a1024.synology.me:222/images/blog2022/FT-200048.jpg)

DDR Ball Map Top view

![](http://a1024.synology.me:222/images/blog2022/FT200049.png)

内存槽芯片两侧布局

![](http://a1024.synology.me:222/images/blog2022/FT2000410.png)

内存槽芯片一侧布局

### 布线参考

内存分两侧布线，需要2 层走线；若内存分一侧出线，需要4 层走线，两侧布线相对一侧布线的方式可省两层布线层，降低了成本，同时走线更短，有利于提高信号质量。若结构无特殊要求的情况下，建议两侧布线的形式。

![](http://a1024.synology.me:222/images/blog2022/FT-2000411.jpg)

内存两侧布线示意图（内存两层布线）

![](http://a1024.synology.me:222/images/blog2022/FT-2000412.jpg)

内存一侧布线示意图（内存四层布线）

### 双DIMM模式

FT-2000/4芯片两个DDR4通道均支持双DIMM 模式，以获取更大内存容量。

![](http://a1024.synology.me:222/images/blog2022/FT2000413.png)

### 阻抗要求

DDR 走线的阻抗需满足如下要求：单端线阻抗45Ω±10%，差分线阻抗75Ω±10%。同时为了减少DDR 走线之间的串扰，单端走线间距S≥Max(3W，3H)，W 为线边缘间距，H 为走线距离最近参考平面的高度。芯片下的引脚扇出和内存插槽，可适当放宽要求。

### 交换准则

若按照 8bit 划分为一个 slice，一个通道 72bit 可划分为 9 个 slice。如表所示，每组 slice 内有 12 个信号，以下准侧是基于该划分。

“X8、X16 兼容内存交换准则”相对宽松和灵活，但不一定能兼容 X4，最终需要采用何种准侧，需依据用户具体需求而定。用户在不确定未来可能采用何种内存类型时候，建议遵循“X4、X8、X16内存交换准则”获取最好的兼容性。

#### X8、X16 内存交换准则

DQ交换：在进行X8兼容内存的设计时，slice内部的8个DQ可以自由互换。

Slice交换：slice\[0:7\]可以进行slice之间交换。Slice\[8\]为ECC用途，不能与其它slice交换。若用户需要使用ECC的内存条，slice\[8\]必须与DIMM条上的slice\[8\]进行连接。若确认无需ECC功能，将slice \[8\]信号浮空即可。

#### X4、X8、X16 内存交换准则

DQ交换：每个slice可以再细拆分为低4位和高4位两组，分别为slice\[n\]\_L与slice\[n\]\_H，如表5-6所示。slice\[n\]\_L内的DQ之间可以互相交换，slice\[n\]\_H内的DQ之间可以互相交换。但不能slice\[n\]\_L内的DQ与slice\[n\]\_H内的DQ进行交换。

Slice交换：slice\[0:7\]可以进行slice之间交换。Slice\[8\]为ECC用途，不能与其它slice交换。若用户需要使用ECC的内存条，slice\[8\]必须与DIMM条上的slice \[8\]进行连接。若确认无需ECC功能，可以将slice \[8\]信号浮空即可。

Slice\[n\]

Slice\[n\]\_L

Slice\[n\]\_H

备注

0-7

S**\[n\]**\_DQ\[0:3\]、DQS**\[n\]**\_C、DQS**\[n\]**\_T

S**\[n\]**\_DQ\[4:7\]、DQS**\[n+9\]**\_C、DQS**\[n+9\]**\_T

数据

8

S8\_DQ\[0:3\]、DQS8\_C、DQS8\_T

S8\_DQ\[4:7\]、DQS17\_C、DQS17\_T

ECC

Slice 分组表

### 校准电阻要求

内存 LMUx\_BP\_ZN 采用240 欧姆1%精度的外部校准电阻与地连接，要求尽可能靠近引脚，避免外部干扰。

![](http://a1024.synology.me:222/images/blog2022/FT2000414.png)

DDR 校准电阻

### 内存布线长度约束

信号

布线要求

Clock

阻抗：75Ω  
等长：差分对之间长度偏差<4mils

CS,ODT,CKE,CMD/ADDR

阻抗：45Ω  
等长：与 clock 长度偏差<40mils

DQ

阻抗：45Ω  
等长：同一 slice 内部DQ 相对DQS 的偏差<20mils  
最大长度 6000mils

DQS

阻抗：75Ω  
等长：差分对之间长度偏差<4mils

布线长度约束

电源
--

FT-2000/4系列处理器电源参数参表

参数

符号

典型值  
(V)

最大电流值

核心电源

VDD

0.8

24A

内存电源

VDDQ

1.2

2.7A

温度传感器电源

VDDA

1.8

1mA

IO电源

VDDPST

1.8

100mA

PLL模拟电源

PLL\_VDDHV

1.8

50mA

PCIE 模拟电源

PEU1\_X1\_AVDDH  
PEU0\_X16\_AVDDH  
PEU1\_X16\_AVDDH

1.8

500mA

PLL数字电源

PLL\_VDDPOST  
PLL\_VDDREF

0.8

20mA

PCIE模拟电源

PEU0\_X16\_AVDD  
PEU1\_X16\_AVDD

0.8

1.2A

PCIE高速时钟电源

PEU0\_X16\_AVDDCLK  
PEU1\_X16\_AVDDCLK

0.8

600mA

内存PLL模拟电源

VAA

1.8

80mA

电源参数

内存电源VDDQ参数仅为CPU电流，不包含内存颗粒部分，设计时应根据具体内存情况设计电源。

### 设计要点

建 议 PCIE 电源连接方如下图6.1 ， FB1 、FB2 、FB3 磁珠推荐参数：120Ω/100Mhz。

![](http://a1024.synology.me:222/images/blog2022/FT2000415.png)

PCIe 电源连接方法

![](http://a1024.synology.me:222/images/blog2022/FT2000416.png)

AVDDCLK 电源放置的电容位置

VAA电源用于内部PLL模拟电源，因此要求非常干净。最大的交流噪声限制在正常电压的±2.5%内。

![](http://a1024.synology.me:222/images/blog2022/FT2000417.png)

VAA 电源连接方法

电源的去耦电容位于CPU背面，尽可能靠近引脚。

![](http://a1024.synology.me:222/images/blog2022/FT2000418.png)

电容放置方式

Pin Delay
---------

[Pin Delay](https://layouto.lanzous.com/i1f1Znij0rc)管脚延时文件需要加载到设计中，以保证时序的一致