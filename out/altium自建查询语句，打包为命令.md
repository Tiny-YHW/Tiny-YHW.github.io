---
title: 'Altium自建查询语句，打包为命令'
date: Mon, 15 Jun 2020 03:33:01 +0000
draft: false
tags: ['Altium', '设计技巧']
---

![](https://www.altium.com/documentation/sites/default/files/resize/wiki_attachments/248076/Query_fromss-320x298.jpg)

Altium Designer的原理图和PCB编辑器的有强大的查询(Query)Filter。通过在Filter中输入查询，您可以在逻辑上精确确定所需的对象。查询是您使用特定关键字和语法输入的字符串，它将返回目标对象。

查询主要在_Filter_面板中定义，但也用于定义PCB设计规则的范围。建立查询语言知识以及可用的功能，关键字和语法后，您将可以直接键入表达式。

一开始，查询语言的广阔之处似乎有些艰巨，但是随着时间的流逝，您将学到它的强大功能-建立一组喜欢的查询表达式，以这些对象为通用对象集。为了快速起步，每个查询功能都提供了信息。突出显示（或单击内部）任何给定的关键字-在“ _查询帮助器”_，“ _过滤器”_面板或PCB设计规则的“ **查询”**字段中，然后按**F1**键访问其在文档中的页面。

个人整理的查询语句和一些其他内容见[Altium 常用语法笔记](https://a1024.synology.me:1024/altium-%e5%b8%b8%e7%94%a8%e8%af%ad%e6%b3%95%e7%ac%94%e8%ae%b0/)

[查询语言参考](https://www.altium.com/documentation/altium-designer/query-language-reference-ad)

本文主要介绍将个人常用的语法打包为命令，从菜单或快捷键直接启动

编辑语法
----

从_Filter_面板或使用Helper、Builder功能构建需要的语法

自定义命令
-----

选择菜单右击选择Customizing（或在菜单栏空白位置双击）打开Customizing Editor面板

![](https://www.altium.com/documentation/sites/default/files/wiki_attachments/296522/Customizing_PCB_Editor_AD18.png)

选择上图New按钮新建一个命令如下图，此处可以定义Altium软件可以执行的所有命令，此处只介绍RunQuery

![](http://a1024.synology.me:222/images/blog2022/Edit%20Command.png)

*   Process中输入PCB:RunQuery或从Browse中选择此项
*   Parameters中输入expr=语法|选项1|选项2|
    *   expr= 固定写法
    *   语法 在_Filter_面板中编辑好的语法
    *   | 固定写法用于分隔
    *   选项1、选项2 对语法执行的选项参数包括Apply=True|Source=Favorite|Index=n|Zoom=True|Select=True|dim=true等
    *   一个例子 expr=IsText And (OnLayer('Top Overlay') Or OnLayer('Bottom Overlay'))|dim=true|Zoom=true|Select = True|apply=True
*   Caotion中可以对自定义的命令起名和描述
*   Image可以指定该命令的图标
*   Shortcuts可以对此命令指定一个快捷键

快捷应用
----

### 快捷键

在上图中指定一个键盘按键

### 加入菜单

新建的命令将位于Customizing面板的Custom中，选择对应名称的命令，用鼠标按住并拖动到菜单栏，即可将命令加入菜单栏，然后通过菜单栏即可执行该指令

[Altium Designer脚本资料](https://a1024.synology.me:1024/altium-designer%e8%84%9a%e6%9c%ac%e8%b5%84%e6%96%99/)
----------------------------------------------------------------------------------------------------------