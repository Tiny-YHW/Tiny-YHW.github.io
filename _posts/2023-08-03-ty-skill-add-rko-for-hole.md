---
layout: post
title: TY-Skill Add->RKO For Hole 为通孔pin增加禁布
categories: TY-Skill
date: 2023-08-22
permalink: ty-skill-add-rko-for-hole
excerpt: 为通孔pin增加禁布
---

## 功能说明

筛选指定类型的通孔pin，对其添加指定尺寸的禁布层

![Snipaste_2023-08-03_11-00-247d53e277736c2ca4.png](https://tiny-yhw.github.io//images/TY-skill/Snipaste_2023-08-03_11-00-247d53e277736c2ca4.png)

## 功能视频演示

<iframe width="720" height="405" frameborder="0" src="https://www.ixigua.com/iframe/7265989625267782207?autoplay=0" referrerpolicy="unsafe-url" allowfullscreen></iframe>

[抖音视频链接](https://v.douyin.com/iJsbr8oN/){:target="_blank"}

6.64 JIv:/ Allegro Skill RKO For Hole 为通孔pin增加禁布#   https://v.douyin.com/iJsbr8oN/ 复制此链接，打开Dou音搜索，直接观看视频！

## 操作说明

本功能仅支持对圆形孔尺寸的通孔pin增加禁布

* 筛选指定类型的通孔Pin，从Plating分组中选择需要筛选的金属化通孔pin类型
	- Only Unplating：仅筛选非金属化属性的通孔pin
	- All Plating：所有通孔pin
* 筛选通孔pin的识别方式，从Filter分组中选择通孔pin的识别方式，通孔将按指定的识别方式罗列到左侧列表区域
	- Drill dia：按孔径分类所有通孔pin
	- Pad name：按焊盘名称分类所有通孔pin
* 选择交互模式，从Cross select mode中选择交互模式后，当从列表区域选择指定类型通孔pin时PCB画布的显示模式略有差异
	- Zoom：视图将自适应大小到选择的焊盘，当选择的焊盘比较多时此功能将自动失效（软件程序限制）
	- Shadow：切换为阴影模式，突出显示选择的对象
* 从列表区域选择需要增加Routekeepout的对象（可以通过按住Ctrl或Shift键进行多选），可以通过列表下方的Select All按钮全选列表中所有对象
* 选择Routekeepout的尺寸计算方式，从RKO expansion by holesize分组中选择计算方式
	- Expand offset(+):禁布圆形直径尺寸按通孔Pin直径加指定值添加，如20代表禁布尺寸按通孔直径（不是焊盘）+ 20（即单边10）作为禁布直径
	- Expand times(x):禁布圆形直径尺寸按通孔Pin直径的倍数添加，如2代表禁布尺寸按通孔直径（不是焊盘）\* 2 作为禁布直径为孔径的2倍
* 点击Run按钮程序将对从列表区域选择的通孔pin按设定的尺寸计算方式批量添加禁布，禁布层为“ROUTE KEEPOUT\\All"
* Del Hole RKO 按钮可以删除所有使用本程序添加的禁布，非本程序添加的进步不会被删除，被锁定的禁布不会被删除
	

