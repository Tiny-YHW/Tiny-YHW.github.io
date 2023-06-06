---
title: 'Renesas Electronics & Integrated Device Technology 瑞萨电子&艾迪悌'
date: Thu, 09 Apr 2020 09:19:48 +0000
draft: false
tags: ['元器件管理']
---

Renesas Electronics
===================

**基础信息**RENESAS
---------------

**官网: **[https://www.renesas.com](https://www.renesas.com)

**中文名称**：瑞萨电子株式会社，日文名称：ルネサス エレクトロニクス株式会社

**厂家缩写：**RENESAS

**厂家介绍**：2010年4月1日，日本东京讯--在完成了对前株式会社瑞萨科技与NEC电子公司的业务整合工作后，新成立的瑞萨电子株式会社（以下简称瑞萨电子；TSE：6723）于2010年4月1日宣布公司正式启动商业运营。瑞萨电子着重关注于包括MCU（微控制器）、SoC解决方案、模拟与电源器件在内的三大专业技术领域。业务范围是半导体产品的研究、开发、设计、生产、销售及服务。

**收购关系**：2018年9月，瑞萨宣布已同意以67亿美元收购IDT。在2019年3月，瑞萨电子完成了收购。

**型号信息**RENESAS
---------------

### 型号

#### **从手册中获取型号**

在手册中查找关键字ORDERING INFORMATION，表格中PART NUMBER列为型号，如图型号为ISLA212P50IRZ，ISLA214P50IR72EV1Z。TEMP. RANGE为温度范围。

![](http://a1024.synology.me:222/images/blog2022/Renesas%20Electronics1.png "点击查看原图")

#### **从官网中获取型号**

在官网的全局搜索处搜索基础型号或类似型号官网中[Parametric Search](https://www.renesas.com/kr/en/search/parametric-search.html)选项下包含所有型号信息，Category为型号分类，part name列点击进去后得到型号详情页。

![](http://a1024.synology.me:222/images/blog2022/Renesas%20Electronics2.png "点击查看原图")

点击ordering即可得到对应型号清单，Orderable Part Name为型号，DATASHEET为对应的元器件手册，Package Info为型号和尺寸图的对应关系。

![](http://a1024.synology.me:222/images/blog2022/Renesas%20Electronics3.png "点击查看原图")

### **手册名**

直接使用官网下载到的文件名关键字REV为版本号

**封装信息**RENESAS
---------------

### **Case Code类型**

官方Case Code优先，有特殊情况使用自定义Case Code

### Case Code

#### **从手册中获取Case Code**

在手册中查找关键字ORDERING INFORMATION，表格中PKG.DWG. #列为官方Case Code，如下图Case Code为L72.10x10E。有些手册中查不到Case Code，需要从官网获取

![](http://a1024.synology.me:222/images/blog2022/Renesas%20Electronics4.png "点击查看原图")

#### **从官网中获取Case Code**

Case Code清单页[https://www.renesas.com/kr/en/search/package-list.html](https://www.renesas.com/us/en/search/package-list.html?category=IC&type=QFP)，包含所有Case Code，Package Code列为Case Code，点击进去Package Drawing项为对应的尺寸图从官网型号详情页可得到型号和Case Code的对应关系从元器件手册型号信息表中的型号和尺寸图对应关系后从Case Code清单页获取对应的Case Code

### **版本号**

使用官方Case Code时需查询尺寸图对应的版本号，如确实查询不到需使用“-”尺寸图版本号一般位于左上角或右下角，关键字为REV，REV后一位为版本号，其余为日期，如下图，版本号为0

![](http://a1024.synology.me:222/images/blog2022/Renesas%20Electronics5.png)

### **补充信息**

1.存在一个官方Case Code对应几组尺寸信息的情况，使用自定义Case Code，如下图官方Case Code为MDP0027，自定义为MDP0027\_8,MDP0027\_14,MDP0027\_16,MDP0027\_SOL-16等。

![](http://a1024.synology.me:222/images/blog2022/Renesas%20Electronics6.png)

2.部分尺寸图中不包含官方Case Code，需要从官网获取

**Integrated Device Technology**
================================

**基础信息**IDT
-----------

**官网：**[www.idt.com](http://www.idt.com/)  
**中文名称：**艾迪悌科技有限公司  
**厂家缩写：**IDT  
**厂家介绍：**IDT是一家总部位于加利福尼亚州圣何塞的美国上市公司，致力于为先进的通信，计算和消费行业设计，制造和销售低功耗，高性能混合信号半导体解决方案。该公司主要将产品推销给原始设备制造商（OEM）。该公司成立于1980年，最初是为通信业务和计算业务提供互补金属氧化物半导体（CMOS）的提供商。该公司专注于三个主要领域：通信基础设施（无线和有线），高性能计算和高级电源管理。  
**收购关系**：2018年9月同意被Renesas Electronics收购

**型号信息**IDT
-----------

### 型号

#### **从手册中获取型号**：

从手册中查找关键字 Ordering Information，表中"Orderable Part Number"即为型号对应的Package项为与封装的对应关系。[案例参考](https://www.idt.com/document/dst/82p33910-1-datasheet.)

#### **从官网中获取型号：**

1.  通过官网主页全局搜索型号或基础型号。
2.  选择对应的搜索结果进入元器件详情界面。[案例参考](https://www.idt.com/products/clocks-timing/clock-generation/programmable-clocks/5p35021-versaclock-3s-programmable-clock-generator)
3.  从元器件详情界面获取Orderable Part ID作为型号，Pkg.Code提供了和封装的对应关系。

### **手册名**

元器件详情界面可下载手册，可直接使用官网使用的名称命名，也可按通用要求重命名，取页眉右侧标识不含Datasheet字段的内容。如参考案例的手册名即为5P49V60。[案例参考](https://www.idt.com/document/dst/5p49v60-datasheet)

**封装信息**IDT
-----------

### **Case Code类型**

官方优先

### Case Code

#### **从官网中获取Case Code**（暂时作废）

从型号信息的元器件详情界面根据型号和封装的对应关系获取Case Code。进入型号信息表中Package info链接，查看PKg.Code即为型号所对应的的Case Code。如[参考案例](https://www.idt.com/products/clocks-timing/clock-generation/programmable-clocks/5p49v60-versaclock-6e-programmable-clock-generator-automotive)中的Case Code信息为NLG24，但考虑到后面介绍的Case Code变体规则，此处Case Code应为NL24

#### **从手册中获取Case Code**

**尺寸图图签**

根据元器件手册中型号和封装的对应关系，从元器件手册尾页查找对应的元器件尺寸图，并从尺寸图页面获取Case Code，常见的元器件尺寸图分为两类尺寸图图签中TITLE如下图CD10即为Cose Code；REV中02为版本号，0不能省略

![](http://a1024.synology.me:222/images/blog2022/Renesas%20Electronics7.png "点击查看原图")

**标题描述**

标题描述中如[参考案例](https://www.idt.com/cn/en/document/dst/5p49v60-datasheet)第27页右上角表头标题第三行NLG24S3即为Case Code；但考虑到后面介绍的Case Code变体规则，此处Case Code应为NL24S3；REV后03为版本号，0不能省略，

#### **从官网中获取单独的元器件尺寸图**

通过官网的PKg.Code链接进入[封装详情界面](https://www.idt.com/package/452431)，点击Download Full Package Info后进入[封装管理界面](https://www.idt.com/cn/en/package/nlg24)从Documentation栏点击Show more从对应文档中寻取对应的的元器件尺寸图，一般Type为Package Outline Drawing均为元器件尺寸图

### **Case Code变体**

对于该厂家经过比对发现很多同一个元器件尺寸的Case Code会分为两种带“G”和不带G版本，这两种版本的元器件尺寸均相同，区别在于引脚镀层材料是否含铅，所以对此两种Case Code做合并处理，处理规则为如获取的Case Code的第三位为G则省略改G。如DA144和DAG144均按DA144标识CaseCode

其它
==

IC PACKAG list  
[https://www.renesas.com/us/en/search/package-list.html?category=IC&type=QFP](https://www.renesas.com/us/en/search/package-list.html?category=IC&type=QFP)  
DIC PACKAGING list  
[https://www.renesas.com/us/en/search/package-list.html?category=Dic&type=TO-220FM](https://www.renesas.com/us/en/search/package-list.html?category=Dic&type=TO-220FM)

PACKAG list  
[https://www.renesas.com/us/en/search/package-list.html](https://www.renesas.com/us/en/search/package-list.html)

Renesas Package Code System  
[https://www.renesas.com/us/en/support/technical-resources/packaging/packing-outline/renesas-code.html](https://www.renesas.com/us/en/support/technical-resources/packaging/packing-outline/renesas-code.html)

https://a1024.synology.me:1024/%e6%94%b6%e5%bd%95%e5%85%83%e5%99%a8%e4%bb%b6%e5%8e%82%e5%ae%b6%e6%b8%85%e5%8d%95/