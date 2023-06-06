---
title: 'Cadence to Altium'
date: Sat, 16 May 2020 06:35:39 +0000
draft: false
tags: ['Allegro', 'Altium', '设计软件']
---

https://v.qq.com/x/page/j3131ncktxz.html

**PCB**
-------

**需求文件：**Altium Designer以及Allegro导入扩展程序、Allegro软件

**转换要点：**Altium Designer导入Allegro是基于Allegro的ASCII格式.alg实现，.alg是由Allegro和它的转换器extracta.exe从.brd文件中提取得到，该文件转换器由Altium Designer随附的特殊批处理文件调用。

**转换步骤**

如果计算机同时安装了Allegro和Altium Designer，向导可以直接将Allegro PCB文件（\*.brd）导入并转换为Altium Designer PCB文件（\*.PcbDoc）无需执行下述1-2步（直接跳到第三部），导入向导中导入文件只需选择brd或alg中的一个。

1、在Altium安装目录\\System中找到Allegro2Altium.bat和AllegroExportViews.txt，复制到装有Allegro的计算机需要转换的brd路径下

2、在此目录，新建txt文本写入Allegro2Altium "your\_file.brd"（你的brd文件名如果包含空格需要增加双引号）,另存为bat后双击执行。将生成.alg格式文件。

![](https://www.altium.com/documentation/sites/default/files/resize/wiki_attachments/296893/AllegroExtractTool-800x670.png)

> tip：在标准的Allegro安装中，专有extracta.exe文件转换程序被添加为系统环境路径，因此可以从所有位置访问。该Allegro2Altium批处理文件，待处理的转换过程中，如果该程序无法访问将失败。

3.使用装有Altium的计算机使用Altium导入向导导入Allegro设计文件（.brd或.alg）

4.选择规则文件导入（可选）

![](https://www.altium.com/documentation/sites/default/files/resize/wiki_attachments/300321/ImportWizard_AllegroConstraintsFiles_AD20-600x463.png)

5.设置功能选项

![](https://www.altium.com/documentation/sites/default/files/wiki_attachments/300321/ImportWizard_AllegroImportWizard_OptimizeClearanceRules_AD20.png)

*   Polygon Connect Options：使用全连接或relief连接方式
*   Plane Connect Options：同上
*   是否导入Copper 的 Cutout导入，选择此选项Cutout将变为Void和优化间距规则

6.设置层映射

![](https://www.altium.com/documentation/sites/default/files/wiki_attachments/300321/AllegroImportWizard_CurrentPCBLayerMappings_AD20.png)

使用Load Layer Mapping和Save Layer Mapping可以加载和保存层映射关系，方便调用。

7.工程设置

8.完成

> tip：导入向导提供了默认的“图层映射”设置，可以对其进行修改并将其保存为\*.ini文件。导入向导使用该映射为导入设计中的每个PCB构建层映射，因此在导入多个PCB文件时，可以加载保存的映射配置文件并将其应用于单个（或所有）PCB文件。

**官网教程：[Allegro Import](https://www.altium.com/documentation/altium-designer/allegro-import-ad)  ****[Import Wizard-Allegro Design Files](https://www.altium.com/documentation/altium-designer/edaimporter-dlg-importermanagerformimport-wizard-ad#ImportWizard-AllegroDesignFiles)**

**关于Allegro的****extracta**  
功能：读取Allegro的二进制格式.brd将数据转换为ASCII文件

![](http://a1024.synology.me:222/images/blog2022/Allegro%E7%9A%84extracta.png "点击查看原图")

上述转换Allegro to Altium的应用中AllegroExportViews.txt=<command.txt> Allegro2Altium.bat文件完成了 转换的相关处理和命令  
更多介绍可从Allegro帮助文件中搜索extracta、extract\_ui、Extracting Views获得