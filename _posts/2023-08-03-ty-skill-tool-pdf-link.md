---
layout: post
title: TY-Skill Tool->PDF Link Allegro与PDF格式原理图交互
categories: TY-Skill
date: 2023-08-03
permalink: ty-skill-tool-pdf-link
excerpt: 
---

![](https://a1024.synology.me/images/blog/2023/PDFlink.jpg)

Dome演示如下
--------

动图为早期版本录制，仅为方便查看保留，新版功能演示见后文视频

![](https://a1024.synology.me/images/blog/2022/PDF_link.gif)

2021年10月份发布过本功能，截止目前已不在可用，本次做升级发布优化一些功能项，并将有效时间改到2023年年底

**本次功能升级如下**
------------

*   增加选择net的选项
*   支持选择是否启用阴影模式
*   支持选择是否启用自动缩放选项。
*   修改UI增加对上述功能的支持

**功能演示视频**
----------

<iframe width="720" height="405" frameborder="0" src="https://www.ixigua.com/iframe/7184736280834474499?autoplay=0" referrerpolicy="unsafe-url" allowfullscreen></iframe>

使用说明
----

1.  获取附件解压文件获得PDF\_link\_pro.cxt（16.X对应的skill文件）、paste.exe（获取剪切板文本程序）64bit文件夹（17.X对应的skill文件）
2.  将上述文件放在“环境变量\\pcbenv\\”根目录位置(可以直接在资源管理器地址栏输入”%home%\\pcbenv\\”跳转)
3.  打开“环境变量\\pcbenv\\allegro.ilinit”文件，新起两行写入如下两行内容（可以从提供的allegro.ilinit文件选择复制）
4.  loadContext("PDF\_link\_pro.cxt")
5.  axlCmdRegister("pdflink" 'PDF\_LinkFormpro ?cmdType "interactive")
6.  重新打开Allegro软件输入命令“pdflink”启用此功能，启动命令可以从上面3中对应的文本"pdflink"修改为你喜欢的命令名

**注意事项**
--------

本功能应用需要从PDF中提取文本，这部分功能由你的PDF浏览软件完成，如果你电脑上的PDF软件对文本提取复制不友好或者根本不支持，那么自然本程序也无能为力，本文推荐使用PDF-XChange Editor软件（软件自己找不到的话可以联系我获取）

不公布源码且设置有效期至2023年底（每年续订），介意者请不要使用此程序

程序购买（[微信公众号内付费](https://mp.weixin.qq.com/s?__biz=MzI2NDQxMjg4NA==&mid=2247484489&idx=1&sn=188b868958a00c8d8bdfce6b5b15aa65&chksm=eaac4ff2dddbc6e48ac83f51abf4e9b6adf1862371106df65a0be9ffdef224a18c4f0f6f2754&mpshare=1&scene=1&srcid=0105QnYGVxcDfHsTPqYwKdc8&sharer_sharetime=1672880960354&sharer_shareid=8871ab4cf08cc6a220f3a092588c518c#rd)，或者你能从其它地方联系到我向我索取）

HDL原理图输出的PDF不能交互的解决方案
---------------------

Cadence HDL格式原理图默认输出的PDF格式原理图中包含很多标签（超链接？属性？不知道叫什么）不能从PDF中框选对应器件位号，鼠标一点击就弹出元器件属性，基于这种情况提供两种解决方案

### 重新输出

从HDL格式原理图重新输出到PDF，输出时有选项把那些附加的选项的勾全部去掉，这样输出的PDF可以通过框选复制文本

### 打印PDF

打开输出的PDF打印（Ctrl+P）,打印机选Adobe PDF（需预装他家的软件，一般电脑都默认有装如果没有装一下或者看看你那有啥可用的），会让你另存一个PDF文件，这样另存的这个PDF文件是不带哪些不受欢迎的标签（超链接？属性？不知道叫什么）的，可以通过框选复制文本