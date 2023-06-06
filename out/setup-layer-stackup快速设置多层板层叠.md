---
title: 'Setup->Layer Stackup快速设置多层板层叠'
date: Thu, 05 Jan 2023 06:19:43 +0000
draft: false
tags: ['TY-Skill']
---

功能说明
----

快速设置多层板常用层叠，多层板叠多层时套用模版直接生成多层板

![layerstackup.png](https://a1024.synology.me:222/images/blog2023/layerstackup.png)

使用说明
----

1.  使用菜单或者命令启动后弹出设置对话框。
2.  软件支持两种创建方式分别为按推荐模版创建和自创建
3.  推荐模版创建时通过选择预设的方案生成对应层叠
4.  自创建方案在输入框输入代码，按输入的代码生成对应层叠，代码分别包含t：TOP、g：GND、s：SIGNAL、p：VCC、b：BOTTOM代号中间用空格隔开，单击刷新更新层叠如：t g s s p b
5.  点击下方创建，程序将按设置生成对应层叠结构

![layerstackup2.png](https://a1024.synology.me:222/images/blog2023/layerstackup2.png)