---
title: 'Sublime Text 安装 破解 汉化 配置skill'
date: Sat, 25 Apr 2020 07:14:54 +0000
draft: false
tags: ['Allegro Skill', '软件应用']
---

软件简介
----

Sublime Text具有漂亮的用户界面和强大的功能，例如代码缩略图，Python的插件，代码段等。还可自定义键绑定，菜单和工具栏。Sublime Text 的主要功能包括：拼写检查，书签，完整的 Python API ， Goto 功能，即时项目切换，多选择，多窗口等等。Sublime Text 是一个跨平台的编辑器，同时支持Windows、Linux、Mac OS X等操作系统。

关于本程序的更多介绍也可以参考H●Horven的博客 [传送门](https://blog.csdn.net/qq_40786521/article/details/106275273)

主要特色
----

*   语法高亮、代码提示补全、代码折叠、自定义皮肤/配色方案、多便签
*   代码地图、多种界面布局与全屏免打扰模式
*   完全开放的用户自定义配置与神奇实用的编辑状态恢复功能
*   强大的多行选择和多行编辑
*   雷电般快速的文件切换
*   随心所欲的跳转：快速罗列与定位函数/HTML的元素、跳转到指定行
*   集所有功能于一身的命令面板
*   Package Control（绝不可错过的扩展插件管理器）
*   多种多样的主题或配色方案

软件下载安装
------

软件下载：[官方传送门](http://www.sublimetext.com/3)，如果你无法访问官网，可使用下方百度网盘链接（不会及时更新最新版本）[提取码：dcam](https://pan.baidu.com/s/1TgZk1RcHxaFORJjfmJi31Q)

软件安装没啥好说的一路next

软件破解
----

1.  打开网站: [https://hexed.it](https://hexed.it/)
2.  点击“Open file”，然后选择“sublime\_text.exe” （ sublime\_text.exe文件位于Sublime Text 3的安装目录下 ）
3.  选择右侧的“Search”，然后在“Search for”框输入“97 94 0D”，点击“Search Now”
4.  下方出现一个搜索结果；这里为 0x0058F144
5.  点击搜索结果，修改搜索结果“97 94 0D”为“00 00 00”
6.  点击“Export”把修改好的exe程序下载并替换原来的sublime\_text.exe
7.  打开sublime text3，然后Help-Enter License-输入下方的license

```
----- BEGIN LICENSE -----
TwitterInc
200 User License
EA7E-890007
1D77F72E 390CDD93 4DCBA022 FAF60790
61AA12C0 A37081C5 D0316412 4584D136
94D7F7D4 95BC8C1C 527DA828 560BB037
D1EDDD8C AE7B379F 50C9D69D B35179EF
2FE898C4 8E4277A8 555CE714 E1FB0E43
D5D52613 C3D12E98 BC49967F 7652EED2
9D2D2E61 67610860 6D338B72 5CF95C69
E36B85CC 84991F19 7575D828 470A92AB
------ END LICENSE ------
```

![](http://a1024.synology.me:222/images/blog2022/Sublime%20Text1.jpg)

最后，为了防止sublime text3检测，添加以下内容到host文件中

```
127.0.0.1 www.sublimetext.com
127.0.0.1 sublimetext.com
127.0.0.1 sublimehq.com
127.0.0.1 telemetry.sublimehq.com
127.0.0.1 license.sublimehq.com
127.0.0.1 45.55.255.55
127.0.0.1 45.55.41.223
0.0.0.0 license.sublimehq.com
0.0.0.0 45.55.255.55
0.0.0.0 45.55.41.223
```

如何安装插件+汉化
---------

插件官方网站：[http://packagecontrol.cn/](http://packagecontrol.cn/)

可以根据官方网站安装，如

![](http://a1024.synology.me:222/images/blog2022/Sublime%20Text2.png)

也可ctrl+shift+p,快捷安装：按下Ctrl+Shift+P调出命令面板，输入install 调出 Install Package 选项并回车 等待片刻 ，然后在列表中选中要安装的插件。

汉化的话输入上述命令后等待片刻再次输出chinese后选择chineselocalizations等待一段时间，软件将自动切换为中文

![](https://a1024.synology.me:222/images/blog2022/Snipaste_2021-10-29_09-50-28.png)

![](https://a1024.synology.me:222/images/blog2022/Snipaste_2021-10-29_09-55-34.png)

![](http://a1024.synology.me:222/images/blog2022/Sublime%20Text4.png)

配置skill语言
---------

也可ctrl+shift+p,快捷安装：按下Ctrl+Shift+P调出命令面板，输入install 调出 Install Package 选项并回车等待片刻，然后在列表中搜索Cadence Skill选择对应的程序即可。

![](https://a1024.synology.me:222/images/blog2022/Snipaste_2021-10-29_10-02-28.png)

![](http://a1024.synology.me:222/images/blog2022/Sublime_skill.gif)

Cadence skill插件不建议用在线的，用附件的比较好。  
插件开源代码：[https://github.com/noisyass2/SublimeCadenceSkill](https://github.com/noisyass2/SublimeCadenceSkill)