---
title: 'Altium Pin Delay'
date: Mon, 20 Apr 2020 01:10:51 +0000
draft: false
tags: ['Altium', '设计技巧']
---

[视频资料](https://www.altium.com.cn/video-enhanced-pin-length-definitions)

[文档资料](https://www.altium.com/documentation/altium-designer/nfs-16-0pin-package-delay-support-ad?version=16.0)

Pin Delay功能要求Altium版本为16或以上

在每一个超过500MHz的高速设计中，连接介质，或者说结合线到裸片，都会给信号引入一个延迟。这种器件内延迟被称为Pin Delay。即使两个器件从设计和PCB的角度来看是完全引脚兼容的，不同的器件之间的Pin Delay也是不同的，因此需要考虑到它们。Pin Delay信息可以在器件的IBIS 6文档中找到。封装引脚信息应在I/O规划阶段或FPGA合成后考虑。

所有的器件制造商都应该能够提供Pin Delay，它可以指定为皮秒延时，也可以指定为长度。Altium使用的是长度法，因为这可以很容易地将其加入到轨迹长度中，使设计中的路由轨迹均衡化。

引脚封装长度包含在总的信号长度中，可以在PCB面板的各种模式下检查，包括Nets模式和xSignals模式。

原理图Pin Delay
------------

可以在引脚属性对话框的**Pin/Pkg Length**字段中定义为原理图组件引脚的属性。软件将默认使用底层文档的单位，输入所需的单位和值。

![](https://www.altium.com/documentation/sites/default/files/resize/wiki_attachments/263561/Dlg_SchPinProperties-highlight-600x654.png)

使用SCHList面板可将多个**Pin/Pkg Length**从数据表复制/粘贴到一组组件引脚中。

PCB Pin Delay
-------------

原理图中定义的**Pin/Pkg Length**可以导入到PCB中，从Pad属性页面可以查看到对应信息，如果直接从PCB中设置或编辑，也可编辑此处数值，

![](https://www.altium.com/documentation/sites/default/files/resize/wiki_attachments/263561/Dlg_PcbPin-highlight-600x757.png)

使用PCB List面板可将多个**Pin/Pkg Length**从数据表复制/粘贴到一组组件引脚中。

Pin/Pkg Length in the PCB Panel
-------------------------------

在 PCB 面板的不同模式下，引脚/包长度会自动包含在信号长度计算中。将面板设置为 "Net "模式，以检查（或编辑）所选网中的引脚/Pkg长度的值。注意 Routed Length一栏反映的是引线的长度，而 Signal Length(信号长度)一栏反映的是引线长度加上该Net的Pin/Pkg Length。

![](https://www.altium.com/documentation/sites/default/files/wiki_attachments/263561/Pnl_PCB_NetsPinLength-highlight.png)

Pin/Pkg Length会自动包含在xSignal的总长度中