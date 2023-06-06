---
title: 'Altium NC Drill错误问题'
date: Thu, 14 May 2020 01:08:53 +0000
draft: false
tags: ['Altium', '设计技巧', '设计软件']
---

![](https://designhelp.fedevel.com/filedata/fetch?photoid=11610)

在Altium生成NC Drill时出现上述错误

Access violation at address 0000000183DE123F in module 'OUT\_Drill.dll'. Read of address 0000002400000000 at 0000000183DE123F

经测试发现下述现象

*   在Altium 10版本中NC Drill可以被输出，但有几个通孔器件的钻孔没有被输出
*   在Altium 20版本中NC Drill不能被生成，上上述图形错误

结论：没有生成钻孔的通过器件的Footprint中焊盘有问题，通过重新放置器件中的通孔焊盘，解决此问题

*   从属性面板看Footprint中焊盘没有任何问题
*   重新放置Footprint中焊盘时，框选原焊盘会跑出一个错误