---
title: 'Allegro DRC Browser DRC浏览器'
date: Tue, 18 Oct 2022 09:10:56 +0000
draft: false
tags: ['Allegro']
---

[视频地址](https://www.ixigua.com/7160935170185527815)

17.2-2016 QIR 4 (Hotfix25)起开始支持该功能

DRC Browser可增强定位、审查和解决 DRC 的能力。浏览器包含导航、排序和过滤功能，可以更轻松地通过 DRC 违规类型和范围解决设计问题。

DRC Browser包括如下几个功能

*   按窗口查看DRC
*   对DRC标记三种状态（已读、未读、审核）
*   多种导航方式
*   给选择的DRC增加waive属性
*   多种过滤和排序方式
*   图形化展示DRC图标的相关信息

DRC 浏览器导航
---------

从菜单Tools –> DRC Browser打开DRC浏览器

DRC 浏览器显示所有 DRC，包括外部 DRC 。在此浏览器中，您可以通过多种方式浏览 DRC。

![](https://a1024.synology.me:222/images/blog2022/DRC%20browser1.png)

*   DRC类目树：在表单的 DRC 树窗口中，您可以展开和折叠 DRC 域的节点和分支，直至 DRC 位置列表。列表的每个节点显示存在的 DRC 数量。
*   导航路径：在导航路径中选择一个项目可帮助您快速导航到当前 DRC 域中的相对位置。导航箭头也可用于前进和后退，使用方法类似与Windows的文件管理器。
*   DRC清单 - 从列表中选择条目向下导航到下一级或约束规则向下导航到 DRC 位置列表。

![](https://a1024.synology.me:222/images/blog2022/DRC%20browser2.png)

进入详细的DRC条目见上图

点击左下按钮Show DRC Chart可以以图标的形式展现DRC信息，个人感觉没什么用，不做介绍了

DRC 浏览器过滤
---------

在查看 DRC 时，DRC 浏览器提供各种过滤和排序功能。

在 DRC 清单中，当前列表可以通过单击鼠标选择列标题从低值到高值排序或反向排序。

过滤选项包括：

*   使用All、Unread或Review单选按钮列出项目状态
*   按文本过滤
*   按数值过滤

![](https://a1024.synology.me:222/images/blog2022/DRC%20browser3.png)

DRC 浏览器功能
---------

当定位到每一个DRC项目时，可以对其分配不同的状态对其进行标记用于让用户更有效的处理各种DRC情况，这些不同的标记将会以不同的颜色或字体状态被显示出来，从而节省手动查找问题的时间。更正问题后，DRC 列表会动态更新，从列表中删除 DRC。

![](https://a1024.synology.me:222/images/blog2022/algPN-158.gif)

具体每种操作详见视频

DRC浏览器选项
--------

从DRC浏览器左下方option按钮处可以打开关于此功能的一些设置，见下图

![](https://a1024.synology.me:222/images/blog2022/DRC%20browser4.png)