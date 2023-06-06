---
title: 'Add->AntiEtch By Outline/RKI分层创建沿板框的Antitch'
date: Fri, 23 Dec 2022 05:32:48 +0000
draft: false
tags: ['TY-Skill']
---

功能说明
----

根据shape形状（一般为板框或Route Keepin）分层创建AntiEtch

设计中平面层内缩或电源层相对地层做20H时好用

沿板框做板边铜皮或开窗时好用

![AntiEtchRKI1.png](https://a1024.synology.me:222/images/blog2023/AntiEtchRKI1.png)

操作说明
----

1.  保证板框为Shape或闭合的Line
2.  使用菜单或者命令启动后从Find面板选择操作对象（Line & Shape），从Option面板配置功能选项。
3.  从选项中选择需要创建的AntiEtch所在层，内缩&外扩，内缩&外扩宽度。
4.  选择板框对象，程序将按设置生成AntiEtch，针对板框层分别对电源层和地层设置不同的内缩值以实现20H的设计

![AntiEtchRKI2.png](https://a1024.synology.me:222/images/blog2023/AntiEtchRKI2.png)