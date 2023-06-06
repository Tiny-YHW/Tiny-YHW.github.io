---
title: 'TPS51200 灌电流和拉电流 DDR 终端稳压器'
date: Mon, 30 May 2022 02:54:26 +0000
draft: false
tags: ['元器件']
---

官网链接：https://www.ti.com/product/TPS51200

简介
--

TPS51200 器件是一款灌电流和拉电流双倍数据速率 (DDR) 终端稳压器，专门针对低输入电压、低成本、低噪声的空间受限型系统而设计。

TPS51200 可保持快速的瞬态响应，仅需 20μF 超低输出电容。TPS51200 支持遥感功能，并满足 DDR、DDR2、DDR3、DDR3L、低功耗 DDR3 和 DDR4 VTT 总线终端的所有电源要求。

此外，TPS51200 还提供一个开漏 PGOOD 信号来监测输出稳压，并提供一个 EN 信号在 S3（挂起至 RAM）期间针对 DDR 应用对 VTT 进行放电。

TPS51200 采用带散热焊盘的高效散热型 10 引脚 VSON 封装（3.00mm × 3.00mm），具有绿色环保和无铅的特性。其额定温度范围为 -40°C 至 +85°C。

特性
--

*   输入电压：支持 2.5V 和 3.3V 电源
*   VLDOIN 电压范围：1.1V 至 3.5V
*   具有压降补偿功能的灌电流和拉电流终端稳压器
*   需要超小的输出电容 20μF（通常为 3 × 10μF MLCC），即可用于存储器终端 应用 (DDR)
*   用于监视输出稳压的 PGOOD
*   EN 输入
*   REFIN 输入允许直接或通过电阻分压器灵活进行输入跟踪
*   远程检测 (VOSNS)
*   ±10mA 缓冲基准 (REFOUT)
*   内置软启动，欠压锁定 (UVLO) 和过流限制 (OCL)
*   热关断

功能框图
----

