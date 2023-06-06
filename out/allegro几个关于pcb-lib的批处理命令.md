---
title: 'Allegro几个关于PCB lib的批处理命令'
date: Tue, 09 Mar 2021 03:19:30 +0000
draft: false
tags: ['Allegro', '设计技巧']
---

批处理命令就是直接在系统CMD（如果不知道什么是CMD自己去查，或者放弃阅读本文章）里执行，不要再问命令怎么执行

create\_sym
-----------

将dra（绘图文件）编译为 \*sm（symbol）文件，\*sm包括

*   psm = package pcb中元器件的焊盘图形，与原理图网表关联
*   bsm = Mechanical 机械元件，与原理图网表没有关联
*   osm = Format 图形元件，有时候logo适用，与原理图网表没有关联
*   ssm = Shape 异形形状 常应用于绘制异形焊盘时再.pad文件中调用
*   fsm = Flash 热风焊盘 插装器件焊盘负片连接实现十字连接增加热阻

windows

```
create_sym *.dra
```

skill

```
shell("create_sym E:\\lib\\TH5X2_2MM.dra")
(axlRunBatchDBProgram "create_sym" "create_sym E:\\lib\\TH5X2_2MM.dra")
```

create\_devices
---------------

对brd文件生成devices

```
create_devices <design_name>
```

dump\_libraries
---------------

从PCB设计文件（brd）中生成绘图文件（dra）或symbol（\*sm）文件，生成的文件放置当前目录中

```
dump_libraries [-a|-f|-m|-s|-c|-d|-p|-x] [-version]design_name.brd
```

*   \-a 只生成package dra对应
*   \-f 只生成Format 图形元件对应的dra
*   \-m 只生成Mechanical 机械元件对应的dra
*   \-s 只生成Shape 异形形状和Flash 热风焊盘对应的dra
*   \-c 生成dra的同时编译生成对应的\*.sm文件
*   \-d 生成dra的同时编译生成对应的\*.sm文件device文件
*   \-p 生成所有焊盘文件（pad）.
*   \-x Does not dump dependencies.
*   \-version 打印文件版本.
*   design\_name.brd 设计文件路径和名称.

qvupdate
--------

更新14.0之前的设计文件（brd、dra、pad、mdd）数据库中的footprint信息

```
qvupdate <database name>
qvupdate * <file extension>
```

\*仅代表支持通配符

uprev
-----

将设计数据库从其当前版本升级到该工具的最新版本。

```
uprev
input_file  Layout, drawing, or symbol file name (*.brd):
output_file layout, drawing, or symbol file name (*.brd):
```

*   input\_file The name of the database you want to uprev. The default is brd.
*   output\_file The name of the database after the uprev. Giving an output name that is different than the input name prevents the input database from being destroyed.
*   \-version Prints the version.

**[allegro\_downrev\_library](https://a1024.synology.me:1024/allegro-pcb%e9%99%8d%e7%89%88%e6%9c%ac/)**
-------------------------------------------------------------------------------------------------------