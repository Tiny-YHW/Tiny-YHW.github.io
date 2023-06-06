---
title: 'Allegro 出光绘报错 Undefined aperture symbol解决方案'
date: Fri, 14 May 2021 02:36:22 +0000
draft: false
tags: ['Allegro']
---

错误情况
----

本文提供当出光绘数据时报类似如下错误的解决方案

```
ERROR: aborting film - Undefined aperture symbol, cannot continue.
See APERTURES USED table in this file for symbols to provide.
Error in L2\_GND--halting output.  Artwork file not generated.
\*\*\* ERROR with L2\_GND 
```

![](http://a1024.synology.me:222/images/blog2022/APERTURES%20USED.png)

错误定位
----

报错信息定位到某个对象使用了一个未定义的aperture symbol，让查看APERTURES USED table查看，通过查看看这个表可以看到信息出错关键为FLASH SYM 67 270.000 NO CLEAR (undefined)，基于此信息继续查找

找到错误焊盘
------

从Tool -> Quike Reports -> Padstack Definition Report 从里面通过Ctrl+F查找可能出错的pad（看Flash Name列和Shape Name列），由下图可知出错的pad名称为S150H100M160

![](http://a1024.synology.me:222/images/blog2022/Padstack%20Definition%20Report1%20.png)

从Tool -> Padstack Finder（需Allegro16.6打补丁及之后的版本，并在启动产品中选取了Allegro（OrCAD） Productivty Toolbox才有这个功能） 找到这个焊盘

![](http://a1024.synology.me:222/images/blog2022/padfinder1.png)

修正错误
----

从Tool -> Padstack -> Modify Design Padstack 或 Modify Library Padstack选到这个pad查看其对应的值，发现错误点，如下如显示为Anti Pad使用了一个名为67的Flash，但这个67并未定义导致的错误，将其删掉，同理别处有类似的错误也会出现问题如下图的59

![](http://a1024.synology.me:222/images/blog2022/paderror1.png)

将错误修正后更新到PCB即可修复这个错误