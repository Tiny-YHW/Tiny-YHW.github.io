---
layout: post
title: PCB上走线电阻评估方法
categories: PCB设计
description: 
date: 2023-06-25
permalink: pcb-wire-resistance
excerpt: PCB上走线电阻评估方法
---

## 粗算方法

1oz铜厚铜导线的电阻约为每个方格0.5mΩ

## 在指定温度时

PCB导线的电阻计算公式为R = ρ \* L / S

* ρ：电阻率（电导率指某种材料单位体积内的电阻）
* L：线长
* S：线截面积

导线的横截棉结 S = T \* W

将其带入上面公式可得

R = (ρ \* L) / (T \* W) = (ρ / T) \* (L / W)

* ρ为定值由导体材料决定，其中最常使用的铜20度时的电导率约为1.75 x 10^(-8) Ωm
* T为铜厚在设计中为定值
* L / W可简化理解为格子数，以导线的宽度为单位画方格每个方格为一个L / W

当使用1oz铜厚（35um） R的计算值约为 0.5mΩ*（L / W），即每个方格0.5mΩ

## 考虑温度时

若考虑温升或特别的温度环境，须在以上公式的基础上考虑温度对电阻的影响

电导率与温度紧密相关。金属的电导率随着温度的增高而降低。半导体的电导率随着温度的增高而增高。在一段温度值域内，电导率可以被近似为与温度成正比。


R= (ρL)/(TW) \* ((1+α(Tamb −25°C))

Tamb是环境温度。

[Omicalculator PCB 走线电阻](https://www.omnicalculator.com/other/pcb-trace-resistance){:target="_blank"}