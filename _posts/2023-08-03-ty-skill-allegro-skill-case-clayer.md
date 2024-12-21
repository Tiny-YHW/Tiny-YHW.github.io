---
layout: post
title: TY-Skill Display->Key Layer Visibility 使用键盘按键切换常用设计视图
categories: Allegro Skill
date: 2024-12-21
permalink: allegro-skill-case-clayer
excerpt: 设计时使用键盘按键切换常用设计视图
---

## 功能说明

设计时使用键盘按键切换常用设计视图

## 使用方法

保持鼠标在PCB绘图窗口或command窗口，输入对应层命令按回车键确认即可

默认输入命令及对应层如下，可自行更改命令

切换信号层后面增加+ 代表同时打开其相邻参考层

*   如下例20位输入命令，所切换的层别为底层布线
*   axlCmdRegister( "2111" 'alllayeron);开所有层
*   axlCmdRegister( "2000" 'alllayeroff);关所有层
*   axlCmdRegister( "20" 'BOTTOM);底层布线
*   axlCmdRegister( "21" 'TOP);顶层布线
*   axlCmdRegister( "210" 'place);顶底层同时布线
*   axlCmdRegister( "22" 'L2);第2层布线
*   ……;省略3-9层
*   axlCmdRegister( "2.0" 'L10);第10层布线
*   axlCmdRegister( "2.1" 'L11));第11层布线
*   ……;省略12-19层
*   axlCmdRegister( "2..0" 'L20));第20层布线
*   axlCmdRegister( "2..1" 'L21));第11层布线
*   ……;省略22-29层
*   axlCmdRegister( "200" 'bottomm);底层布局
*   axlCmdRegister( "211" 'topp);顶层布局
*   axlCmdRegister( "2100" 'placee);顶底层同开布局
*   axlCmdRegister( "st" 'skt) ;顶层丝印
*   axlCmdRegister( "sb" 'skb) ;底层丝印
*   axlCmdRegister( "stb" 'sktb);顶底层同开丝印
*   axlCmdRegister( "art" 'allart);所有光绘相关层叠
*   axlCmdRegister( "20+" 'BOTTOMadd);底层布线
*   axlCmdRegister( "21+" 'TOPadd);顶层布线
*   axlCmdRegister( "22+" 'L2add);第2层布线
*   ……;省略3-9层
*   axlCmdRegister( "2.0+" 'L10add);第10层布线
*   axlCmdRegister( "2.1+" 'L11add);第11层布线
*   ……;省略12-19层
*   axlCmdRegister( "2..0+" 'L20));第20层布线
*   axlCmdRegister( "2..1+" 'L21));第11层布线
*   ……;省略22-29层

功能演示
----

抖音：[https://v.douyin.com/LgYCrFc](https://v.douyin.com/LgYCrFc)

辅助标识层使用说明
----

考虑常见有设计有类似晶振或功率电感所在区域禁止布信号线(可以布设电源或地或不重要信号)的情况

对于此类情况若对指定区域设置常规keepout会产生DRC,若不添加任何标记则很可能在布线时忽略了这部分区域存在的限制导致设计返工甚至出问题

本文引入一种设计方法，添加几个辅助层用来标识这个情况，以警示对这些区域的限制

下文描述的这些层将在使用本程序功能切换层叠时一同被显示出来

辅助层分为TOP、BOTTOM和所有层

![](https://tiny-yhw.github.io//images/TY-skill/Y_clayer_mark.png)


使用层的最佳应用为在设计中新建自定义层(更加推荐将这个自定义层放到你的默认brd模版中)

* TOP:BOARD GEOMETRY/ROOM_TOP
* BOTTOM:BOARD GEOMETRY/ROOM_BOTTOM
* ALL:BOARD GEOMETRY/ROOM_ALL

若设计中没有上述对应的层叠则程度默认使用下述设计中自带的层叠

* TOP:BOARD GEOMETRY/TOP_ROOM
* BOTTOM:BOARD GEOMETRY/BOTTOM_ROOM
* ALL:BOARD GEOMETRY/BOTH_ROOMS

更加建议对这些层自行定义一个个人习惯的颜色

本文提及的晶振或者功率电感只是作为一个例子，其它所有需要标识但不能同时作为禁布层的情况均可以使用此思路来解，自行举一反三


更新说明
----
### 20241221更新V6.0

* 新增20-29层快捷命令：2..0代表第20层 - 2..9代表第29层
* paste层快捷命令：PA、PB
* 2100和2100+命令不再开BOARD GEOMETRY/Dimension层
* 辅助标识层的应用

### 20230725更新V5.0

*   增加开所有层和关所有层快捷键功能

### 20220120更新V4.0

*   增加同时打开指定层及其相邻参考层的功能
*   切换信号层增加对应层的对应的BOUNDARY层（Shape边框）

### 20200820更新V3.0

*   新增为布局布线层增加Plan/layer层，方便查看规划视图
*   简化代码

### 20160509更新到V2.0

*   增加功能呢切换到对应布线层同时设置当前活动层为对应层
*   eg：按23回车，层显示为L3层相关内容同时设置活动层为L3