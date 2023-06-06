---
title: 'Altium Designer Dblib-基于数据库方式管理的元器件中心库（公共数据库）'
date: Sat, 16 Apr 2022 01:07:33 +0000
draft: false
tags: ['Altium']
---

1中心库简介
======

1.1公共数据库
--------

公共数据库是指数据库软件生成的各种包含元器件信息的表格文件。Altium Design通过创建和使用关联数据库\*．DBLib文件，可直接从公共数据库调取元器件并通过连接库文件与公共数据库保持同步更新，使当前设计文件中的元器件参数与器件库中元器件资料变更一致。当Libraries面板加载了关联数据库后，相当一个数据库浏览器，可由此选取元件。

1.2公共数据库的连接
-----------

Altium Designer提供两个用于连接公共数据库的文件，一是关联数据"库文件"(\*．DBLib)：二是数据库"链接文件"。

### 1.2.1关联数据库"库文件"

关联数据库文件定义了电路设计原理图元件和公共数据库中相匹配记录之间的联系。匹配记录则是由单个关键字段或多个关键字段来建立。这种方式将元件的符号、模型和参数信息作为外部数据库(Access或Excel等文件)保存，而原理图的器件库文件则仅仅定义了元件的符号。  
在关联数据库中选择元件后，通过相关字段定义的映射，元件模型和参数信息会随之建立。这些参数通过连接文件与外部数据库保持同步匹配联系。这种方式用于"多数据库记录对应一个元件"的模式，即调用一个元件可检索到多条记录参数。  
关联数据库通常采用面向库的模式配置\*．DBLib文件，只需作为Libraries面板的可用元件库使用，例如，在公共数据库中建立一个所有电阻详细资料的文件或所有电容详细资料的文件，不需添加到工程项目中。这样可在任何设计中从公共数据库记录中有效检索元件信息，动态获取元件。

### 1.2.2数据库"链接"文件

数据库链接(\*．DBLink)文件通过关键字段定义原理图元件和关联数据库记录之间的匹配关系。元件的模型参数预先定义为库元件的一部分，之后将连接文件添加到PCB项目或封装库中，可确保元件信息与关键字段内容同步。此方法用于"一个数据库对应一个元件"的模式，即数据库中元件不会重复出现。  
设计者在使用数据库放置一个器件时，Altium Designer软件通过数据库接口链接到公共数据库并读取与这个元器件相关的所有列表。读取到元器件的各种模型信息并加载到设计中，同时也将其他相关信息，如采购信息和库存信息等也加载到元器件的属性中。  
由于数据库形式固定了元器件各种模型之间的对应关系，所以实现了设计元件库的统一管理。如果数据库来源于公司的PDM/ERP系统，就可以实现Altium Designer电子开发平台与PDM/ERP系统在器件库的集成。  
完整数据库驱动的器件信息系统DBLIB为每个集成库元件添加了与数据库的接口链接，可以实现远程调用数据库信息。SVNDBLIB在DBLIB的基础上，将元器件各种模型信息添加到PDM/ERP系统的版本控制流程，使Altium Designer的电子设计平台集成到PDM/ERP系统中，更加确保了设计元件库的安全性和统一管理。  
在设计中实时查看数据库中各种元器件的采购信息和库存信息，为设计人员与采购人员之间建立了双向沟通的桥梁。避免了由于元器件的采购周期太长、采购差错、研发产品成本超过预算、大量长期不用的元器件占据库存管理的资源等原因造成的研发延期和浪费现象。

1.3特点
-----

公共数据库规模大、数据量多，增长迅速，使用便捷、无时空限制，不同的用户可在不同的时间使用，可直接从公共数据库调取元器件并通过连接库文件与公共数据库保持同步更新，使当前设计文件中的元器件参数与器件库中元器件资料变更一致。检索结果的显示与输出灵活、多样 ，方便使用。

2中心库创建
======

2.1打开AD10，新建DBLIB文件
-------------------

### 2.1.1File->New->Library->Database Library

![](https://a1024.synology.me:222/images/blog2022/Altium_Designer_Dblib1.png)

### 2.1.2选择数据管理文件类型

在数据类型选择栏，可以导入Excel和Access数据文件，此处以Access为例。

![](https://a1024.synology.me:222/images/blog2022/Altium_Designer_Dblib2.png)

2.2创建数据管理文件
-----------

### 2.2.1新建Access数据库文件，后缀.mdb

![](https://a1024.synology.me:222/images/blog2022/Altium_Designer_Dblib3.png)

### 2.2.2配置数据管理文件

打开Central lib.mdb按照指定数据格式建立数据文件表头。  
表头需要写入我们关心的参数，也就是每种物料都共有的一些属性，可以根据需要添加。比如物料代码、物料类型、型号信息、厂家信息等，方便查询管理。  
其中，Library Path（原理图库路径）、Library Ref（原理图标号）、Footprintf Path（PCB封装库路径）、Footprintf Ref（PCB封装标号）必须创建，否则后续无法与原理库以及封装库文件建立正确链接关系。

![](https://a1024.synology.me:222/images/blog2022/Altium_Designer_Dblib4.png)

2.3建立链接
-------

### 2.3.1导入文件

输入信息完成，保存Access文件。回到AD软件，选择数据类型为Microsoft Access，找到Central lib.mdb的路径。

![](https://a1024.synology.me:222/images/blog2022/Altium_Designer_Dblib5.png)

### 2.3.2链接

点击Connect，可以看到我们新建项目信息已经被识别

![](https://a1024.synology.me:222/images/blog2022/Altium_Designer_Dblib6.png)

![](https://a1024.synology.me:222/images/blog2022/Altium_Designer_Dblib7.png)

2.4数据管理
-------

物料的属性条目已经建立，后续物料管理就可以根据各个物料的实际情况，将数据按照格式填入Access数据库中。

![](https://a1024.synology.me:222/images/blog2022/Altium_Designer_Dblib8.png)

3中心库应用
======

3.1中心库文件介绍
----------

*   Footprint.PcbLib，元器件封装库；
*   Symbol.SchLib，原理符号库；
*   Central lib.DbLib，关联/加载文件；
*   Central lib.mdb，数据库文件，信息管理；

3.2路径加载
-------

### 3.2.1打开设置窗口

打开AD软件，右下角找到System按钮单击，在弹出的窗口选择Libraries，打开Libraries窗口。

![](https://a1024.synology.me:222/images/blog2022/Altium_Designer_Dblib9.png)

### 3.2.2打开加载窗口

点击Libraries按钮，打开路径加载窗口，选择文件存放路径，加载..DbLib中心库文件。

![](https://a1024.synology.me:222/images/blog2022/Altium_Designer_Dblib10.png)

### 3.2.3设置显示字段

器件列表任意空白位置右击，在弹出窗口选择列设置选项Select Columns，选择想要显示的字段即可

![](https://a1024.synology.me:222/images/blog2022/Altium_Designer_Dblib11.png)

![](https://a1024.synology.me:222/images/blog2022/Altium_Designer_Dblib12.png)

![](https://a1024.synology.me:222/images/blog2022/Altium_Designer_Dblib13.png)

3.3应用
-----

### 3.3.1放置器件

从封装列表直接拖至原理图中便可以实现器件放置。

![](https://a1024.synology.me:222/images/blog2022/Altium_Designer_Dblib14.png)

### 3.3.2查看属性

双击器件可以发现，我们在Access数据库中填写的器件相关信息都已经自动连接到原理中中，封装库也是对应好的。

![](https://a1024.synology.me:222/images/blog2022/Altium_Designer_Dblib15.png)