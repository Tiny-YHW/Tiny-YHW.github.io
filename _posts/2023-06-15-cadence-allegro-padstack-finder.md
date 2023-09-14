---
layout: post
title: Allegro Padstack Finder 查找查看板中的过孔Via或焊盘Padstack
categories: Allegro
description: 
date: 2023-06-15
---

在早期版本的Allegro中，如果想在板中批量查看板中有哪些过孔或焊盘类型，分别在板中什么位置，操作不是很友好的需要通过report->modify design padstack或钻孔图表等工具查询，本文介绍一种新的查看板中的过孔via类型或焊盘padstack类型的方法Padstack Finder

Padstack Finder
---------------

### 功能介绍

Padstack Finder是一个Productivity Toolbox工具，再16.6某补丁及之后版本可用，并需要启用Productivity Toolbox选项，如果设置了默认打开方式则可以从File-Change Editor处更换

![](https://a1024.synology.me/images/blog/2022/toolbox.jpg)

Padstack Finder使用户可以搜索设计中的各个Padstack进行查看。 Padstack Finder包含以下功能

*   按Padstack名称搜索
*   按钻孔尺寸搜索
*   支持通配符
*   支持Pad和Via分别查看
*   高亮和对象和交互查看

![](https://a1024.synology.me/images/blog/2022/Padstack%20Finder.png)

### 使用方法

*   从菜单Tools->Padstack Finder启动或直接使用tbx findpadstack命令启动
*   从Filter中选择或设置过滤项，支持选择Pin或Via，名称过滤（支持通配符\*和？）
*   Drill size钻孔尺寸过滤设置好后Filter后将出现符合条件的对象
*   选取对象（安装Ctrl或Shift进行多选或加减选）
*   从Mode中选择高亮或仅输出报告使用Apply执行
*   通过报告中的列表，可以选取对象交互查看对象详情

### 注意事项

Via objects can be permanently highlighted only if they are part of a group (At the moment the Highlight and Assign color command in PCB Editor does not support vias). If you want to colorize your padstacks with different colors (e.g. micro vias -> red and through vias blue) you have to specify a different group name before. If you specify nothing Padstack Finder assigns the color always to a group named DEFAULT. Once you press the Clear button all existing groups and its color assignments will be removed.