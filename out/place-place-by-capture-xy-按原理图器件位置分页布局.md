---
title: 'Place->Place By Capture XY 按原理图器件位置分页布局'
date: Fri, 13 Jan 2023 06:55:18 +0000
draft: false
tags: ['TY-Skill']
---

功能说明
----

按原理图中元器件的相对位置分页布局PCB

布局初始化时使用，如果板中有已经布好的器件则不建议使用，或者尝试锁定已布好的器件后再使用，否则程序将重新打乱已经布局的部分，针对此种情况建议使用[Smart Place Tool](https://a1024.synology.me:1024/?p=3716)中的同类功能

操作说明
----

按下图步骤从原理图输出EXP文件，建议放置到brd同级路径方便调用

![](https://a1024.synology.me:222/images/blog2023/expexp.png)

使用菜单或命令启动功能

点击打开文件，选择输出的EXP文件

设置间距倍数，点击运行程序自动完成分页按原理图器件位置放置

![](https://a1024.synology.me:222/images/blog2023/placecapture.png)