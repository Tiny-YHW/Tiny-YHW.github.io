---
title: 'Text->Quick Change Text Size字号设置和调整'
date: Thu, 16 Feb 2023 06:45:23 +0000
draft: false
tags: ['TY-Skill']
---

功能说明
----

![](https://a1024.synology.me:222/images/blog2023/textset.png)

功能说明：几项针对与字号的大小调整和设置

1.  重置设置Text字号1-20号的各个参数，字号大小渐进
2.  将所有Pin\_number放置到其对应焊盘原点处，角度调整为0
3.  几个常用层Text的字号调整

操作说明
----

1.  使用菜单或者命令启动
2.  从多选框选择指定的功能项，勾选的项目将被执行，不勾选的不执行
3.  Ignore fixed用于设置使用忽略锁定属性，不勾选时将不对锁定对象进行调整
4.  点击？按钮可以查看对应功能的中文注解
5.  点击Run按钮，程序将按选定项目执行

功能详解
----

### 重置1-20字号

将1-20字号调整为下图（单位为mil的案例，其它单位也支持）

1.  1号小字一般用于指定给pin number使用
2.  2-3号字适中 一般用于给需要作出的丝印号使用
3.  4-16号字字体渐进增大
4.  17-20号字介意小和适中中间，需要使用小字体时可以使用，尤其适用于配合[Label Tune](https://a1024.synology.me:1024/?p=803)使用Fit Text将字号指定为1-20时特别好用

![textsetsize.png](https://a1024.synology.me:222/images/blog2023/textsetsize.png)

![labeltunetextfit.png](https://a1024.synology.me:222/images/blog2023/labeltunetextfit.png)

### Pin Number旋转和居中

设计Pin Number经常位置没有与Pin对齐且角度各异，影响视观，使用此功能可以一并解决这些问题

![textsetpinnumber.png](https://a1024.synology.me:222/images/blog2023/textsetpinnumber.png)

### 常用字丝印字号设置

参考中文注解