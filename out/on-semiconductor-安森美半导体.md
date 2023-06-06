---
title: 'ON Semiconductor & Fairchild Semiconductor 安森美半导体 &仙童半导体'
date: Thu, 09 Apr 2020 09:20:59 +0000
draft: false
tags: ['元器件管理']
---

ON Semiconductor
================

**基础信息**
--------

**官网:**[http://www.onsemi.com](http://www.onsemi.com)

**中文名称：**安森美半导体

**厂家介绍：**ON Semiconductor应用于高能效电子产品的首要高性能硅方案供应商。公司的产品系列包括电源和信号管理、逻辑、分立及定制器件，帮助客户解决他们在汽车、通信、计算机、消费电子、工业、LED照明、医疗、军事/航空及电源应用的独特设计挑战，既快速又符合高性价比。公司在北美、欧洲和亚太地区之关键市场运营包括制造厂、销售办事处及设计中心在内的世界一流、增值型供应链和网络。

**收购关系：**2016年9月16日ON Semiconductor成功收购Fairchild Semiconductor。注释：虽然ON Semiconductor收购了Fairchild Semiconductor，但是ON Semiconductor自身的手册和Fairchild Semiconducto的手册还是存在着一定的差别，关于Fairchild Semiconductor的手册下方会有单独的信息介绍。

**型号信息**
--------

### 型号

#### **从手册中获取型号**

从手册中查找关键字 Ordering Information，表中"Device"列或者”Part Number”列即为型号，对应的Package项为与封装的对应关系。[案例参考](https://www.onsemi.cn/PowerSolutions/document/MC1413-D.PDF)

#### **从官网中获取型号**

1.  通过官网主页全局搜索型号或基础型号。
2.  选择对应的搜索结果进入元器件详情界面。[案例参考](https://www.onsemi.com/products/power-management/motor-drivers/load-drivers-relay-drivers/mc1413)
3.  从元器件详情界面获取“prduct”作为型号，对应的“PACKAGE”列下的“TYPE”列提供了和封装的对应关系,“Case Outline”列提供了尺寸图链接。

### **手册名**

元器件详情界面可下载手册，直接使用官网使用的名称命名。

**封装信息**
--------

### **Case Code类型**

官方Case code优先

### Case Code

#### **从手册中获取Case Code**

根据元器件手册中型号和封装的对应关系，从元器件手册查找对应的元器件尺寸图，并从尺寸图页面获取Case Code。 元器件尺寸图页上方PACKAGE DIMENSIONS，下方第二行文本去除CASE，即为Case Code，第三行ISSUE后的内容即为版本号。如下图Case Code为873A-02，版本号为C。

![](http://a1024.synology.me:222/images/blog2022/ON%20Semiconductor1.png "点击查看原图")

#### **从官网中获取Case Code**

元器件详情界面，“PACKAGE”列下的“Case Outline”列即为Case Code。

**Fairchild Semiconductor**
===========================

**手册信息**
--------

Fairchild Semiconductor系列在首页会有下图Fairchild的图标

![](http://a1024.synology.me:222/images/blog2022/ON%20Semiconductor2.png "点击查看原图")

**从手册中获取型号**
------------

从手册中查找关键字 Ordering Information，对应的“part”或者”Part Number”即为型号，对应的Package项为与封装的对应关系。[案例参考](https://www.onsemi.com/pub/Collateral/FJA4313CN-D.pdf)

**从手册中获取Case Code**
-------------------

### 官方Case Code

元器件尺寸页注释，最后一条文本去除MTK-和版本号，如下图应为TO220E06,版本号为REV后的内容，下图的版本号即为2。

![](http://a1024.synology.me:222/images/blog2022/ON%20Semiconductor3.png)

### 自定义Case Code

若元器件尺寸页没有注释或没有MTK字样，则按通用规则处理，使用手册名+“\_”+封装特征作为Case Code。[案例参考](https://www.onsemi.com/pub/Collateral/FJA4313CN-D.pdf)

https://a1024.synology.me:1024/%e6%94%b6%e5%bd%95%e5%85%83%e5%99%a8%e4%bb%b6%e5%8e%82%e5%ae%b6%e6%b8%85%e5%8d%95/