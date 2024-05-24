---
layout: post
title: TY-Skill Text->Add Text By Select 根据选择对象增加字符
categories: TY-Skill
date: 2024-05-24
permalink: ty-skill-text-add-text
excerpt: 
---

![](https://tiny-yhw.github.io//images/TY-skill/image-50.png)

## 功能说明
本程序一般用于为指定引脚添加引脚号、网络名、器件位号标识

## 操作说明

1. 从菜单或命令启动此程序
2. 从Allegro自己Options（非skill界面）的Active Class and Subclass选择目标层面
3. 从skill界面的Parameters中指定增加的Text是否镜像、放置角度、放置字号、对齐方式
4. 如果需要增加的Text关联到此器件，则勾选Attach text to Symbol，这样Text和Symbol是关联的，就像封装的引脚标号一样会跟随器件一起移动，一起高亮
5. 点击下述按钮再从PCB界面选择对象，Text将跟随鼠标，通过点击放置到合适的位置
  - Netname：从PCB点击Pin脚，添加对应Pin脚的网络名称
  - Refdes：从PCB点击器件，添加对应器件的位号
  - Pin Number：从PCB点击Pin脚，添加对应Pin脚的引脚号
6. 依次点击多个对象，可以循环添加，使用Done命令或右键Done完成本次添加操作