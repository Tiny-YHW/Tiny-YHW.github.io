---
layout: wiki
title: What’s New
cate1: Altium PCB
cate2: 
---

![](https://a1024.synology.me:222/images/blog2022/Promo2.jpg){:target="_blank"}

* * *

各版本主要更新
-------

不全个人整理，可能存在错误，如发现错误欢迎联系我指出

### 已知跨版本问题

AD6之前的版本不支持region图形，如果使用6之后的版本做了region存到低版本或用低版本打开，region会丢失，如果设计需要同时兼容6之前的版本请不要使用region

AD14开始针对差分线线宽线间距一齐设置，切换版本时，规则管理对于此项处理逻辑不一样，需重新定义线宽使用规则

AD15开始支持xSignals如果 从15及之后版本规则管理器设置了此功能，使用15之前的版本开设计修改时，因DRC会判断无效程序一直报错，可以通过删除此类规则解决此问题（本条规则应该对所有高版本支持的规则类目语法有效，举一反三）

AD18及以上版本与低版本（AD16及以下）切换时有时候会出现莫名的问题，具体表现为器件不能被选择，显示异常等，可尝试使用AD17版本打开PCB并保存一次设计来修复类似问题

### Altium Designer 21（2021-2022）

[官方更新说明](https://www.altium.com/documentation/altium-designer/release-notes-for-altium-designer?version=21)

[通过插入图片功能增加Logo，Place->Graphics](https://a1024.synology.me:1024/altium-pcb%e4%b8%ad%e6%b7%bb%e5%8a%a0%e5%9b%be%e5%bd%a2/)

[新的规则管理编辑器](https://v.qq.com/x/page/v3215lrr5v8.html)

[吴川斌整理Altium Designer AD 21 下载及安装教程](https://www.mr-wu.cn/altium-designer-ad-21-free-download/)

### Altium Designer 20（2019-2021）

[Altium Designer20 新功能](https://a1024.synology.me:1024/?p=656)

\[Altium Designer 设计软件合集\] [https://pan.baidu.com/s/1Rt9oTYSu4TMXPIeYepaPrQ](https://pan.baidu.com/s/1Rt9oTYSu4TMXPIeYepaPrQ) 提取码: ehw6

### [Altium Designer 18（2017-2018）](https://www.altium.com/documentation/altium-designer/new-in-altium-designer?version=18.0)

[公众号引文](https://mp.weixin.qq.com/s?__biz=MzI2NDQxMjg4NA==&mid=2247483900&idx=1&sn=57699d83c4cca444356c727a0a93095c&chksm=eaac4a47dddbc3516a800b3054fed82cc3641e9e46f9bc9bd9a777de5d7a160523f0e4b21b75#rd)

不再支持32位系统  
全新界面  
全新版本  
可以认为是一个全新版本不做功能新增介绍  
[Draftsman功能支持](https://a1024.synology.me:1024/%e5%88%a9%e7%94%a8draftsman%e5%bf%ab%e9%80%9f%e5%88%9b%e5%bb%ba%e7%94%b5%e8%b7%af%e6%9d%bf%e7%9a%84%e8%a3%85%e9%85%8d%e5%9b%be%e3%80%81%e5%88%b6%e9%80%a0%e5%9b%be%e7%ad%89/)

### [**Release 17**（2016-2017）](https://www.altium.com/documentation/altium-designer/new-in-altium-designer?version=17.0)

Active Route 自动交互布线功能

背钻孔功能增强

铜皮编辑功能增强

智能输出功能Draftsman功能增强

Support of object specific keepouts  
支持对对象设置特殊禁布，如布局禁布，过孔禁布，线禁布等

Support of waived violations  
支持无视规则冲突

Support of backdrilling 支持背钻设置  
Component parameters added.  添加了元器件参数  
增加板边间距规则

### [**Release 16**（2015-2016）](https://www.altium.com/documentation/altium-designer/new-in-altium-designer?version=16.0)

*   Pad/Via hole size tolerance value added. 增加支持Pad/Via hole尺寸误差
*   新增3D测量功能
*   按IPC规则创建带3D step格式分焊盘图形
*   部分规则管理设计功能增强
*   无效规则会红色警示
*   间距规则可视化
*   原理图和PCB网络原色同步
*   [新增智能元器件放置功能](https://a1024.synology.me:1024/?p=1955)
*   [Altium Pin Delay功能支持](https://a1024.synology.me:1024/altium-pin-delay/)

### [**Release 15**（2015-2016）](https://www.altium.com/documentation/altium-designer/new-in-altium-designer?version=15.1)

*   Support Multi-line PCB Text added.  支持增加多行文本功能
*   Support of separate solder masks for top & bottom of pads added.增加了对焊盘顶部和底部的独立solder masks的支持，可单面开窗。
*   引入xSignals功能
*   增加了 signal length 的概念线长的算法改进（焊盘内的线头、重叠布线、焊盘内弯折均不计长度或按直线距离，包含过孔长度）
*   新增矩形孔

### **Release 14**

The Differential Pairs Routing rule added support for control of the width. Be aware that these widths must be manually entered as Width rules in this version.差分设置规则添加，针对差分线线宽线间距一齐设置，且优先级高于全局线宽

新增[Removing Unused Pads Shapes](https://a1024.synology.me:1024/?p=1898)（去除Pad或Via内层没有连接的环）功能

### **Release 13**

Silk To Solder Mask Clearance Rules are converted to Silkscreen Over Component Pads Rules.  
丝印到阻焊间距规则变为丝印到器件焊盘规则

### **Release 12**

Air Gap Width previously controlled by Clearance rule is now controlled by Polygon Connect Style rule's newly introduced Air Gap Width (set to default value). Suggest reviewing each Polygon Connect Style rule's Air Gap Width attribute for correctness.

### **Release 10**

Support of Solder Mask and Paste Mask expansions for Tracks, Arcs, Fills and Regions was introduced. Be aware that your design might contain Solder Mask and Paste Mask expansions for these types of primitives that cannot be read in the version of Altium Designer you are currently using.  
可以对Tracks, Arcs, Fills 和 Regions增加Solder Mask and Paste Mask expansions属性  
Release 10 update 1  
New Clearance Rule subscopes targeting differential pairs were introduced. Be aware that your design might containClearance Rules using those subscopes that cannot be read in previous versions.  
新的差分对规则

New PCB 3D Movie Manager was introduced. Be aware that your design might contain 3D PCB movie that cannot be read in previous versions.新的3D管理器，全三维PCB 设计环境

New Structured Clusters were introduced. Be aware that your design might contain Structured Clusters that cannot be read in previous versions.  
新的Structured Clusters

New Custom Grids and Guides were introduced. Be aware that your design might contain Custom Grids and Guides that cannot be read in previous versions.新的自定义网格和参考线

### **Summer 09**

File contains assembly testpoint rules and/or settings. Assembly testpoint information will be discarded.  
Support was added for 32 Mechanical Layers. Objects on mechanical layers beyond 16 have been moved to Mechanical Layer 16.支持32个机械层

File contains new custom violations that replaced the old violation objects. These violations were introduced in AltiumDesigner Summer 09. The new custom violations will be discarded.新的规则查看界面

### **Altium Designer Summer 8.0**

将ECAD 和MCAD 两种文件格式结合在一起，

[Altium Designer 10 update 17 (10.972.23595)](https://techdocs.altium.com/display/ADOH/Release+notes+for+Altium+Designer+10+update+(10.972.23595))

[16](https://techdocs.altium.com/display/ADOH/Altium+Designer+16.0+-+New+Features+Round-up)  
[Altium Designer What's New - Previous Releases 6.0-15](https://techdocs.altium.com/display/ADOH/Altium+Designer+What's+New+-+Previous+Releases)