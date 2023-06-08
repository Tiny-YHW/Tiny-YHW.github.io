---
layout: post
title: Sublime Text
categories: Sublime
date: 2023-06-07
---

Sublime Text 3 的官方网站在[这里open in new window](https://www.sublimetext.com/)，找到适合自己的平台进行下载并安装。如如果你无法访问官网，可使用下方百度网盘链接（不会及时更新最新版本）[提取码：dcam](https://pan.baidu.com/s/1TgZk1RcHxaFORJjfmJi31Q)

软件安装没啥好说的一路next

Sublime Text具有漂亮的用户界面和强大的功能，例如代码缩略图，Python的插件，代码段等。还可自定义键绑定，菜单和工具栏。Sublime Text 的主要功能包括：拼写检查，书签，完整的 Python API ， Goto 功能，即时项目切换，多选择，多窗口等等。Sublime Text 是一个跨平台的编辑器，同时支持Windows、Linux、Mac OS X等操作系统。

## 主要特色
*   语法高亮、代码提示补全、代码折叠、自定义皮肤/配色方案、多便签
*   代码地图、多种界面布局与全屏免打扰模式
*   完全开放的用户自定义配置与神奇实用的编辑状态恢复功能
*   强大的多行选择和多行编辑
*   雷电般快速的文件切换
*   随心所欲的跳转：快速罗列与定位函数/HTML的元素、跳转到指定行
*   集所有功能于一身的命令面板
*   Package Control（绝不可错过的扩展插件管理器）
*   多种多样的主题或配色方案

## 软件破解

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




### 安装插件

通过菜单安装 在Sublime Text编辑器顶部的`Tools`\->`Install Package Control...`，点击它安装Sublime Text的包管理工具，稍等片刻即可安装成功。
成功后返回如下的提示窗信息。

插件官方网站：[http://packagecontrol.cn/](http://packagecontrol.cn/)

![](http://a1024.synology.me:222/images/blog2022/Sublime%20Text2.png)

### 使用
--------------------------------------

通过 `Package Control` 能很方便安装其它插件。

### [#](about:blank#%E5%AE%89%E8%A3%85%E6%8F%92%E4%BB%B6) 安装插件

这里以`Emmet`插件的安装为例，一般插件的安装都可以通过这种方式。

使用快捷键`Command + Shift + p`，输入`Install Package`字符后再输入要安装的插件名称`Emmet`回车等待安装完成。

### [#](about:blank#%E5%8D%B8%E8%BD%BD%E6%8F%92%E4%BB%B6) 卸载插件

使用快捷键`Command + Shift + p`，输入`Remove Package`字符后再输入要安装的插件名称`Emmet`回车等待安装完成。

### [#](about:blank#%E7%A6%81%E7%94%A8%E6%8F%92%E4%BB%B6) 禁用插件

使用快捷键`Command + Shift + p`，输入`Disable Package`字符后再输入要安装的插件名称禁用插件。（其实就是在个人配置中的`ignored_packages`中添加插件名称。）

> 使用这个命令可以禁用系统默认安装的插件。

### [#](about:blank#%E5%90%AF%E7%94%A8%E6%8F%92%E4%BB%B6) 启用插件

使用快捷键`Command + Shift + p`，输入`Enable Package`字符后再输入要安装的插件名称禁用插件。（其实就是在个人配置中的`ignored_packages`中移除插件名称。）

### [#](about:blank#%E6%8F%92%E4%BB%B6%E5%88%97%E8%A1%A8) 插件列表

使用快捷键`Command + Shift + p`，输入`List Package`字符后查看当前环境已经安装的插件。

[#](about:blank#%E5%91%BD%E4%BB%A4%E5%85%B3%E9%94%AE%E5%AD%97) 命令关键字
--------------------------------------------------------------------

*   `Install Package` 升级插件
*   `Remove Package` 移除插件
*   `Disable Package` 禁用插件
*   `Enable Package` 启用插件
*   `List Package` 插件列表


## 手工安装插件

手工安装的方式需要进入网站 packagecontrol.io

在Search处输入想要安装的插件的名称，比如emmet

这里就需要大家注意了，详细界面里面一般都会写明该插件的安装方法，使用方法。不过都是英文的，所以需要大家具备一定的英文阅读能力。不过对于手工安装来说，无外乎于就是下载该插件到本地，然后放入特定的文件夹中。

下载到本地后，现在开始手工安装，安装的过程很简单，就是复制粘贴一下文件。
1. 在Sublime菜单栏中点击 Preferences > Browse Packages
2. 将下载的文件解压到该目录。

## 如何安装插件+汉化
按下Ctrl+Shift+P调出命令面板，输入install 调出 Install Package 选项并回车 等待片刻 ，然后在列表中选中要安装的插件。

汉化的话输入上述命令后等待片刻再次输出chinese后选择chineselocalizations等待一段时间，软件将自动切换为中文

![](https://a1024.synology.me:222/images/blog2022/Snipaste_2021-10-29_09-50-28.png)

![](https://a1024.synology.me:222/images/blog2022/Snipaste_2021-10-29_09-55-34.png)

![](http://a1024.synology.me:222/images/blog2022/Sublime%20Text4.png)

### 配置skill语言

也可ctrl+shift+p,快捷安装：按下Ctrl+Shift+P调出命令面板，输入install 调出 Install Package 选项并回车等待片刻，然后在列表中搜索Cadence Skill选择对应的程序即可。

![](https://a1024.synology.me:222/images/blog2022/Snipaste_2021-10-29_10-02-28.png)

![](http://a1024.synology.me:222/images/blog2022/Sublime_skill.gif)

Cadence skill插件不建议用在线的，用附件的比较好。  
插件开源代码：[https://github.com/noisyass2/SublimeCadenceSkill](https://github.com/noisyass2/SublimeCadenceSkill)