---
title: 'Allegro 17.2 不能创建XNET'
date: Sun, 26 Apr 2020 06:22:49 +0000
draft: false
tags: ['Allegro']
---

解决方案：[官网论坛](https://community.cadence.com/cadence_technology_forums/f/pcb-design/38866/export-physical-error)

1.  Add the following to your <normally home folder>/PCBENV/ENV file:  set CDS\_XNET\_STATE\_UI=1
2.  Restart the tool and open Constraint Manager
3.  In Constraint Manager, select _Tools > Options_ and enable the option "Create XNets and Differential Pairs using DML Models (same as SPB16.6)"
4.  Save the design to a new name and try running the flow again.

1.  打开ENV，增加set CDS\_XNET\_STATE\_UI=1
2.  重新打开Allegro和规则管理其器
3.  从规则管理器 _Tools > Options_ 选择 "Create XNets and Differential Pairs using DML Models (same as SPB16.6)"选项
4.  另存为新的设计.

![](http://a1024.synology.me:222/images/blog2022/Snipaste_2020-04-26_14-12-04.png)

如果没能生效，建议打最新补丁S061补丁实测如上