![](https://www.ti.com.cn/ods/images/ZHCSL06D/v08019_slus812.gif)

参考电路图
-----

![](https://www.ti.com.cn/ods/images/ZHCSL06D/simp_app_slus812.gif)

引脚配置及功能
-------

![](https://www.ti.com.cn/ods/images/ZHCSL06D/pinout_drc_10_slus812.gif)

引脚名称

引脚号

I/O

描述

EN

7

输入

对于 DDR VTT 应用，使用 EN 引脚作为 ON/OFF 功能，  
EN 被驱动为高电平时，VO 稳压器开始正常工作  
当器件将 EN 驱动为低电平时，VO 通过内部 18Ω MOSFET 放电至 GND

GND

8

地

信号地

PGND

4

地

LOD电源地

PGOOD

9

输出

当 VO 输出在 REFOUT 的 ±20% 范围内时，该输出变为高电平。  
PGOOD 在输出超过 powergood 窗口大小后的 10 μs 内取消断言。  
在初始 VO 启动期间，PGOOD 在 VO 进入电源良好窗口后置高 2 ms（典型值）。  
由于 PGOOD 是开漏输出，因此需要一个值介于 1 kΩ 和 100 kΩ 之间的上拉电阻，置于 PGOOD 和稳定的有源电源电压轨之间。

REFIN

1

输入

REF输入电源，0.5-1.8V，可由VDDQ通过电阻分压获得

REFOUT

6

输出

RFF输出电源，Vref=VDDQ/2=0.75V，电流较小，但是需要确保VREF的AC Noise保持在±25mv。否则会引起时序的误差以及抖动等不确定的行为。建议线宽15mil以上  
为DDR生成VTT的参考电压，它能够支持 10 mA 的拉电流和灌电流负载。当 REFIN 电压升至 0.390 V 且 VIN 高于 UVLO 阈值时，REFOUT 变为活动状态。  
当 REFOUT 低于 0.375 V 时，它被禁用并随后通过内部 10-kΩ MOSFET 放电至 GND

VIN

10

输入

2.5V 或 3.3V 电源输入，可支持范围为（1.1V-3.5V），偏置电压，用于控制环路

VLDOIN

2

电源输入

LDO 的输入电压，为VTT输出提供输入，过大电流

VO

3

输出

LDO 的电源输出VTT，VTT=VDDQ/2=0.75V  
最大支持到3.5A电流。能够提供和吸收电流。  
当DDR芯片的地址总线为高时，VO引脚为灌电流，当DDR芯片的地址总线为低时，VO引脚为拉电流。

VOSNS

5

输入

LDO 的电压检测输入。连接到输出电容或负载的正极。  
电压：1.25 V (DDR1),0.9 V (DDR2), 0.75 V (DDR3),0.675 V (DDR3L), 0.6 V (DDR4)

Layout
------

### 设计要点

*   将输入电容器放置在尽可能靠近 VDLOIN 引脚的位置，并采用短而宽的连接。
*   将输出电容尽可能靠近 VO 引脚放置，连接短而宽。如果需要将其余输出电容器放置在负载侧，则在靠近 VO 引脚的位置放置一个值至少为 10µF 的陶瓷电容器。
*   将 VOSNS 引脚连接到输出电容器的正节点作为单独的走线。在 DDR VTT 应用中，将 VO 感应走线连接到 DIMM 侧，以确保 DIMM 侧的 VTT 电压得到良好调节。
*   如果 VO 感应迹线很长，请考虑在 VOSNS 处添加低通滤波器。
*   将 GND 引脚和 PGND 引脚直接连接到散热焊盘。
*   TPS51200 使用其导热垫来散热。为了有效地从 TPS51200 封装中散热，请在散热焊盘上放置多个接地过孔。使用大的接地铜平面，尤其是表面层的铜平面，将这些通孔倒在导热垫上。

### 示例

![](https://www.ti.com.cn/ods/images/ZHCSL06D/art_layout_slus812.gif)

元器件和焊盘图形
--------

[VSON (DRC)](https://www.ti.com/lit/pdf/mpds117l) [QFND013N](https://www.ti.com/cn/lit/pdf/qfnd013?_ticdt=MTY1Mzg3NzM3NHwwMTgxMTI3YTg5YjUwMDBlN2I4YmE2YmIyMmU1MDUwNzMwMDNiMDZiMDBiZDB8R0ExLjMuNDQxODMxMzMzLjE2NTM4NzI0MzA)

可订购型号
-----

[TPS51200DRCR](https://www.ti.com/store/ti/en/p/product/?p=TPS51200DRCR)；[TPS51200DRCT](https://www.ti.com/store/ti/en/p/product/?p=TPS51200DRCT)

典型应用
----

### 设计示例 3.3-V IN DDR3 配置

![](https://www.ti.com.cn/ods/images/ZHCSL06D/v08029_lus812.gif)

*   V IN = 3.3 V
*   VDDDQ = 1.5 V
*   V VLDOIN = V VDDQ = 1.5 V
*   VTT = 0.75V

### 3.3-VIN, DDR2

![](https://www.ti.com.cn/ods/images/ZHCSL06D/application_DDR2_tps51200.gif)

### 2.5-VIN, DDR3

![](https://www.ti.com.cn/ods/images/ZHCSL06D/v08030_lus812.gif)

### 3.3-VIN, LP DDR3 or DDR4

![](https://www.ti.com.cn/ods/images/ZHCSL06D/v08031_lus812.gif)

### 3.3-VIN, DDR3 Tracking

![](https://www.ti.com.cn/ods/images/ZHCSL06D/v08032_lus812.gif)

### 3.3-VIN, LDO

![](https://www.ti.com.cn/ods/images/ZHCSL06D/v08033_slus812.gif)

### 3.3-VIN, DDR3 Configuration with LFP

![](https://www.ti.com.cn/ods/images/ZHCSL06D/v08034_lus812.gif)