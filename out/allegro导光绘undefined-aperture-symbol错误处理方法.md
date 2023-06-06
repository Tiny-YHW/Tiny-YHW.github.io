---
title: 'Allegro导光绘Undefined aperture symbol错误处理方法'
date: Mon, 01 Jun 2020 06:13:25 +0000
draft: false
tags: ['Allegro', '设计技巧']
---

遇到好几次有人问这个问题，所以决定出个帖子说下这个问题的处理方法

首先说明这个问题是由于创建或编辑焊盘时写了软件识别不到的数据，如果创建焊盘规范是不会有这个问题的

我这个方法是自己用的土方法，能用行得通但用起来还是有点繁琐，如果你有更好的方法，欢迎评论区见，或者你也写一下你的处理方法。

报错内容如下，有个FLASH SYM未定义

![](http://wx3.sinaimg.cn/large/006wPhLtgy1fx0f474z1lj30mj0dg74r.jpg)

然后是找到这个FLASH SYM用到哪里了，这里利用报告查看

![](http://wx2.sinaimg.cn/large/006wPhLtgy1fx0f475073j30ew09pgm7.jpg)

找到这个定义到哪里了，然后确定是那个焊盘

![](http://wx4.sinaimg.cn/mw690/006wPhLtgy1fx0f475yprj30g60fl0t9.jpg)

然后到焊盘管理里面找到它准备编辑，或者你从库里找到这个焊盘修改焊盘文件后更新这个焊盘

![](http://wx3.sinaimg.cn/large/006wPhLtgy1fx0f475af5j30jy0di754.jpg)

编辑发现这个80写在这里是多余的因为写了80，这里是指向数据库的，所以他会在数据库里找80，然而并没有找到软件无法处理造成的报错，这里把80删掉包括其它各内层都一起改掉，可能都有相同的问题。

![](http://wx2.sinaimg.cn/mw690/006wPhLtgy1fx0f474oo1j30hi0fnt8u.jpg)

![](http://wx4.sinaimg.cn/mw690/006wPhLtgy1fx0f477pi8j30dk0f6dg8.jpg)

然后应该就可以了，不过也有可能还有其它焊盘也有这个问题，反观步骤1里面发现其实明显还有其它几个焊盘都有问题，因为软件遇到错误就停止了，所以只报出了一个未定义，这里可以在步骤3中把这几个焊盘一次性找出来，一并修改掉的，好了改完你就可以安心出数据了

![](http://wx1.sinaimg.cn/mw690/006wPhLtgy1fx0f4776mrj30cb03y0sj.jpg)