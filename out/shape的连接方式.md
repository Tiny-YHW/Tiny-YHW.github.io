---
title: 'Shape的连接方式'
date: Thu, 21 May 2020 09:16:25 +0000
draft: false
tags: ['Allegro', '设计经验', '设计软件']
---

Shape的连接方式需同时考虑焊接效果和载流量

**焊接方面**

当铜皮连接面积较大，且铜皮面积较大时，焊接时容易使焊锡膏散热过快导致虚焊或元器件立碑

**载流方面**

铜皮的与对应焊盘连接的各处瓶颈值应满足载流要求，否则自己想象

基于上述情况可能对Shape采取不同的连接方式使其同事满足载流和焊接要求

应用场景
----

电源电路电感smd焊盘全连接保证电流，电容仅作滤波电流要求不高优先保证焊接则需要再同一个shape同为smd pin需要不同的连接方式

![](http://a1024.synology.me:222/images/blog2022/allegroshape1.jpg)

整板铺铜机械孔优先保证连接散热，其他类插装pin优先保证焊接十字连接，跟上面类似

![](http://a1024.synology.me:222/images/blog2022/allegroshape2.jpg)

上述两种方案解决方案一致，allegro在做shape和其他元素连接时可以通过两种方式

shape属性面板
---------

在shape—Global Dynamic Params或选择shape右键parameters 弹出下面窗口建议设置

![](http://a1024.synology.me:222/images/blog2022/allegroshape3.jpg)

选项卡更多介绍见后文

连接接对象属性值
--------

 在edit—Propreties如果选择多个配合Temp Group使用，然后find面板只勾选需要设置的元素一般为pin，再在设计中点击需要单独设置连接的元素，弹出窗口并设置如下

![](http://a1024.synology.me:222/images/blog2022/allegroshape4.jpg)

亦可在Idle（done后）情况下，先通过Shift或Ctrl多选pin，再执行命令，有效减少操作

优先级
---

Eidt Propreties>Shape Propreties>Global Shape Propreties

Shape Parameters 选项卡介绍
----------------------

### Shape Fill Tab 铜皮填充样式

![](https://ww4.sinaimg.cn/mw690/006wPhLtgw1facpda34rdj30bu0bv40e.jpg)

Xhatch style的几种方式如下图  
![](https://ww4.sinaimg.cn/mw690/006wPhLtgw1facpd9p4hyg309s07kjr7.gif)

### Void Controls Tab

![](http://ww2.sinaimg.cn/mw690/006wPhLtgw1facpdas7n6j30bu0bvgog.jpg)

![](http://ww2.sinaimg.cn/mw690/006wPhLtgw1facpd82altj30ir07xwid.jpg)

![](http://ww3.sinaimg.cn/mw690/006wPhLtgw1facpd8h9rgj30dl0c5djr.jpg)

### Clearances Tab

![](http://ww3.sinaimg.cn/mw690/006wPhLtgw1facpdb9zlbj30bu0bvgmm.jpg)  

*   各元素避让间距设置
*   DRC：以规则设置为基础
*   Thermal/Anti：以定义的Thermal/Anti为基础，但当前述值小于DRC值时仍以DRC为基础，即取三者最大值为基础
*   Oversize Value：超出基础数生效，当为0时代表不超出

### Thermal Relief Connects Tab

![](http://ww2.sinaimg.cn/mw690/006wPhLtgw1facpdbm1ekj30bu0bvjt6.jpg)

*   pin/via连接方式
*   Orthogonal：十字   Diagonal：X字
*   8-Way：米字   Full Contact:：全连接
*   Best contact：当实际正常连接不能满足最小连接数要求时,改变规则，以15度为增量，设置连接线，以满足最小连接数要求