---
title: 'Analog Devices&Linear Technology 亚德诺半导体&凌特科技'
date: Thu, 09 Apr 2020 08:45:03 +0000
draft: false
tags: ['元器件管理']
---

**基础信息**
--------

**官网: **[https://www.analog.com/](https://www.analog.com/)  
**中文名称**：亚德诺半导体  
**厂家缩写**：ANALOG  
**厂家介绍**：Analog Devices 公司总部设在美国马萨诸塞州诺伍德市，设计和制造基地遍布全球。主要产品有：放大器和线性产品、[数据转换器](https://baike.baidu.com/item/%E6%95%B0%E6%8D%AE%E8%BD%AC%E6%8D%A2%E5%99%A8)、音频和视频产品、宽带产品、时钟和定时IC、光纤和光通信产品、接口和隔离、MEMS和传感器、电源和散热管理、处理器和DSP、RF和IF ICs、开关和多路复用器等等  
**收购关系**：2017年3月，ADI以148亿美元完成对Linear Technology Corporation（凌力尔特）的收购。Linear Technology 被收购后，官网即为Analog Devices官网。

**型号信息**
--------

### 型号

#### **官网中获取型号**

1.  通过全局搜索型号或基础型号[型号搜索界面](https://www.analog.com/en/products.html)。
2.  选择对应的搜索结果进入[元器件详情界面](https://www.analog.com/en/products/ada4945-1.html)。
3.  从元器件详情界面获取Model作为型号，Package提供了和封装的对应关系。

#### **手册中获取型号**

**Analog Devices**手册中查找型号的关键字为ORDERING GUIDE，其中包含型号信息，Model代表型号。如下图ORDERING GUIDE为型号信息表，Model列中包含AD818AN、AD818ANZ、AD818AR、AD818ARZ四个型号

![](http://a1024.synology.me:222/images/blog2022/Analog%20Devices1.png "点击查看原图")

**Linear Technology**手册中查找型号的关键字为PACKAGE/ORDER INFORMATION，其中ORDER PART NUMBER代表型号如下图PACKAGE/ORDER INFORMATION为型号信息表，ORDER PART NUMBER代表型号，图中包含LTC1041CN8、LTC1041CS8两个型号

![](http://a1024.synology.me:222/images/blog2022/Analog%20Devices2.png "点击查看原图")

### **手册名**

元器件详情界面可下载手册，可直接使用官网使用的名称命名，也可按通用要求重命名。手册中型号包含自定义Case Code 的，需按通用要求对元器件手册重命名例如：[链接](https://www.analog.com/media/en/technical-documentation/data-sheets/ADA4945-1.pdf)手册的手册名即为ADA4945-1

**封装信息**
--------

### **Case Code类型**

官方优先元器件尺寸图纸：官网下载的单独的尺寸图纸优先

从官方网站元器件[封装清单列表](http://www.analog.com/en/design-center/packaging-quality-symbols-footprints/package-index.html)获取Case Code，如下图红色框所示，outline字段pdf链接为尺寸图

![](http://a1024.synology.me:222/images/blog2022/Analog%20Devices3.png)

**从元器件手册中获取Case Code**

**Analog Devices**厂家元器件手册中ORDERING GUIDE表中包含型号信息和封装信息，Package Option字段即为Case Code。

![](http://a1024.synology.me:222/images/blog2022/Analog%20Devices4.png "点击查看原图")

**Linear Technology**厂家元器件手册中UPACKAGE DESCRIPTION中包含Case Code以及尺寸图。Case Code位于尺寸图的标题处，如图Case Code为05-08-1510

![](http://a1024.synology.me:222/images/blog2022/Analog%20Devices5.png "点击查看原图")

**注意：**Case Code中包含（）的用\_代替，Case Code首尾若有\_则去掉，\_不连续出现，若有多个连续出现，如“\_\_”,则使用一个代替。

Case Code优先从官网获取，直接使用元器件手册中的Case Code时需核对正确性  
从官网获取元器件尺寸图通过官网提供的[封装清单](http://www.analog.com/en/design-center/packaging-quality-symbols-footprints/package-index.html)，通过过滤项从清单中选择目标Case Code，进入详情页获取尺寸图。

**版本号**
-------

官网获取的尺寸图为Analog Devices 和Linear Technology Corporation两个厂家的尺寸图。ADI尺寸图的版本号为右下角字符串的最后一位，如图尺寸图版本号为A。

![](http://a1024.synology.me:222/images/blog2022/Analog%20Devices6.png "点击查看原图")

LTC尺寸图的版本号位于表头，关键字为REV。如图尺寸图版本号为B。

![](http://a1024.synology.me:222/images/blog2022/Analog%20Devices7.png "点击查看原图")

一些尺寸图没有版本号或版本号为Ø，均以版本号为空处理，即版本号为-。

Linear Technology Case Code
---------------------------

封装类型

封装描述

Case Code

BGA

108-Lead BGA (16mm x 11.9mm x 2.42mm)

[05-08-1576](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-bga/05081576_0_bga108.pdf)

BGA

108-Lead BGA (16mm x 11.9mm x 3.01mm)

[05-08-1935](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-bga/05081935_C_bga108.pdf)

BGA

108-Lead BGA (16mm x 11.9mm x 3.51mm)

[05-08-1931](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-bga/05081931_B_bga108.pdf)

BGA

108-Lead BGA (16mm x 11.9mm x 4.92mm)

[05-08-1965](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-bga/05081965_A_bga108.pdf)

BGA

108-Lead BGA (16mm x 11.9mm x 5.01mm)

[05-08-1933](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-bga/05081933_A_bga108.pdf)

BGA

113-Lead BGA (15mm x 15mm x 4.92mm)

[05-08-1980](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-bga/05081980_A_bga113.pdf)

BGA

114-Lead BGA (15mm x 15mm x 4.92mm)

[05-08-1894](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-bga/05081894_B_bga114.pdf)

BGA

118-Lead BGA (15mm x 15mm x 3.42mm)

[05-08-1903](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-bga/05081903_C_bga118.pdf)

BGA

120-Lead BGA (16mm x 16mm x 10.34mm)

[05-08-1623](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-bga/05081623_0_bga120.pdf)

BGA

121-Lead BGA (15mm x 15mm x 3.42mm)

[05-08-1923](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-bga/05081923_B_bga121.pdf)

BGA

121-Lead BGA (15mm x 15mm x 4.92mm)

[05-08-1891](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-bga/05081891_B_bga121.pdf)

BGA

133-Lead BGA (15mm x 15mm x 3.42mm)

[05-08-1877](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-bga/05081877_D_bga133.pdf)

BGA

133-Lead BGA (15mm x 15mm x 3.42mm)

[05-08-1943](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-bga/05081943_A_bga133.pdf)

BGA

133-Lead BGA (15mm x 15mm x 4.92mm)

[05-08-1897](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-bga/05081897_B_bga133.pdf)

BGA

133-Lead BGA (15mm x 15mm x 4.92mm)

[05-08-1940](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-bga/05081940_A_bga133.pdf)

BGA

133-Lead BGA (15mm x 15mm x 4.92mm)

[05-08-1962](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-bga/05081962_A_bga133.pdf)

BGA

133-Lead BGA (15mm x 15mm x 4.92mm)

[05-08-1992](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-bga/05081992_A_bga133.pdf)

BGA

140-Lead BGA (11.25mm 9mm x 2.22mm)

[05-08-1569](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-bga/05081569_0_bga140.pdf)

BGA

140-Lead BGA (11.25mm x 9mm x 2.72mm)

[05-08-1849](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-bga/05081849_C_bga140.pdf)

BGA

141-Lead BGA (15mm x 15mm x 3.42mm)

[05-08-1899](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-bga/05081899_C_bga141.pdf)

BGA

144-Lead BGA (12mm x 12mm x 1.29mm)

[05-08-1967](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-bga/05081967_B_bga144.pdf)

BGA

144-Lead BGA (15mm x 15mm x 3.42mm)

[05-08-1902](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-bga/05081902_C_bga144.pdf)

BGA

144-Lead BGA (15mm x 15mm x 3.42mm)

[05-08-1946](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-bga/05081946_B_bga144.pdf)

BGA

144-Lead BGA (15mm x 15mm x 4.92mm)

[05-08-1921](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-bga/05081921_B_bga144.pdf)

BGA

144-Lead BGA (15mm x 15mm x 5.01mm)

[05-08-1880](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-bga/05081880_C_bga144.pdf)

BGA

144-Lead BGA (15mm x 15mm x 5.01mm)

[05-08-1908](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-bga/05081908_A_bga144.pdf)

BGA

144-Lead BGA (15mm x 15mm x 5.01mm)

[05-08-1914](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-bga/05081914_B_bga144.pdf)

BGA

144-Lead BGA (16mm × 16mm × 5.86mm)

[05-08-1540](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-bga/05081540_C_BGA144%20.pdf)

BGA

144-Lead BGA (16mm x 16mm x 2.42mm)

[05-08-1577](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-bga/05081577_A_bga144.pdf)

BGA

144-Lead BGA (16mm x 16mm x 2.51mm)

[05-08-1503](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-bga/05081503_B_bga144.pdf)

BGA

144-Lead BGA (16mm x 16mm x 5.01mm)

[05-08-1523](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-bga/05081523_A_bga144.pdf)

BGA

144-Lead BGA (16mm x 16mm x 5.01mm)

[05-08-1920](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-bga/05081920_C_bga144.pdf)

BGA

144-Lead BGA (16mm x 16mm x 5.01mm)

[05-08-1969](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-bga/05081969_A_bga144.pdf)

BGA

144-Lead BGA (16mm x 16mm x 7.07mm)

[05-08-1562](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-bga/05081562_A_bga144.pdf)

BGA

144-Lead BGA (16mm x 16mm x 7.07mm)

[05-08-1937](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-bga/05081937_D_bga144.pdf)

BGA

144-Lead BGA (16mm x 16mm x 7.82mm)

[05-08-1583](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-bga/05081583_C_bga144.pdf)

BGA

162-Lead BGA (15mm x 7.5mm x 4.6mm)

[05-08-1646](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-bga/05081646_0_BGA162.pdf)

BGA

165-Lead (16mm × 11.9mm × 3.32mm)

[05-08-1605](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-bga/05081605_b_bga165.pdf)

BGA

170-Lead BGA (15mm x 9mm x 1.54mm)

[05-08-1890](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-bga/05081890_C_bga170.pdf)

BGA

186-Lead BGA (15mm x 15mm x 3.32mm)

[05-08-1670](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-bga/05081670_A_bga186.pdf)

BGA

187-Lead BGA (22mm x 15mm x 3.42mm)

[05-08-1942](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-bga/05081942_B_bga187.pdf)

BGA

196-Lead BGA (15mm x 15mm x 2.82mm)

[05-08-1907](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-bga/05081907_B_bga196.pdf)

BGA

196-Lead BGA (15mm x 15mm x 3.32mm)

[05-08-1970](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-bga/05081970_A_bga196.pdf)

BGA

209-Lead (16mm × 9.50mm × 11.40mm) 

[05-08-7001](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-bga/05087001_B_BGA209.pdf)

BGA

209-Lead BGA (16mm x 9.5mm x 4.72mm)

[05-08-1561](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-bga/05081561_bga209.pdf)

BGA

210-Lead BGA (16.9mm × 8.1mm × 1.52mm)

[05-08-1828](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-bga/05081828_a_bga210.pdf)

BGA

221-Lead BGA (15mm x 11.25mm x 2.82mm)

[05-08-1886](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-bga/05081886_C_bga221.pdf)

BGA

225-Lead BGA (16mm x 16mm x 2.32mm)

[05-08-1827](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-bga/05081827_0_bga225.pdf)

BGA

240-Lead BGA (16mm x 16mm x 7.72mm)

[05-08-1567](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-bga/05081567_B_bga240.pdf)

BGA

242-Lead (22mm × 11mm × 8.32mm)

[05-08-7016](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-bga/05087016_0_BGA242.pdf)

BGA

24-Lead BGA (22mm x 6.25mm x 2.06mm)

[05-08-1991](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-bga/05081991_A_bga24.pdf)

BGA

24-Lead BGA (4mm x 3mm x 1.48mm)

[05-08-1658](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-bga/05081658_0_bga24.pdf)

BGA

24-Lead BGA (9mm x 6.25mm x 2.91mm)

[05-08-1898](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-bga/05081898_C_bga24.pdf)

BGA

25-Lead (4mm × 4mm × 4.62mm)

[05-08-7028](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-bga/05087028_0_bga25.pdf)

BGA

25-Lead BGA (4mm x 3.5mm x 1.8mm)

[05-08-1627](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-bga/05081627_0_bga25.pdf)

BGA

25-Lead BGA (4mm x 4mm x 1.82mm)

[05-08-1566](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-bga/05081566_A_bga25.pdf)

BGA

25-Lead BGA (4mm x 4mm x 3.65mm)

[05-08-1625](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-bga/05081625_0_bga25.pdf)

BGA

25-Lead BGA (6.25mm x 6.25mm x 2.42mm)

[05-08-1502](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-bga/05081502_A_bga25.pdf)

BGA

25-Lead BGA (6.25mm x 6.25mm x 5.01mm)

[05-08-1905](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-bga/05081905_C_bga25.pdf)

BGA

28-Lead BGA (6.25mm x 4mm x 2.22mm)

[05-08-1517](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-bga/05081517_A_bga28.pdf)

BGA

30-Lead BGA (15mm x 6.25mm x 3.48mm)

[08-05-1580](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-bga/05081580_%C3%98_bga30.pdf)

BGA

32-Lead BGA (15mm x 11.25mm x 3.42mm)

[05-08-1851](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-bga/05081851_E_bga32.pdf)

BGA

32-Lead BGA (15mm x 11.25mm x 4.98mm)

[05-08-1860](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-bga/05081860_C_bga32.pdf)

BGA

32-Lead BGA (22m x 9mm x 3.06mm)

[05-08-1975](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-bga/05081975_A_bga32.pdf)

BGA

32-Lead BGA (22mm x 9mm x 5.06mm)

[05-08-1945](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-bga/05081945_A_bga32.pdf)

BGA

330-Lead BGA (22mm x 15mm x 7.87mm)

[05-08-1568](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-bga/05081568_A_bga330.pdf)

BGA

330-Lead BGA (22mm x 15mm x 8.17mm)

[05-08-1654](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-bga/05081654_0_bga330.pdf)

BGA

35-Lead BGA (11.25mm x 6.25mm x 3.42mm)

[05-08-1878](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-bga/05081878_B_bga35.pdf)

BGA

35-Lead BGA (11.25mm x 6.25mm x 4.92mm)

[05-08-1879](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-bga/05081879_B_bga35.pdf)

BGA

361-Lead BGA (16mm x 16mm x 4.72mm)

[05-08-1601](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-bga/05081601_a_bga361.pdf)

BGA

36-Lead BGA (15mm x 6.25mm x 2.06mm)

[05-08-1987](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-bga/05081987_A_bga36.pdf)

BGA

36-Lead BGA (5mm x 5mm x 1.72mm)

[05-08-1671](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-bga/05081671_B_bga36.pdf)

BGA

36-Lead BGA (6.25mm x 22.0mm x 2.06mm)

[05-08-1588\_BGA](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-bga/05081588_0_bga36.pdf)

BGA

36-Lead BGA (6.25mm x 6.25mm x 2.22mm)

[05-08-1976](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-bga/05081976_A_bga36.pdf)

BGA

36-Lead BGA (6.25mm x 6.25mm x 2.32mm)

[05-08-1998](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-bga/05081998_A_bga36.pdf)

BGA

38-Lead BGA (11.25mm x 9mm x 4.92mm)

[05-08-1925](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-bga/05081925_B_bga38.pdf)

BGA

40-Lead BGA (11.25mm x 6.25mm x 4.92mm)

[05-08-1867](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-bga/05081867_B_bga40.pdf)

BGA

42-Lead BGA (22mm x 9mm x 5.16mm)

[05-08-1960](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-bga/05081960_B_bga42.pdf)

BGA

42-Lead BGA (22mm x 9mm x 5.16mm)

[05-08-1973](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-bga/BGA_42_05-08-1973_Rev_A.pdf)

BGA

42-Lead BGA (6mm x 5mm x 1.3mm)

[05-08-1515](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-bga/05081515_C_bga42.pdf)

BGA

44-Lead BGA (15mm x 15mm x 5.02mm)

[05-08-1881](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-bga/BGA_44_05-08-1881_Rev_B.pdf)

BGA

45-Lead BGA (11.25mm x 9mm x 4.92mm)

[05-08-1869](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-bga/BGA_45_05-08-1869_Rev_B.pdf)

BGA

48-Lead BGA (6.25mm x 9mm x 3.22mm)

[05-08-1977](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-bga/BGA_48_05-08-1977_Rev_A.pdf)

BGA

48-Lead BGA (9mm x 6.25mm x 3.32mm)

[05-08-1999](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-bga/BGA_48_05-08-1999_Rev_B.pdf)

BGA

49-Lead (6.25mm × 6.25mm × 10.12mm)

[05-08-7018](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-bga/05087018_0_bga49.pdf)

BGA

49-Lead (6.25mm × 6.25mm × 4.91mm)

[05-08-7026](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-bga/05087026_0_BGA49.pdf)

BGA

49-Lead BGA (6.25mm × 6.25mm × 1.72mm)

[05-08-1797](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-bga/05081797_0_BGA49.pdf)

BGA

49-Lead BGA (6.25mm × 6.25mm × 3.87mm)

[05-08-1573](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-bga/05-08-1573.pdf)

BGA

49-Lead BGA (6.25mm x 6.25mm x 2.10mm)

[05-08-1600](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-bga/05081600_0_bga49.pdf)

BGA

49-Lead BGA (6.25mm x 6.25mm x 2.22mm)

[05-08-1518](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-bga/05081518_b_bga49.pdf)

BGA

49-Lead BGA (6.25mm x 6.25mm x 5.02mm)

[05-08-1574](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-bga/05081574_A_BGA49.pdf)

BGA

50-Lead BGA (11.25mm x 9mm x 3.42mm)

[05-08-1883](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-bga/BGA_50_05-08-1883_Rev_B.pdf)

BGA

51-Lead BGA (15mm x 9mm x 4.92mm)

[05-08-1889](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-bga/BGA_51_05-08-1889_Rev_A.pdf)

BGA

56-Lead BGA (11.25mm x 9mm x 4.92mm)

[05-08-1910](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-bga/BGA_56_05-08-1910_Rev_B.pdf)

BGA

56-Lead BGA (11.25mm x 9mm x 4.92mm)

[05-08-1961](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-bga/BGA_56_05-08-1961_Rev_A.pdf)

BGA

63-Lead BGA (7.5mm x 6.25mm x 1.34mm)

[05-08-1572](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-bga/05081572_A_BGA63.pdf)

BGA

63-Lead BGA (7.5mm x 6.25mm x 1.52mm)

[05-08-1547](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-bga/05081547_%C3%98_BGA63.pdf)

BGA

63-Lead BGA (7.5mm x 6.25mm x 2.22mm)

[05-08-1988](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-bga/BGA_63_05-08-1988_Rev_A.pdf)

BGA

64-Lead BGA (7mm x 7mm x 1.34mm)

[05-08-1587](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-bga/05081587_0_bga64.pdf)

BGA

66-Lead BGA (15mm x 9mm x 3.42mm)

[05-08-1954](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-bga/BGA_66_05-08-1954_Rev_A.pdf)

BGA

66-Lead BGA (22mm x 15mm x 5.16mm)

[05-08-1972](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-bga/BGA_66_05-08-1972_Rev_A.pdf)

BGA

68-Lead BGA (15mm x 9mm x 3.42mm)

[05-08-1993](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-bga/BGA_68_05-08-1993_Rev_A.pdf)

BGA

68-Lead BGA (15mm x 9mm x 4.92mm)

[05-08-1892](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-bga/BGA_68_05-08-1892_Rev_B.pdf)

BGA

70-Lead BGA (15mm x 9mm x 4.92mm)

[05-08-1918](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-bga/BGA_70_05-08-1918_Rev_B.pdf)

BGA

71-Lead BGA (15mm x 9mm x 3.42mm)

[05-08-1885](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-bga/BGA_71_05-08-1885_Rev_B.pdf)

BGA

76-Lead BGA (15mm x 11.25mm x 4.92mm)

[05-08-1952](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-bga/BGA_76_05-08-1952_Rev_A.pdf)

BGA

77-Lead BGA (15mm x 9mm x 2.42mm)

[05-08-1559](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-bga/05081559_0_bga77.pdf)

BGA

77-Lead BGA (15mm x 9mm x 2.42mm)

[05-08-1964](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-bga/05081964_B_bga77.pdf)

BGA

77-Lead BGA (15mm x 9mm x 3.51mm)

[05-08-1542](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-bga/05081542_0_bga77.pdf)

BGA

77-Lead BGA (15mm x 9mm x 5.01mm)

[05-08-1900](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-bga/05081900_E_bga77.pdf)

BGA

77-Lead BGA (15mm x 9mm x 5.01mm)

[05-08-1994](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-bga/05081994_A_bga77.pdf)

BGA

77-Lead BGA (6.25mm x 4mm x 0.97mm)

[05-08-1596](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-bga/05081596_0_bga77.pdf)

BGA

77-Lead BGA (9mm x 15mm x 5.01mm)

[05-08-1826](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-bga/05081826_%C3%98_bga77.pdf)

BGA

80-Lead BGA (11.25mm x 9mm x 2.22mm)

[05-08-1979](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-bga/05081979_A_bga80.pdf)

BGA

80-Lead BGA (11.25mm x 9mm x 2.32mm)

[05-08-1506](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-bga/BGA_80_05-08-1506_Rev_%C3%98.pdf)

BGA

80-Lead BGA (11.25mm x 9mm x 3.32mm)

[05-08-1997](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-bga/05081997_b_bga80.pdf)

BGA

81-Lead BGA (15mm x 11.25mm x 3.42mm)

[05-08-1959](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-bga/05081959_A_bga81.pdf)

BGA

84-Lead BGA (15mm x 9mm x 4.92mm)

[05-08-1674](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-bga/05081674_A_bga84.pdf)

BGA

88-Lead BGA (11.25mm x 9mm x 3.32mm)

[05-08-1535](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-bga/05081535_A_bga88.pdf)

BGA

88-Lead BGA (15mm x 11.25mm x 3.42mm)

[05-08-1928](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-bga/05081928_C_bga88.pdf)

BGA

88-Lead BGA (15mm x 11.25mm x 5.01mm)

[05-08-1541](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-bga/05081541_A_bga88.pdf)

BGA

88-Lead BGA (15mm x 11.25mm x 5.74mm)

[05-08-1526](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-bga/05081526_C_bga88.pdf)

BGA

91-Lead BGA (11.25mm x 6.25mm x 2.22mm)

[05-08-1608](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-bga/05081608_-_BGA91.pdf)

BGA

99-Lead (9mm × 7.5mm × 1.52mm)

[05-08-7029](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-bga/05087029_0_BGA99.pdf)

BGA

[05-08-1615](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-bga/05081615_0_bga49.pdf)

BGA Trays

BGA Tray Drawing 11.9mm x 16mm x 3.01mm-5.01mm

[50-8090](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-bga-trays/LTC-50-8090.pdf)

BGA Trays

BGA Tray Drawing 15mm x 15mm x 2.82mm-4.92mm

[50-8072](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-bga-trays/50-8072_completed.pdf)

BGA Trays

BGA Tray Drawing 15mm x 15mm x 4.92mm-5.02mm

[50-8068](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-bga-trays/50-8068_completed.pdf)

BGA Trays

BGA Tray Drawing 15mm x 9mm x 3.42mm-5.01mm

[50-8074](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-bga-trays/50-8074_completed.pdf)

BGA Trays

BGA Tray Drawing 6.25mm x 6.25mm x 5.01mm

[50-8084](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-bga-trays/50-8084-6.25_X_6.25_X5.01.pdf)

BGA Trays

BGA Tray Drawing 6.25mm x 9mm x 2.91mm

[50-8086](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-bga-trays/LTC_50-8086_BLACK.pdf)

BGA Trays

BGA Tray Drawing 9mm x 11.25mm x 2.72mm

[50-8064](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-bga-trays/50-8064-BLACK-PAGEcompleted.pdf)

BGA Trays

BGA Tray Drawing 9mm x 11.25mm x 3.42mm

[50-8066](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-bga-trays/KS-880442(00)BLACK.pdf)

BGA Trays

BGA/LGA Tray Drawing 15mm x 22mm x 7.87mm

[50-8211](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-bga-trays/50-8211.pdf)

BGA Trays

BGA/LGA Tray Drawing 16mm x 16mm x 7.82mm

[50-8083](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-bga-trays/50-8083.pdf)

BGA Trays

LGA Tray Drawing 11.25mm x 15mm x 4.32mm-4.92mm

[50-8062](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-bga-trays/50-8062.pdf)

BGA Trays

LGA Tray Drawing 11.25mm x 6.25mm x 4.92mm

[50-8076](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-bga-trays/50-8076-completed.pdf)

BGA Trays

LGA Tray Drawing 15mm x 9mm x 1.54mm-2.82mm

[50-8028](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-bga-trays/LGA_Tray_50-8028.pdf)

Ceramic FlatPack

10-Lead Flatpak (Glass Sealed Hermetic)

[05-08-1130](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-ceranic-flat-package/Flatpak_10_05-08-1130.pdf)

Ceramic FlatPack

10-Lead Flatpak (Metal Sealed Bottom Brazed

[05-08-1230](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-ceranic-flat-package/Flatpak_10_05-08-1230.pdf)

Ceramic FlatPack

14-Lead Flatpak (Hermetic)

[05-08-1140](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-ceranic-flat-package/05081140_A_W14.pdf)

Ceramic FlatPack

14-Lead Flatpak (Metal Sealed Bottom Braised Hermetic)

[05-08-1240](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-ceranic-flat-package/Flatpak_14_05-08-1240.pdf)

CerDIP

14-Lead CERDIP (Narrow 0.3 Inch

[05-08-1110\_J14](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-cerdip/Cerdip_14_05-08-1110.pdf)

CerDIP

16-Lead CERDIP (Narrow 0.3 Inch

[05-08-1110\_J16](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-cerdip/Cerdip_16_05-08-1110.pdf)

CerDIP

8-Lead CERDIP (Narrow 0.3 Inch)  
    

[05-08-1110\_J8](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-cerdip/Cerdip_8_05-08-1110.pdf)

CerDIP Side Brazed, Legacy LTC

14-Lead CerDIP (Side Brazed Hermetic)  
     

[05-08-1210\_D14](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-cerdip-side-brazed/Sidebrazed_14_05-08-1210.pdf)

CerDIP Side Brazed, Legacy LTC

16-Lead CERDIP (Side Brazed Hermetic)  
     

[05-08-1210\_D16](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-cerdip-side-brazed/Sidebrazed_16_05-08-1210.pdf)

CerDIP Side Brazed, Legacy LTC

18-Lead CerDip (Side Brazed

[05-08-1210\_D18](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-cerdip-side-brazed/Sidebrazed_18_05-08-1210.pdf)

CerDIP Side Brazed, Legacy LTC

20-Lead Side Brazed (Hermetic)  
     

[05-08-1210\_D20](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-cerdip-side-brazed/Sidebrazed_20_05-08-1210.pdf)

CerDIP Side Brazed, Legacy LTC

8-Lead CERDIP (Side Brazed

[05-08-1210\_D8](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-cerdip-side-brazed/Sidebrazed_%208_05-08-1210.pdf)

DD Pak

3-Lead DD Pak

[05-08-1460](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-dd-pak/05081460_F_M.pdf)

DD Pak

5-Lead DD Pak

[05-08-1461](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-dd-pak/Q%20DD5%2005-08-1461%20Rev%20F.pdf)

DD Pak

7-Lead DD Pak

[05-08-1462](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-dd-pak/05081462_G_R.pdf)

DFN

10-lead DFN (3 mm x 2mm x 0.75 mm)

[05-08-1531](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-dfn/05081531_DDB10.pdf)

DFN

10-Lead DFN (3mm x 2mm w/ EP)

[05-08-1722](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-dfn/DFN_10_05-08-1722.pdf)

DFN

10-Lead DFN (3mm x 3mm

[05-08-1647](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-dfn/05081647_0_DDM10.pdf)

DFN

10-Lead DFN (3mm x 3mm w/ EP)

[05-08-1699](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-dfn/DFN_10_05-08-1699.pdf)

DFN

10-Lead Plastic SIDE WETTABLE DFN (3mm × 2mm) 

[05-08-1655](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-dd-pak/05081655_A_DDBM10.pdf)

DFN

12(10)-Lead DFN (4mm x 3mm w/ EP)

[05-08-1971](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-dfn/05081971_0_DE12(10).pdf)

DFN

12-Lead DFN (3mm x 2mm w/ EP)

[05-08-1723](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-dfn/DFN_12_05-08-1723.pdf)

DFN

12-Lead DFN (3mm x 3mm w/ EP)

[05-08-1725](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-dfn/DFN_12_05-08-1725.pdf)

DFN

12-Lead DFN (3mm x 3mm w/ EP)

[05-08-1743](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-dfn/DFN_12_05-08-1743.pdf)

DFN

12-Lead DFN (4mm x 3mm w/ EP)

[05-08-1695](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-dfn/DFN_12_05-08-1695.pdf)

DFN

12-Lead DFN (4mm x 4mm w/ EP)

[05-08-1733](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-dfn/05081733_A_DF12.pdf)

DFN

12-Lead LDFN (3mm x 3mm x 0.75mm)

[05-08-1578](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-ldfn/05081578_b_ldfn12.pdf)

DFN

12-Lead Plastic Side Solderable DFN (4mm × 4mm)

[05-08-1791](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-dfn/05081791_0_dfm12.pdf)

DFN

14(12)-Lead DFN (4mm x 4mm w/ EP)

[05-08-1963](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-dfn/05081963_0_DFN14(12).pdf)

DFN

14-Lead DFN (4mm x 3mm w/ EP)

[05-08-1708](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-dfn/DFN_14_05-08-1708.pdf)

DFN

14-Lead DFN (4mm x 3mm x 0.75mm w/ EP)

[05-08-1731](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-dfn/05081731_C_DE14MA.pdf)

DFN

14-Lead UTDFN (4mm x 3mm x 0.55mm w/ EP)

[05-08-1751](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-utdfn/UTDFN_14_05-08-1751.pdf)

DFN

16-Lead DFN (3mm x 4mm w/ EP)

[05-08-1744](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-dfn/DFN_16_05-08-1744.pdf)

DFN

16-Lead DFN (4mm x 3mm w/ EP)

[05-08-1732](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-dfn/DFN_16_05-08-1732.pdf)

DFN

16-Lead DFN (5mm x 3mm w/ EP)

[05-08-1706](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-dfn/DFN_16_05-08-1706.pdf)

DFN

16-Lead DFN (5mm x 3mm w/ EP)

[05-08-1872](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-dfn/(DHC16%20Var%20A)%20DFN%2005-08-1872%20Rev%200.pdf)

DFN

16-Lead DFN (5mm x 4mm w/ EP)

[05-08-1707](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-dfn/05081707_A_DHD16.pdf)

DFN

16-Lead DFN (5mm x 5mm w/ EP)

[05-08-1709](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-dfn/DFN_16_05-08-1709.pdf)

DFN

18-Lead DFN (5mm x 3mm w/ EP)

[05-08-1955](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-dfn/05081955_0_DHC18.pdf)

DFN

18-Lead DFN (5mm x 4mm w/ EP)

[05-08-1778](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-dfn/DFN_18_05-08-1778.pdf)

DFN

22-Lead DFN (6mm x 3mm w/ EP)

[05-08-1714](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-dfn/DFN_22_05-08-1714.pdf)

DFN

24-Lead DFN (7mm x 4mm w/ EP)

[05-08-1864](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-dfn/DFN_24_05-08-1864.pdf)

DFN

32-Lead DFN (7mm x 4mm w/ EP)

[05-08-1734](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-dfn/DFN_32_05-08-1734.pdf)

DFN

32-Lead Plastic DFN (7mm × 5mm)

[05-08-1789](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-dfn/05081789_A_(DKE32)DFN.pdf)

DFN

3-Lead DFN (2mm x 2mm w/ EP)

[05-08-1717](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-dfn/DFN_3_05-08-1717.pdf)

DFN

44-Lead DFN (4mm x 7mm w/ EP)

[05-08-1500](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-qfn/05081500_%C3%98_UFF44.pdf)

DFN

4-Lead DFN (2mm x 2mm w/ EP)

[05-08-1724](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-dfn/DFN_4_05-08-1724.pdf)

DFN

6-Lead DFN (2mm x 2mm w/ EP)

[05-08-1703](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-dfn/05081703_C_DC6.pdf)

DFN

6-Lead DFN (2mm x 3mm w/ EP)

[05-08-1715](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-dfn/(DCB6)%20DFN%2005-08-1715%20Rev%20A.pdf)

DFN

8-Lead DFN (2mm x 2mm w/ EP)

[05-08-1719](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-dfn/DFN_8_05-08-1719.pdf)

DFN

8-Lead DFN (2mm x 2mm w/ EP)

[05-08-1939](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-dfn/05081939_0_DC8AA.pdf)

DFN

8-Lead DFN (2mm x 2mm w/ EP)

[05-08-1957](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-dfn/05-08-1957__REV._A_DCFC.pdf)

DFN

8-Lead DFN (2mm x 3mm w/ EP)

[05-08-1718](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-dfn/DFN_8_05-08-1718.pdf)

DFN

8-Lead DFN (3mm x 2mm w/ EP)

[05-08-1702](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-dfn/05081702_C_DDB8.pdf)

DFN

8-Lead DFN (3mm x 3mm x 0.75mm w/ EP)

[05-08-1698](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-dfn/DFN_8_05-08-1698.pdf)

DFN

8-Lead UTDFN (2mm x 2mm w/ EP)

[05-08-1749](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-utdfn/UTDFN_8_05-08-1749.pdf)

DFN

8-Lead UTDFN (3mm x 3mm x 0.55mm w/ EP)

[05-08-1739](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-utdfn/UTDFN_10_05-08-1739.pdf)

GQFN

12-Lead LFCSP (2mm x 3mm)

[05-08-1628](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-qfn/05081628_A_gqfn_12.pdf)

GQFN

16-Lead LFCSP (3mm x 3mm)

[05-08-1648](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-qfn/05081648_A_gqfn16.pdf)

GQFN

48-Lead GQFN (5mm x 6mm x 0.65mm w/ EP)

[05-08-1527](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-qfn/05081527_c_rhe48.pdf)

LCC

20-Lead LCC (7.75mm x 11.18mm)

[05-08-1250](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-lcc/LCC_20_05-08-1250.pdf)

LCC

20-Lead LCC (8.89mm x 8.89mm)

[05-08-1260](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-lcc/LCC_20_05-08-1260.pdf)

LCC

8-Lead LCC (5mm x 5mm)

[05-08-1852](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-lcc/LS8_(LCC)_05-08-1852_Rev_B.pdf)

LCC Trays

LGA Tray Drawing 5mm x 

[50-8060](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-lcc-trays/50-8060.pdf)

LGA

100-Lead SiPLGA (16mm x 16mm x 2.32mm w/ EP)

[05-08-1802](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-lga/05081802_A_SiPlga100.pdf)

LGA

104-Lead LGA (15mm x 15mm x 2.82mm)

[05-08-1800](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-lga/05051800_C_lga104.pdf)

LGA

108-Lead LGA (15mm x 11.25mm x 2.32mm)

[05-08-1757](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-lga/05081757_A_lga108.pdf)

LGA

108-Lead LGA (16mm x 11.9mm x 1.4mm)

[05-08-1656](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-lga/05081656_0_lga108.pdf)

LGA

108-Lead LGA (16mm x 11.9mm x 1.82mm)

[05-08-1563](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-lga/05081563_0_lga108.pdf)

LGA

108-Lead LGA (16mm x 11.9mm x 2.82mm)

[05-08-1936](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-lga/05081936_0_lga108.pdf)

LGA

113-Lead LGA (15mm x 15mm x 4.32mm)

[05-08-1756](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-lga/05081756_A_lga113.pdf)

LGA

114-Lead LGA (15mm x 15mm x 4.32mm)

[05-08-1882](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-lga/05081882_A_lga114.pdf)

LGA

118-Lead LGA (15mm x 15mm x 2.82mm)

[05-08-1801](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-lga/05081801_B_lga118.pdf)

LGA

121-Lead LGA (15mm x 15mm x 2.82mm)

[05-08-1775](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-lga/05081775_B_lga121.pdf)

LGA

121-Lead LGA (15mm x 15mm x 2.82mm)

[05-08-1861](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-lga/05081861_B_lga121.pdf)

LGA

121-Lead LGA (15mm x 15mm x 2.82mm)

[05-08-1895](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-lga/05081895_A_lga121.pdf)

LGA

133-Lead LGA (15mm x 15mm x 2.82mm)

[05-08-1755](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-lga/05081755_A_lga133.pdf)

LGA

133-Lead LGA (15mm x 15mm x 2.82mm)

[05-08-1766](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-lga/05081766_A_lga133.pdf)

LGA

133-Lead LGA (15mm x 15mm x 4.32mm)

[05-08-1777](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-lga/05081777_A_lga133.pdf)

LGA

133-Lead LGA (15mm x 15mm x 4.32mm)

[05-08-1884](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-lga/05081884_A_lga133.pdf)

LGA

133-Lead LGA (15mm x 15mm x 4.32mm)

[05-08-1906](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-lga/05081906_0_lga133.pdf)

LGA

141-Lead LGA (15mm x 15mm x 2.82mm)

[05-08-1815](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-lga/05081815_C_lga141.pdf)

LGA

141-Lead LGA (15mm x 15mm x 2.82mm)

[05-08-1840](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-lga/05081840_B_lga141.pdf)

LGA

144-Lead LGA (15mm x 15mm x 2.82mm)

[05-08-1816](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-lga/05081816_C_lga144.pdf)

LGA

144-Lead LGA (15mm x 15mm x 4.32mm)

[05-08-1843](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-lga/05081843_A_lga144.pdf)

LGA

144-Lead LGA (15mm x 15mm x 4.41mm)

[05-08-1844](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-lga/05081844_C_lga144.pdf)

LGA

144-Lead LGA (15mm x 15mm x 4.41mm)

[05-08-1873](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-lga/05081873_A_lga144.pdf)

LGA

144-Lead LGA (15mm x 15mm x 4.41mm)

[05-08-1909](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-lga/05081909_A_lga144.pdf)

LGA

144-Lead LGA (16mm x 16mm x 1.82mm)

[05-08-1948](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-lga/05081948_lga144_0.pdf)

LGA

144-Lead LGA (16mm x 16mm x 1.91mm)

[05-08-1504](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-lga/05081504_A_lga144.pdf)

LGA

144-Lead LGA (16mm x 16mm x 4.41mm)

[05-08-1594](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-lga/05081594_0_lga144.pdf)

LGA

144-Lead LGA (16mm x 16mm x 4.41mm)

[05-08-1901](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-lga/05081901_B_lga144.pdf)

LGA

144-Lead LGA (16mm x 16mm x 4.41mm)

[05-08-1915](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-lga/05081915_B_lga144.pdf)

LGA

149-Lead LGA (15mm x 15mm x 1.67mm)

[05-08-1944](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-lga/05081944_A_LGA149.pdf)

LGA

170-Lead LGA (15mm x 9mm x 1.14mm)

[05-08-1533](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-lga/05081533_%C3%98_LGA170.pdf)

LGA

204-Lead LGA (22mm x 15mm x 2.91mm)

[05-08-1822](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-lga/05081822_C_lga204.pdf)

LGA

204-Lead LGA (22mm x 15mm x 4.41mm)

[05-08-1841](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-lga/05081841_B_lga204.pdf)

LGA

20-Lead LGA (4mm x 3mm x 0.75mm w/ EP)

[05-08-1529](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-lga/LGA_20_05-08-1529_Rev_%C3%98.pdf)

LGA

21-Lead LGA (6.25mm x 6.25mm x 2.32mm)

[05-08-1803](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-lga/05081803_B_lga21.pdf)

LGA

21-Lead LGA (9mm x 6.25mm x 2.06mm)

[05-08-1532](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-lga/05081532_%C3%98_LGA21.pdf)

LGA

24-Lead (3mm × 4mm × 1.18mm)

[05-08-1657](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-lga/05081657_a_lga24.pdf)

LGA

25-Lead (3.5mm × 4mm × 1.25mm)

[05-08-7014](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-lga/05087014_0_LGA25.pdf)

LGA

25-Lead (4mm × 3.5mm × 1.3mm)

[05-08-1785](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-lga/05081785_0_lga25.pdf)

LGA

25-Lead (4mm × 4mm × 1.25mm)

[05-08-7013](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-lga/05087013_0_LGA25.pdf)

LGA

25-Lead LGA (4mm x 3.5mm x 1.8mm)

[05-08-1629](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-lga/05081629_0_LGA25.pdf)

LGA

25-Lead LGA (4mm x 4mm x 1.4mm)

[05-08-1553](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-lga/05081553_0_lga_25.pdf)

LGA

25-Lead LGA (6.25mm x 6.25mm x 1.82mm)

[05-08-1949](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-lga/05081949_0_lga25.pdf)

LGA

28-Lead LGA (15mm x 9mm x 2.82mm)

[05-08-1824](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-lga/05081824_A_lga28.pdf)

LGA

28-Lead LGA (6mm x 4mm x 0.94mm)

[05-08-1673](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-lga/05081673_A_lga28.pdf)

LGA

30-Lead LGA (6mm x 4mm x 0.94mm w/ EP)

[05-08-1558](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-lga/05081558_0_lga30.pdf)

LGA

32-Lead LGA (11.25mm x 6.25mm x 2.82mm)

[05-08-1838](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-lga/05081838_A_lga32.pdf)

LGA

32-Lead LGA (15mm x 11.25mm x 2.82mm)

[05-08-1773](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-lga/05081773_A_lga32.pdf)

LGA

32-Lead LGA (15mm x 11.25mm x 4.38mm)

[05-08-1858](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-lga/05081858_A_lga32.pdf)

LGA

35-Lead LGA (11.25mm x 6.25mm x 2.82mm)

[05-08-1805](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-lga/05081805_B_lga35.pdf)

LGA

40-Lead LGA (11.25mm x 6.25mm x 4.32mm)

[05-08-1839](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-lga/05081839_A_lga40.pdf)

LGA

40-Lead LGA (12mm x 12mm x 1.59mm)

[05-08-1974](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-lga/05081974_%C3%98_LGA40.pdf)

LGA

45-Lead LGA (11.25mm x 9mm x 4.32mm)

[05-08-1837](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-lga/05081837_A_lga45.pdf)

LGA

49-Lead LGA (6.25mm x 6.25mm x 1.70mm)

[05-08-1599](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-lga/05081599_0_lga49.pdf)

LGA

50-Lead BGA (11.25mm x 9mm x 2.82mm)

[05-08-1804](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-lga/05081804_C_lga50.pdf)

LGA

56-Lead LGA (11.25mm x 9mm x 2.82mm)

[05-08-1825](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-lga/05081825_A_lga56.pdf)

LGA

56-Lead LGA (11.25mm x 9mm x 4.32mm)

[05-08-1911](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-lga/05081911_A_lga56.pdf)

LGA

63-Lead LGA (7.5mm × 6.25mm × 1.12mm)

[05-08-7017](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-lga/05087017_0_LGA63.pdf)

LGA

66-Lead LGA (15mm x 9mm x 2.32mm)

[05-08-1807](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-lga/05081807_B_lga66.pdf)

LGA

66-Lead LGA (15mm x 9mm x 2.32mm)

[05-08-1820](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-lga/05081820_A_lga66.pdf)

LGA

66-Lead LGA (15mm x 9mm x 4.32mm)

[05-08-1810](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-lga/05081810_B_lga66.pdf)

LGA

68-Lead LGA (15mm x 9mm x 2.82mm)

[05-08-1808](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-lga/05081808_B_lga68.pdf)

LGA

68-Lead LGA (15mm x 9mm x 2.82mm)

[05-08-1821](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-lga/05081821_A_lga68.pdf)

LGA

68-Lead LGA (15mm x 9mm x 4.32mm)

[05-08-1893](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-lga/05081893_B_lga68.pdf)

LGA

69-Lead (15mm x 9mm x 2.82mm)

[05-08-1813](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-lga/05081813_B_lga69.pdf)

LGA

70-Lead LGA (15mm x 9mm x 4.32mm)

[05-08-1817](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-lga/05081817_A_lga70.pdf)

LGA

70-Lead LGA (15mm x 9mm x 4.32mm)

[05-08-1919](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-lga/05081919_A_lga70.pdf)

LGA

71-Lead LGA (15mm x 9mm x 2.82mm)

[05-08-1823](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-lga/05081823_A_lga71.pdf)

LGA

76-Lead LGA (15mm x 11.25mm x 2.32mm)

[05-08-1560](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-lga/05081560_A_lga76.pdf)

LGA

77-Lead LGA (15mm x 9mm x 1.82mm)

[05-08-1508](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-lga/05081508_0_lga77.pdf)

LGA

77-Lead LGA (15mm x 9mm x 2.82mm)

[05-08-1859](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-lga/LGA_77_05-08-1859_Rev_%C3%98.pdf)

LGA

77-Lead LGA (15mm x 9mm x 4.32mm)

[05-08-1856](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-lga/05081856_B_lga77.pdf)

LGA

81-Lead LGA (11.25mm x 11.25mm x 2.32mm)

[05-08-1809](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-lga/05081809_B_lga81.pdf)

LGA

81-Lead LGA (15mm x 11.25mm x 2.82mm)

[05-08-1868](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-lga/05081868_A_lga81.pdf)

LGA

84-Lead LGA (15mm x 9mm x 4.32mm)

[05-08-1842](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-lga/05081842_B_lga84.pdf)

LGA Trays

11.25mm x 6.25mm 3.42mm - 4.32mm Package Height

[50-8050](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-lga-trays/50-8050.pdf)

LGA Trays

15mm x 11.25mm 2.82mm Package Height

[50-8052](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-lga-trays/50-8052-tray.pdf)

LGA Trays

LGA Tray Drawing 11.25mm x 11.25mm x 2.32mm

[50-8038](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-lga-trays/LGA_Tray_50-8038.pdf)

LGA Trays

LGA Tray Drawing 11.25mm x 6.25mm x 2.82mm

[50-8036](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-lga-trays/LGA_Tray_50-8036.pdf)

LGA Trays

LGA Tray Drawing 11.25mm x 9mm x 2.82mm

[50-8042](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-lga-trays/LGA_Tray_50-8042.pdf)

LGA Trays

LGA Tray Drawing 15mm x 11.25mm x 2.32mm

[50-8044](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-lga-trays/LGA_Tray_50-8044.pdf)

LGA Trays

LGA Tray Drawing 15mm x 15mm x 2.82mm

[50-8023](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-lga-trays/LGA_Tray_50-8023.pdf)

LGA Trays

LGA Tray Drawing 15mm x 15mm x 4.32mm-4.41mm

[50-8046](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-lga-trays/LGA_Tray_50-8046.pdf)

LGA Trays

LGA Tray Drawing 15mm x 9mm x 4.32mm

[50-8048](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-sip-trays/15x9x4.32mm_Black_LTC_50--8048_Ks-870253(00)_completed.pdf)

LGA Trays

LGA Tray Drawing 16mm x 16mm x 5.01mm

[50-8078](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-lga-trays/50-8078.pdf)

LGA Trays

LGA Tray Drawing 4mm x 4mm

[50-8020](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-lga-trays/50-8020.pdf)

LGA Trays

LGA Tray Drawing 6.25mm x 6.25mm x 2.32mm

[50-8040](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-lga-trays/LGA_Tray_50-8040.pdf)

LQFN

10-Lead LQFN (1.4mm x 1.8mm x 0.71mm w/ EP)

[05-08-1582](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-lqfn/05081582_%C3%98_lqfn10.pdf)

LQFN

10-Lead LQFN (2mm x 2mm x 0.75mm)

[05-08-1644](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-lqfn/05081644_0_LQFN10.pdf)

LQFN

12-Lead LQFN (2mm x 2mm x 0.74mm)

[05-08-1530](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-lqfn/05081530_B_LQFN12.pdf)

LQFN

12-Lead LQFN (2mm x 3mm x 0.74mm)

[05-08-1565](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-lqfn/05081565_B_lqfn12.pdf)

LQFN

16-Lead LQFN (2mm x 3mm x 0.75mm)

[05-08-1683](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-lqfn/05081683_0_lqfn16.pdf)

LQFN

16-Lead LQFN (3mm × 3mm × 0.94mm)

[05-08-1626](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-lqfn/05081626_a_lqfn16.pdf)

LQFN

16-Lead LQFN (3mm x 3mm x 0.74mm)

[05-08-1595](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-lqfn/05081595_0_lqfn16.pdf)

LQFN

16-Lead LQFN (3mm x 3mm x 0.94mm w/ EP)

[05-08-1516](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-lqfn/05081516_B_lqfn16.pdf)

LQFN

18-Lead (3mm × 3mm × 0.94mm)

[05-08-1548](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-lqfn/05081548_C_LQFN18.pdf)

LQFN

18-Lead LQFN (3mm × 3mm × 0.95mm)

[05-08-1688](https://www.analog.com/media/en/package-pcb-resources/package/05081688_A_lqfn18.pdf)

LQFN

20(14)-Lead LQFN (3mm × 3mm × 0.95mm)

[05-08-7011](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-lqfn/05087011_0_LQFN%2020(14).pdf)

LQFN

20-Lead LQFN (3mm x 4mm x 0.74mm)

[05-08-1679](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-lqfn/05081679_0_lqfn20.pdf)

LQFN

20-Lead LQFN (4mm x 3mm x 0.75mm w/ EP)

[05-08-1519](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-lqfn/05081519_C_LQFN20.pdf)

LQFN

20-Lead LQFN (4mm x 3mm x 0.94mm w/ EP)

[05-08-1524](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-lqfn/05081524_B_lqfn20.pdf)

LQFN

20-Lead LQFN (4mm x 3mm x 0.94mm)

[05-08-1602](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-lqfn/05081602_A_lqfn20.pdf)

LQFN

22-Lead LQFN (4mm × 3mm × 0.95mm)

[05-08-7012](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-lqfn/05087012_0_lqfn22.pdf)

LQFN

24-Lead LQFN (3mm x 5mm x 0.95mm)

[05-08-1687](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-lqfn/05081687_%EF%BF%BD_LQFN24.pdf)

LQFN

24-Lead LQFN (4mm x 4mm x 0.94mm w/ EP)

[05-08-1511](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-lqfn/05081511_C_lqfn24.pdf)

LQFN

26-Lead LQFN (6mm x 5mm x 0.94mm)

[05-08-1645](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-lqfn/05081645_0_LQFN36.pdf)

LQFN

26-Lead LQFN (7mm × 7mm × 4.32mm)

[05-08-7019](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-lqfn/05087019_0_lqfn26.pdf)

LQFN

28(26)-Lead LQFN (4mm × 5mm × 0.95mm)

[05-08-1486](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-lqfn/05081486_0_lqfn28(26).pdf)

LQFN

28-Lead LQFN (4mm × 5mm × 0.95mm)

[05-08-1597](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-lqfn/05081597_A_LQFN28.pdf)

LQFN

28-Lead LQFN (4mm × 5mm × 0.95mm)

[05-08-7007](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-lqfn/05087007_0_LQFN28.pdf)

LQFN

28-Lead LQFN (4mm x 5mm x 0.74mm w/ EP)

[05-08-1552](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-lqfn/05081552_A_lqfn28.pdf)

LQFN

28-Lead LQFN (5mm × 4mm × 0.75mm)

[05-08-7000](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-lqfn/05087000_0_lqfn28.pdf)

LQFN

28-Lead LQFN (5mm x 4mm x 0.74mm)

[05-08-1593](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-lqfn/05081593_-_LQFN28.pdf)

LQFN

28-Lead LQFN (5mm x 4mm x 0.74mm)

[05-08-1603](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-lqfn/05081603_-_LQFN28.pdf)

LQFN

28-Lead LQFN (5mm x 4mm x 0.94mm)

[05-08-1585](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-lqfn/05081585_A_LQFN28.pdf)

LQFN

28-Lead LQFN (5mm x 4mm x 0.94mm)

[05-08-1643](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-lqfn/05081643_0_LQFN28.pdf)

LQFN

28-Lead LQFN (5mm x 4mm x 0.94mm)

[05-08-1675](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-lqfn/05081675_0_lqfn28.pdf)

LQFN

28-Lead QFN (5mm x 4mm x 0.94mm w/ EP)

[05-08-1579](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-lqfn/05081579_%C3%98_lqfn28.pdf)

LQFN

30-Lead LQFN (4mm × 5mm × 0.95mm)

[05-08-7022](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-lqfn/05087022_0_lqfn30.pdf)

LQFN

32(22)-Lead LQFN (5mm x 5mm x 1.4mm)

[05-08-1618](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-lqfn/05081618_0_lqfn32(22).pdf)

LQFN

32(28)-Lead LQFN (6mm x 4mm x 0.94mm)

[05-08-1622](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-lqfn/05081622_-_LQFN32(28).pdf)

LQFN

32(28)-Lead LQFN (6mm x 4mm x 0.94mm)

[05-08-1676](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-lqfn/05081676_0_lqfn32(28).pdf)

LQFN

32(30)-Lead (6mm × 4mm × 0.94mm)

[05-08-1588\_LQFN](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-lqfn/05081558_a_lqfn32(30).pdf)

LQFN

32-Lead LQFN (5mm x 5mm x 0.94mm)

[05-08-1609](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-lqfn/05081609_A_lqfn32.pdf)

LQFN

32-Lead LQFN (6mm × 4mm × 0.95mm)

[05-08-7027](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-lqfn/05087027_a_lqfn32.pdf)

LQFN

32-Lead LQFN (6mm x 4mm x 0.94mm w/ EP)

[05-08-1512](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-lqfn/05081512_C_lqfn32.pdf)

LQFN

32-Lead LQFN (6mm x 4mm x 0.94mm w/ EP)

[05-08-1557](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-lqfn/05081557_A_lqfn32.pdf)

LQFN

32-Lead LQFN (6mm x 4mm x 0.94mm w/ EP)

[05-08-1665](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-lqfn/05081665_A_lqfn32.pdf)

LQFN

36(26)-Lead LQFN (6mm × 5mm × 1.45mm)

[05-08-1619](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-lqfn/05081619_c_lqfn36(26).pdf)

LQFN

36-Lead LQFN (4mm × 7mm × 0.94mm)

[05-08-1525](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-lqfn/05081525_B_lqfn36.pdf)

LQFN

36-Lead LQFN (4mm × 7mm × 0.95mm)

[05-08-1829](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-lqfn/05081829_0_lqfn36.pdf)

LQFN

36-Lead LQFN (7mm x 4mm x 0.94mm)

[05-08-1604](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-lqfn/05081604_0_lqfn36.pdf)

LQFN

38-Lead LQFN (4mm x 7mm x 0.7mm w/ EP)

[05-08-1584](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-lqfn/05081584_0_lqfn38.pdf)

LQFN

40-Lead LQFN (7mm x 5mm x 0.9mm)

[05-08-1607](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-lqfn/05081607_-_LQFN40.pdf)

LQFN

42-Lead LQFN (8mm x 5mm x 0.75mm w/ EP)

[05-08-1571](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-lqfn/05081571_A_LQFN42%20.pdf)

LQFN

48-Lead LQFN (10mm × 4mm × 1.02mm)

[05-08-1831](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-lqfn/05081831_0_LQFN48_.pdf)

LQFN

48-Lead LQFN (5mm × 6mm × 0.94mm)

[05-08-1606](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-lqfn/05081606_A_lqfn48.pdf)

LQFN

48-Lead LQFN (6mm x 8mm x 0.94mm)

[05-08-1649](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-lqfn/05081649_A_lqfn48.pdf)

LQFP

48-Lead LQFP (7mm x 7mm w/ EP)

[05-08-1832](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-lqfp/05081832_E_LXE48(BB).pdf)

LQFP

48-Lead LQFP (7mm x 7mm w/ EP)

[05-08-1927](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-lqfp/05081927_B_LXE48(AA).pdf)

LQFP

48-Lead LQFP (7mm x 7mm)

[05-08-1760](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-lqfp/05081760_A_LX48.pdf)

LQFP

64-Lead LQFP (10mm x 10mm w/ EP)

[05-08-1982](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-lqfp/05081982_A_LWE64.pdf)

LQFP

64-Lead LQFP (10mm x 10mm)

[05-08-1539](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-lqfp/05081539_%C3%98_LW64.pdf)

LQFP

80-Lead Plastic Exposed Pad LQFP

[05-08-1783](https://www.analog.com/media/en/package-pcb-resources/package/05081783_0_lqfp80.pdf)

LQFP Trays

LGA Tray Drawing 10mm x 1

[50-8098](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-lqfp-trays/50-8098.pdf)

LQFP Trays

LGA Tray Drawing 7mm x 

[50-8030](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-lqfp-trays/50-8030.pdf)

MSOP

10-Lead MSOP

[05-08-1661](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-msop/05081661_F_MS.pdf)

MSOP

10-Lead MSOP w/ EP

[05-08-1664](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-msop/05081664_I_MSE.pdf)

MSOP

12-Lead MSOP

[05-08-1668](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-msop/05081668_A_MS12.pdf)

MSOP

12-Lead MSOP w/ EP

[05-08-1666](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-msop/05081666_G_MSE12.pdf)

MSOP

16(12)-Lead MSOP

[05-08-1847](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-msop/05081847_B_MS16(12).pdf)

MSOP

16(12)-Lead MSOP w/ EP

[05-08-1871](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-msop/05081871_D_MSE16(12).pdf)

MSOP

16-Lead MSOP

[05-08-1669](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-msop/05081669_A_MS16.pdf)

MSOP

16-Lead MSOP w/ EP

[05-08-1667](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-msop/05081667_F_MSE16.pdf)

MSOP

8-Lead MSOP

[05-08-1660](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-msop/05081660_G_MS8.pdf)

MSOP

8-Lead MSOP w/ EP

[05-08-1662](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-msop/05081662_K_MS8E.pdf)

PCA Modules

22-Lead PCA  
           

[061-0183](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-pca-modules/061-0183REV3_PCA_OUTLINE_DRAWING,_LTP5900.PDF)

PCA Modules

66-Lead PCA  
           

[061-0167](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-pca-modules/061-0167REV3_PCA_OUTLINE_DRAWING,_LTP5901.PDF)

PCA Modules

66-Lead PCA  
           

[061-0176](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-pca-modules/061-0176REV3_PCA_OUTLINE_DRAWING,_LTP5902.PDF)

PDIP

14-Lead PDIP (Narrow 0.3 Inch)  
     

[05-08-1510\_N14](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc_legacy-pdip/05081510_I_N14.pdf)

PDIP

16-Lead Flatpak Glass Sealed (Hermetic)

[05-08-7003](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc_legacy-pdip/05087003_0_w16.pdf)

PDIP

16-Lead PDIP (Narrow 0.30 Inch)  
     

[05-08-1510\_N16](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc_legacy-pdip/05081510_I_N16.pdf)

PDIP

18-Lead PDIP (Narrow 0.3 Inch)  
     

[05-08-1510\_N18](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc_legacy-pdip/05081510_I_N18.pdf)

PDIP

20-Lead PDIP (Narrow 0.3 Inch)  
     

[05-08-1510\_N20](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc_legacy-pdip/05081510_I_N20.pdf)

PDIP

24-Lead PDIP (Narrow 0.3 Inch)  
     

[05-08-1510\_N24](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc_legacy-pdip/05081510_I_N24.pdf)

PDIP

28-Lead PDIP (Narrow 0.3 Inch)  
     

[05-08-1510\_N28](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc_legacy-pdip/05081510_I_N28.pdf)

PDIP

28-Lead PDIP (Wide 0.6 Inch)

[05-08-1520](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc_legacy-pdip/PDIP_28_05-08-1520.pdf)

PDIP

8-Lead PDIP (Narrow 0.3 Inch)  
    

[05-08-1510\_N8](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc_legacy-pdip/05081510_I_N8.pdf)

QFN

10-Lead QFN (2mm x 2mm x 0.75mm w/ EP)

[05-08-1534](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-qfn/05081534_%C3%98_UC10.pdf)

QFN

10-Lead QFN (3mm x 2mm x 0.75mm)

[05-08-1848](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-qfn/(UDB10)%20TQFN%2005-08-1848%20Rev%20A.pdf)

QFN

12-Lead QFN (3mm x 2mm x 0.75mm w/ EP)

[05-08-1855](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-qfn/QFN_12_%2005-08-1855.pdf)

QFN

12-Lead QFN (3mm x 2mm x 0.75mm)

[05-08-1941](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-qfn/05081941_A_UDB12.pdf)

QFN

12-Lead QFN (3mm x 2mm x 0.75mm)

[05-08-1985](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-qfn/05081985_%C3%98_UDB12.pdf)

QFN

16-Lead Plastic QFN

[05-08-1782](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-qfn/05081782_0_UD16-BB.pdf)

QFN

16-Lead Plastic Side Solderable QFN (4mm × 4mm)

[05-08-1799](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-qfn/05081799_0_ufm16.pdf)

QFN

16-Lead QFN (3mm x 3mm x 0.75mm w/ EP)

[05-08-1514](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-qfn/05081514_%C3%98_UD16(BB).pdf)

QFN

16-Lead QFN (3mm x 3mm x 0.75mm w/ EP)

[05-08-1691](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-qfn/QFN_16_05-08-1691.pdf)

QFN

16-Lead QFN (3mm x 3mm x 0.75mm w/ EP)

[05-08-1700](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-qfn/QFN_16_05-08-1700.pdf)

QFN

16-Lead QFN (4mm x 4mm x 0.75mm w/ EP)

[05-08-1692](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-qfn/QFN_16_05-08-1692.pdf)

QFN

16-Lead QFN (4mm x 6mm x 0.75mm w/ EP)

[05-08-1966](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-qfn/05081966_A_UFE16.pdf)

QFN

20(18)-Lead Plastic Side Wettable QFN (3mm × 4mm)

[05-08-7030](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-qfn/05087030_0_udcm(aa)20(18).pdf)

QFN

20(18)-Lead Plastic Side Wettable QFN (3mm × 4mm) 

[05-08-1617](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-lqfn/05081617_0_UDCF20-18.pdf)

QFN

20(18)-Lead QFN (3mm x 4mm x 0.75mm w/ EP)

[05-08-1956](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-qfn/05081956_C_UDC20(18)(AA).pdf)

QFN

20-Lead Plastic Side Solderable QFN (3mm × 4mm)

[05-08-1793](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-qfn/05081793_0_udcm20.pdf)

QFN

20-Lead QFN (3mm x 3mm x 0.75mm w/ EP)

[05-08-1720](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-qfn/QFN_20_05-08-1720.pdf)

QFN

20-Lead QFN (3mm x 4mm x 0.75mm w/ EP)

[05-08-1549](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-qfn/05081549_%C3%98_UDC20.pdf)

QFN

20-Lead QFN (3mm x 4mm x 0.75mm w/ EP)

[05-08-1742](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-qfn/QFN_20_05-08-1742.pdf)

QFN

20-Lead QFN (3mm x 4mm)

[05-08-1536](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-qfn/05081536_B_UDC20(AB).pdf)

QFN

20-Lead QFN (4mm x 4mm x 0.75mm w/ EP)

[05-08-1710](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-qfn/QFN_20_05-08-1710.pdf)

QFN

20-Lead QFN (4mm x 5mm x 0.75mm w/ EP)

[05-08-1711](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-qfn/QFN_20_05-08-1711.pdf)

QFN

20-Lead QFN (5mm x 5mm x 0.75mm w/ EP)

[05-08-1818](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-qfn/QFN_20_05-08-1818.pdf)

QFN

24-Lead Plastic Side Solderable QFN (3mm × 5mm)

[05-08-1795](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-qfn/05081795_0_uddm24.pdf)

QFN

24-Lead QFN (3mm x 4mm x 0.75mm w/ EP)

[05-08-1745](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-qfn/QFN_24_05-08-1745.pdf)

QFN

24-Lead QFN (3mm x 5mm x 0.75mm w/ EP)

[05-08-1537](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-qfn/05081537_%C3%98_UDD24(AA).pdf)

QFN

24-Lead QFN (3mm x 5mm x 0.75mm w/ EP)

[05-08-1833](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-qfn/(UDD24)%20QFN%2005-08-1833%20Rev%20%C3%98.pdf)

QFN

24-Lead QFN (4mm x 4mm x 0.75mm w/ EP)

[05-08-1697](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-qfn/(UF24)%20QFN%2005-08-1697%20Rev%20B.pdf)

QFN

24-Lead QFN (4mm x 5mm x 0.75mm w/ EP)

[05-08-1505](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-qfn/05081505_%C3%98_UFD24.pdf)

QFN

24-Lead QFN (4mm x 5mm x 0.75mm w/ EP)

[05-08-1696](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-qfn/QFN_24_05-08-1696.pdf)

QFN

24-Lead QFN (5mm x 5mm x 0.75mm w/ EP)

[05-08-1747](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-qfn/(UH24)%20QFN%2005-08-1747%20Rev%20A.pdf)

QFN

24-Lead QFN (7mm x 7mm x 0.75mm w/ EP)

[05-08-1981](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-qfn/(TLA24)_TLUK_QFN_05-08-1981_Rev_%C3%98_.pdf)

QFN

26-Lead QFN (6mm x 4mm x 0.75mm w/ EP)

[05-08-1770](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-qfn/05081770_B_UFE26MA.pdf)

QFN

28-Lead QFN (3mm x 6mm x 0.75mm w/ EP)

[05-08-1926](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-qfn/05081926_0_UDE28.pdf)

QFN

28-Lead QFN (4mm x 4mm x 0.75mm w/ EP)

[05-08-1721](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-qfn/QFN_28_05-08-1721.pdf)

QFN

28-Lead QFN (4mm x 4mm x 0.75mm w/ EP)

[05-08-1866](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-qfn/QFN_28_05-08-1866.pdf)

QFN

28-Lead QFN (4mm x 5mm

[05-08-1682](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-qfn/05081682_0_ufdm28qfn.pdf)

QFN

28-Lead QFN (4mm x 5mm x 0.75mm w/ EP)

[05-08-1538](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-qfn/05081538_A_UFD28.pdf)

QFN

28-Lead QFN (4mm x 5mm x 0.75mm w/ EP)

[05-08-1546](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-qfn/05081546_%C3%98_UPFD28.pdf)

QFN

28-Lead QFN (4mm x 5mm x 0.75mm w/ EP)

[05-08-1712](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-qfn/05081712_C_UFD28.pdf)

QFN

28-Lead QFN (5mm x 6mm x 0.75mm w/ EP)

[05-08-1932](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-qfn/05081932_0_UHE28.pdf)

QFN

32-Lead QFN (4mm x 6mm x 0.75mm w/ EP)

[05-08-1938](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-qfn/05081938_B_UFE32MA.pdf)

QFN

32-Lead QFN (4mm x 7mm x 0.75mm w/ EP)

[05-08-1758](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-qfn/QFN_34_05-08-1758.pdf)

QFN

32-Lead QFN (5mm x 5mm x 0.75mm w/ EP)

[05-08-1693](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-qfn/QFN_32_05-08-1693.pdf)

QFN

32-Lead QFN (5mm x 7mm x 0.75mm w/ EP)

[05-08-1555](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-qfn/05081555_%C3%98_WHF32.pdf)

QFN

36-Lead Plastic Side Solderable QFN (4mm × 7mm)

[05-08-8033](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-qfn/05088033_0_uffm36.pdf)

QFN

36-Lead QFN (4mm x 5mm x 0.75mm w/ EP)

[05-08-1575](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-qfn/05081575_%C3%98_UFD36.pdf)

QFN

36-Lead QFN (4mm x 7mm x 0.75mm w/ EP)

[05-08-1863](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-qfn/(UFF36)%20QFN%2005-08-1863%20Rev%20%C3%98.pdf)

QFN

36-Lead QFN (5mm x 6mm x 0.75mm w/ EP)

[05-08-1753](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-qfn/(UHE36MA)%20QFN%2005-08-1753%20Rev%20A.pdf)

QFN

36-Lead QFN (5mm x 6mm x 0.75mm w/ EP)

[05-08-1836](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-qfn/QFN_28_05-08-1836.pdf)

QFN

36-Lead QFN (5mm x 6mm x 0.75mm w/ EP)

[05-08-1876](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-qfn/(UHE36)%20QFN%2005-08-1876%20Rev%20%C3%98.pdf)

QFN

36-Lead QFN (5mm x 6mm x 0.75mm w/ EP)

[05-08-1983](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-qfn/05081983_%C3%98_UHE36.pdf)

QFN

36-Lead Side Solderable Plastic QFN (5mm × 6mm) 

[05-08-1794](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-qfn/05081794_0_uhem36.pdf)

QFN

38-Lead Plastic QFN (5mm × 7mm) 

[05-08-1598](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-qfn/UHF38-QFN-05-08-1598-Rev0.pdf)

QFN

38-Lead Plastic QFN (5mm × 9mm)

[05-08-1934](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-qfn/05081934_A_(WHH38)%20QFN.pdf)

QFN

38-Lead Plastic Side Wettable QFN

[05-08-1781](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-qfn/05081781_0_UHFM38.pdf)

QFN

38-Lead QFN (4mm x 6mm x 0.75mm w/ EP)

[05-08-1750](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-qfn/QFN_38_05-08-1750.pdf)

QFN

38-Lead QFN (5mm x 7mm w/ EP)

[05-08-1701](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-qfn/QFN_38_05-08-1701.pdf)

QFN

40-Lead QFN (5mm x 5mm x 0.75mm w/ EP)

[05-08-1746](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-qfn/05081746_B_UH40.pdf)

QFN

40-Lead QFN (5mm x 7mm x 0.75mm w/ EP)

[05-08-1951](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-qfn/(UHF40)_QFN_05-08-1951_Rev_%C3%98.pdf)

QFN

40-Lead QFN (5mm x 8mm x 0.75mm w/ EP)

[05-08-1528](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-qfn/05081528_A_UHG40.pdf)

QFN

40-Lead QFN (6mm x 6mm

[05-08-1681](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-qfn/05081681_0_ujm40qfn.pdf)

QFN

40-Lead QFN (6mm x 6mm x 0.75mm w/ EP)

[05-08-1545](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-qfn/05081545_%C3%98_UPJ40.pdf)

QFN

40-Lead QFN (6mm x 6mm x 0.75mm w/ EP)

[05-08-1728](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-qfn/QFN_40_05-08-1728.pdf)

QFN

42-Lead QFN (5mm x 5mm x 0.75mm w/ EP)

[05-08-1875](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-qfn/05081875_0_UHE42.pdf)

QFN

44(38)-Lead Plastic QFN (5mm × 8mm) 

[05-08-1616](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-qfn/05081616_0_UHG44-38.pdf)

QFN

44-Lead QFN (4mm x 7mm x 0.75mm w/ EP)

[05-08-1762](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-qfn/QFN_44_05-08-1762.pdf)

QFN

44-Lead QFN (5mm x 8mm x 0.75mm w/ EP)

[05-08-1581](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-qfn/05081581_%C3%98_UHG44.pdf)

QFN

44-Lead QFN (6mm x 7mm x 0.75mm w/ EP)

[05-08-1501](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-qfn/05081501_%C3%98_UJF44.pdf)

QFN

44-Lead QFN (7mm x 7mm x 0.75mm w/ EP)

[05-08-1763](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-qfn/QFN_44_05-08-1763.pdf)

QFN

48(39) Lead Plastic QFN (7mm x 7mm x 0.75mm w/ 5.4mm x 3.65mm EP) (05-08-1792) 

[05-08-1792](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-lqfn/05081792_0_uk48(39).pdf)

QFN

48-Lead QFN (5mm x 9mm x 0.75mm w/ EP)

[05-08-1845](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-qfn/QFN_48_05-08-1845.pdf)

QFN

48-Lead QFN (7mm x 7mm

[05-08-1685](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-qfn/05081685_0_ukm48qfn.pdf)

QFN

48-Lead QFN (7mm x 7mm x 0.75mm w/ EP)

[05-08-1704](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-qfn/QFN_48_05-08-1704.pdf)

QFN

52-Lead QFN (5mm x 8mm x 0.75mm w/ EP)

[05-08-1507](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-qfn/05081507_%C3%98_UHG52.pdf)

QFN

52-Lead QFN (5mm x 8mm x 0.75mm w/ EP)

[05-08-1846](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-qfn/QFN_52_05-08-1846.pdf)

QFN

52-Lead QFN (7mm x 7mm x 0.75mm w/ EP)

[05-08-1768](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-qfn/05081768_C_WKG52.pdf)

QFN

52-Lead QFN (7mm x 8mm x 0.75mm w/ EP)

[05-08-1729](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-qfn/QFN_52_05-08-1729.pdf)

QFN

52-Lead QFN (7mm x 8mm x 0.75mm w/ EP)

[05-08-1874](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-qfn/(UKG52)(47)%20QFN%2005-08-1874%20Rev%20%C3%98.pdf)

QFN

52-Lead QFN (7mm x 8mm x 0.75mm w/ EP)

[05-08-1947](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-qfn/05081947_0_UKG52(46).pdf)

QFN

52-Lead QFN (7mm x 8mm x 0.75mm w/ EP)

[05-08-1984](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-qfn/05081984_%C3%98_UKG52.pdf)

QFN

56-Lead QFN (5mm x 9mm x 0.75mm w/ EP)

[05-08-1727](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-qfn/05081727_B_UHH56.pdf)

QFN

56-Lead QFN (6mm x 6mm x 0.75mm w/ EP)

[05-08-1968](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-qfn/05081968_C_TJ56.pdf)

QFN

56-Lead QFN (7mm x 7mm x 0.75mm w/ EP)

[05-08-1870](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-qfn/(WKH56)_QFN_05-08-1870_Rev_A.pdf)

QFN

58-Lead QFN (5mm x 9mm x 0.75mm w/ EP)

[05-08-1672](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-qfn/05081672_%C3%98_UHH58(AA).pdf)

QFN

58-Lead QFN (5mm x 9mm x 0.75mm w/ EP)

[05-08-1995](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-qfn/05081995_%C3%98_UHH58.pdf)

QFN

64-Lead Plastic QFN (7mm × 11mm)

[05-08-1780](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-lqfn/05081780_0_qfn(ukj)64.pdf)

QFN

64-Lead QFN (7mm x 11mm x 0.75mm w/ EP)

[05-08-1853](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-qfn/QFN_64_05-08-1853.pdf)

QFN

64-Lead QFN (7mm x 11mm x 0.75mm w/ EP)

[05-08-1922](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-qfn/05081992_0_UKJ64(58).pdf)

QFN

64-Lead QFN (7mm x 9mm w/ EP)

[05-08-1741](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-qfn/QFN_64_%2005-08-1741.pdf)

QFN

64-Lead QFN (9mm x 9mm x 0.75mm w/ EP)

[05-08-1705](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-qfn/QFN_64_05-08-1705.pdf)

QFN

64-Lead QFN (9mm x 9mm x 0.9mm w/ EP)

[05-08-1812](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-qfn/05081812_D_WP64.pdf)

QFN

68-Lead QFN (7mm x 12mm x 0.75mm w/ EP)

[05-08-1862](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-qfn/QFN_68_05-08-1862.pdf)

QFN

72-Lead QFN (10mm x 10mm x 1mm w/ EP)

[05-08-1930](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-qfn/05081930_A_WR72.pdf)

QFN

76-Lead QFN (7mm x 7mm x 0.78mm w/ EP)

[05-08-1989](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-qfn/05081989_B_TK76.pdf)

SC-70

6-Lead SC70

[05-08-1638](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-sc-70/SOT_6_05-08-1638.pdf)

SC-70

8-Lead SC70

[05-08-1639](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-sc-70/SOT_8_05-08-1639.pdf)

SOIC

14-Lead SOIC (Narrow 0.15 Inch)  
     

[05-08-1610\_S14](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-soic/05081610_G_S14.pdf)

SOIC

16-Lead SOIC (Narrow 0.15 Inch)  
     

[05-08-1610\_S16](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-soic/S16%2005-08-1610%20Rev%20G.pdf)

SOIC

16-Lead SOIC (Wide 0.3 Inch)  
      

[05-08-1620\_SW16](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-soic/SO_16_05-08-1620.pdf)

SOIC

18-Lead SOIC (Wide 0.3 Inch)  
      

[05-08-1620\_SW18](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-soic/SO_18_05-08-1620.pdf)

SOIC

20-Lead SOIC (Wide 0.3 Inch)  
      

[05-08-1620\_SW20](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-soic/SO_20_05-08-1620.pdf)

SOIC

24-Lead SOIC (Wide 0.3 Inch)  
      

[05-08-1620\_SW24](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-soic/SO_24_05-08-1620.pdf)

SOIC

28-Lead SOIC (Wide 0.3 Inch)  
      

[05-08-1620\_SW28](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-soic/SO_28_05-08-1620.pdf)

SOIC

8-Lead Plastic SOIC (Narrow .150 Inch) Exposed Pad

[05-08-1796](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-soic/05081796_0_S8E8.pdf)

SOIC

8-Lead SOIC (Narrow 0.15 Inch w/ EP)

[05-08-1857](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-soic/05081857_C_S8E.pdf)

SOIC

8-Lead SOIC (Narrow 0.15 Inch)  
    

[05-08-1610\_S8](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-soic/05081610_G_SO8.pdf)

SOT-223

3-Lead SOT-223

[05-08-1630](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-sot-223/SOT_3_05-08-1630.pdf)

SOT-23

3-Lead SOT-23

[05-08-1631](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-sot-23/SOT3%2005-08-1631%20Rev%20D.pdf)

SOT-23

4-Lead SOT-23

[05-08-1632](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-sot-23/SOT_4_05-08-1632.pdf)

SOT-23

5-Lead SOT-23

[05-08-1635](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-sot-23/SOT_5_05-08-1635.pdf)

SOT-23

6-Lead SOT-23

[05-08-1636](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-sot-23/SOT_6_05-08-1636.pdf)

SOT-23

8-Lead SOT-23

[05-08-1637](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-sot-23/SOT_8_05-08-1637.pdf)

SSOP

16-Lead SSOP (Narrow 0.15 Inch)  
      

[05-08-1641\_GN16](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-ssop/05081641_B_GN16.pdf)

SSOP

16-Lead SSOP  
     

[05-08-1640\_G16](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-ssop/SSOP_16_05-08-1640.pdf)

SSOP

20-Lead SSOP (Narrow 0.15 Inch)  
      

[05-08-1641\_GN20](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-ssop/05081641_B_GN20.pdf)

SSOP

20-Lead SSOP  
     

[05-08-1640\_G20](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-ssop/SSOP_20_05-08-1640.pdf)

SSOP

24-Lead SSOP (Narrow 0.15 Inch)  
      

[05-08-1641\_GN24](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-ssop/05081641_B_GN24.pdf)

SSOP

24-Lead SSOP  
     

[05-08-1640\_G24](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-ssop/SSOP_24_05-08-1640.pdf)

SSOP

28-Lead SSOP (Narrow 0.15 Inch)  
      

[05-08-1641\_GN28](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-ssop/05081641_B_GN28.pdf)

SSOP

28-Lead SSOP  
     

[05-08-1640\_G28](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-ssop/SSOP_28_05-08-1640.pdf)

SSOP

36-Lead SSOP (Wide 0.3 Inch)  
      

[05-08-1642\_GW36](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-ssop/SSOP_36_05-08-1642.pdf)

SSOP

36-Lead SSOP  
     

[05-08-1640\_G36](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-ssop/SSOP_36_05-08-1640.pdf)

SSOP

44-Lead SSOP

[05-08-1754](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-ssop/05081754_A_G44.pdf)

SSOP

44-Lead SSOP (Wide 0.3 Inch)  
      

[05-08-1642\_GW44](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-ssop/SSOP_44_05-08-1642.pdf)

SSOP

48-Lead SSOP

[05-08-1887](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-ssop/05081887_A_G48.pdf)

TO-220

3-Lead TO-220

[05-08-1420](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-to-220/TO-220_3_05-08-1420.pdf)

TO-220

3-Lead TO-220 (Flow 32)

[05-08-1492](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-to-220/TO-220_3_05-08-1492.pdf)

TO-220

3-Lead TO-220 (Flow 34)

[05-08-1494](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-to-220/TO-220_3_05-08-1494.pdf)

TO-220

3-Lead TO-220 (Flow 36)

[05-08-1496](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-to-220/TO-220_3_05-08-1496.pdf)

TO-220

3-Lead TO-220 (Flow 41)

[05-08-1481](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-to-220/TO-220_3_05-08-1481.pdf)

TO-220

3-Lead TO-220 (Flow 43)

[05-08-1483](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-to-220/TO-220_3_05-08-1483.pdf)

TO-220

5-Lead TO-220 (Flow 06)  
         

[05-08-1421\_Flow06](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-to-220/TO-220_5_05-08-1421_STRAIGHT_LEAD.pdf)

TO-220

5-Lead TO-220 (Flow 30)

[05-08-1490](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-to-220/TO-220_5_05-08-1490.pdf)

TO-220

5-Lead TO-220 (Flow 31)

[05-08-1491](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-to-220/TO-220_5_05-08-1491.pdf)

TO-220

5-Lead TO-220 (Flow 33)

[05-08-1493](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-to-220/TO-220_5_05-08-1493.pdf)

TO-220

5-Lead TO-220 (Flow 38)

[05-08-1498](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-to-220/T05%20(TO-220)(Flow%2038).pdf)

TO-220

5-Lead TO-220 (Flow 40)

[05-08-1480](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-to-220/TO-220_5_05-08-1480.pdf)

TO-220

5-Lead TO-220  
     

[05-08-1421\_STD](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-to-220/TO-220_5_05-08-1421.pdf)

TO-220

7-Lead TO-220 (Flow 06)  
         

[05-08-1422\_Flow06](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-to-220/TO-220_7_05-08-1422_STRAIGHT_LEAD.pdf)

TO-220

7-Lead TO-220 (Flow 35)

[05-08-1495](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-to-220/TO-220_7_05-08-1495.pdf)

TO-220

7-Lead TO-220 (Flow 37)

[05-08-1497](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-to-220/TO-220_7_05-08-1497.pdf)

TO-220

7-Lead TO-220 (Flow 44)

[05-08-1484](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-to-220/TO-220-7_05-08-1484.pdf)

TO-220

7-Lead TO-220 (Flow 45)

[05-08-1485](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-to-220/T07%20(TO-220)(Flow%2045).pdf)

TO-220

7-Lead TO-220  
     

[05-08-1422\_STD](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-to-220/TO-220_7_05-08-1422.pdf)

TO-247

3-Lead TO-3P

[05-08-1450](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-to-247/P3(TO-3P)%2005-08-1450%20Rev%20A.pdf)

TO-257

3-Lead TO-257

[05-08-1360](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-to-257/TO-257_3_05-08-1360.pdf)

TO-92

3-Lead TO-92

[05-08-1410](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-to-92/TO-92_3_05-08-1410.pdf)

TO-XX

10-Lead TO-5

[05-08-1322](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-to-xx/MetalCan_10_05-08-1322.pdf)

TO-XX

3-Lead TO-39

[05-08-1330](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-to-xx/MetalCan_3_05-08-1330.pdf)

TO-XX

3-Lead TO-46

[05-08-1340](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-to-xx/MetalCan_2_3_05-08-1340.pdf)

TO-XX

3-Lead TO-52

[05-08-1350](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-to-xx/MetalCan_3_05-08-1350.pdf)

TO-XX

4-Lead TO-39

[05-08-1331](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-to-xx/MetalCan_4_05-08-1331.pdf)

TO-XX

4-Lead TO-46

[05-08-1341](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-to-xx/MetalCan_4_05-08-1341.pdf)

TO-XX

8-Lead TO-5 (0.2 Inch PCD)

[05-08-1320](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-to-xx/MetalCan_8_05-08-1320.pdf)

TO-XX

8-Lead TO-5 (0.23 Inch PCD)

[05-08-1321](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-to-xx/MetalCan_8_05-08-1321.pdf)

TQFP

32-Lead TQFP (5mm x 5mm w/ EP)

[05-08-1986](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-tqfp/05081986_A_LUE32.pdf)

TQFP

32-Lead TQFP (5mm x 5mm)

[05-08-1735](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-tqfp/TQFP_32_05-08-1735.pdf)

TSSOP

14-Lead TSSOP  
     

[05-08-1650\_F14](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-tssop/TSSOP_14_05-08-1650.pdf)

TSSOP

16-Lead TSSOP w/ EP  
    

[05-08-1663\_BA](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-tssop/05081663_L_FE16(BA).pdf)

TSSOP

16-Lead TSSOP w/ EP  
    

[05-08-1663\_BB](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-tssop/05081663_K_FE16(BB).pdf)

TSSOP

16-Lead TSSOP w/ EP  
    

[05-08-1663\_BC](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-tssop/05081663_K_FE16(BC).pdf)

TSSOP

20-Lead TSSOP w/ EP

[05-08-1924](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-tssop/05081924_0_FE20(16)(CB).pdf)

TSSOP

20-Lead TSSOP w/ EP

[05-08-1950](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-tssop/05081950_0_FE20(CC).pdf)

TSSOP

20-Lead TSSOP w/ EP

[05-08-1990](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-tssop/05081990_%C3%98_FE20(16)(BB).pdf)

TSSOP

20-Lead TSSOP w/ EP  
    

[05-08-1663\_CA](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-tssop/05081663_K_FE20(CA).pdf)

TSSOP

20-Lead TSSOP w/ EP  
    

[05-08-1663\_CB](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-tssop/05081663_K_FE20(CB).pdf)

TSSOP

20-Lead TSSOP  
     

[05-08-1650\_F20](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-tssop/TSSOP_20_05-08-1650.pdf)

TSSOP

24-Lead TSSOP w/ EP

[05-08-1771](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-tssop/TSSOP_24_05-08-1771.pdf)

TSSOP

28-Lead TSSOP w/ EP  
    

[05-08-1663\_EA](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-tssop/05081663_K_FE28(EA).pdf)

TSSOP

28-Lead TSSOP w/ EP  
    

[05-08-1663\_EB](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-tssop/05081663_K_FE28(EB).pdf)

TSSOP

38-Lead TSSOP w/ EP

[05-08-1772](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-tssop/TSSOP_38_05-08-1772.pdf)

TSSOP

38-Lead TSSOP w/ EP

[05-08-1779](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-tssop/05081779_0_FE38(AC).pdf)

TSSOP

38-Lead TSSOP w/ EP

[05-08-1865](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-tssop/TSSOP_38_05-08-1865.pdf)

TSSOP

38-Lead TSSOP w/ EP

[05-08-1917](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-tssop/05081917_0_FTE38.pdf)

TSSOP

48-Lead TSSOP

[05-08-1651](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-tssop/TSSOP_48_05-08-1651.pdf)

TSSOP

56-Lead TSSOP

[05-08-1652](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-tssop/TSSOP_56_05-08-1652.pdf)

UTDFN 

20-Lead UTQFN (3mm x 3mm x 0.55mm w/ EP)

[05-08-1835](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-utqfn/UTQFN_20_%2005-08-1835.pdf)

UTDFN 

20-Lead UTQFN (3mm x 4mm x 0.55mm w/ EP)

[05-08-1752](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-utqfn/UTQFN_20_05-08-1752.pdf)

UTDFN 

24-Lead UTQFN (4mm x 4mm x 0.55mm w/ EP)

[05-08-1834](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-utqfn/UTQFN_24_05-08-1834.pdf)

UTDFN 

28-Lead UTQFN (4mm x 4mm x 0.55mm w/ EP)

[05-08-1759](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-utqfn/(PF28)%20UTQFN%2005-08-1759%20Rev%20%C3%98.pdf)

UTQFN

16-Lead UTQFN (3mm x 3mm x 0.55mm w/ EP)

[05-08-1738](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-utqfn/UTQFN_16_05-08-1738.pdf)

UTQFN

24-Lead UTQFN (4mm x 4mm x 0.55mm w/ EP)

[05-08-1748](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-utqfn/UTQFN_24_05-08-1748.pdf)

Analog Devices Case Code
------------------------

封装描述

Case Code

24-Lead LFCSP (4mm x 4mm w/ EP)

[cp-24-2](https://www.analog.com/media/en/package-pcb-resources/package/588305704543880784658541cp_24_2.pdf)

10-Lead LFCSP (2mm x 3mm w/ EP)

[cp-10-12](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lfcspcp/cp_10_12.pdf)

40-Lead LFCSP (6mm x 6mm w/ EP)

[cp-40-1](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lfcspcp/cp_40_1.pdf)

124-Ball CSPBGA (15mm x 15mm)

[bc-124-2](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/cspbga-bc/bc_124_2.pdf)

176-Lead LQFP (24mm x 24mm w/ EP)

[sq-176-1](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lqfp_edsq/sq_176_1.pdf)

10-Lead LFCSP (4mm x 4mm x 0.65mm w/ EP)

[CP-10-14](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lfcspcp/cp-10/CP_10_14.pdf)

32-Lead LFCSP (5mm x 5mm x 0.75mm w/ EP)

[cp-32-21](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lfcspcp/cp-32/CP_32_21.pdf)

8-Lead LFCSP (2mm x 2mm w/ EP)

[cp-8-8](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lfcspcp/cp_8_8.pdf)

80-Lead TQFP (12mm x 12mm w/ EP)

[sv-80-2](https://www.analog.com/media/en/package-pcb-resources/package/4006832525359956539sv_80_2.pdf)

100-Lead MQFP (14mm x 20mm)

[s-100-3](https://www.analog.com/media/en/package-pcb-resources/package/24359501s_100_3.pdf)

9-Ball WLCSP (1.26mm x 1.26mm x 0.50mm)

[cb-9-8](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/wlcspcb/CB_9_8.pdf)

84-Ball CSPBGA (6mm x 6mm x 1.26mm)

[bc-84-1](https://www.analog.com/media/en/package-pcb-resources/package/3173555732137686576bc_84_1.pdf)

6-Lead LGA\_CAV (4.76mm x 3.76mm)

[ce-6-1](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lga_cavce/ce_6_1.pdf)

16-Lead LFCSP (4mm x 4mm w/ EP)

[cp-16-9](https://www.analog.com/media/en/package-pcb-resources/package/43737455216358834709492cp_16_9.pdf)

8-Lead SOT-23

[rj-8](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/sot-23rj/RJ_8.pdf)

64-Lead LFCSP (9mm x 9mm x 0.75mm w/ EP)

[cp-64-17](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lfcspcp/cp-64/CP_64_17.pdf)

12-Pin TO-8

[h-12](https://www.analog.com/media/en/package-pcb-resources/package/280776812h_12.pdf)

4-Lead LFCSP (2mm x 3mm x 0.95mm w/ EP)

[cp-4-2](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lfcspcp/cp_4_2.pdf)

72-Lead LFCSP (10mm x 10mm w/ EP)

[cp-72-10](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lfcspcp/cp-72/CP_72_10.pdf)

260-Ball PBGA (19mm x 16.95mm)

[b-260](https://www.analog.com/media/en/package-pcb-resources/package/4532729474093b_260.pdf)

48-Lead LQFP\_EP (7mm x 7mm x 1.60mm w/ EP

[SW-48-1](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lqfp_edsw/sw-48-1.pdf)

196-Ball CSP-BGA (12mm x 12mm x 1.24mm)

[BC-196-9](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/cspbga-bc/BC_196_9.pdf)

52-Lead LQFP\_EP (14mm x 14mm x 1.4mm)

[SW-52-1](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lqfp_edsw/SW_52_1.pdf)

15-Lead SIP

[y-15](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/sipy/y_15.pdf)

16-Lead LFCSP (4mm x 4mm w/ EP)

[cp-16-14](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lfcspcp/cp-16/cp_16_14.pdf)

32-Lead LFCSP (5mm x 5mm x 0.85mm w/ EP)

[cp-32-10](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lfcspcp/cp_32_10.pdf)

256-Ball BGA\_ED (27mm x 27mm x 1.9mm)

[BP-256-3](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/bga_ed-bp/bp_256_3.pdf)

24-Lead TSSOP w/ EP

[re-24](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/tssop_epre/re_24.pdf)

10-Lead LDCC (11.43mm x 17.32mm

[ej-10-1](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ldcc-leaded-chip-carrier/EJ-10-1.pdf)

56-Lead LFCSP (8mm x 8mm w/ EP)

[cp-56-2](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lfcspcp/cp-56/cp_56_2.pdf)

24-Lead Module with Connector Interface

[ml-24-2](https://www.analog.com/media/en/package-pcb-resources/package/332229597ml_24_2.pdf)

24-Lead QFN (4mm x 4mm w/ EP

[hcp-24-3](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/hittite-legacy-packages/HCP-24-3.pdf)

124-Ball CSPBGA (9mm x 9mm x 1.4mm)

[bc-124-1](https://www.analog.com/media/en/package-pcb-resources/package/63567309174006bc_124_1.pdf)

6-Ball WLCSP (1mm x 1.5mm)

[cb-6-2](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/wlcspcb/CB_6_2.pdf)

176-Lead LQFP (24mm x 24mm)

[st-176](https://www.analog.com/media/en/package-pcb-resources/package/274678845st_176.pdf)

23-Ball WLCSP (2.22mm x 2.34mm x 0.5mm)

[CB-23-2](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/wlcspcb/CB_23_2.pdf)

7-Lead SMT

[FR-7-1](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/flatpack-f/FR-7-1.pdf)

12-Lead LFCSP (4mm x 4mm w/ EP

[cs-12-3](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lfcsp-cs-side-solderable/cs-12/CS_12_3.pdf)

225-Ball CSPBGA (17mm x 17mm)

[bc-225-1](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/cspbga-bc/BC_225_1.pdf)

Connectorized Hermetic Module (C

[hml-16](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/hittite-legacy-packages/HML-16.pdf)

144-Lead LQFP (10mm x 10mm w/ EP)

[sw-144-1](https://www.analog.com/media/en/package-pcb-resources/package/32960356620991sw_144_1.pdf)

8-Lead SOIC w/ EP

[RD-8-2](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/soic_edrd/RD_8_2.pdf)

24-Lead LFCSP (3.5mm x 3.5mm w/ EP)

[cp-24-11](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lfcspcp/cp_24_11.pdf)

13-Lead LGA (5mm x 5mm)

[cc-13-1](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lgacc/CC_13_1.pdf)

297-Ball PBGA (27mm x 27mm)

[b-297](https://www.analog.com/media/en/package-pcb-resources/package/251630103b_297.pdf)

237-Ball CSPBGA (13mm x 13mm x 1.4mm)

[bc-237-2](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/cspbga-bc/bc_237_2.pdf)

16-Lead LFCSP (3mm x 3mm w/ EP)

[cp-16-21](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lfcspcp/cp-16/CP_16_21.pdf)

9-Ball WLCSP (1.515mm x 1.69mm)

[cb-9-1](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/wlcspcb/cb_9_1.pdf)

8-Ball WLCSP (0.8mm x 1.56mm)

[cb-8-6](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/wlcspcb/CB_8_6.pdf)

49-Ball WLCSP (4.04 mm x 4.04 mm x 0.60 mm)

[cb-49-5](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/wlcspcb/CB_49_5.pdf)

8-Lead LCC w/ EP

[hlce-8-1](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/hittite-legacy-packages/HLCE-8-1.pdf)

32-Lead QFN (5mm x 5mmx.75 w/ 3.6EP)

[hcp-32-12](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/hittite-legacy-packages/CP_32_12.pdf)

10-Lead FlatPack

[f-10-1](https://www.analog.com/media/en/package-pcb-resources/package/260162565f_10.pdf)

72-Lead LFCSP (10mm x 10mm w/ EP)

[cp-72-7](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lfcspcp/cp_72_7.pdf)

48-Lead LQFP (7mm x 7mm)

[st-48](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lqfpst/ST_48.pdf)

28-Lead TSSOP (6.1mm x 9.7mm)

[rv-28](https://www.analog.com/media/en/package-pcb-resources/package/108212315rv_28.pdf)

208-Lead LQFP (28mm x 28mm w/ EP)

[sw-208-2](https://www.analog.com/media/en/package-pcb-resources/package/sw_208_2.pdf)

8-Lead LGA\_CAV (5.08mm x 5.08mm)

[CE-8-1](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lga_cavce/CE-8-1.pdf)

6-Lead LFCSP (1.6mm x 1.6mm w/ EP)

[cp-6-4](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lfcspcp/cp_6_4.pdf)

14-Lead LCC (6mm x 6mm)

[e-14-1](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lcce/E_14_1.pdf)

8-Lead SMT (4.83mm x 4.83mm)

[hrj-8-2](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/hittite-legacy-packages/HRJ-8-2.pdf)

196-Ball CSPBGA (15mm x 15mm x 1.7mm)

[bc-196-3](https://www.analog.com/media/en/package-pcb-resources/package/5193887552279bc_196_3.pdf)

16-Lead LGA\_CAV (4mm x 3mm x 1.2mm)

[ce-16-3](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lga_cavce/CE_16_3.pdf)

49-Ball CSPBGA (8mm x 8mm)

[bc-49-3](https://www.analog.com/media/en/package-pcb-resources/package/5225654635437328832bc_49_3.pdf)

576-Ball SBGA (25mm x 25mm)

[bp-576](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/bga_ed-bp/bp_576.pdf)

48-Lead LFCSP (7mm x 7mm w/ EP)

[cp-48-12](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lfcspcp/cp_48_12.pdf)

6-Lead SOIC (Increased Creepage)

[ri-6-1](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/soic_wide-rw/RI_6_1.pdf)

16-Lead LFCSP (3mm x 3mm x 0.75mm)

[cp-16-32](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lfcspcp/cp-16/CP_16_32.pdf)

8-Lead TSSOP

[ru-8](https://www.analog.com/media/en/package-pcb-resources/package/359224089841708504863856053953356548880ru08.pdf)

64-Lead LQFP (10mm x 10mm)

[st-64-2](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lqfpst/st_64_2.pdf)

48-Lead LFCSP (7mm x 7mm x 0.85mm w/ EP)

[cp-48-6](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lfcspcp/cp_48_6.pdf)

8-Lead PDIP

[n-8](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/pdipn/n_8.pdf)

10-Lead LFCSP (3mm x 4mm x 0.65mm w/ EP)

[CP-10-13](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lfcspcp/cp-10/CP_10_13.pdf)

80-Lead TQFP (14mm x 14mm w/ EP)

[sv-80-4](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/tqfp_edsv/sv_80_4.pdf)

12-Ball WLCSP (1.665mm x 2.245mm)

[cb-12-9](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/wlcspcb/CB_12_9.pdf)

3-Lead TO-52

[h-03-1](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/headerh/h_03_1.pdf)

11-Ball WLCSP (2.04mm x 1.57mm)

[cb-11-1](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/wlcspcb/cb_11_1.pdf)

32-Lead LFCSP (5mm x 5mm x 0.85mm w/ EP)

[cp-32-11](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lfcspcp/cp-32/cp_32_11.pdf)

6-Lead LFCSP (2mm x 2mm w/ EP)

[cp-6-3](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lfcspcp/cp_6_3.pdf)

256-Ball CSPBGA (17mm x 17mm)

[bc-256-2](https://www.analog.com/media/en/package-pcb-resources/package/5685336469362195555bc_256_2.pdf)

24-Lead LFCSP (4mm x 5mm w/ EP)

[cp-24-14](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lfcspcp/cp_24_14.pdf)

24-Lead QSOP

[hrq-24-1](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/hittite-legacy-packages/HRQ-24-1.pdf)

20-Lead LGA

[cc-20-6](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lgacc/CC_20_6.pdf)

6-Lead LFCSP (2.05mm x 2.05mm w/ EP)

[cp-6-7](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lfcspcp/cp-6/CP_6_7.pdf)

24-Lead LGA\_CAV (3.8mm x 5mm x 0.9mm)

[ce-24-1](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lga_cavce/CE_24_1.pdf)

49-Ball WLCSP (3.96mm x 3.96mm)

[cb-49-4](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/wlcspcb/CB_49_4.pdf)

16-Lead LFCSP (4mm x 4mm w/ EP)

[cp-16-23](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lfcspcp/cp_16_23.pdf)

28 ld LGA (6mm x 6mm w/4 EP)

[cc-28-3](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lgacc/CC_28_3.pdf)

40-Lead Side-Brazed CerDIP

[d-40-1](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/sb_cerdipd/D_40_1.pdf)

24-Lead LFCSP (4mm x 4mm w/ EP)

[cp-24-16](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lfcspcp/cp-24/cp_24_16.pdf)

8-Lead LFCSP (2.44mm x 1.6mm w/ EP)

[cp-8-19](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lfcspcp/CP_8_19.pdf)

32-Lead LFCSP (5mm x 5mm x 0.75mm w/ EP)

[CP-32-12](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lfcspcp/cp-32/CP_32_12.pdf)

4-Ball WLCSP (0.965mm x 0.965mm)

[cb-4-1](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/wlcspcb/CB_4_1.pdf)

18-Lead Side-Brazed CerDIP

[d-18](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/sb_cerdipd/d_18.pdf)

3-Lead TO-92

[t-3-1](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/to-92t/T-3-1.pdf)

32-Lead LFCSP (5mm x 5mm w/ EP)

[cp-32-27](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lfcspcp/cp-32/CP_32_27.pdf)

100-Lead TQFP (14mm x 14mm w/ EP)

[sv-100-1](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/tqfp_edsv/sv_100_1.pdf)

8-Lead QSOP w/ EP

[hrc-8-1](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/hittite-legacy-packages/HRC-8-1.pdf)

60-Terminal LGA (9mm x 9mm x 0.73mm w/EP)

[CC-60-1](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lgacc/CC_60_1.pdf)

24-Lead LGA (5mm x 4mm x 1.65mm)

[cc-24-2](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lgacc/CC_24_2.pdf)

196-Ball BGA (12mm x 12mm x 1.42mm w/ EP)

[bp-196-4](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/sbga-heatsink/BP_196_4.pdf)

19-Ball WLCSP (1.74mm x 2.1mm)

[cb-19-1](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/wlcspcb/CB_19_1.pdf)

68-Lead QFN (10mm x 10mm w/ EP)

[hcp-68-1](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/hittite-legacy-packages/HCP-68-1.pdf)

12-Lead LCC (2.9mm x 2.9mm w/ EP)

[E-12-4](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lcce/E-12-4.pdf)

24-Lead LCC (4 x 4mm)

[e-24-1](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/hittite-legacy-packages/pkg-5378-e-24-1.pdf)

40-Lead LFCSP (6mm x 6mm w/ EP)

[cp-40-22](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lfcspcp/cp-40/CP_40_22.pdf)

72-Lead LFCSP (10mm x 10mm w/ EP)

[cs-72-1](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lfcsp-cs-side-solderable/cs-72/CS_72_1.pdf)

24-Lead LFCSP (4mm x 4mm x 0.75mm w/ EP)

[cp-24-8](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lfcspcp/cp-24/CP_24_8.pdf)

24-Lead LFSCP (4mm x 4mm x 0.95mm w/ EP)

[cp-24-17](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lfcspcp/cp-24/CP_24_17.pdf)

112-Ball CSPBGA (8mm x 8mm)

[bc-112-1](https://www.analog.com/media/en/package-pcb-resources/package/4449158528294629955bc_112_1.pdf)

10-Lead LFCSP (3mm x 3mm)

[cp-10-9](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lfcspcp/cp-10/cp_10_9.pdf)

8-Lead LFCSP (2mm x 2mm w/ EP)

[cp-8-10](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lfcspcp/cp_8_10.pdf)

148-Ball CSPBGA (9mm x 9mm x 1.4mm)

[bc-148](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/cspbga-bc/bc_148.pdf)

48-Lead LFCSP (8mm x 7mm w/ EP)

[cp-48-18](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lfcspcp/cp-48/CP_48_18.pdf)

15-Lead Ceramic DIP Vertical Form  
 

[DY-15-1](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/sb_cerdipd/DY-15-1.pdf)

72-Lead LFCSP (10mm x 10mm w/ EP)

[cp-72-6](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lfcspcp/cp_72_6.pdf)

4-Lead SOT-143

[ra-4](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/sot-143ra/ra_4.pdf)

28-Lead TSSOP w/ EP

[re-28-1](https://www.analog.com/media/en/package-pcb-resources/package/37555854052684re_28_1.pdf)

100-Lead TQFP (14mm x 14mm)

[sv-100-3](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/tqfp_edsv/sv_100_3.pdf)

72-Lead LFCSP (10mm x 10mm w/ EP)

[cp-72-5](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lfcspcp/cp-72/cp_72_5.pdf)

14-Lead FlatPack

[f-14-1](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/flatpack-f/f_14.pdf)

8-Lead LFCSP (2mm x 3mm x 0.85mm)

[cp-8-1](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lfcspcp/cp_8_1.pdf)

20-Lead PSOP

[rp-20](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/psoprp/rp_20.pdf)

120-Lead Non-Hermetic Surface Mount (2.9 Inch x 2.6 Inch)

[ws-120](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/special-by-part-number/ad12401_ws.pdf)

16-Lead TSSOP w/ EP

[re-16-2](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/tssop_epre/re_16_2.pdf)

16-Lead LFCSP (4mm x 4mm x 0.75mm w/ EP)

[cp-16-39](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lfcspcp/cp-16/cp_16_39.pdf)

10-Lead SIP

[y-10(204)](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/sipy/y_10(204).pdf)

6-Pad EWLP (0.9mm x 1.3mm)

[CN-6-1](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ewlp/CN_6_1.pdf)

16-Lead QFN (4mm x 4mm w/ EP)

[hcp-16-4](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/hittite-legacy-packages/HCP-16-4.pdf)

32-Ball Ceramic BGA (6.85mm x 6.85mm x 3.8mm)

[BG-32-3](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ceramic-bga-bg/bg_32_3.pdf)

64-Lead LFCSP (9mm x 9mm w/ EP)

[cp-64-5](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lfcspcp/cp_64_5.pdf)

32-Lead LFCSP (5mm x 5mm w/ EP)

[cp-32-3](https://www.analog.com/media/en/package-pcb-resources/package/32877413525511988cp_32_3.pdf)

64-Lead LFCSP (9mm x 9mm w/ EP)

[cp-64-6](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lfcspcp/cp_64_6.pdf)

35-Ball WLCSP (2.70 mm x 3.06 mm x 0.50 mm)

[cb-35-1](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/wlcspcb/CB_35_1.pdf)

16-Ball WLCSP (1.4mm x 2.46mm)

[cb-16-18](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/wlcspcb/CB_16_18.pdf)

16-Lead LFCSP (4mm x 4mm w/ EP)

[cp-16-5](https://www.analog.com/media/en/package-pcb-resources/package/4501839832215095857cp_16_5.pdf)

48-Lead LQFP\_EP (7mm x 7mm x 1.60mm w/ EP)

[SW-48-3](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lqfp_edsw/sw-48-3.pdf)

3-Lead TO-05

[h-03b](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/headerh/h_03b_military.pdf)

40-Lead LFCSP (6mm x 6mm w/ EP)

[cp-40-11](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lfcspcp/cp_40_11.pdf)

5-Lead SC70

[ks-5](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/sc70ks/ks_5.pdf)

56-Lead LFCSP (8mm x 8mm w/ EP)

[cp-56-3](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lfcspcp/cp_56_3.pdf)

48-Lead Side Brazed CerDIP

[d-48](https://www.analog.com/media/en/package-pcb-resources/package/52872018d_48.pdf)

144-Ball CSPBGA (10mm x 10mm x 1.4mm)

[bc-144-1](https://www.analog.com/media/en/package-pcb-resources/package/453163286836504146030385bc_144_1.pdf)

16-Lead LFCSP (3mm x 3mm x 0.85mm w/ EP)

[cp-16-52](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lfcspcp/cp-16/CP_16_52.pdf)

24 ld- LFCSP-4X4X0.55

[cp-24-25](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lfcspcp/cp-24/CP_24_25.pdf)

8-Lead Side Brazed CerDIP

[d-8-1](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/sb_cerdipd/d_8_1.pdf)

24-Lead LGA (5mm x 5mm x 1.13mm w/ EP)

[CC-24-8](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lgacc/cc_24_8.pdf)

192-Ball BGA\_ED (12mm x 12mm x 1.56mm w/ EP)

[BP-192-1](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/sbga-heatsink/BP_192_1.pdf)

34-Lead LGA\_CAV (11mm x 13mm x 2.93mm)

[CE-34-2](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lga_cavce/CE-34-2.pdf)

14-Lead Module with Connector Interface  
 

[ML-14-6](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/module/ML_14_6.pdf)

9-Ball WLCSP (1.21mm x 1.21mm)

[cb-9-3](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/wlcspcb/cb_9_3.pdf)

24-Lead Module with Connector Interface  
 

[ML-24-9](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/module/ML_24_9.pdf)

28-Lead CerDIP

[q-28-2](https://www.analog.com/media/en/package-pcb-resources/package/4045339666127361303q_28_2.pdf)

16-Lead LCC (3mm x 3mm w/ EP)

[e-16-1](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lcce/E-16-1.pdf)

32-Lead LFCSP (5mm x 5mm x 1.8mm w/ EP)

[cp-32-26](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lfcspcp/cp-32/CP_32_26.pdf)

144-Lead LQFP (20mm x 20mm)

[st-144](https://www.analog.com/media/en/package-pcb-resources/package/579143512st_144.pdf)

18-Lead CerDIP

[q-18](https://www.analog.com/media/en/package-pcb-resources/package/3949539816247344490q_18.pdf)

109-Ball CSPBGA (10mm x 10mm x 1.4mm)

[bc-109](https://www.analog.com/media/en/package-pcb-resources/package/6068938198123802949bc_109.pdf)

64-Lead LQFP (14mm x 14mm)

[st-64-3](https://www.analog.com/media/en/package-pcb-resources/package/56514372682292st_64_3.pdf)

16-Lead LFCSP (3mm x 3mm w/ EP)

[cp-16-38](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lfcspcp/cp-16/CP-16-38.pdf)

16-Lead LFCSP (4mm x 4mm x 0.85mm w/ EP)

[cp-16-42](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lfcspcp/cp-16/CP_16_42.pdf)

176-Lead LQFP (24mm x 24mm w/ heatsink)

[sw-176-2](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lqfp_edsw/sw_176_2.pdf)

120-Lead LQFP (14mm x 14mm w/ dual heatsink)

[sw-120-2](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lqfp_edsw/sw_120_2.pdf)

48-Lead TQFP (7mm x 7mm w/ EP)

[sv-48-2](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/tqfp_edsv/sv_48_2.pdf)

12-Lead LCC (6.4mm x 6.4mm)

[he-12-2](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/hittite-legacy-packages/he-12-2.pdf)

24-Lead Side-Brazed CerDIP

[d-24-1](https://www.analog.com/media/en/package-pcb-resources/package/93534281d_24_1.pdf)

16-Lead LFCSP (2.5mm x 3mm x 0.55mm w/ EP)

[cp-16-44](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lfcspcp/cp-16/CP_16_44.pdf)

4-Lead Module with Connector Interface (44mm x 42.6mm x 14mm w/EP)

[ml-24-6](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/module/ml_24_6.pdf)

625-Ball PBGA (27mm x 27mm)

[b-625](https://www.analog.com/media/en/package-pcb-resources/package/45005548173527848192875606315b625.pdf)

8-Lead MSOP (3mm x 3mm w/ EP)

[rh-8-3](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/msop_edrh/RH_8_3.pdf)

16-Lead LFCSP (4mm x 4mm w/ EP)

[cp-16-16](https://www.analog.com/media/en/package-pcb-resources/package/45168886780289cp_16_16.pdf)

72-Terminal 6 x 5 mm Land Grid Array \[LGA\]  
 

[cc-72-2](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lgacc/CC_72_2.pdf)

16-Lead LFCSP (3mm x 3mm x 0.9mm w/EP)

[CP-16-54](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lfcspcp/cp-16/cp_16_54.pdf)

56-Lead LFCSP (8mm x 8mm)

[cp-56-1](https://www.analog.com/media/en/package-pcb-resources/package/32698137492825cp_56_1.pdf)

14-Lead PDIP

[n-14](https://www.analog.com/media/en/package-pcb-resources/package/n_14.pdf)

12-Ball WLCSP (1.64mm x 1.44mm)

[cb-12-11](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/wlcspcb/CB_12_11.pdf)

14-Lead LGA (5mm x 3mm)

[cc-14-1](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lgacc/cc_14_1.pdf)

16-Lead SOIC

[r-16](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/soic_narrow-r/r_16.pdf)

64-Lead LFCSP (9mm x 9mm x 0.75mm w/ EP)

[cp-64-12](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lfcspcp/cp-64/CP_64_12.pdf)

24-Lead SOIC w/ Batwing

[rb-24](https://www.analog.com/media/en/package-pcb-resources/package/479743993852630252966076rb_24.pdf)

352-Ball BGA-ED (35mm x 35mm x 1.9mm)

[BP-352-2](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/sbga-heatsink/BP_352_2.pdf)

75-Ball WLBGA

[BF-75-1](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/cspbga-bc/BF-75-1.pdf)

16-Ball WLCSP (1.96mm x 1.96mm)

[cb-16-3](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/wlcspcb/cb_16_3.pdf)

48-Terminal Land Grid Array \[LGA\]  
 

[CC-48-4](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-lga/CC_48_4.pdf)

49-Ball CSPBGA (5mm x 5mm)

[bc-49-1](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/cspbga-bc/bc_49_1.pdf)

48-Lead TQFP (7mm x 7mm w/ EP)

[sv-48-4](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/tqfp_edsv/sv_48_4.pdf)

8-Lead Flatpack

[f-8-2](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/flatpack-f/f-8-2.pdf)

16-Lead LGA (2.5mm x 2.5mm x 0.75mm)

[cc-16-6](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lgacc/CC_16_6.pdf)

24-Lead LGA (3.5mm x 4.5mm)

[cc-24](https://www.analog.com/media/en/package-pcb-resources/package/225633059cc_24.pdf)

8-Lead LFCSP (3mm x 3mm w/ EP)

[cp-8-9](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lfcspcp/cp_8_9.pdf)

28-Lead LCC

[e-28-1](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lcce/e_28_1.pdf)

124-Ball CSP-BGA (15mm x 15mm x 1.29mm)

[BC-124-4](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/cspbga-bc/BC_124_4.pdf)

8-Lead LFCSP (3mm x 3mm x 0.75mm)

[CP-8-29](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lfcspcp/cp-8/cp_8_29.pdf)

52-Lead TQFP (10mm x 10mm w/ EP)

[sv-52-2](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/tqfp_edsv/sv_52_2.pdf)

9-Ball WLCSP (1.2mm x 1.2mm)

[cb-9-5](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/wlcspcb/CB_9_5.pdf)

8-Lead SOIC w/ EP  
 

[rd-8-1](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/soic_edrd/rd_8_1.pdf)

Connectorized Hermetic Module (C9)

[hml-9](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/hittite-legacy-packages/HML-9.pdf)

56-Lead LFCSP (8mm x 8mm w/ EP)

[cp-56-11](https://www.analog.com/media/en/package-pcb-resources/package/CP_56_11.pdf)

80-Lead MQFP (14mm x 14mm)

[s-80-1](https://www.analog.com/media/en/package-pcb-resources/package/5232242034409054825345011893360435s_80(14x14).pdf)

48-Terminal Land Grid Array \[LGA\] (7 mm x 7 mm)

[cc-48-2](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lgacc/CC_48_2.pdf)

14-Lead CerDIP  
 

[q-14](https://www.analog.com/media/en/package-pcb-resources/package/393665681442905251546090q_14.pdf)

40-Lead LFCSP (6mm x 6mm w/ EP)

[cp-40-8](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lfcspcp/cp_40_8.pdf)

400-Ball BGA (17mm x 17mm x 1.5mm)

[bc-400-2](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/cspbga-bc/BC_400_2.pdf)

8-Lead LCC  
 

[e-8-1](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lcce/e_8_1.pdf)

16-Lead LFCSP (4mm x 4mm)

[cp-16-17](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lfcspcp/cp_16_17.pdf)

24-Lead LFCSP (4mm x 5mm w/ EP)

[cp-24-5](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lfcspcp/cp_24_5.pdf)

10-Lead MSOP  
 

[HRM-10-1](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/hittite-legacy-packages/HRM-10-1.pdf)

41-Lead LFCSP (9mm x 7mm)

[cp-41-1](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lfcspcp/CP_41_1.pdf)

212-Ball CSPBGA (19mm x 19mm x 1.51mm)

[bc-212-1](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/cspbga-bc/BC_212_1.pdf)

8-Lead LFCSP (3mm x 3mm x 0.65mm w/ EP)

[CP-8-22](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lfcspcp/cp-8/CP_8_22.pdf)

28-Lead PDIP  
 

[n-28-2](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/pdipn/N_28_2.pdf)

3-Lead SOT-23  
 

[rt-3](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/sot-23-3-rt/rt_3.pdf)

88-Lead LFCSP (12mm x 12mm w/ EP)

[cp-88-5](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lfcspcp/cp_88_5.pdf)

20-Lead LFCSP (4mm x 4mm w/ EP)

[cp-20-6](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lfcspcp/cp_20_6.pdf)

16-Lead QSOP w/ EP  
 

[rc-16](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/qsop_eprc/rc_16.pdf)

48-Lead LFCSP (7mm x 7mm w/ EP)

[cp-48-22](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lfcspcp/cp-48/CP_48_22.pdf)

32-Lead LFCSP (5mm x 5mm w/ EP)

[cs-32-1](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lfcsp-cs-side-solderable/cs-32/CS_32_1.pdf)

20-Lead TSSOP (4.4mm x 6.5mm w/ EP)

[re-20-1](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/tssop_epre/re_20_1.pdf)

400-Ball PBGA (27mm x 27mm)

[b-400](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/bga-b/B_400.pdf)

8-Lead SOIC  
 

[hr-8-1](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/hittite-legacy-packages/HR-8-1.pdf)

64-Lead TQFP (10mm x 10mm w/ EP)

[sv-64-5](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/tqfp_edsv/sv_64_5.pdf)

32-Lead LFCSP (6mm x 6mm x 0.95mm w/ EP)

[cp-32-15](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lfcspcp/cp_32_15.pdf)

20-Ball WLCSP (1.955m x 2.355mm)

[cb-20-6](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/wlcspcb/CB_20_6.pdf)

16-Ball WLCSP (1.7mm x 1.7mm x 0.6mm)

[cb-16-4](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/wlcspcb/cb_16_4.pdf)

48-Lead LFCSP (7mm x 7mm x 0.85mm w/ EP)

[cp-48-3](https://www.analog.com/media/en/package-pcb-resources/package/32365178961902cp_48_3.pdf)

8-Lead LCC w/ EP  
 

[hlce-8-2](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/hittite-legacy-packages/HLCE-8-2.pdf)

196-Ball CSPBGA (12mm x 12mm x 1.41mm)

[bc-196-8](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/cspbga-bc/bc_196_8.pdf)

184-Ball CSPBGA (12mm x 12mm x 1.7mm)

[BC-184-1](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/cspbga-bc/BC_184_1.pdf)

8-Lead LFCSP (2mm x 2mm w/ EP)

[cp-8-27](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lfcspcp/cp-8/CP_8_27.pdf)

Connectorized Hermetic Module (C3B)

[hml-3](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/hittite-legacy-packages/HML-3.pdf)

36-Lead LFCSP (6mm x 6mm w/ EP)

[cp-36-5](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lfcspcp/cp-36/CP_36_5.pdf)

88-Lead LFCSP (12mm x 12mm w/ EP)

[cp-88-9](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lfcspcp/CP_88_9.pdf)

160-Ball CSPBGA (12mm x 12mm x 1.7mm)

[bc-160-2](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/cspbga-bc/bc_160_2.pdf)

49-Ball CSPBGA (7mm x 7mm)

[bc-49-5](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/cspbga-bc/BC-49-5.pdf)

16-Lead LFCSP (3mm x 3mm w/ EP)

[cs-16-1](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lfcsp-cs-side-solderable/cs-16/CS_16_1.pdf)

Connectorized Hermetic Module (C2B)

[hml-2](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/hittite-legacy-packages/HML-2.pdf)

8-Lead SMT (4.32mm x 5.59mm)

[hrj-8-1](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/hittite-legacy-packages/HRJ-8-1.pdf)

18-Lead LFCSP (5mm x 4mm x 0.75mm w/ EP)

[cp-18-1](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lfcspcp/cp-18/CP_18_1.pdf)

32-Lead Hybrid DIP  
 

[dh-32b](https://www.analog.com/media/en/package-pcb-resources/package/313717823dh_32b.pdf)

6-Lead LFCSP (2mm x 2mm x 0.85mm w/ EP)

[CP-6-9](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lfcspcp/cp-6/CP_6_9.pdf)

8-Lead LFCSP (3mm x 3mm w/ EP)

[cp-8-12](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lfcspcp/cp_8_12.pdf)

32-Lead LFCSP (5mm x 5mm x 0.75mm w/ EP)

[CP-32-31](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lfcspcp/cp-32/CP_32_31.pdf)

64-Lead LFCSP (9mm x 9mm w/ EP)

[cp-64-2](https://www.analog.com/media/en/package-pcb-resources/package/cp_64_2.pdf)

100-Ball Ball Grid Array Module (15mm x 15mm x 5.72mm)

[ML-100-1](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/module/ML_100_1.pdf)

20-Lead Module w/ connector interface (24.15mm x 32.7mm x 10.6mm)

[ml-20-1](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/module/ml_20_1.pdf)

176-Lead LQFP (24mm x 24mm w/ EP)

[SW-176-5](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lqfp_edsw/SW_176_5.pdf)

20-Lead LFCSP (5mm x 5mm x 0.75mm w/ EP)

[cp-20-9](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lfcspcp/cp-20/cp_20_9.pdf)

16-Lead Side Brazed CerDIP  
 

[d-16](https://www.analog.com/media/en/package-pcb-resources/package/411773807540737148809448d_16.pdf)

16-Ball WLCSP (2.08mm x 2.08mm)

[cb-16-7](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/wlcspcb/CB_16_7.pdf)

20-Lead SOIC (Increased Creepage)

[ri-20-1](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/soic_wide-rw/RI_20_1.pdf)

100-Ball CSPBGA (10mm x 10mm x 1.35mm)

[bc-100-2](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/cspbga-bc/bc_100_2.pdf)

100-Lead TQFP w/ EP  
 

[sv-100-4](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/tqfp_edsv/sv_100_4.pdf)

20-Lead LSA (5mm x 8mm x 1.07mm)

[CC-20-5](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lgacc/CC_20_5.pdf)

8-Lead LFCSP (2mm x 3mm w/ EP)

[cp-8-17](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lfcspcp/CP_8_17.pdf)

49-Ball WLCSP (3.46mm x 3.46mm)

[cb-49-1](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/wlcspcb/cb_49_1.pdf)

120-Lead LQFP (14mm x 14mm w/ EP)

[sw-120-4](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lqfp_edsw/SW_120_4.pdf)

32-Lead LGA (5mm x 5mm)

[cc-32-6](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lgacc/CC_32_6.pdf)

32-Lead LFCSP (5mm x 5mm x 0.9mm w/ EP)

[cp-32-19](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lfcspcp/CP_32_19.pdf)

18-Lead LGA\_CAV (4.5mm x 5.8mm)

[ce-18-2](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lga_cavce/CE_18_2.pdf)

48-Lead LFCSP (7mm x 7mm w/ EP)

[cp-48-1](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lfcspcp/cp-48/cp_48_1.pdf)

12-Lead LCC (5mm x 5mm)

[e-12-3](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lcce/E-12-3.pdf)

3-Lead LGA\_CAV (2.5mm x 3.35mm)

[ce-3-2](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lga_cavce/ce_3_2.pdf)

68-Lead CLCC (24.13mm x 24.13mm x 5.84mm)

[es-68-3](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/clcces/es_68_3.pdf)

16-Ball WLCSP (1.94mm x 1.92mm)

[cb-16-12](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/wlcspcb/CB_16_12.pdf)

128-Lead LQFP (14mm x 14mm)

[st-128-1](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lqfpst/ST_128_1.pdf)

8-Lead LFCSP (3mm x 3mm)

[cp-8-2](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lfcspcp/cp_8_2.pdf)

184-Lead LQFP (20mm x 20mm)

[st-184](https://www.analog.com/media/en/package-pcb-resources/package/383064742445236181254945st184_22x22.pdf)

38-Lead LGA (10.5mm x 5.5mm x 0.98mm w/ dual EP)

[CC-38-1](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lgacc/CC_38_1.pdf)

20-Lead LFCSP (4mm x 4mm w/ EP)

[cp-20-3](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lfcspcp/cp_20_3.pdf)

16-Lead TSSOP w/EP (5mm x 4.4mm x 1.1mm)

[RE-16-4](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/tssop_epre/RE_16_4.pdf)

40-terminal LGA (6 mm × 6mm)

[cc-40-8](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lgacc/cc_40_8.pdf)

24-Lead LGA (4mm x 4mm x 0.96mm w/ EP)

[cc-24-4](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lgacc/cc_24_4.pdf)

144-Ball CSPBGA (10mm x 10mm x 1.7mm)

[bc-144-7](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/cspbga-bc/bc_144_7.pdf)

4-Ball WLCSP (0.79mm x 0.79mm)

[cb-4-6](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/wlcspcb/CB_4_6.pdf)

68-Pin PGA  
 

[g-68](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/pgag/g_68.pdf)

32-Lead LFCSP (5mm x 5mm x 0.75mm w/ EP)

[cs-32-2](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lfcsp-cs-side-solderable/cs-32/CS_32_2.pdf)

88-Lead LFCSP (12mm x 12mm w/ EP)

[cp-88-2](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lfcspcp/cp_88_2.pdf)

24-Lead SOIC (Wide)

[rw-24](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/soic_wide-rw/RW_24.pdf)

8-Lead MSOP  
 

[HRM-8-1](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/hittite-legacy-packages/HRM-8-1.pdf)

16-Lead LFCSP (4mm x 4mm w/ EP)

[cp-16-26](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lfcspcp/cp-16/cp_16_26.pdf)

56-Lead LFCSP (8mm x 8mm w/ EP)

[cp-56-9](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lfcspcp/cp-56/CP_56_9.pdf)

6-Lead WLCSP (0.91mm x 1.39mm)

[cb-6-8](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/wlcspcb/CB_6_8.pdf)

16-Lead LFCSP (2.1mm x 2.1mm)

[cp-16-15](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lfcspcp/cp_16_15.pdf)

16-Lead LFCSP (3mm x 3mm w/ EP)

[cp-16-22](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lfcspcp/cp-16/CP_16_22.pdf)

10-Lead LFCSP (2mm x 2mm)

[cp-10-11](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lfcspcp/cp_10_11.pdf)

32-lead LFCSP (5mm x 5mm)

[cp-32-29](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lfcspcp/cp-32/CP_32_29.pdf)

14-Lead SOIC  
 

[r-14](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/soic_narrow-r/r_14.pdf)

44-Lead JLCC  
 

[j-44](https://www.analog.com/media/en/package-pcb-resources/package/j-44.pdf)

20-Lead LCC  
 

[e-20-1](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lcce/E_20_1.pdf)

240-Lead MQFP (32mm x 32mm w/ heat slug)

[sp-240-1](https://www.analog.com/media/en/package-pcb-resources/package/974459624sp_240_1.pdf)

10-Ball WLCSP (1.5mm x 2mm)

[cb-10-1](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/wlcspcb/CB_10_1.pdf)

Connectorized Hermetic Module (C19)

[hml-19](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/hittite-legacy-packages/HML-19.pdf)

240-Lead CQFP Mount, Heat Slug Up  
 

[qs-240-2b](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/cqfpqs/qs_240_2b.pdf)

28-Lead PDIP (Narrow 0.3 Inch)

[n-28-1](https://www.analog.com/media/en/package-pcb-resources/package/70961940n_28_1.pdf)

32-Lead LCC (4.9mm x 4.9mm)

[e-32-1](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lcce/e-32-1.pdf)

16-Lead PDIP  
 

[n-16](https://www.analog.com/media/en/package-pcb-resources/package/N-16.pdf)

24-Lead LCC (4mm x 4mm w/ EP)

[he-24-1](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/hittite-legacy-packages/HE-24-1.pdf)

16-Lead LFCSP (3mm x 3mm w/ EP)

[cp-16-25](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lfcspcp/cp_16_25.pdf)

260-Ball CSPBGA (15mm x 15mm x 1.5mm)

[bc-260-1](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/cspbga-bc/bc_260_1.pdf)

16-Lead SOIC (Increased Creepage)

[ri-16-2](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ri_soic_ic/ri_16_2.pdf)

108-Ball CSPBGA (13mm x 13mm x 1.7mm)

[bc-108-2](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/cspbga-bc/bc_108_2.pdf)

24-Lead QSOP  
 

[rq-24](https://www.analog.com/media/en/package-pcb-resources/package/5011644139806rq_24.pdf)

44-Lead TQFP (10mm x 10mm)

[su-44](https://www.analog.com/media/en/package-pcb-resources/package/433604008844224432481202su_44.pdf)

100-Lead LFCSP (12mm x 12mm w/ EP)

[cp-100-1](https://www.analog.com/media/en/package-pcb-resources/package/cp_100_1%20.pdf)

12-Ball WLCSP (1.415mm x 1.665mm)

[cb-12-6](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/wlcspcb/CB_12_6.pdf)

16-Lead LFCSP (4mm x 4mm x 0.9mm w/ EP)

[cp-16-40](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lfcspcp/cp-16/cp-16-40.pdf)

96-Ball CSPBGA (6mm x 6mm)

[bc-96-2](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/cspbga-bc/bc_96_2.pdf)

48-Lead TQFP (7mm x 7mm w/ EP)

[sv-48-1](https://www.analog.com/media/en/package-pcb-resources/package/324948562sv_48_1.pdf)

14-Lead CerPak  
 

[qc-14](https://www.analog.com/media/en/package-pcb-resources/package/qc_14.pdf)

24-Lead LFCSP (5mm x 4mm x 0.95mm w/ EP)

[cp-24-9](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lfcspcp/cp-24/CP_24_9.pdf)

28-Lead TSSOP w/ EP  
 

[re-28-2](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/tssop_epre/re_28_2.pdf)

20-Lead LGA w/ EP  
 

[cc-20-3](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lgacc/CC_20_3.pdf)

16-Ball WLCSP (2mm x 2mm)

[cb-16-8](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/wlcspcb/CB_16_8.pdf)

128-Lead TQFP (14mm x 14mm w/ EP)

[sv-128-1](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/tqfp_edsv/sv_128_1.pdf)

32-Ball WLCSP (2.56mm x 2.56mm x 0.5mm)

[CB-32-2](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/wlcspcb/CB_32_2.pdf)

88-Lead LFCSP (12mm x 12mm w/ EP)

[cp-88-8](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lfcspcp/CP_88_8.pdf)

88-Lead LFCSP (12mm x 12mm w/ EP)

[cp-88-7](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lfcspcp/cp_88_7.pdf)

64-Lead TQFP (10mm x 10mm w/ EP)

[sv-64-2](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/tqfp_edsv/sv_64_2.pdf)

32-Lead LQFP (7mm x 7mm)

[st-32-2](https://www.analog.com/media/en/package-pcb-resources/package/428424022542261211948156st_32_2.pdf)

124-Ball CSP-BGA (15mm x 15mm x 1.4mm)

[BC-124-5](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/cspbga-bc/BC_124_5.pdf)

225-Ball PBGA (23mm x 20mm)

[b-225-2](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/bga-b/b_225_2.pdf)

24-Lead Module with Connector Interface  
 

[ml-24-5](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/module/ml_24_5.pdf)

28-Lead PLCC  
 

[p-28](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/plccp/p_28.pdf)

20-Lead LFCSP (4mm x 4mm w/ EP)

[cp-20-8](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lfcspcp/cp-20/CP_20_8.pdf)

8-Lead SOIC w/ EP  
 

[RD-8-3](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/soic_edrd/rd-8-3.pdf)

10-Lead PDIP  
 

[n-10](https://www.analog.com/media/en/package-pcb-resources/package/81941746ad202_4_dip.pdf)

16-Lead QSOP  
 

[hrq-16-1](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/hittite-legacy-packages/HRQ-16-1.pdf)

16-Lead LFCSP (3mm x 3mm x 0.85mm w/ EP)

[cp-16-18](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lfcspcp/cp-16/cp_16_18.pdf)

28-Lead JLCC  
 

[j-28-1](https://www.analog.com/media/en/package-pcb-resources/package/104050446j_28_1.pdf)

128-Lead MQFP (28mm x 28mm)

[s-128-2](https://www.analog.com/media/en/package-pcb-resources/package/686468536s_128_2.pdf)

144-Ball CSP-BGA (10mm x 10mm x 1.70mm)

[ca-144-1](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/cspbga-bc/CA_144_1.pdf)

20-Lead LFCSP (4mm x 4mm w/ EP)

[cp-20-10](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lfcspcp/CP_20_10.pdf)

81-Ball WLCSP (3.82mm x 4.045mm)

[cb-81-1](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/wlcspcb/cb_81_1.pdf)

8-Lead MSOP w/ EP  
 

[HRH-8-1](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/hittite-legacy-packages/HRH-8-1.pdf)

128-Lead LQFP (14mm x 20mm)

[st-128-2](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lqfpst/ST_128_2.pdf)

12-Ball WLCSP (1.2mm x 1.6mm)

[cb-12-10](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/wlcspcb/CB_12_10.pdf)

24-Lead LFCSP (4mm x 4mm w/ EP)

[cp-24-12](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lfcspcp/cp_24_12.pdf)

16-Lead Flatpak Reversed Form Gullwing Leads  
 

[fr-16-1](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/flatpack-f/FR-16-1.pdf)

169-Ball PBGA (19mm x 19mm)

[b-169](https://www.analog.com/media/en/package-pcb-resources/package/4508238598123917727b_169.pdf)

12-Lead LFCSP (3mm x 3mm w/ EP)

[cp-12-3](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lfcspcp/cp_12_3.pdf)

64-Lead LFCSP (9mm x 9mm w/ EP)

[cp-64-7](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lfcspcp/cp_64_7.pdf)

24-Lead TSSOP  
 

[ru-24](https://www.analog.com/media/en/package-pcb-resources/package/380523655245964505593671154107510036154ru24.pdf)

196-Ball BGA (12mm x 12mm x 1.38mm w/ EP)

[bp-196-3](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/sbga-heatsink/BP_196_3.pdf)

32-Lead QFN (5mm x 5mm w/ EP)

[hcp-32-1](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/hittite-legacy-packages/HCP-32-1.pdf)

28-Lead QFN (5mm x 5mm w/ EP)

[hcp-28-1](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/hittite-legacy-packages/HCP-28-1.pdf)

80-Lead MQFP (14mm x 14mm x 2.7mm)

[s-80-2](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/mqfps/s_80_2.pdf)

144 ball (10x10x1.71 w/6.6 mm EP)

[BP-144-1](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/sbga-heatsink/BP_144_1.pdf)

9-Ball WLCSP (1.46mm x1.46mm)

[cb-9-2](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/wlcspcb/CB_9_2.pdf)

32-Lead LFCSP (5mm x 5mm w/ EP)

[cp-32-20](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lfcspcp/cp-32/CP_32_20.pdf)

14-Ball WLCSP (1.46mm x 2.96mm)

[cb-14-1](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/wlcspcb/CB_14_1.pdf)

Connectorized Hermetic Module (C15)

[hml-15](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/hittite-legacy-packages/HML-15.pdf)

32-Lead LCC (5mm x 5mm w/ EP)

[he-32-1](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/hittite-legacy-packages/HE-32-1.pdf)

48-Lead LFCSP (7mm x 7mm w/ EP)

[cp-48-16](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lfcspcp/CP_48_16.pdf)

64-Lead LFCSP (9mm x 9mm w/ EP)

[cp-64-16](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lfcspcp/CP_64_16.pdf)

84-Ball CSPBGA (6.85mm x 6.85mm x 3.8mm)

[bc-84-2](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/cspbga-bc/bc_84_2.pdf)

24-Lead CerDIP (Wide 0.6 Inch)

[q-24-2](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/cerdipq/q_24_2.pdf)

18-Terminal LCC (7mm x 7mm x 1.317mm)

[EH-18-1](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lcc-ep/EH-18-1.pdf)

6-Lead QFN (2mm x 2mm w/ EP)

[hcp-6-1](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/hittite-legacy-packages/HCP-6-1.pdf)

32-Lead LFCSP\_CAV (5mm x 5mm w/ EP)

[cg-32-1](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lfcsp-cav/CG-32-1.pdf)

56-Lead LFCSP (8mm x 8mm w/ EP)

[cp-56-10](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lfcspcp/cp-56/CP_56_10.pdf)

385-Lead BGA (35mm x 35mm)

[b-385](https://www.analog.com/media/en/package-pcb-resources/package/45557425288079b_385.pdf)

12-Lead SIP  
 

[y-12](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/sipy/y-12.pdf)

289-Ball Chip Scale Package Ball Grid Array  
 

[BC-289-6](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/cspbga-bc/BC_289_6.pdf)

16-Lead LFCSP (3mm x 3mm x 0.55mm w/ EP)

[cp-16-12](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lfcspcp/cp_16_12.pdf)

Connectorized Hermetic Module (C18)

[hml-18](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/hittite-legacy-packages/HML-18.pdf)

16-Lead LGA (8.35mm x 8.2mm)

[cc-16-1](https://www.analog.com/media/en/package-pcb-resources/package/726059754cc_16_1.pdf)

28-Lead LFCSP (5mm x 5mm w/ EP)

[cp-28-4](https://www.analog.com/media/en/package-pcb-resources/package/291374509cp_28_4.pdf)

6-Lead LFCSP (2mm x 2mm)

[cp-6-12](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lfcspcp/cp-6/CP_6_12.pdf)

196-Ball CSPBGA (15mm x 15mm x 1.5mm)

[bc-196-1](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/cspbga-bc/bc_196_1.pdf)

160-Ball CSPBGA (12mm x 12mm x 1.4mm)

[bc-160-1](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/cspbga-bc/BC_160_1.pdf)

52-Lead LQFP (10mm x 10mm)

[st-52](https://www.analog.com/media/en/package-pcb-resources/package/61012411624300842189414155189544791816408612st_52_10x10.pdf)

84-Lead LFCSP (10mm x 10mm w/ EP)

[cp-84-1](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lfcspcp/cp-84/cp_84_1.pdf)

12-Lead LFCSP (3mm x 3mm x 0.75mm)

[cp-12-4](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lfcspcp/cp-12/CP_12_4.pdf)

10-Lead LFCSP (3mm x 2mm x 0.75mm)

[CP-10-16](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lfcspcp/cp-10/cp_10_16.pdf)

48-Lead TQFP (7mm x 7mm)

[su-48](https://www.analog.com/media/en/package-pcb-resources/package/470644706845302410119987su48_7x7.pdf)

16-Lead QFN (3mm x 3mm w/ EP)

[hcp-16-5](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/hittite-legacy-packages/HCP-16-5.pdf)

12-Lead LCC (6.35mm x 6.35mm)

[e-12-2](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lcce/E-12-2.pdf)

14-Lead SOIC (Wide)

[rw-14](https://www.analog.com/media/en/package-pcb-resources/package/54614177245586rw_14.pdf)

6-Ball WLCSP (1.5mm x 1.3mm)

[cb-6-12](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/wlcspcb/CB_6_12.pdf)

16 ld SOIC  
 

[RW-16](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ri_soic_ic/rw_16.pdf)

43-Terminal LGA (5mm x 5mm x 0.868mm)

[cc-43-1](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lgacc/cc_43_1.pdf)

15-terminal Module (15mm x15mm x 15mm)

[ml-15-1](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/module/ml_15_1.pdf)

22-Lead PDIP  
 

[n-22-1](https://www.analog.com/media/en/package-pcb-resources/package/152658964nd_22_1.pdf)

28-Lead SOIC (Wide)

[rw-28](https://www.analog.com/media/en/package-pcb-resources/package/35833120341221rw_28.pdf)

54-Ball WLCSP (2.76mm x 2.76mm)

[cb-54-1](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/wlcspcb/CB_54_1.pdf)

32-Ball CSPBGA (6.85mm x 8.85mm x 3.2mm)

[bc-32](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/cspbga-bc/bc_32_1.pdf)

16-Lead SOIC (Increased Creepage)

[ri-16-1](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ri_soic_ic/ri_16_1.pdf)

64-Ball CSPBGA (9mm x 9mm x 1.4mm)

[bc-64-2](https://www.analog.com/media/en/package-pcb-resources/package/3665130266459604316443026134898045bc_64_2.pdf)

144 Ball WLCSP (6.095 x 6.135 x 0.6)

[cb-144-2](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/wlcspcb/CB_144_2.pdf)

10-Lead LFCSP (1.3mm x 1.6mm)

[cp-10-10](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lfcspcp/cp_10_10.pdf)

256-Ball SBGA (27mm x 27mm)

[bp-256](https://www.analog.com/media/en/package-pcb-resources/package/287254833bp_256.pdf)

52-Lead LQFP (14mm x 14mm x 1.4mm w/ EP)

[sq-52-2](https://www.analog.com/media/en/package-pcb-resources/package/4098517785306sq_52_ed.pdf)

18-Lead SOIC (Wide)

[rw-18](https://www.analog.com/media/en/package-pcb-resources/package/33254132129439rw_18.pdf)

24-terminal LGA (8 mm x 4 mm x 1.2 mm)

[CC-24-6](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lgacc/CC_24_6.pdf)

108-Ball CSPBGA (7mm x 7mm x 1.4mm)

[bc-108-4](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/cspbga-bc/bc_108_4.pdf)

44-Lead PLCC  
 

[p-44a](https://www.analog.com/media/en/package-pcb-resources/package/533756178731793364534243243792136664964p44a.pdf)

196-Ball BGA (12mm x 12mm x 1.32mm w/ EP)

[bp-196-1](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/sbga-heatsink/BP_196_1.pdf)

20-Ball WLCSP (1.8mm x 2.2mm x 0.56mm)

[cb-20-10](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/wlcspcb/CB_20_10.pdf)

16-Lead LCC (5mm x 5mm w/ EP)

[e-16-2](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lcce/E-16-2.pdf)

23-Ball WLCSP (2.135mm x 2.085mm)

[cb-23-1](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/wlcspcb/cb_23_1.pdf)

3-Lead LGA\_CAV (2.5mm x 3.35mm)

[ce-3-5](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lga_cavce/ce_3_5.pdf)

5-Lead TSOT  
 

[uj-5](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/tsotuj/uj_5.pdf)

6-Ball WLCSP (1.14mm x 2.18mm)

[cb-6-1](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/wlcspcb/CB_6_1.pdf)

16-Lead SOIC\_CAV  
 

[rg-16-1](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/soic_pcprg/rg_16_1.pdf)

32-Lead LFCSP (5mm x 5mm w/ EP)

[cp-32-4](https://www.analog.com/media/en/package-pcb-resources/package/3416438741201015623cp_32_4.pdf)

12-Lead LFCSP (3mm x 3mm x 0.85mm w/ EP)

[cp-12-10](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lfcspcp/cp-12/CP_12_10.pdf)

20-Lead QSOP  
 

[rq-20](https://www.analog.com/media/en/package-pcb-resources/package/184195322rq_20.pdf)

20-Lead CerDIP (Side Brazed)

[d-20](https://www.analog.com/media/en/package-pcb-resources/package/31639175472309d_20.pdf)

100-Lead LQFP (14mm x 14mm w/ heat sink)

[sq-100-2](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lqfp_edsq/sq_100_2.pdf)

20-Lead LFCSP (4mm x 4mm x 0.75mm w/ EP)

[cp-24-23](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lfcspcp/cp-24/CP_24_23.pdf)

4-Ball WLCSP (0.74mm x 0.74mm)

[cb-4-5](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/wlcspcb/CB_4_5.pdf)

24-Lead LFCSP (4mm x 4mm x 0.75mm w/ EP)

[cp-24-10](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lfcspcp/cp-24/CP_24_10.pdf)

4-Lead SOT-89  
 

[hrk-4-1](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/hittite-legacy-packages/HRJ-3-1.pdf)

Connectorized Hermetic Module (C10b)

[hml-10-2](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/hittite-legacy-packages/HML-10-2.pdf)

169-Ball CSPBGA (11mm x 11mm x 0.95mm)

[bc-169-2](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/cspbga-bc/BC_169_2.pdf)

36-Lead LFCSP (6mm x 6mm x 0.85mm w/ EP)

[cp-36-1](https://www.analog.com/media/en/package-pcb-resources/package/cp_36_1.pdf)

12-Lead LGA\_CAV (2.8mm x 5mm x 1.35mm)

[ce-12-2](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lga_cavce/CE_12_2.pdf)

56-Ball WLCSP (4.16 mm x 3.56 mm)

[cb-56-3](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/wlcspcb/CB_56_3.pdf)

72-Ball BGA (8mm x 8mm x 1.4mm)

[bc-72-2](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/cspbga-bc/BC_72_2.pdf)

40-Lead LFCSP (6mm x 6mm w/ EP)

[CP-40-15](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lfcspcp/cp-40/CP_40_15.pdf)

32-Lead QFN (5mm x 5mm w/ EP)

[hcp-32-3](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/hittite-legacy-packages/HCP-32-3.pdf)

36-Lead LFCSP (6mm x 6mm x 0.85mm w/ EP)

[cp-36-2](https://www.analog.com/media/en/package-pcb-resources/package/cp_36_2.pdf)

100-Lead LQFP (14mm x 14mm)

[st-100-1](https://www.analog.com/media/en/package-pcb-resources/package/92490886st_100_1.pdf)

4-Lead SC70  
 

[ks-4](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/sc70ks/ks_4.pdf)

240-Lead CQFP Mount, Heat Slug Up  
 

[qs-240-2a](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/cqfpqs/qs_240_2a.pdf)

44-Lead LCC  
 

[e-44-1](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lcce/e_44_1.pdf)

5-Lead LGA\_CAV (4mm x 3mm)

[ce-5-1](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lga_cavce/ce_5_1.pdf)

80-Lead TQFP (12mm x 12mm w/ EP)

[sv-80-3](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/tqfp_edsv/sv_80_3.pdf)

124-Ball CSP-BGA (15mm x 15mm x 1.66mm)

[BC-124-3](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/cspbga-bc/BC_124_3.pdf)

31-Lead LGA (10mm x 10mm)

[cc-31](https://www.analog.com/media/en/package-pcb-resources/package/170167271cc_31.pdf)

48-Lead LFCSP (7mm x 7mm x 0.85mm w/ EP)

[cp-48-4](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lfcspcp/cp_48_4.pdf)

Connectorized Hermetic Module (C21)

[hml-21](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/hittite-legacy-packages/HML-21.pdf)

16-Lead SMT  
 

[hrj-16-1](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/hittite-legacy-packages/HRJ-16-1.pdf)

36-Ball WLCSP (3.4mm x 3.4mm)

[cb-36-3](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/wlcspcb/cb_36_3.pdf)

16-Lead LFCSP (3mm x 3mm w/ EP)

[cp-16-35](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lfcspcp/cp-16/CP_16_35.pdf)

24-Lead LFCSP (4mm x 4mm x 0.85mm w/ EP)

[CP-24-22](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lfcspcp/cp-24/CP_24_22.pdf)

8-Lead LFCSP (3mm x 3mm x 0.75mm)

[cp-8-15](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lfcspcp/CP_8_15.pdf)

16-Lead LFCSP (3mm x 3mm w/ EP)

[cp-16-3](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lfcspcp/cp_16_3.pdf)

8-Ball WLCSP (1.42mm x 1.42mm)

[cb-8-2](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/wlcspcb/CB_8_2.pdf)

676-Ball PBGA (27mm x 27mm)

[b-676](https://www.analog.com/media/en/package-pcb-resources/package/b_676.pdf)

8-Lead QSOP w/ EP  
 

[hrc-8-2](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/hittite-legacy-packages/HRC-8-2.pdf)

17-Ball WLCSP  
 

[cb-17-1](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/wlcspcb/CB_17_1.pdf)

8-Lead SOT-115J Module Package  
 

[ML-8-1](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/module/ML-8-1.pdf)

56-Lead LFCSP (8mm x 8mm w/ EP)

[cp-56-8](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lfcspcp/cp-56/CP_56_8.pdf)

8-Lead LFCSP (3mm x 3mm w/ EP)

[cp-8-13](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lfcspcp/cp-8/CP_8_13.pdf)

42-Ball WLCSP (2.695mm x 2.320mm x 0.47mm)

[CB-42-2](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/wlcspcb/CB_42_2.pdf)

100-Lead TQFP (14mm x 14mm w/ EP)

[sv-100-2](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/tqfp_edsv/sv_100_2.pdf)

8-Ball WLCSP (1.5mm x 1.5mm)

[cb-8-3](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/wlcspcb/CB_8_3.pdf)

32-Lead LFCSP (5mm x 5mm x 0.85mm w/ EP)

[cp-32-8](https://www.analog.com/media/en/package-pcb-resources/package/3743763361381667927cp_32_8.pdf)

8-Lead TSOT  
 

[uj-8](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/tsotuj/uj_8.pdf)

88-Lead LGA (7mm x 7mm)

[CC-88-1](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lgacc/CC_88_1.pdf)

36-Lead QFN (7mm x 4mm w/ EP)

[hcp-36-1](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/hittite-legacy-packages/HCP-36-1.pdf)

16-Lead LFCSP (3mm x 3mm x 0.75mm w/ EP)

[CP-16-45](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lfcspcp/cp-16/CP_16_45.pdf)

4-Lead PDIP (36.7mm x 8.9mm)

[n-4](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/pdipn/n-4.pdf)

308-Lead CQFP  
 

[qs-308](https://www.analog.com/media/en/package-pcb-resources/package/70879964qs_308.pdf)

6-Ball WLCSP (0.9mm x 1.3mm)

[cb-6-4](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/wlcspcb/cb_6_4.pdf)

16-Lead LFCSP (4mm x 4mm w/ EP)

[cp-16-20](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lfcspcp/cp-16/cp_16_20.pdf)

40-Lead LFCSP (6mm x 6mm w/ EP)

[cp-40-9](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lfcspcp/cp_40_9.pdf)

100-Pin Ceramic PGA  
 

[g-100](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/pgag/g_100.pdf)

20-Ball WLCSP (2.71mm x 2.04mm)

[cb-20-8](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/wlcspcb/CB_20_8.pdf)

32-Lead LFCSP (5mm x 5mm x 1.55mm w/ EP)

[cp-32-17](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lfcspcp/cp_32_17.pdf)

40-Lead LFCSP (6mm x 6mm w/ EP)

[cp-40-14](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lfcspcp/cp_40_14.pdf)

176-Lead LQFP (24mm x 24mm w/ EP)

[sw-176-1](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lqfp_edsw/sw_176_1.pdf)

Connectorized Hermetic Module (C7)

[hml-7](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/hittite-legacy-packages/HML-7.pdf)

4-Lead SIP  
 

[y-4](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/sipy/y-4.pdf)

16-Lead LFCSP (5mm x 5mm w/ EP)

[cp-16-8](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lfcspcp/cp_16_8.pdf)

16-Lead LFCSP (3mm x 3mm w/ EP)

[cp-16-1](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lfcspcp/cp_16_1.pdf)

28-Lead Flatpack  
 

[f-28-1](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/flatpack-f/f_28.pdf)

40-Terminal Land Grid Array \[LGA\]  
 

[cc-40-7](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lgacc/cc_40_7.pdf)

88-Lead LFCSP (12mm x 12mm w/ EP)

[cp-88-4](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lfcspcp/CP_88_4.pdf)

60-Lead Hybrid Surface Mount (2.2 Inch x 2.8 Inch)

[ws-60](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/special-by-part-number/ad10677_ev.pdf)

35-Ball WLCSP (2.14 mm x 3.11 mm x 0.50 mm)

[CB-35-2](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/wlcspcb/CB_35_2.pdf)

32-lead FLATPACK\_RF  
 

[FR-32-1](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/flatpack-f/FR-32-1.pdf)

1024-Ball SBGA  
 

[bp-1024-1](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/sbga-heatsink/BP_1024_1.pdf)

48-Lead TSSOP  
 

[rv-48](https://www.analog.com/media/en/package-pcb-resources/package/59272155rv_48.pdf)

80-Lead TQFP (12mm x 12mm)

[sv-80-1](https://www.analog.com/media/en/package-pcb-resources/package/3250240192292635369sv_80_1.pdf)

4-Lead Module (44.45mm x 41.15mm x 13.34mm)

[ml-4-1](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/module/ml_4_1.pdf)

48-Lead LFCSP (7mm x 7mm x 0.85mm w/ EP)

[cp-48-8](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lfcspcp/cp_48_8.pdf)

40-Lead QFN (6mm x 6mm w/ EP)

[hcp-40-1](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/hittite-legacy-packages/HCP-40-1.pdf)

32-Lead SMT (4.83mm x 4.83mm)

[hrj-32-1](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/hittite-legacy-packages/HRJ-32-1.pdf)

324-Ball BGA\_ED (15mm x 15mm x 1.52mm)

[bp-324-1](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/bga_ed-bp/bp_324_1.pdf)

8-Lead Module (0.98 in x 1.346 in x 0.154 in)

[mc-18-1](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/hittite-legacy-packages/mc-18-1.pdf)

16-Lead LFCSP (3mm x 3mm x 0.85mm w/ EP)

[cp-16-51](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lfcspcp/cp-16/cp_16_51.pdf)

316-Lead PBGA (23mm x 23mm)

[b-316](https://www.analog.com/media/en/package-pcb-resources/package/61868185924959b_316.pdf)

80-Ball CSPBGA (9mm x 9mm x 1.4mm)

[bc-80](https://www.analog.com/media/en/package-pcb-resources/package/4587646203202649811bc_80.pdf)

25-Ball WLCSP (2.25mm x 2.05mm)

[cb-25-3](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/wlcspcb/cb_25_3.pdf)

44-Lead MQFP (13.9mm x 10mm)

[s-44-2](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/mqfps/S_44_2.pdf)

240-Lead MQFP (32mm x 32mm w/ heat slug)

[sp-240-2](https://www.analog.com/media/en/package-pcb-resources/package/822609751sp_240_2.pdf)

75-Ball CSPBGA (6mm x 6mm x 1.2mm)

[bc-76-2](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/cspbga-bc/bc_76_2.pdf)

168-Ball CSPBGA (12mm x 12mm x 1.6mm)

[bc-168-1](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/cspbga-bc/bc_168_1.pdf)

72-Lead LFCSP (10mm x 10mm w/ EP)

[cp-72-3](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lfcspcp/cp_72_3.pdf)

128-Ball CSPBGA (9mm x 9mm x 1.4mm)

[bc-128](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/cspbga-bc/bc_128.pdf)

5-Lead SOT-89  
 

[rk-5](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/sot-89rk/rk_5.pdf)

5-Lead SIP (Vertical Leads)

[ys-5](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/sipy/ys_5.pdf)

Connectorized Hermetic Module (C-4)

[hml-4](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/hittite-legacy-packages/HML-4.pdf)

28-Lead SSOP  
 

[rs-28](https://www.analog.com/media/en/package-pcb-resources/package/32122249223724rs_28.pdf)

20-Ball WLCSP (2.595mm x 1.995mm)

[cb-20-9](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/wlcspcb/CB_20_9.pdf)

291-Ball CSPBGA (12mm x 12mm x 1.2mm)

[bc-291-1](https://www.analog.com/media/en/package-pcb-resources/package/336841218bc_291_1.pdf)

5-Ball WLCSP (1.02mm x 1.45mm)

[cb-5-3](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/wlcspcb/CB_5_3.pdf)

24-Lead LFCSP (5mm x 4mm w/ EP)

[cp-24-4](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lfcspcp/cp-24/CP_24_4.pdf)

72-Ball WLCSP (4.46mm x 3.96mm)

[cb-72-2](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/wlcspcb/CB_72_2.pdf)

324-Ball PBGA (19mm x 19mm)

[b-324](https://www.analog.com/media/en/package-pcb-resources/package/454473177139443477109483b_324.pdf)

20-Lead CerDIP  
 

[q-20](https://www.analog.com/media/en/package-pcb-resources/package/50516416473314q_20.pdf)

40-Lead LFCSP (6mm x 6mm w/ EP)

[cp-40-16](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lfcspcp/cp-40/CP-40-16.pdf)

176-Lead LQFP\_EP (24mm x 24mm w/ heatsink)

[SW-176-3](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lqfp_edsw/SW_176_3.pdf)

9-Ball WLCSP (1.65mm x 1.87mm)

[cb-9-6](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/wlcspcb/CB_9_6.pdf)

121-Ball CSPBGA (12mm x 12mm)

[bc-121-1](https://www.analog.com/media/en/package-pcb-resources/package/3232325371445bc_121_1.pdf)

20-Lead Flatpack  
 

[p-20](https://www.analog.com/media/en/package-pcb-resources/package/3121431516544404277643669223804694P20A.pdf)

24-Lead CerDIP (Narrow 0.3 Inch)

[q-24-1](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/cerdipq/q_24_1.pdf)

144-Ball CSPBGA (13mm x 13mm)

[bc-144-2](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/cspbga-bc/bc_144_2.pdf)

14-Lead TSSOP  
 

[ru-14](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/tssop-ru/ru_14.pdf)

16-Lead LCC (6mm x 6mm w/EP)

[EP-16-2](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lcc-ep/ep-16-2.pdf)

20-Lead SOIC (Wide)

[rw-20](https://www.analog.com/media/en/package-pcb-resources/package/233848rw_20.pdf)

Connectorized Hermetic Module (C10)

[hml-10-1](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/hittite-legacy-packages/HML-10.pdf)

3-Lead SC70  
 

[ks-3](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/sc70ks/ks_3.pdf)

72-Lead LFCSP (10mm x 10mm w/ EP)

[cp-72-4](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lfcspcp/cp_72_4.pdf)

32-Lead LFCSP (5mm x 5mm)

[cp-32-2](https://www.analog.com/media/en/package-pcb-resources/package/414143737956480539664569cp_32_2.pdf)

196-Ball CSPBGA (12mm x 12mm x 1.27mm)

[bc-196-12](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/cspbga-bc/BC_196_12.pdf)

164-Ball CSPBGA (12mm x 12mm x 1.22mm)

[bc-164-1](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/cspbga-bc/bc_164_1.pdf)

176-Lead LQFP\_EP (24mm x 24mm w/ heatsink)

[SW-176-4](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lqfp_edsw/SW_176_4.pdf)

12-Lead LGA\_CAV (4mm x 4mm x 1.65mm)

[CE-12-4](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lga_cavce/CE-12-4.pdf)

6-Lead SC70  
 

[ks-6](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/sc70ks/ks_6.pdf)

28-Lead SOIC (Wide, Finer Pitch)

[rn-28-1](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/soic_wide-rw/RN-28-1.pdf)

88-Ball CSPBGA (6mm x 6mm x 0.87mm)

[bc-88-1](https://www.analog.com/media/en/package-pcb-resources/package/bc_88_1.pdf)

72-Lead WLCSP (3.57mm x 3.16mm)

[cb-72-3](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/wlcspcb/CB_72_3.pdf)

16-Lead FlatPack  
 

[f-16-1](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/flatpack-f/F-16-1.pdf)

8-Lead MSOP (3mm x 3mm w/ EP)

[rh-8-4](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/msop_edrh/RH_8_4.pdf)

6-Lead LFCSP (2mm x 2mm x 0.85mm)

[cp-6-10](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lfcspcp/cp-6/CP_6_10.pdf)

20-Lead TSSOP  
 

[ru-20](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/tssop/ru_20.pdf)

10-Lead LFCSP (3mm x 3mm w/ EP)

[cp-10-3](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lfcspcp/cp_10_3.pdf)

16-Lead LGA (3mm x 3.25mm)

[cc-16-4](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lgacc/cc_16_4.pdf)

28-Lead LFCSP (4mm x 5mm x 0.75mm w/ EP)

[cp-28-12](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lfcspcp/cp-28/CP_28_12.pdf)

16-Lead LFCSP (3mm x 3mm w/ EP)

[cp-16-33](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lfcspcp/CP_16_33.pdf)

208-Lead MQFP (28mm x 28mm x 3.4mm)

[s-208-2](https://www.analog.com/media/en/package-pcb-resources/package/142377737s_208_2.pdf)

32-Ball WLCSP (3.36mm x 3.31mm x 0.6mm)

[CB-32-1](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/wlcspcb/CB_32_1.pdf)

40-Lead LFCSP (6mm x 6mm w/ EP)

[cp-40-6](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lfcspcp/cp-40/cp_40_6.pdf)

88-Lead LFCSP (12mm x 12mm x 0.85mm w/ EP)

[cp-88-10](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lfcspcp/cp-88/CP_88_10.pdf)

240-Lead CQFP, Heat Slug Down  
 

[qs-240-1a](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/cqfpqs/qs_240_1a.pdf)

12-Lead LGA (2.25mm x 2.25mm x 0.75mm w/ EP)

[cc-12-3](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lgacc/CC_12_3.pdf)

12-Ball WLCSP (1.61mm x 2.01mm)

[cb-12-1](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/wlcspcb/cb_12_1.pdf)

8-Lead LCC (6mm x 6mm)

[hlcc-16-2](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/hittite-legacy-packages/HLCC-16-2.pdf)

56-Lead LFCSP (8mm x 8mm w/ EP)

[cp-56-5](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lfcspcp/cp_56_5.pdf)

30-Ball WLCSP (2.64mm x 3.4mm)

[cb-30-2](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/wlcspcb/CB_30_2.pdf)

16-Lead LFCSP (3mm x 3mm w/ EP)

[cp-16-28](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lfcspcp/cp_16_28.pdf)

6-Lead TO-78  
 

[h-6](https://www.analog.com/media/en/package-pcb-resources/package/41780315633726945423451238615h_06.pdf)

8-Lead CerDIP  
 

[q-8](https://www.analog.com/media/en/package-pcb-resources/package/3925655241313314758q_8.pdf)

20-Lead LFCSP (5mm x 5mm w/ EP)

[cp-20-5](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lfcspcp/cp_20_5.pdf)

8-Lead SOIC  
 

[r-8](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/soic_narrow-r/r_8.pdf)

14-Lead LFCSP (2mm x 3mm x 0.75mm w/EP)

[CP-14-6](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lfcspcp/cp-14/cp-14-6.pdf)

8-Lead LFCSP (3mm x 2mm x 0.75mm w/ EP)

[cp-8-23](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lfcspcp/cp-8/CP_8_23.pdf)

28-Lead QFN (6mm x 6mm w/ EP)

[hcp-28-2](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/hittite-legacy-packages/HCP-28-2.pdf)

18-Lead PDIP  
 

[n-18](https://www.analog.com/media/en/package-pcb-resources/package/44930452931834n_18.pdf)

24-Terminal LCC (3.9mm x 3.9mm)

[e-24-2](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lcce/E-24-2.pdf)

208-Lead MQFP (31.2mm x 28mm)

[s-208-1](https://www.analog.com/media/en/package-pcb-resources/package/771712971s_208_1.pdf)

6 ld LCC (6x6x1.317mm w/3.55mm ep)

[EH-16-1](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lcc-ep/EH-16-1.pdf)

8-Lead MSOP w/ EP  
 

[rh-8-1](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/msop_edrh/rh_8_1.pdf)

40-Lead LFCSP (6mm x 6mm w/ EP)

[cp-40-13](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lfcspcp/cp_40_13.pdf)

6-Lead LGA\_CAV (5.08mm x 5.08mm)

[ce-6-3](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lga_cavce/CE-6-3.pdf)

32-Lead LFCSP (5mm x 5mm x 0.75mm w/ EP)

[cp-32-13](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lfcspcp/cp-32/CP_32_13.pdf)

8-Lead LFCSP (3mm x 3mm w/ EP)

[cp-8-21](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lfcspcp/cp-8/CP_8_21.pdf)

28-Lead LFCSP (5mm x 5mm w/ EP)

[cp-28-1](https://www.analog.com/media/en/package-pcb-resources/package/529741326693cp_28_1.pdf)

2-Lead TO-51  
 

[H-02-1](https://www.analog.com/media/en/package-pcb-resources/package/156851330h_02_1.pdf)

5-Ball WLCSP (0.9mm x 1.29mm x 0.55mm)

[cb-5-1](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/wlcspcb/cb_5_1.pdf)

24-Lead Metal DIP  
 

[m-24](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/metal-dip-m/m_24.pdf)

16-Lead LFCSP (4mm x 4mm w/ EP)

[cp-16-29](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lfcspcp/cp-16/CP_16_29.pdf)

12-Lead LCC (5.08mmm x 5.08mm)

[E-12-5](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lcce/E-12-5.pdf)

256-Ball CSPBGA (17mm x 17mm x 1.76mm)

[bc-256-4](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/cspbga-bc/bc_256_4.pdf)

14-Lead LFCSP (4mm x 3mm x 0.75mm w/ EP)

[cp-14-2](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lfcspcp/cp-14/CP_14_2.pdf)

16-Lead LFCSP (5mm x 5mm w/ EP)

[cp-16-31](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lfcspcp/cp_16_31.pdf)

38-Lead TSSOP  
 

[ru-38](https://www.analog.com/media/en/package-pcb-resources/package/36817415413609854197792024125ru38.pdf)

117-Ball WLCSP (6.04 mm x 6.12 mm x 0.60 mm)

[cb-117-2](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/wlcspcb/CB_117_2.pdf)

24-Terminal LGA (4mm x 4mm x 0.75mm w/ 2.4 mm EP)

[CC-24-5](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lgacc/CC_24_5.pdf)

16-Lead LFCSP (3mm x 3mm x 0.75mm w/ EP)

[cp-16-48](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lfcspcp/cp-16/CP_16_48.pdf)

400-Ball CSPBGA (17mm x 17mm x 1.7mm)

[bc-400-1](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/cspbga-bc/BC_400_1.pdf)

20-Lead SSOP  
 

[rs-20](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ssoprs/rs_20.pdf)

44-Ball BGA Module  
 

[ML-44-1](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/module/ML_44_1.pdf)

16-Ball WLCSP (2.6mm x 2.6mm)

[cb-16-16](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/wlcspcb/CB_16_16.pdf)

16-Lead SOIC w/ EP  
 

[rd-16-1](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/soic_edrd/rd_16_1.pdf)

24-Lead LFCSP (4mm x 4mm w/ EP)

[cp-24-19](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lfcspcp/cp-24/CP_24_19.pdf)

64-Ball CSPBGA (8mm x 8mm x 1.55mm)

[bc-64-1](https://www.analog.com/media/en/package-pcb-resources/package/3754742434402422209bc_64_1.pdf)

12-Lead QFN (3mm x 3mm w/ EP)

[hcp-12-1](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/hittite-legacy-packages/HCP-12-1.pdf)

28-Lead LFCSP (5mm x 5mm x 0.75mm w/ EP)

[cp-28-6](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lfcspcp/cp_28_6.pdf)

196-Ball CSPBGA (12mm x 12mm)

[bc-196-13](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/cspbga-bc/BC_196_13.pdf)

52-Lead TQFP (10mm x 10mm w/ EP)

[sv-52-1](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/tqfp_edsv/sv_52_1.pdf)

8-Lead LFCSP (2mm x 2mm)

[cp-8-6](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lfcspcp/cp_8_6.pdf)

36-Ball WLCSP (3.765mm x 3.195mm)

[cb-36-4](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/wlcspcb/CB_36_4.pdf)

100-Lead TQFP (14mm x 14mm)

[su-100](https://www.analog.com/media/en/package-pcb-resources/package/473745520051687316725816su100_14x14.pdf)

6-Lead SOT-66  
 

[ry-6-1](https://www.analog.com/media/en/package-pcb-resources/package/31264640944370943880196908582ry_6_1.pdf)

25-Ball WLCSP (1.99mm x 1.99mm)

[cb-25-5](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/wlcspcb/CB_25_5.pdf)

12-Lead LFCSP (3mm x 3mm)

[cp-12-1](https://www.analog.com/media/en/package-pcb-resources/package/cp_12_1.pdf)

52-Lead FlatPack  
 

[f-52](https://www.analog.com/media/en/package-pcb-resources/package/122521907f_52.pdf)

24-Lead LFCSP (4mm x 4mm w/ EP)

[cp-24-1](https://www.analog.com/media/en/package-pcb-resources/package/cp_24_1.pdf)

64-Ball CSPBGA (6mm x 6mm x 1.4mm)

[bc-64-4](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/cspbga-bc/bc_64_4.pdf)

4-Lead LFCSP (2mm x 3mm)

[CP-4-1](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lfcspcp/cp_4_1.pdf)

40-Lead CerDIP  
 

[q-40](https://www.analog.com/media/en/package-pcb-resources/package/281170859q_40.pdf)

8-Ball WLCSP (1.43mm x 1.775mm)

[cb-8-1](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/wlcspcb/CB_8_1.pdf)

16-Lead TSSOP w/ EP  
 

[re-16-3](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/tssop_epre/RE_16_3.pdf)

100-Lead TQFP (14mm x 14mm w/ EP)

[sv-100-8](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/tqfp_edsv/sv_100_8.pdf)

60-Terminal LGA (9mm x 8mm x 0.73mm w/EP)

[CC-60-2](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lgacc/CC-60-2.pdf)

144-Ball CSPBGA (10mm x 10mm)

[bc-144-6](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/cspbga-bc/BC_144_6.pdf)

28-Lead Side Brazed CerDIP (35.92mm x 15.49mm)

[dh-28b](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/hybrid-cerdip-dh/dh_28b.pdf)

10-Lead MSOP w/ EP  
 

[HRH-10-1](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/hittite-legacy-packages/HRH-10-1.pdf)

20-Ball WLCSP (1.61 mm x 2.18 mm x 0.50 mm)

[cb-20-14](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/wlcspcb/CB_20_14.pdf)

16-Lead LFCSP (4mm x 4mm x 0.85mm)

[cp-16-19](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lfcspcp/cp_16_19.pdf)

16-Lead LFCSP (3mm x 3mm w/ EP)

[cp-16-27](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lfcspcp/cp_16_27.pdf)

120-Lead LQFP (14mm x 14mm w/ EP)

[sw-120-3](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lqfp_edsw/sw_120_3.pdf)

100-Lead TQFP (14mm x 14mm w/ EP)

[sv-100-7](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/tqfp_edsv/sv_100_7.pdf)

16-Lead LCC (3mm x 3mm w/ EP)

[e-16-3](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lcce/E-16-3.pdf)

16-Lead SOIC  
 

[r-16-s](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/soic-narrow-sensor/R-16-S.pdf)

12-Ball WLCSP (1.5mm x 2.01mm)

[cb-12-5](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/wlcspcb/cb_12_5.pdf)

80-Ball WLCSP (4.29mm x 5.04mm)

[cb-80-5](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/wlcspcb/CB_80_5.pdf)

324-Ball BGA\_ED (15mm x 15mm x 1.58mm)

[BP-324-3](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/bga_ed-bp/bp_324_3.pdf)

49-Ball CSPBGA (8mm x 8mm x 1.465mm)

[BC-49-4](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/cspbga-bc/BC_49_4.pdf)

165-Ball CSPBGA (8mm x 8mm)

[bc-165-1](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/cspbga-bc/BC_165_1.pdf)

4-Lead MP86  
 

[hrj-4-1](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/hittite-legacy-packages/HRJ-4-1.pdf)

25-Ball WLCSP (2.54mm x 2.54mm)

[cb-25-7](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/wlcspcb/CB_25_7.pdf)

7-Lead SMT  
 

[hrj-7-1](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/hittite-legacy-packages/HRJ-7-1.pdf)

24-Lead SSOP  
 

[rs-24](https://www.analog.com/media/en/package-pcb-resources/package/320374674442511497835109639857509214147739880195087340rs_24.pdf)

14-lead Module (27 mm x 23.7 mm x 12.4 mm)

[ML-14-7](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/module/ML_14_7.pdf)

25-Lead LGA\_CAV (4mm x 4mm x 1.55mm)

[CE-25-1](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lga_cavce/CE-25-1.pdf)

12-Lead LCC (3mm x 3mm w/ EP)

[he-12-1](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/hittite-legacy-packages/HE-12-1.pdf)

40-Lead LFCSP (6mm x 6mm)

[CP-40-27](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lfcspcp/cp-40/CP_40_27.pdf)

256-Ball CSPBGA (12mm x 12mm)

[bc-256-1](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/cspbga-bc/bc_256_1.pdf)

48-Lead LQFP\_EP (7mm x 7mm x 1.60mm w/ EP)

[SW-48-2](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lqfp_edsw/sw-48-2.pdf)

52-Lead MQFP (13.2mm x 10mm)

[s-52-1](https://www.analog.com/media/en/package-pcb-resources/package/57875705s_52_1.pdf)

16-Lead LGA (3mm x 3mm)

[cc-16-3](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lgacc/cc_16_3.pdf)

36-Lead LFCSP (6mm x 6mm w/ EP)

[cp-36-4](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lfcspcp/cp-36/CP_36_4.pdf)

14-Lead Side Brazed CerDIP  
 

[d-14](https://www.analog.com/media/en/package-pcb-resources/package/51235406179213d_14.pdf)

425-Ball CSPBGA (19mm x 19mm)

[bc-425-1](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/cspbga-bc/bc_425_1.pdf)

16-Ball WLCSP (2mm x 2mm x 0.59mm)

[cb-16-1](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/wlcspcb/CB_16_1.pdf)

169-Ball CSPBGA (9mm x 9mm)

[bc-169](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/cspbga-bc/bc_169.pdf)

24-Lead PDIP  
 

[n-24-1](https://www.analog.com/media/en/package-pcb-resources/package/50726455539629n_24_1.pdf)

44-Lead PLCC  
 

[p-44-1](https://www.analog.com/media/en/package-pcb-resources/package/24254983pp_44_1.pdf)

16-Lead QFN (3mm x 3mm w/ EP)

[hcp-16-2](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/hittite-legacy-packages/HCP-16-2.pdf)

289-Ball CSPBGA (12mm x 12mm x 1.26mm)

[bc-289-2](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/cspbga-bc/bc_289_2.pdf)

10-Lead MSOP  
 

[rm-10](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/msoprm/rm_10.pdf)

80-Lead LQFP (14mm x 14mm)

[st-80-2](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lqfpst/ST_80_2.pdf)

48-Lead QFN (7mm x 7mm w/ EP)

[hcp-48-1](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/hittite-legacy-packages/HCP-48-1.pdf)

80-Lead LQFP (14mm x 14mm w/ heat sink)

[sq-80-2](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lqfp_edsq/sq_80_2.pdf)

28-lead LFCSP (4mm x 4mm x 0.95mm w/EP)

[cp-28-9](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lfcspcp/cp-28/CP_28_9.pdf)

10-Lead FlatPack  
 

[f-10-2](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/flatpack-f/F-10-2.pdf)

28-Lead CerDIP (Side Brazed)

[d-28-2](https://www.analog.com/media/en/package-pcb-resources/package/28824602d_28_2.pdf)

40-Lead LFCSP (6mm x 6mm w/ EP)

[cp-40-7](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lfcspcp/cp-40/CP_40_7.pdf)

20-Lead Module (24.15mm x 27.7mm x 10.8mm)

[ml-20-2](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/module/ml_20_2.pdf)

5-Lead SOT-23  
 

[rj-5](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/sot-23rj/rj_5.pdf)

74-Ball CSPBGA (12mm x 12mm)

[bc-74](https://www.analog.com/media/en/package-pcb-resources/package/466795438540441203902150bc_74.pdf)

56-Lead LFCSP (9mm x 9mm x 0.85mm w/ EP)

[cp-56-7](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lfcspcp/cp-56/CP_56_7.pdf)

20-Lead Power SOIC  
 

[rr-20-1](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/ltc-legacy-soic/RR-20-1.pdf)

12-Lead LFCSP (3mm x 3mm w/ EP)

[cs-12-4](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lfcsp-cs-side-solderable/cs-12/CS_12_4.pdf)

24-Lead LFCSP (4mm x 4mm w/ EP)

[cp-24-7](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lfcspcp/cp_24_7.pdf)

64-Lead TQFP (7mm x 7mm)

[su-64-1](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/tqfpsu/su_64_1.pdf)

52-Lead LQFP (10mm x 10mm x 1.4mm w/ EP)

[sq-52-1](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lqfp_edsq/sq_52_1.pdf)

8-Lead LS6 (6mm x 6mm)

[hlcc-8-1](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/hittite-legacy-packages/HLCC-8-1.pdf)

119-Ball PBGA (14mm x 22mm)

[b-119](https://www.analog.com/media/en/package-pcb-resources/package/41287574715699b_119.pdf)

32-Lead METAL\_DIP (44.2mm x 28.96mm)

[M-32](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/metal-dip-m/M_32.pdf)

20-Lead PDIP  
 

[n-20](https://www.analog.com/media/en/package-pcb-resources/package/50601349676519n_20.pdf)

24-Lead CerDIP (Hybrid Side-Brazed)

[dh-24c](https://www.analog.com/media/en/package-pcb-resources/package/494685263dh_24c.pdf)

12-Lead LFCSP (4mm x 4mm x 1.45mm w/ EP)

[cp-12-9](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lfcspcp/cp-12/CP_12_9.pdf)

20-Lead LFCSP (4mm x 4mm w/ EP)

[cp-20-4](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lfcspcp/cp_20_4.pdf)

16-Ball WLCSP (1.56mm x 1.56mm)

[cb-16-6](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/wlcspcb/CB_16_6.pdf)

64-Lead TQFP (10mm x 10mm)

[su-64-2](https://www.analog.com/media/en/package-pcb-resources/package/44524945su_64_2.pdf)

8-Lead LFCSP (3mm x 3mm w/ EP)

[cp-8-3](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lfcspcp/cp_8_3.pdf)

304-Ball SBGA (31mm x 31mm)

[bp-304](https://www.analog.com/media/en/package-pcb-resources/package/3733895948083bp_304.pdf)

6-Lead TSOT  
 

[uj-6](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/tsotuj/uj_6.pdf)

Connectorized Hermetic Module (C5)

[hml-5](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/hittite-legacy-packages/HML-5.pdf)

100-Lead LQFP (14mm x 14mm w/ heatsink)

[sw-100-2](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lqfp_edsw/sw_100_2.pdf)

12-Lead LGA (7.35mm x 7.2mm)

[cc-12-1](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lgacc/cc_12_1.pdf)

24-Lead QFN (4mm x 4mm w/ EP)

[hcp-24-1](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/hittite-legacy-packages/HCP-24-1.pdf)

40-Lead LGA  
 

[cc-40-5](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lgacc/CC_40_5.pdf)

3-Lead SOT-223  
 

[kc-3](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/sot_223kc/kc_3.pdf)

4-Ball WLCSP (0.8mm x 0.8mm)

[cb-4-3](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/wlcspcb/CB_4_3.pdf)

16-Lead QSOP w/ EP  
 

[hrc-16-1](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/hittite-legacy-packages/HRC-16-1.pdf)

8-Lead SOIC w/ EP  
 

[HRD-8-1](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/hittite-legacy-packages/HRD-8-1.pdf)

16-Lead LFCSP (4mm x 4mm)

[cp-16-5a](https://www.analog.com/media/en/package-pcb-resources/package/45789401034275374892178cp_16_5a.pdf)

8-Lead MSOP  
 

[RM-8](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/hittite-legacy-packages/rm_8.pdf)

28-Lead QSOP  
 

[rq-28](https://www.analog.com/media/en/package-pcb-resources/package/196781212rq_28.pdf)

64-Lead LFCSP (9mm x 9mm w/ EP)

[cp-64-4](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lfcspcp/cp_64_4.pdf)

136-Ball CSPBGA (12mm x 12mm)

[bc-136](https://www.analog.com/media/en/package-pcb-resources/package/327325864833575181914184bc_136.pdf)

40-Lead LFCSP (6mm x 6mm w/ EP)

[cp-40-4](https://www.analog.com/media/en/package-pcb-resources/package/5297332792203067151cp_40_4.pdf)

32-Lead LFCSP (3mm x 3mm x 0.85mm w/ EP)

[cp-32-1](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lfcspcp/cp_32_1.pdf)

24-Terminal LGA (3mm x 3mm x 0.828mm)

[CC-24-12](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lgacc/cc-24-12.pdf)

33-Ball WLCSP (2.14 mm x 3.11 mm x 0.50 mm)

[cb-33-1](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/wlcspcb/CB_33_1.pdf)

16-Lead LFCSP (4mm x 4mm w/ EP)

[cp-16-13](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lfcspcp/cp-16/cp_16_13.pdf)

24-Lead CerDIP (Hybrid Side Brazed)

[dh-24a](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/hybrid-cerdip-dh/dh_24a.pdf)

10-Lead MSOP w/ EP  
 

[rh-10-1](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/msop_edrh/rh_10_1.pdf)

76-Ball CSPBGA (6mm x 6mm x 1.4mm)

[bc-76-1](https://www.analog.com/media/en/package-pcb-resources/package/607124133724bc_76_1.pdf)

16-Lead LFCSP (3mm x 3mm w/ EP)

[hcp-16-1](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/hittite-legacy-packages/HCP-16-1.pdf)

6-Lead SOT-26  
 

[HRJ-6-1](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/hittite-legacy-packages/HRJ-6-1.pdf)

40-Lead LFCSP (6mm x 6mm x 0.85mm w/EP)

[CP-40-19](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lfcspcp/cp-40/cp_40_19.pdf)

68-Lead CLCC (24.13mm x 24.13mm x 4.45mm)

[es-68-1](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/clcces/ES-68-1(formed).pdf)

12-Lead LFCSP (3mm x 3mm w/ EP)

[cp-12-6](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lfcspcp/cp-12/cp_12_6.pdf)

68-Lead CLCC (24.13mm x 24.13mm x 2.67mm)

[es-68-2](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/clcces/es_68_2.pdf)

256-Ball BGA (27mm x 27mm x 2.65mm w/EP)

[BP-256-2](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/sbga-heatsink/BP_256_2.pdf)

40-Lead LFCSP (6mm x 6mm x 0.75mm w/ EP)

[cp-40-12](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lfcspcp/cp-40/CP_40_12.pdf)

20-lead LFCSP (4mm x 4mm x 0.85mm w/EP)

[cp-20-22](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lfcspcp/cp-20/cp-20-22.pdf)

64-Lead LQFP (10mm x 10mm w/ EP)

[sw-64-2](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lqfp_edsw/sw_64_2.pdf)

Connectorized Hermetic Module (C13)

[hml-13](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/hittite-legacy-packages/HML-13.pdf)

16-Lead LFCSP (4mm x 4mm w/ EP)

[cp-16-10](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lfcspcp/cp_16_10.pdf)

16-Lead CerDIP  
 

[q-16](https://www.analog.com/media/en/package-pcb-resources/package/54083157002221q_16.pdf)

196-Ball BGA (12mm x 12mm)

[bp-196-2](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/sbga-heatsink/BP_196_2.pdf)

16-Lead LFCSP (3mm x 3mm x 0.85mm)

[cp-16-50](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lfcspcp/cp-16/cp_16_50.pdf)

Connectorized Hermetic Module (C11)

[hml-11](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/hittite-legacy-packages/HML-11.pdf)

52-Ball CSPGA (5mm x 5mm)

[bc-52](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/cspbga-bc/bc_52.pdf)

6-Lead LFCSP (3mm x 2mm w/ EP)

[cp-6-5](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lfcspcp/cp_6_5.pdf)

56-Lead LFCSP (8mm x 8mm w/ EP)

[cp-56-4](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lfcspcp/cp_56_4.pdf)

12-Lead LFCSP (4mm x 4mm w/ EP)

[cs-12-2](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lfcsp-cs-side-solderable/cs-12/CS_12_2.pdf)

16 ld LCC (6x6x1.52mm w/3.55 ep)

[EH-16-2](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lcc-ep/EH-16-2.pdf)

20-Ball WLCSP (2.15mm x 2.35mm x 0.6mm)

[cb-20-7](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/wlcspcb/CB_20_7.pdf)

208-Ball CSPBGA (17mm x 17mm x 1.75mm)

[bc-208-2](https://www.analog.com/media/en/package-pcb-resources/package/5644737621750bc_208_2.pdf)

182-Ball CSPBGA (12mm x 12mm x 1.7mm)

[bc-182](https://www.analog.com/media/en/package-pcb-resources/package/435944981798899302bc_182.pdf)

16-Lead SSOP  
 

[rs-16](https://www.analog.com/media/en/package-pcb-resources/package/31572257652246rs_16.pdf)

20-Lead LFCSP (4mm x 4mm)

[cp-20-1](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lfcspcp/cp_20_1.pdf)

18-Lead LCC (7mm x 7mm w/ EP)

[he-18-1](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/hittite-legacy-packages/HE-18-1.pdf)

52-Lead MQFP (10mm x 10mm)

[s-52-2](https://www.analog.com/media/en/package-pcb-resources/package/32717196300961s_52_2.pdf)

14-Lead LCC (9mm x 9mm x 4mm)

[ey-14-1](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lcce/ey_14_1.pdf)

144-Ball CSPBGA (13mm x 13mm x 1.85mm)

[bc-144-3](https://www.analog.com/media/en/package-pcb-resources/package/4570739740260815403bc_144_3.pdf)

80-Ball CSPBGA (10mm x 10mm)

[bc-80-2](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/cspbga-bc/bc_80_2.pdf)

9-Lead LGA\_CAV (4.72mm x 3.76mm)

[ce-9-1](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lga_cavce/ce_9_1.pdf)

6-Ball WLCSP (1.36mm x 0.76mm)

[cb-6-14](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/wlcspcb/CB_6_14.pdf)

28-Lead PSOP (17.9mm x 7.5mm)

[rp-28](https://www.analog.com/media/en/package-pcb-resources/package/306150045rp_28.pdf)

324-Ball CSPBGA (19mm x 19mm)

[bc-324-1](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/cspbga-bc/bc_324_1.pdf)

6-Ball WLCSP (0.905mm x 1.385mm)

[cb-6-7](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/wlcspcb/CB_6_7.pdf)

6-Ball WLCSP (0.95mm x 1.16mm)

[cb-6-15](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/wlcspcb/CB_6_15.pdf)

16-Lead QSOP  
 

[rq-16](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/qsoprq/rq_16.pdf)

196-Ball CSPBGA (15mm x 15mm x 1.9mm)

[bc-196-4](https://www.analog.com/media/en/package-pcb-resources/package/52079123195727bc_196_4.pdf)

8-Pin TO-99  
 

[h-08-1](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/headerh/h_08_1.pdf)

48-Terminal Land Grid Array \[LGA\]  
 

[CC-48-1](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lgacc/CC_48_1.pdf)

24-Lead LFCSP (4mm x 4mm w/ EP)

[cp-24-3](https://www.analog.com/media/en/package-pcb-resources/package/56702234806764cp_24_3.pdf)

88-Lead LFCSP (12mm x 12mm w/ EP)

[cp-88-6](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lfcspcp/CP_88_6.pdf)

8-Lead SOIC (Increased Creepage)

[ri-8-1](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/soic_wide-rw/RI_8_1.pdf)

40-Lead LFCSP (6mm x 6mm w/ EP)

[cp-40-10](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lfcspcp/cp-40/CP_40_10.pdf)

48-Lead TQFP (7mm x 7mm w/ EP)

[sv-48-5](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/tqfp_edsv/sv_48_5.pdf)

10-Lead Mini Small Outline Package with Exposed Pad  
 

[RH-10-3](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/msop_edrh/RH_10_3.pdf)

12-Lead LFCSP (4mm x 4mm w/ EP)

[cs-12-1](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lfcsp-cs-side-solderable/cs-12/CS_12_1.pdf)

24-Lead Flatpack  
 

[f-24](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/flatpack-f/f_24.pdf)

64-Lead LFCSP (9mm x 9mm w/ EP)

[cp-64-3](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lfcspcp/cp_64_3.pdf)

24-Lead QFN (4mm x 4mm w/ EP)

[hcp-24-2](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/hittite-legacy-packages/HCP-24-2.pdf)

48-Lead LFCSP (7mm x 7mm w/ EP)

[cs-48-1](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lfcsp-cs-side-solderable/cs-48/CS_48_1.pdf)

484-Ball BGA (19mm x 19mm)

[b-484](https://www.analog.com/media/en/package-pcb-resources/package/3235251121324624786157688555b484.pdf)

32-Lead LFCSP (5mm x 5mm x 1.45 w/EP)

[cs-32-4](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lfcsp-cs-side-solderable/cs-32/CS_32_4.pdf)

16-Lead SOIC\_CAV (10.30mm x 10.42mm x 3.58mm)

[RG-16-2](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/soic_pcprg/RG_16_2.pdf)

128-Lead MQFP (14mm x 20mm)

[s-128-1](https://www.analog.com/media/en/package-pcb-resources/package/511414619s_128_1.pdf)

100-Ball CSPBGA (9mm x 9mm x 1.4mm)

[bc-100-1](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/cspbga-bc/bc_100_1.pdf)

6-Ball WLCSP (0.96mm x 1.46mm)

[cb-6-17](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/wlcspcb/CB_6_17.pdf)

Connectorized Hermetic Module (C17)

[hml-17](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/hittite-legacy-packages/HML-17.pdf)

120-Ball CSPBGA (8mm x 8mm x 1.23mm)

[bc-120-3](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/cspbga-bc/BC_120_3.pdf)

32-Lead Side Brazed CerDIP (41.02mm x 23.11mm)

[dh-32c](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/hybrid-cerdip-dh/dh_32c.pdf)

240-Lead MQFP  
 

[s-240](https://www.analog.com/media/en/package-pcb-resources/package/59748450094758745169714887593s_240.pdf)

28-Lead LFCSP (5mm x 5mm x 0.75mm w/ EP)

[cp-28-10](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lfcspcp/cp-28/CP_28_10.pdf)

24-Lead Module (35.6mm x 44mm x 13.8mm)

[ML-24-3](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/module/ml_24_3.pdf)

108-Ball CSPBGA (10mm x 10mm x 1.4mm)

[bc-108-1](https://www.analog.com/media/en/package-pcb-resources/package/362811145bc_108_1.pdf)

144-Lead LQFP (20mm x 20mm w/ heatsink)

[sq-144-3](https://www.analog.com/media/en/package-pcb-resources/package/35836314649221sq_144_3.pdf)

204-Ball CSPBGA (12mm x 12mm x 1.4mm)

[bc-204](https://www.analog.com/media/en/package-pcb-resources/package/57724312598477bc_204.pdf)

80-Lead LQFP (12mm x 12mm x 1.4mm)

[st-80-1](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lqfpst/st_80_1.pdf)

48-Lead LFCSP (7mm x 7mm x 0.85mm w/ EP)

[cp-48-13](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lfcspcp/cp_48_13.pdf)

30-Ball WLCSP (3mm x 2.5mm)

[cb-30-3](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/wlcspcb/cb_30_3.pdf)

8-Lead LFCSP (3mm x 2mm x 0.75mm)

[cp-8-4](https://www.analog.com/media/en/package-pcb-resources/package/57080735642908cp_8_4.pdf)

10-Lead SIP  
 

[y-10(202)](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/sipy/y_10(202).pdf)

3-Lead LGA\_CAV (2.5mm x 3.35mm)

[ce-3-1](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lga_cavce/ce_3_1.pdf)

44-Lead LQFP (10mm x 10mm)

[st-44-1](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lqfpst/st_44_1.pdf)

64-Lead LQFP (7mm x 7mm)

[st-64-1](https://www.analog.com/media/en/package-pcb-resources/package/54932241139605st_64_1.pdf)

11-Lead PDIP  
 

[n-11](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/pdipn/n-11.pdf)

40-Lead LFCSP (6mm x 6mm w/ EP)

[cp-40-17](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lfcspcp/cp-40/CP_40_17.pdf)

256-Ball CSPBGA (17mm x 17mm x 1.7mm)

[bc-256-3](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/cspbga-bc/bc_256_3.pdf)

40-Lead LFCSP (6mm x 6mm x 0.75mm w/ EP)

[CP-40-26](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lfcspcp/cp-40/CP_40_26.pdf)

8-Lead Flat Package with Gullwing Formed Leads  
 

[fr-8-2](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/flatpack-f/FR-8-2.pdf)

42-Ball WLCSP (2.94mm x 2.84mm x 0.50mm)

[CB-42-1](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/wlcspcb/CB_42_1.pdf)

14-Lead CerDIP (Bottom Brazed)

[dh-14-1](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/bb-cerdipdh/dh_14_1.pdf)

20-Lead LFCSP (4mm x 4mm x 0.75mm w/ EP)

[cp-20-11](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lfcspcp/cp-20/CP_20_11.pdf)

68-Lead PLCC  
 

[p-68a](https://www.analog.com/media/en/package-pcb-resources/package/3952049764524854029344014438152809p_68a.pdf)

24-Lead LFCSP (4mm x 4mm w/ EP)

[cp-24-15](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lfcspcp/CP_24_15.pdf)

50-Lead LGA\_CAV (16mm x 14mm x 2.93mm)

[CE-50-2](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lga_cavce/CE-50-2.pdf)

32-Lead Side Brazed CerDIP (41.66mm x 22.99mm)

[dh-32f](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/bb-cerdipdh/dh_32f.pdf)

44-Lead LQFP (14mm x 14mm)

[st-44-2](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lqfpst/st_44_2.pdf)

32-Lead LFCSP (5mm x 5mm w/ EP)

[cp-32-7](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lfcspcp/cp-32/CP_32_7.pdf)

Connectorized Hermetic Module (C14)

[hml-14](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/hittite-legacy-packages/HML-14.pdf)

4-Ball WLCSP (0.82mm x 0.82mm)

[cb-4-2](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/wlcspcb/CB_4_2.pdf)

28-Lead LFCSP (4mm x 4mm w/ EP)

[cp-28-5](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lfcspcp/cp-28/cp_28_5.pdf)

64-Lead LFCSP (9mm x 9mm w/ EP)

[cp-64-15](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lfcspcp/CP_64_15.pdf)

10-Lead TO-100  
 

[h-10-1](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/headerh/h_10_1.pdf)

240-Lead CQFP, Heat Slug Down  
 

[qs-240-1b](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/cqfpqs/qs_240_1b.pdf)

44-Ball CSPBGA (12mm x 12mm x 1.4mm)

[bc-44-1](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/cspbga-bc/bc_44_1.pdf)

16-Lead LGA (9.35mm x 9.2mm)

[cc-16-2](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lgacc/cc_16_2.pdf)

16-Lead LFCSP (5mm x 5mm)

[cp-16-6](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lfcspcp/cp_16_6.pdf)

6-Terminal LGA\_CAV (4.72mm x 3.76mm x 3.5mm)

[ce-6-2](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lga_cavce/CE_6_2.pdf)

64-Lead LFCSP (9mm x 9mm w/ EP)

[cp-64-1](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lfcspcp/cp-64/CP_64_1.pdf)

16-Ball WLCSP (1.74mm x 1.74mm)

[cb-16-15](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/wlcspcb/CB_16_15.pdf)

16-Lead Flat Package with Gullwing Formed Leads  
 

[FR-16-2](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/flatpack-f/FR-16-2.pdf)

112-Ball CSP-BGA (6mm x 6mm x 1.083mm)

[BC-112-4](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/cspbga-bc/BC_112_4.pdf)

8-Lead LFCSP (3mm x 3mm w/ EP)

[cp-8-11](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lfcspcp/cp_8_11.pdf)

32-Lead TQFP (7mm x 7mm x 1mm)

[su-32-2](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/tqfpsu/su_32_2.pdf)

72-Lead LFCSP (10mm x 10mm w/ EP)

[cp-72-1](https://www.analog.com/media/en/package-pcb-resources/package/cp_72_1.pdf)

48-Lead LFCSP (7mm x 7mm x 0.85mm w/ EP)

[cp-48-9](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lfcspcp/cp_48_9.pdf)

32-Lead CerDIP (Side Brazed, 41.05mm x 23.11mm)

[dh-32d](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/hybrid-cerdip-dh/dh_32d.pdf)

4-Ball WLCSP (1.02mm x 0.95mm)

[cb-4-4](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/wlcspcb/cb_4_4.pdf)

20-Lead LGA (11.15mm x 11mm)

[cc-20-1](https://www.analog.com/media/en/package-pcb-resources/package/953157811cc_20_1.pdf)

16-Lead TSSOP  
 

[ru-16](https://www.analog.com/media/en/package-pcb-resources/package/RU-16.jpg)

256-Ball CSPBGA (17mm x 17mm x 2mm)

[bc-255-1](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/cspbga-bc/bc_255_1.pdf)

65-Ball WLBGA  
 

[bf-65-1](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/cspbga-bc/BF-65-1.pdf)

72-Terminal LGA (10mm x 10mm x 0.7mm)

[CC-72-3](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lgacc/CC_72_3.pdf)

48-Lead LFCSP (7mm x 7mm w/ EP)

[cp-48-5](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lfcspcp/cp_48_5.pdf)

12-Lead LFCSP (3mm x 3mm w/ EP)

[cp-12-5](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lfcspcp/CP_12_5.pdf)

32-Lead LFCSP (5mm x 5mm w/ EP)

[CG-32-2](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lfcsp-cav/CG-32-2.pdf)

12-Lead LFCSP (7mm x 7mm x 0.75mm w/ EP)

[cp-12-8](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lfcspcp/cp-12/CP_12_8.pdf)

Connectorized Hermetic Module (C1)

[HML-1](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/hittite-legacy-packages/HML-1.pdf)

14-Lead LFCSP (4mm x 3mm w/ EP)

[cp-14-1](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lfcspcp/cp-14/CP_14_1.pdf)

208-Lead LQFP (28mm x 28mm w/ EP)

[sw-208-1](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lqfp_edsw/sw_208_1.pdf)

16-Ball WLCSP (1.59mm x 1.59mm)

[cb-16-10](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/wlcspcb/CB_16_10.pdf)

20-Ball WLCSP (2.04mm x 1.705mm)

[cb-20-13](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/wlcspcb/CB_20_13.pdf)

12-Lead PDIP  
 

[n-12](https://www.analog.com/media/en/package-pcb-resources/package/213080991ad210_dip.pdf)

529-Ball CSP-BGA (19mm x 19mm x 1.36mm)

[bc-529-1](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/cspbga-bc/BC_529_1.pdf)

Connectorized Hermetic Module (C20)

[hml-20](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/hittite-legacy-packages/HML-20.pdf)

12-Lead LCC  
 

[e-12-1](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lcce/E-12-1.pdf)

3-Lead SOT-89  
 

[rk-3](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/sot-89rk/RK_3.pdf)

304-Ball PBGA (31mm x 31mm)

[b-304](https://www.analog.com/media/en/package-pcb-resources/package/3641645393185830319b_304.pdf)

316-Ball CSPBGA (17mm x 17mm)

[bc-316](https://www.analog.com/media/en/package-pcb-resources/package/5092430472609712019bc_316.pdf)

24-Lead LFCSP (5mm x 5mm w/ EP)

[cp-24-20](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lfcspcp/cp-24/CP_24_20.pdf)

6-Lead SOT-23  
 

[rj-6](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/sot-23rj/rj_6.pdf)

56-Lead LFCSP (8mm x 8mm x 0.75mm w/ EP)

[cp-56-16](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lfcspcp/cp-56/CP_56_16.pdf)

349-Ball CSPBGA (19mm x 19mm)

[bc-349-1](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/cspbga-bc/bc_349_1.pdf)

84-Lead LFCSP (10mm x 10mm w/ EP)

[cp-84-2](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lfcspcp/cp_84_2.pdf)

20-Lead LGA with EP  
 

[cc-20-4](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lgacc/cc_20_4.pdf)

20-Ball WLCSP (2.39mm x 2.39mm)

[cb-20-12](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/wlcspcb/CB_20_12.pdf)

Connectorized Hermetic Module (C12)

[hml-12](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/hittite-legacy-packages/HML-12.pdf)

18-Terminal Ceramic Leadless Chip Carrier  
 

[E-18-1](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lcce/E-18-1.pdf)

105-Ball CSPBGA (8mm x 8mm)

[bc-105-1](https://www.analog.com/media/en/package-pcb-resources/package/359546420bc_105_1.pdf)

12-Ball WLCSP (1.54mm x 2.04mm)

[cb-12-4](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/wlcspcb/cb_12_4.pdf)

16 ld LFCSP\_CAV (3x3x1.25mm w/1.15mm EP)

[CG-16-1](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lfcsp-cav/CG-16-1.pdf)

6-Lead SC70  
 

[hks-6-1](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/hittite-legacy-packages/HRK-6-1.pdf)  
HRK-6-1

24-Lead PCB Module with Connector Interface  
 

[ml-24](https://www.analog.com/media/en/package-pcb-resources/package/137792200ml_24_1.pdf)

432-Ball BGA (40mm x 40mm)

[bp-432](https://www.analog.com/media/en/package-pcb-resources/package/99289205bp_432.pdf)

16-Ball WLCSP (2.21mm x 2.21mm)

[cb-16-13](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/wlcspcb/cb_16_13.pdf)

16-Lead SOIC w/ EP  
 

[rd-16-3](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/soic_edrd/RD_16_3.pdf)

8-Lead LFCSP (2mm x 2mm w/ EP)

[cp-8-26](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lfcspcp/cp-8/CP_8_26.pdf)

2-Lead Flatpack  
 

[f-2](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/flatpack-f/F_2.pdf)

16-Lead QFN (3mm x 3mm w/ EP)

[hcp-16-3](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/hittite-legacy-packages/HCP-16-3.pdf)

25-Ball WLCSP (2.765mm x 2.545mm)

[cb-25-1](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/wlcspcb/CB_25_1.pdf)

96-Ball CSPBGA (8mm x 8mm)

[bc-96](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/cspbga-bc/bc_96.pdf)

14-Ball WLCSP (2.123mm x 1.128mm)

[cb-14-2](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/wlcspcb/CB_14_2.pdf)

28-Lead TSSOP (4.4mm x 9.7mm)

[ru-28](https://www.analog.com/media/en/package-pcb-resources/package/249854663ru_28.pdf)

196-Ball CSPBGA (12mm x 12mm x 1.3mm)

[bc-196-7](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/cspbga-bc/bc_196_7.pdf)

32-Lead LFCSP (5mm x 5mm x 0.95mm w/ EP)

[cp-32-30](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lfcspcp/cp-32/CP_32_30.pdf)

PCB Module with Connector Interface  
 

[ml-22-1](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/module/ml_22_1.pdf)

100-Ball CSPBGA (9mm x 9mm x 1.25mm)

[bc-100-4](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/cspbga-bc/BC_100_4.pdf)

44-Lead MQFP (13.2mm x 10mm)

[s-44-1](https://www.analog.com/media/en/package-pcb-resources/package/217364s_44_1.pdf)

24-Lead LFCSP (4mm x 5mm w/ EP)

[cp-24-13](https://www.analog.com/media/en/package-pcb-resources/package/cp_24_13.pdf)

196-Ball CSPBGA (15mm x 15mm)

[bc-196-2](https://www.analog.com/media/en/package-pcb-resources/package/53689996208570bc_196_2.pdf)

9-Ball WLCSP (1.24mm x 1.24mm)

[cb-9-4](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/wlcspcb/CB_9_4.pdf)

36-Lead LFCSP (6mm x 6mm x 0.85mm w/ EP)

[cp-36-3](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lfcspcp/cp_36_3.pdf)

64-Lead TQFP (10mm x 10mm w/ EP)

[sv-64-3](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/tqfp_edsv/sv_64_3.pdf)

20-Lead QFN (4mm x 4mm w/ EP)

[hcp-20-1](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/hittite-legacy-packages/HCP-20-1.pdf)

400-Ball BGA (17mm x 17mm x 1.28mm)

[bc-400-3](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/cspbga-bc/BC_400_3.pdf)

16-Lead LCC (6mm x 6mm w/ EP)

[he-16-1](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/hittite-legacy-packages/HE-16-1.pdf)

16-Lead LFCSP (3mm x 3mm w/ EP)

[cp-16-2](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lfcspcp/cp_16_2.pdf)

8-Lead LFCSP (3mm x 3mm w/ EP)

[cp-8-5](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lfcspcp/cp_8_5.pdf)

Connectorized Hermetic Module (C6)

[hml-6](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/hittite-legacy-packages/HML-6.pdf)

160-Lead MQFP  
 

[s-160](https://www.analog.com/media/en/package-pcb-resources/package/58988587574807545054807693309s_160.pdf)

176-Lead LQFP (24mm x 24mm w/ EP)

[sq-176-2](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lqfp_edsq/sq_176_2.pdf)

16-Lead LFCSP (4mm x 4mm x 0.85mm w/ EP)

[cp-16-4](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/lfcspcp/cp_16_4.pdf)

40-Lead LFCSP (6mm x 6mm w/ EP)

[cp-40-2](https://www.analog.com/media/en/package-pcb-resources/package/cp_40_2.pdf)

64-Lead TQFP (10mm x 10mm w/ EP)

[sv-64-4](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/tqfp_edsv/sv_64_4.pdf)

32-Lead BB Hybrid DIP (43.89mm x 27.99mm)

[dh-32e](https://www.analog.com/media/en/package-pcb-resources/package/pkg_pdf/hybrid-cerdip-dh/dh_32e.pdf)

官方指定ECAD平台
----------

[合作平台Ultra Librarian](https://www.analog.com/cn/design-center/packaging-quality-symbols-footprints/symbols-and-footprints.html)

https://a1024.synology.me:1024/%e6%94%b6%e5%bd%95%e5%85%83%e5%99%a8%e4%bb%b6%e5%8e%82%e5%ae%b6%e6%b8%85%e5%8d%95/