---
layout: post
title: Sublime Text
categories: Sublime
date: 2023-06-07
---

Sublime Text 3 的官方网站在[这里open in new window](https://www.sublimetext.com/)，找到适合自己的平台进行下载并安装。

### 安装

通过菜单安装 在Sublime Text编辑器顶部的`Tools`\->`Install Package Control...`，点击它安装Sublime Text的包管理工具，稍等片刻即可安装成功。
成功后返回如下的提示窗信息。

![](https://curder.github.io/blog/images/tools/sublime/sublime-text-3-install-success-alert.png)

### 卸载

使用快捷键`Command + Shift + p`，输入`Package Control: Remove Package`字符后点击回车完成卸载。

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