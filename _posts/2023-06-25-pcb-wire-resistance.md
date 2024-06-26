---
layout: post
title: PCB上走线电阻评估方法
categories: PCB设计
date: 2023-06-25
permalink: pcb-wire-resistance
excerpt: PCB上走线电阻评估方法
---

## 粗算方法

1oz铜厚铜导线的电阻约为每个方格0.5mΩ

## 电阻率

电阻率（英语：Resistivity），又称电阻系数，是描述材料导电性能的物理量，科学符号为 ρ。

电阻率在数值上等于单位长度、单位截面的某种物质的电阻，数值上等于长度为一米，横截面为一平方米的该种物质的电阻大小。

电阻率的倒数为电导率。电阻率与导体的长度、横截面积等因素无关，是导体材料本身的电学性质，由导体的材料决定，且与温度有关。

电阻率在国际单位制的单位是Ω·m，读作欧姆米，简称欧米。常用单位为“欧姆·米”

其中最常使用的铜20度时的电阻率约为1.75 x 10^(-8) Ω·m

## 在指定温度时

PCB导线的电阻计算公式为R = ρ \* L / S

* L：线长
* S：线截面积

导线的横截面积 S = T \* W

将其带入上面公式可得

R = (ρ \* L) / (T \* W) = (ρ / T) \* (L / W)

* T为铜厚在设计中为定值
* L / W可简化理解为格子数，以导线的宽度为单位画方格每个方格为一个L / W

当使用1oz铜厚（35um） R的计算值约为 0.5Ω·m\*（L / W），即每个方格0.5mΩ

## 考虑温度时

若考虑温升或特别的温度环境，须在以上公式的基础上考虑温度对电阻的影响

电导率与温度紧密相关。金属的电导率随着温度的增高而降低。半导体的电导率随着温度的增高而增高。在一段温度值域内，电导率可以被近似为与温度成正比。


R= (ρL)/(TW) \* ((1+α(Tamb −25°C))

Tamb是环境温度。

[Omicalculator PCB 走线电阻](https://www.omnicalculator.com/other/pcb-trace-resistance){:target="_blank"}