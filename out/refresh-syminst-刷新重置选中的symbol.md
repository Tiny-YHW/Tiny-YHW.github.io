---
title: 'refresh syminst 刷新重置选中的symbol'
date: Fri, 17 Apr 2020 04:13:26 +0000
draft: false
tags: ['Allegro', '设计技巧']
---

The refresh syminst command lets you refresh the symbol instance that is already placed on the board. This command restores the data related to the symbol. For example, the silkscreen outline or text. You can access this command from the pop-up menu in the Placement Edit application mode.  
Note: This command however, does not refresh the symbol in the library.

refresh syminst命令使您可以刷新PCB中已经放置的symbol。 该命令将恢复与symbol有关的数据。 例如，丝印框或文本。 您可以从Placement Edit应用程序模式的右键菜单中访问此命令。  
注意：此命令不会刷新库中的symbol，仅对选中器件生效。

应用：设计检查时发现的元器件某元素误删，可使用此功能恢复

**不完全测试结果**

**Move对象**

*   Line属性所有对象将被重置
*   Shape属性所有对象将被重置
*   Pinnumber对象将被重置
*   除Pinnumber对象外所有Text将被不会被重置

**Del对象**

*   所有被删除的对象将被重置

**总结**

除Pinnumber对象外所有被移动或改变Text不会被重置，其它所有对象将被重置