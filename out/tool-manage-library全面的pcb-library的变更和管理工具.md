---
title: 'Tool->Manage Library全面的PCB library的变更和管理工具'
date: Tue, 17 Jan 2023 09:01:08 +0000
draft: false
tags: ['TY-Skill']
---

功能说明
----

功能说明：全面的PCB library的变更和管理工具，主要包含功能如下

1.  通过在PCB中选取Package symbol或Pad实时更新到当前PCB的数据库或库路径中的库文件，并更新板中同名的Package symbol或pad，不需要手动在各个工具之间相互切换
2.  通过选择输出指定的Package symbol或Pad，而不是输出所有的Package symbol或Pad
3.  PCB中已加载的库的原始位置报告
4.  对Package symbol分类查看，分类包括pin数、孔数、高度等更多分类方式
5.  板中的Package symbol与库路径中的Package symbol比对，输出差异报告

操作说明
----

以下所有需要修改或更新对应的pads或symbols的操作，需要在对应的库路径中存在该文件，才能对其进行更新或

### 在PCB中修改或更新Package symbol或Pads

修改和更新功能对应的标签页分别为Modify和Refresh，界面操作逻辑类似，下文将已修改为例描述功能

![](https://a1024.synology.me:222/images/blog2023/dallibmodify.png)

1.  选择Modify标签
2.  设置文件更改后PCB中对应对象的动作
    *   Refresh after modify：勾选代表修改完成后立即更新到PCB
    *   Update symbol padstacks：勾选代表更新symbols时，同时更新这个symbols中包含的pads
    *   Reset symbol text locations：勾选代表更新symbols时，同时更新text位置
    *   Ignore FIXED property：勾选代表即便对象有锁定属性，也将被更新
3.  通过Select padstacks或Select symbol从PCB中选择对应对象；或从…中打开列表，从列表中选择对应对象
4.  程序将跳转到编辑对象窗口，对对象进行编辑后需手动关闭窗口
5.  如果设置了Refresh after modify回到PCB窗口软件提示是否更新被编辑的对象，选择是则PCB中对应的对象将被更新

### 在PCB中输出指定psm或pad

![](https://a1024.synology.me:222/images/blog2023/dallibexp.png)

1.  选择Export标签，输入或从...选择输出路径，点击Explore export directory按钮可以输出库路径
2.  通过Select padstacks或Select symbol从PCB中选择对应对象或从…中选择对应对象
3.  选择的对象将被输出到指定路径，Command窗口提示输出文件完成

### 库路径报告

![dallibrep.png](https://a1024.synology.me:222/images/blog2023/dallibrep.png)

1.  选择Report标签，对应的报告模式
2.  .brd library path report：当前设计中库加载的路径及加载时间等信息
3.  Psm path library path report：Package symbol路径中包含的Package symbol清单
4.  Library symbol area report：Package symbol的Place Bound面积报告

![dallibrep2.png](https://a1024.synology.me:222/images/blog2023/dallibrep2.png)

### Package symbol分类查看

![](https://a1024.synology.me:222/images/blog2023/dallibhilight.png)

1.  选择Highlight标签
2.  指定或输入条件
    *   点击Symtype或Padstack后面的...从列表中选择指定名称的对象或者点击其后面的Like后从PCB中选择对象，其同类会被高亮
    *   后面的一些多选项都是字面意思，按需使用即可
3.  对应条件的Symbol将会被Highlight

### Package symbol与库路径中的Package symbol比对

![](https://a1024.synology.me:222/images/blog2023/Snipaste_2023-01-18_16-08-09.png)

1.  选择Compare标签
2.  设置对应比对选项
3.  通过Selected选择需要比对的对象
4.  程序将输出比对结果报告

### Place标签貌似没啥用，暂不介绍