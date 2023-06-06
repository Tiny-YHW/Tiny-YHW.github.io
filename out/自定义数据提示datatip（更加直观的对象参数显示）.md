---
title: '自定义数据提示datatip（更加直观的对象参数显示）'
date: Mon, 21 Dec 2020 02:30:45 +0000
draft: false
tags: ['Allegro', '设计技巧']
---

什么是datatip
----------

在Allegro中如果鼠标指向一个对象（Find面板过滤对象类别）时，对象会被高亮同时会跟随一个白框显示对象的相关参数，这个相关的参数即为datatip，在设计软件中可对其进行设置我们希望看到的对象内容，从而更高效的获取到我们希望看到的信息，提高设计效率。

从哪里进行设置
-------

**Menu Path Setup - Datatip Customization**

![](http://a1024.synology.me:222/images/blog2022/datatip1.jpg)

数据对应关系
------

![](http://a1024.synology.me:222/images/blog2022/datatip3.jpg)

从Object Type选择对象类型，在右侧设置当鼠标指向该类型对象时哪些信息会显示出来，Name对应是否显示信息参数名称如Pin、Net Name；Value对应是否显示信息参数的值如R1.1、GND，对话框下方会显示数据将会以何种形式展现出来，通过灵活设置这些对象的参数值，将会使你设计时事半功倍。

如何复用
----

### 存储位置

**默认的datatip配置文件custdatatips.cdt位于<installation\_directory> / share / pcb / text/**custdatatips.cdt**。如果你定义了环境变量，则它们位于pcbenv目录中的本地custdatatips.cdt中。**

### 导入导出

DataTips Customization Dialog Box  
可以通过File导出或导入设置参数，供再次使用

![](http://a1024.synology.me:222/images/blog2022/datatip2.jpg)