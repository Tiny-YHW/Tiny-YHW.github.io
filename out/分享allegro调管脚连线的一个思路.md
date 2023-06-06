---
title: '分享allegro调管脚连线的一个思路'
date: Fri, 30 Oct 2020 01:06:17 +0000
draft: false
tags: ['Allegro', '设计技巧']
---

不管是net logic还是swap pin均适用

规划线路
----

不管哪种方法首先规划好要调管脚的一组线走到哪些层哪一部分

![](http://a1024.synology.me:222/images/blog2022/%E5%88%86%E4%BA%ABallegro%E8%B0%83%E7%AE%A1%E8%84%9A%E8%BF%9E%E7%BA%BF%E7%9A%84%E4%B8%80%E4%B8%AA%E6%80%9D%E8%B7%AF1.jpg)

两端出线
----

两边同时引出线（线长短因人而异可引出线头示意一下即可，也可接近完全连上不易出错）。  
小技巧：且线数量一致可用show element然后find只勾选clines两边各框一下，会有信息栏跳出，第一行LISTING: X element(s)，X即代表线的数量。

![](http://a1024.synology.me:222/images/blog2022/%E5%88%86%E4%BA%ABallegro%E8%B0%83%E7%AE%A1%E8%84%9A%E8%BF%9E%E7%BA%BF%E7%9A%84%E4%B8%80%E4%B8%AA%E6%80%9D%E8%B7%AF2.jpg)

两端互联
----

注意此时两端线是不能很方便的连到一起的因为两端都有网络且不相同，所以现在要做的事去掉一段的网络，这里思路做一个转变，其实打断其中一端即可，这里有人想到了删线（删顶层短线），这里我建议move，把短线移动出来，现在下面一端就是无网络了，然后两端互联

![](http://a1024.synology.me:222/images/blog2022/%E5%88%86%E4%BA%ABallegro%E8%B0%83%E7%AE%A1%E8%84%9A%E8%BF%9E%E7%BA%BF%E7%9A%84%E4%B8%80%E4%B8%AA%E6%80%9D%E8%B7%AF03.jpg)

![](http://a1024.synology.me:222/images/blog2022/%E5%88%86%E4%BA%ABallegro%E8%B0%83%E7%AE%A1%E8%84%9A%E8%BF%9E%E7%BA%BF%E7%9A%84%E4%B8%80%E4%B8%AA%E6%80%9D%E8%B7%AF04.jpg)

完成链路
----

然后移回顶层线，此时飞线已集中到FPGA一侧

![](http://a1024.synology.me:222/images/blog2022/%E5%88%86%E4%BA%ABallegro%E8%B0%83%E7%AE%A1%E8%84%9A%E8%BF%9E%E7%BA%BF%E7%9A%84%E4%B8%80%E4%B8%AA%E6%80%9D%E8%B7%AF05.jpg)

交换管脚
----

只开顶层线连接关系显而易见，netlogic、swap pin调整网络即可，像玩连连看一样

![](http://a1024.synology.me:222/images/blog2022/%E5%88%86%E4%BA%ABallegro%E8%B0%83%E7%AE%A1%E8%84%9A%E8%BF%9E%E7%BA%BF%E7%9A%84%E4%B8%80%E4%B8%AA%E6%80%9D%E8%B7%AF06.jpg)

完成连接
----

![](http://a1024.synology.me:222/images/blog2022/%E5%88%86%E4%BA%ABallegro%E8%B0%83%E7%AE%A1%E8%84%9A%E8%BF%9E%E7%BA%BF%E7%9A%84%E4%B8%80%E4%B8%AA%E6%80%9D%E8%B7%AF07.jpg)