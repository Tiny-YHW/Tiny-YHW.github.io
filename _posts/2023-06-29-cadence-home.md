---
layout: post
title: Cadence（Allegro）的环境变量-Home
categories: Allegro
date: 2023-06-29
permalink: cadence-home
excerpt: Cadence Allegro在启动时会加载一些用户配置文件，基于这些配置文件来决定Allegro启动后的状态包含但不限于env、allegro.ilinit、.men、等，这些文件都将在软件启动时被执行一次以导入这些文件包含的命令。
---

以下所有内容为个人理解及测试得出，不保证正确，如有错误欢迎指出

## 基本逻辑

Cadence Allegro在启动时会加载一些用户配置文件，基于这些配置文件来决定Allegro启动后的状态包含但不限于env、allegro.ilinit、.men、等，这些文件都将在软件启动时被执行一次以导入这些文件包含的命令。

本文主要介绍环境变量-Home，此路径的相关文件优先级最高，如果不考虑版本差异建议所有用户自定义配置使用此路径的相关文件

PCB编辑器按以下顺序加载设置：均生效，但HOME优先级最高，因为它最后被加载会覆盖先前的设置。

*   $ cdsroot / share / pcb / text（系统级）
*   $ CDS\_SITE / pcb（网站级别）
*   $ HOME / pcbenv（用户级别）

## 环境变量路径配置

HOME存储所有用户特定的路径和环境信息。从**开始 – >设置 – >控制面板 – >系统 – >高级 – >环境变量，可以查看或编辑此路径**（也可以从我的电脑（此电脑）右键选择属性查找）

![](https://a1024.synology.me:222/images/blog2022/skill13.jpg)

查看或编辑变量名为Home的值，如果没有Home变量可以自己新建一个

![](http://a1024.synology.me:222/images/blog2022/skill14.jpg)

在文件浏览器输入%home%可直接打开此路径

环境变量文件说明
--------

$ HOME / pcbenv目录用来存储用户首选项和其他启动信息

在文件浏览器输入%home%\\pcbenv可直接打开此路径

**ENV：**本地环境文件，存储Allegro环境变量。此文件中的设置通常取代Cadence主文件和CDS\_SITE文件中提供的变量。使用enved工具管理变量设置。  
如果通过文本编辑器编辑env文件，则应始终将编辑内容添加到注释“### User Preferences”部分的行上方。此行下方的任何内容都保留给环境编辑器。  
切勿将Cadence主env文件复制到本地env文件。切换SPB版本时有可能导致兼容性问题。

**allegro.ini**：用于存储主窗口大小和位置，用户最后编辑的项目文件，控制面板停靠状态和大小，还用于存储默认绘图配置设置。此文件会默认实时更新，每次打开软件有相关设置被更改时，此文件都会更新储存。将文件设置为只读将阻止其更新。

**\<program name\>.geo**：存储辅助窗口位置和大小。辅助窗口是指表单（对话框）和文本窗口（示例“show element”，日志文件查看器和报告等）。该数据在程序退出时更新（同上）。可以通过调用对话框*View-> Customization-> Display*并选择“Restore windows positions”按钮来重置这些位置。将文件设置为只读可阻止其更新。

**\<program name\>.mru**：存储程序最近使用的文件列表。这将显示在程序的“file”菜单中。文件数由*recentFileList*环境变量控制。文件在程序退出时更新。将文件设置为只读将阻止其更新。

**allegro.strokes：**存储用户定义的手势。可以在Allegro中通过菜单*tool – >Utilities – >Stroke Edit*管理Allegro中的手势文件。

**allegro.ilinit**：用户在程序启动时加载的skill代码。顺序在在加载数据库或菜单之前，如果需要在数据库打开时执行操作，请通过axlTriggerSet API 注册回调触发器。

**license\_cache\_allegro\_16.6.txt**：每次开启并关闭Allegro都会被重置

**my\_favorites:**用户选项（User Preferences）中设置的喜爱（Favorites）