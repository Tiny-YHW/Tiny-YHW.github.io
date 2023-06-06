---
title: 'Texas Instruments & National Semiconductor 德州仪器 & 国家半导体'
date: Thu, 09 Apr 2020 09:07:26 +0000
draft: false
tags: ['元器件管理']
---

**基础信息**
--------

**官网: **[http://www.ti.com/](http://www.ti.com/)

**中文名称**：德州仪器

**厂家介绍**：德州仪器（英语：Texas Instruments，简称：TI），是全球领先的半导体跨国公司，以开发、制造、销售半导体和计算机技术闻名于世，主要从事创新型数字信号处理与模拟电路方面的研究、制造和销售。除半导体业务外，还提供包括传感与控制、教育产品和数字光源处理解决方案。德州仪器（TI）总部位于美国德克萨斯州的达拉斯，并在25多个国家设有制造、设计或销售机构。德州仪器是世界第一大数字信号处理器(DSP)和模拟电路元件制造商，其模拟和数字信号处理技术在全球具有统治地位。

**收购关系**：2011年德州仪器以65亿美元收购美国国家半导体（National Semiconductor）

**型号信息Texas Instruments**
-------------------------

### 型号

#### **从手册中获取型号**

在手册中查找关键字  PACKAGING INFORMATION 表中的"Orderable Device" 对应的即为型号

#### **从官网中获取型号**  

1.   通过全局搜索型号或基础型号。
2.  选择对应的搜索结果进入[元器件详情界面](http://www.ti.com/sitesearch/docs/universalsearch.tsp?searchTerm=LM63615-Q1#q=LM63615-Q1&t=everything&linkId=1)
3.  点击元器件后点Order Now 进入元器件详情界面获取Part作为型号，Package提供了和封装的对应关系

#### [型号BOM & cross reference tool](https://bomcross.ti.com/en/)

### **手册名**

元器件详情界面可下载手册，手册中型号均使用官方Case Code或型号型Case Code的，可直接使用官网下载到的文件名，也可按通用要求重命名。

手册中型号包含自定义Case Code 的，需按通用要求重命名

如[链接](http://www.ti.com/lit/ds/symlink/lm63615-q1.pdf)手册网下载到的文件名为im63615-q1，按通用要求重命名SNVSB55（如末位为版本号，需删除版本号）

如[链接](http://www.ti.com/lit/ds/symlink/opa227.pdf)手册网下载到的文件名为opa227，按通用要求重命名SBOS110（如末位为版本号，需删除版本号）  

**封装信息Texas Instruments**
-------------------------

### **Case Code类型**

**官方优先元器件尺寸图纸：官网下载的单独的尺寸图纸优先**

**[所有封装类型](http://www.ti.com/support-packaging/packaging-tools/find-packages.html)**

### Case code

#### **官网查询Case Code**

1.  **按型号或封装类型查找元器件：**[链](http://www.ti.com/packaging/docs/searchproductbypackage.tsp)[接](http://www.ti.com/packaging/docs/searchproductbypackage.tsp)输入型号和引脚数量或输入TI package name和引脚数量，可查询符合条件的型号信息
2.  **元器件详情界面获取Case Code**：Case Code如下图红框所示: "PW\_20"     "TSSOP(PW) " 字段链接可转到元器件尺寸图

![](http://a1024.synology.me:222/images/blog2022/Texas%20Instruments1.png "点击查看原图")

#### **从元器件手册中获取Case Code**

一般情况下元器件手册中PACKAGING INFORMATION表中包含型号对应的封装信息，将红框中的Package Drawing + “\_” +Pins为Case Code，如下图Case Code包含DW\_23、N\_20、PW\_20

![](http://a1024.synology.me:222/images/blog2022/Texas%20Instruments2.bmp)

#### **Case Code变体1**

**BGA类元器件D、E值不确定**

部分Case Code从官网获取的尺寸图存在尺寸缺失，本例为BGA类器件D、E值缺失 示例[http://www.ti.com/lit/ml/mxbg313a/mxbg313a.pdf](http://www.ti.com/lit/ml/mxbg313a/mxbg313a.pdf)此种情况对应到此Case Code的不同型号D、E值可能存在差异元器件长宽高从对应的元器件手册获取使用Case Code加元器件长宽高作为最终Case CodeB代表封装体尺寸，格式为Case Code + "\_" + "B" + DXEXA,如YFF\_40\_B306X276尺寸值中D、E为长宽取中值，A为高度取最大值可直接参考LE中自动生成的Footprint Name中的长宽高部分

#### **Case Code变体2**

**散热盘长宽不确定**

**QFN、SOP、SON、QFP**系列的封装尺寸含有散热焊盘时可能不会标注散热焊盘的尺寸需要到手册中查找，根据Case Code加散热盘尺寸作为Case CodeT代表散热盘，格式为Case Code + "\_" + "T" + D2XE2若D2=E2需省略其中一个， 如DKD\_36\_T1590X585、DPJ\_8\_T230尺寸值中D2、E2为散热盘长宽标准的矩形取中值，其它种类按推荐焊盘值设计可直接参考LE中自动生成的Footprint Name中的散热盘长宽部分

### **版本号**

使用官方Case Code的情况如查询到的尺寸图包含版本号则需登记版本号，否则使用“-”。尺寸图的版本号为元器件尺寸图右下角字符串的最后一位。如下图版本号应为H，后方的05/13代表2013年5月

![](http://a1024.synology.me:222/images/blog2022/Texas%20Instruments3.png)

官方指定ECAD平台
----------

[合作平台Ultra Librarian](https://webench.ti.com/cad/)

* * *

**型号信息National Semiconductor**
------------------------------

按通用方法

**封装信息National Semiconductor**
------------------------------

按自定义Case Code

**补充事项**
--------

注：出现散热焊盘尺寸有多个时，LE封装库中的尺寸链接依旧指向尺寸图，并备注散热焊盘大小不一，请依照对应型号的手册获取当打开尺寸图后发现只有一张图片没有尺寸信息时，应该打开元器件手册进行查询  
图片下面会附带一条注释：  
**This image is a representation of the package family, actual package may vary.Refer to the product data sheet for package details.**  
翻译：此图像代表封装系列，实际封装可能有所不同。有关封装的详细信息，请参见元器件手册。则按自定义类型Case Code

https://a1024.synology.me:1024/%e6%94%b6%e5%bd%95%e5%85%83%e5%99%a8%e4%bb%b6%e5%8e%82%e5%ae%b6%e6%b8%85%e5%8d%95/