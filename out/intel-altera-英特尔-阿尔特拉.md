---
title: 'Intel & Altera 英特尔 & 阿尔特拉'
date: Thu, 09 Apr 2020 07:35:51 +0000
draft: false
tags: ['元器件管理']
---

**基础信息**
--------

**官网**：[https://www.intel.com/](https://www.intel.com/)  
**中文名称**：英特尔  阿尔特拉  
**维基百科**：[https://zh.wikipedia.org/wiki/Altera](https://zh.wikipedia.org/wiki/Altera)  
**厂家介绍**：Altera是位于美国硅谷的一家可编程逻辑器件和可反复配置的复杂数字电路的制造企业，Altera的主要产品为FPGA（分属Stratix、Arria和Cyclone三大系列）、CPLD复杂可编程逻辑设备（MAX系列）和ASIC（HardCopy系列）。  
**收购关系**：2015年6月1日，英特尔宣布以167亿美元收购Altera。 2015年12月28日，英特尔完成收购Altera

**型号信息**
--------

由于该厂商的型号获取较为困难，让步采用如下方式编辑型号，需知此方式获取的型号可能不是完整的型号，可能缺少部分后缀字段，如下图 本文给出的型号对应到型号结构截取到Package Code为止，缺少后续字段变量

![](http://a1024.synology.me:222/images/blog2022/51_178_2cc4d44466de9db.png)

### 型号

该厂家型号从手册中获取较为困难，常规获取方式为从手册中识别出元器件系列号，根据系列号从下面链接选择对应的系列，获得该系列的所有型号，选择与手册匹配的型号作为型号 [链接](https://www.intel.com/content/www/us/en/programmable/support/literature/lit-index/lit-pkg.html)  
如[手册](https://www.intel.com/content/dam/www/programmable/us/en/pdfs/literature/hb/cyclone-v/cv_51001.pdf)型号应为[对应系列](https://www.intel.com/content/www/us/en/programmable/support/literature/lit-index/lit-pkg/package.html?family=Cyclone_V)中的所有型号

中心库中录入的型号有一些有特殊后缀解释如下后缀为ES的型号，为正式型号变体表示，解释参考 [百度百科](https://baike.baidu.com/item/CPU-ES%E7%89%88%E6%9C%AC/1691760?fr=aladdin)后缀为Lidless的型号，该类型号存在两种封装，一种顶部有盖 一种顶部无盖，Lidless后缀的型号为无盖的型号后缀为 (RoHS6 G Suffix)的型号，代表符合RoHS6标准的型号类型，后续对应RoHS字段应使用G

**封装信息**
--------

**Csae Code类型：**官方优先

**元器件尺寸图纸：**官网下载的单独的尺寸图纸优先，图纸查找见下面两个链接

### **[按元器件系列号查找型号和封装](https://www.intel.com/content/www/us/en/programmable/support/literature/lit-index/lit-pkg.html)**

### **[按型号或特定参数查找封装](https://www.intel.com/content/www/us/en/programmable/support/literature/lit-index/lit-pkg/package-search.html?type=search)**

### **Altera&Intel Case Code**

**尺寸图纸文档号**：如[链接](https://www.intel.com/content/dam/www/programmable/us/en/pdfs/literature/packaging/04r00231-03.pdf)应为04R-00231，如[链接](https://www.intel.com/content/dam/www/programmable/us/en/pdfs/literature/packaging/04r00366-04.pdf)应为04R-00366，如[链接](https://www.intel.com/content/dam/www/programmable/us/en/pdfs/literature/packaging/k14719_r03_final.pdf)应为K14719

### **Altera 版本号version**

**尺寸图文档页脚文档号最末段或** 尾页Document Revision History最新的一条Version，如[链接](https://www.intel.com/content/dam/www/programmable/us/en/pdfs/literature/packaging/04r00231-03.pdf)为2.0  
**页脚文档号最末段字段为00的 **尾页Document Revision History最新的一条Version为00的特殊处理 版本号写为1.0

### **Intel 版本号version**

图签中REV字段，如[链接](https://www.intel.com/content/dam/www/programmable/us/en/pdfs/literature/packaging/k14719_r03_final.pdf)为03，这里是03不能写成3