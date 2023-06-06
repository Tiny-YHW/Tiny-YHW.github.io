---
title: 'Altium安装和启动自定义脚本（Scripting）'
date: Sat, 13 Jun 2020 02:06:44 +0000
draft: false
tags: ['Altium', '设计技巧']
---

参考链接：[https://techdocs.altium.com/display/SCRT/Running+Scripts+in+Altium+Designer](https://techdocs.altium.com/display/SCRT/Running+Scripts+in+Altium+Designer)

**原始方式**
--------

最原始方式：将脚本程序拖入Altium软件打开，通过运行脚本命令执行**DXP»Run Script**菜单，此方式仅适用于单次执行

**脚本安装**
--------

若某脚本需长期使用，可安装到Altium中，可免去每次将脚本程序拖入Altium软件打开的操作

*   新建一个脚本工程把脚本拖入工程
*   使用Altium菜单**DXP » Preferences**, **Scripting System | Global Projects**选择安装上面的功能
*   当完成上述脚本安装时，无论该脚本程序是否被打开，均可通过**DXP»Run Script**运行此脚本程序

**命令启动（快捷键、菜单）**
----------------

完成脚本安装后可以从**DXP » Customize**的\[Scripting\]的Command面板看到该脚本，点击对应程序则调出设置菜单，和其他命令一样，可以在这里为功能指定快捷键或拖到菜单里，这样更方便脚本的启动

更多可查看上述参考链接

[Altium Designer脚本资料](https://a1024.synology.me:1024/altium-designer%e8%84%9a%e6%9c%ac%e8%b5%84%e6%96%99/)