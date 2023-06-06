---
title: 'Mentor安装和启动自定义脚本（Scripting）'
date: Thu, 31 Dec 2020 05:55:45 +0000
draft: false
tags: ['Mentor', '设计技巧']
---

Layout中
-------

以VX.2.2为例

### 手动加载运行

#### 菜单

*   选择文件 -> 编写脚本 -> 打开脚本列表（快捷键Ctrl+Alt+O）菜单
*   选择对应脚本
*   从脚本窗口选择Run（快捷键F5）

#### 拖入

除了上述从的菜单处加载执行，还可以直接将脚本文件拖入到打开的PCB中，直接执行此脚本文件

### 通过命令运行

直接输入命令run <脚本路径> 即可

### 配置到快捷键启动

按下述方法可以直接将脚本配置为自动加载，永久有效，原理就是设置一个快捷键代替上文的run命令

1、新建一个定义快捷键（文本）文件Hotkey.vbs编写快键键及对应命令

```
Set KeyBindTabers = Gui.Bindings("Document")
KeyBindTabers.AddKeyBinding "Ctrl+1","run <脚本路径>" ,1,1
```

2、打开Mentor安装路径下的脚本配置文件，路径为盘符\\Mentor……\\版本\\SSD\_HOME\\standard\\scripts.ini，在尾部增加代码，以实现快捷键文件的的自动加载，D:\\Mentorscr\\Hotkey.vbs替换为你对应脚本文件的路径

```
[Expedition PCB]
script#0= D:\Mentorscr\Hotkey.vbs
```