---
title: 'Integrated Silicon 矽成'
date: Thu, 09 Apr 2020 08:08:55 +0000
draft: false
tags: ['元器件管理']
---

**基础信息**
--------

**官网:  **[http://www.issi.com/US/Index.shtml](http://www.issi.com/US/Index.shtml)  
**中文名称**：矽成  
**厂家介绍**：专门设计、开发、销售高性能存储半导体产品，用于Internet存储器件、网络设备、远程通讯和移动通讯设备、计算机外设等。  
**收购关系**：无

**型号信息**
--------

### 型号

**优先从PDF中获取型号**一般均可以从手册中直接读取型号信息，关键字ORDERING INFORMATION，搜索后会出现对应的表格，一般信息呈现为元器件参数信息表的形式，同时提供了型号和封装的对应关系

![](http://a1024.synology.me:222/images/blog2022/Integrated%20Silicon1.png "点击查看原图")

### **手册名**

若手册中所有尺寸均为官方Case Code时，手册可直接使用官网使用的名称命名，也可按通用要求重命名。

当手册用自定义Case Code时，手册使用表头中的基础型号，若手册给出的基础型号大于等于三个，为了避免Case Code过长，选取第一个基础型号作为手册名

*   如[链接](http://www.issi.com/WW/pdf/62WV1288ALL.pdf)手册名应为IS62WV1288ALL
*   如[链接](http://www.issiusa.com/pdf/65WV12816ALL_BLL.pdf)手册名应为IS65WV12816ALL\_IS65WV12816BLL 

**封装信息**
--------

### **Csae Code类型**

官方优先**元器件尺寸图纸：**不容易找到官网提供的单独的尺寸图文档，直接使用手册中的图纸。

### **Case Code**

尺寸图签中Package Outline信息如下图为100L 14×20×1.4mm LQFP则Case Code应为100L\_14X20X1\_4mm\_LQFP**（图中的乘号转换为大写X，空格和小数点转换为“\_”）**

![](http://a1024.synology.me:222/images/blog2022/Integrated%20Silicon2.png "点击查看原图")

### **版本号**

尺寸图签中 REV信息，如上图为F  
该厂家有一些手册中没有尺寸图图签，则不能使用官方Case Code管理按自定义或型号型Case Code来命名例如下图 为自定义Case Code时 Case Code应为 “手册名+\_+FCQFN-16”

![](http://a1024.synology.me:222/images/blog2022/Integrated%20Silicon3.png "点击查看原图")

自定义或型号型Case Code无需管理版本号