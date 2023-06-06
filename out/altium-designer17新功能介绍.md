---
title: 'Altium Designer17新功能介绍'
date: Thu, 19 Jan 2023 07:12:46 +0000
draft: false
tags: ['Altium']
---

[更多官方新功能介绍](https://www.altium.com/cn/documentation/altium-designer/new/?version=17.0)

![](https://a1024.synology.me:222/images/blog2023/AD17tu.png)

ACTIVEROUTE 动态布线
----------------

  ActiveRoute是一个自动化的交互布线技术，可提供有效的多网络的布线算法，添加到由设计者选择的特定网络或连接。ActiveRoute还允许设计人员交互定义的路由路径或指南

 ActiveRoute不是一个自动布线器，它是一个引导互动布线器侧重于一组选定网的简洁，优质的布线。

![AD17101.gif](https://a1024.synology.me:222/images/blog2023/AD17101.gif)

POST-ROUTE GLOSSING TOOL 布线后平滑工具
--------------------------------

    菜单：Edit » Gloss (或 Route » Gloss Selected)    默认键盘快捷键Ctrl + Alt + G

BACK DRILLING 背钻控制
------------------

 对高速信号通孔做背钻，去除残端，内容较多详见 [官网链接](http://www.altium.com/documentation/17.0/display/ADES/((Controlled+Depth+Drilling,+or+Back+Drilling))_AD)

NEW PROJECTRELEASER 新项目发布工具
---------------------------

       方便用户输出各种数据  
       提供一个崭新、直观的新项目发布工具，你可以直接发布相关的制作数据、安装数据、设计原文件，而无需在各界面上切换，甚至无需担心输出文件。  
       下述视频仅为一个简单应用 实际功能强大到没朋友

DESIGN RULES IMPROVEMENTS 设计规则进一步完善
-----------------------------------

![AD17102.gif](https://a1024.synology.me:222/images/blog2023/AD17102.gif)

简化间距规则，Arc和Track统一称为Track  Fill Poly Region统一成为Copper

![AD17103.jpg](https://a1024.synology.me:222/images/blog2023/AD17103.jpg)

   并允许忽略同一个器件的pad to pad间距

![AD17104.jpg](https://a1024.synology.me:222/images/blog2023/AD17104.jpg)

![AD17105.jpg](https://a1024.synology.me:222/images/blog2023/AD17105.jpg)

 同时新增hole元素，允许编辑元素到孔壁的间距

![AD17106.jpg](https://a1024.synology.me:222/images/blog2023/AD17106.jpg)

  检查布线未连到焊盘中心  
   去除差分网络（Parallel Segment rule）并行耦合长度检查

SMART COPPEREDITING 智能铜箔编辑
--------------------------

Smart Copper Editing可以轻松地直接在工作区中对区域，定义板框和铜皮进行图形化管理

合并选择的铜皮：使铜皮交叉并全选，然后在其中一个上右击选择 Polygon Actions » Combine Selected Polygons

![](https://a1024.synology.me:222/images/blog2023/11_178_092212a97ca73e6.gif)

减选铜皮：使铜皮交叉并全选，指向主体铜皮右击选择olygon Actions » Subtract Selected Polygons ，减选其他图形

![](https://a1024.synology.me:222/images/blog2023/11_178_35d7dc958486157.gif)

改变编辑顶点  
全句柄（Full Handles）：多边形的角。  
空句柄（Empty Handles）：多边形单边线（弧）的中心。  
按住（开始时）Ctrl可以在铜皮边缘任意位置增加全句柄

![](https://a1024.synology.me:222/images/blog2023/AD17203.jpg)

全句柄和空句柄可以直接通过鼠标移动并通过Shift+Space切换线性

![](https://a1024.synology.me:222/images/blog2023/AD17204.jpg)

修改多边形边框：选择铜皮右击Polygon Actions »Modify Polygon Border

![AD17205.gif](https://a1024.synology.me:222/images/blog2023/AD17205.gif)

智能编辑板的形状：同上类似Design » Modify Board Shape

![AD17206.gif](https://a1024.synology.me:222/images/blog2023/AD17206.gif)

SUPPORT FOR PARAMETERS IN PCBFOOTPRINTS对封装中的参数支持
------------------------------------------------

着实有些看不懂，友人说：在目标中附带参数值是Altium Design提供的强大而灵活的往PCB设计中注入附加信息的工具。参数可用于一定范围的层级，包括一个设计中关于项目的，文档的，模板的，以及单个元素参数。 小伙伴们有需要的自己看吧 [http://www.altium.com](http://www.altium.com/documentation/17.0/display/ADES/NFS_17_0((Support+for+Parameters+in+PCB+Footprints))_AD)

![AD17207.jpg](https://a1024.synology.me:222/images/blog2023/AD17207.jpg)

![AD17208.jpg](https://a1024.synology.me:222/images/blog2023/AD17208.jpg)

SELECTION AND DISPLAY IMPROVEMENTS 选取和显示方面的增强
---------------------------------------------

新的套索选择功能，使您能够通过定义的自由形式套索和智能拖动选择来选择（和取消选择）对象，其中选择功能根据拖动的矩形选择区域的方向而改变。

套索选择： Edit » Select » Lasso Select 或按键SE 单击起点开始 按空格键在自由形式和折线模式之间切换

![AD17209.gif](https://a1024.synology.me:222/images/blog2023/AD17209.gif)

Edit » DeSelect » Lasso Deselect 或键盘按键XE 可用相同方式减选对象  
智能拖动选择从左向右拖动选择窗口 -选择完全落在选择区域边界内的所有对象。原Edit » Select » Inside Area  
从右向左拖动选择窗口 -选择完全位于选择区域内或由其边界触摸的所有对象。原Edit » Select » Touching Rectangle

![AD17210.gif](https://a1024.synology.me:222/images/blog2023/AD17210.gif)

增强SELECT NEXT功能：Edit » Select » Select Next 默认快捷键Tab先选择的初始对象，该命令用于基于逻辑层次结构扩展选择以包括下一较高级对象（或多个对象），自己多用用就知道了，逻辑关系如下  
Track Segment ---> All Connected (Contiguous) Track on the Same Layer ---> All Connected Copper ---> All Electrical Objects in the Associated NetConnected Pad ---> All Connected (Contiguous) Track on the Same Layer ---> All Connected Copper ---> All Electrical Objects in the Associated Net  
Unconnected Pad ---> All Electrical Objects in the Associated NetVia ---> All Connected (Contiguous) Track on Layers Associated with Via ---> All Connected Copper ---> All Electrical Objects in the Associated Net  
Copper (Region/Polygon Pour/Fill) ---> All Connected Copper ---> All Electrical Objects in the Associated NetFree Pad/Via ---> All Connected (Contiguous) Track on the Same Layer as Pad, or on Layers Associated with Via---> All Connected Copper ---> All Electrical Objects in the Associated Net.

![AD17211.gif](https://a1024.synology.me:222/images/blog2023/AD17211.gif)

这个功能在使用ActiveRoute或Gloss功能时，此功能选择非常有效。新增按住Alt键为选择connection 可理解为飞线

CROSS SELECT MODE AND CROSS-PROBING 交互选择模式和交互探查
-----------------------------------------------

您现在可以使用“交叉选择模式”功能选择一系列对象类型。 原理图和PCB之间的交叉选择

菜单及快捷键：Tools- Cross Select Mode需配置首选项

![AD17212.jpg](https://a1024.synology.me:222/images/blog2023/AD17212.jpg)

首选项可设置使能选项和遮罩类型及缩放选项

LAYERS TACK MANAGEMENTENHANCEMENTS 层叠管理能力更加强大
---------------------------------------------

可以保存及加载

![AD17214.jpg](https://a1024.synology.me:222/images/blog2023/AD17214.jpg)

图层对比及编辑功能

![AD17215.jpg](https://a1024.synology.me:222/images/blog2023/AD17215.jpg)