---
layout: post
title: Allegro 输出两个brd文件网表差异报告（调管脚swap pin报告）
categories: Allegro
permalink: allegro-design-compare-net
date: 2024-01-12
---

公众号聊天发送“allegro-design-compare-net”或“240112”从公众号阅读此文，包含所有图文内容

本文章介绍不用输出文件直接比对两个brd文件即可生成网表差异报告的方法，非常适用于在发生调管脚swap pin后，生成网表比对文件供原理图设计方参照调整

使用此功能需要Allegro17.2及以上版本，且启用了Allegro Productivity Toolbox选项

![/](https://a1024.synology.me/images/blog/2024/compare2.png)

有网表差异的两个brd文件存放在任意位置

![/](https://a1024.synology.me/images/blog/2024/compare1.png)

使用Allegro打开其中一个brd文件，本案例使用newnetlist.brd

![/](https://a1024.synology.me/images/blog/2024/compare3.png)

点击菜单①Tools-②PCB Design Compare打开设计比较功能，如下图

功能默认使用当前操作的brd作为③First文档，从④Second文档处选择需要比对的brd文档，本案例使用oldnetlist.brd

点击⑤Start按钮，程序将生成design_compare.html报告文件，存放在当前brd同级目录，这个文件可以直接发给原理图设计方并告知网表差异如何查看（本文后面的内容）

![/](https://a1024.synology.me/images/blog/2024/compare4.png)

从上述章节点击⑤Start按钮后设计差异报告会被立即打开一次，如果过程中关掉了这个报告，也可以再次打开design_compare.html报告文件查看

![/](https://a1024.synology.me/images/blog/2024/compare5.png)

通过点击Netlist展开网表差异

* 展开Connection Details - Net based为基于网络的的差异报告，此报告内容为有差异的网络分别在比较的两个版本中所在的Pin点
* 展开Connection Details - Pin based为基于Pin点的差异报告，此报告包含有差异的Pin点在比较的两个版本中对应的网络分配

* 表头中的Design V1对应③First文档即本案例的newnetlist.brd的网表信息
* 表头中的Design V2对应④Second文档即本案例的oldnetlist.brd的网表信息

我已将design_compare.html报告的说明做了一个截图，可以将截图文件（保存下面图片）和报告文件一起发送给原理图设计方即可

![/](https://a1024.synology.me/images/blog/2024/compare.png)