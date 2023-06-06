---
title: 'Text->Manage Text多功能Text管理工具'
date: Thu, 16 Feb 2023 08:34:19 +0000
draft: false
tags: ['TY-Skill']
---

功能说明
----

1.  Rotate标签页：旋转和居中文本，有其它更好用的重复功能（此处不再做介绍）
2.  DRC标签页：丝印DRC检查类似后续Silk Checks（不做介绍）
3.  Edit标签页：Package symbol的引脚编号自动化
4.  Save/Restore标签页：保存和恢复恢复文本字体设置，字号批量编辑（作用较小不做介绍）
5.  Edit标签页：两个设计Text的位置比较和更新，可用于协作时导入协作者的丝印调整
6.  Add标签页：增加网络名（引脚号）丝印，并关联到该symbol
7.  Find标签页：文本搜索查找分类查看功能（作用较小不做介绍）
8.  Add标签页：文本转换为Shape或Line格式（作用较小不做介绍）
9.  更多功能请自行探索

Package symbol的引脚编号自动化
----------------------

![textpinnumber.png](https://a1024.synology.me:222/images/blog2023/textpinnumber.png)

Package symbol创建、修改或优化时引脚号按顺序编码和调整功能

1.  选择Edit标签页，从下方选择Pin number change设置编号前缀、后缀、起始值、步进值。
2.  单击Re-number pins(select)
3.  从Package symbol编辑界面依次点击对应Pin脚的Pin number，Pin number将被重置
4.  从Center pin numbers设置Pin number角度
5.  单击Center pin nums
6.  从Package symbol编辑界面框选Pin number，Pin number将被放置到焊盘中心

两个设计Text的位置比较和更新
----------------

![textcompair.png](https://a1024.synology.me:222/images/blog2023/textcompair.png)

从另一个设计导入装配层和丝印层上与元器件相关的文本位置、大小和角度适用于协同设计时丝印文字的导入

1.  选择Edit标签页，从下方选择Import symbol/text locations。
2.  从Template(.brd)处选择要比对或导入的设计
3.  单击Check程序自动执行，并在下面生成报告列表
4.  对报告进行选择性查看
5.  选择或全选需要更新的Text
6.  点击Update selected文本调整为与被选比对对象一致的位置大小和方向（增加或删除的Text不支持）

增加网络名（引脚号）丝印，并关联到该symbol
------------------------

设计中需要为某元器件的引脚以网络名（引脚号）为名称增加标识时使用，Package symbol创建、修改或优化需要标识引脚号时也非常适用

![daltextadd.png](https://a1024.synology.me:222/images/blog2023/daltextadd.png)

1.  选择Add标签页，从下方Param处设置字体。
2.  将要添加丝印的层设置为活动层
3.  选择Net name后从PCB设计中选择对应的Pad，出现网络名Text直接放置或右击选择旋转后放置到合适位置
4.  选择Net name后效果和3）类似，适用与PCB设置中，同样适用与Package symbol创建、修改或优化需要标识引脚号的情况
5.  选择Change标签页，从下方选择Attach text to symbol
6.  从PCB设计中选择Text然后选择Symbol，程序将为Text和Symbol创建关联（移动Symbol时Text将被一起移动）
7.  选择Detach text from symbol再进行同样的操作，可取消此关联

![attachtexttosymbol.png](https://a1024.synology.me:222/images/blog2023/attachtexttosymbol.png)