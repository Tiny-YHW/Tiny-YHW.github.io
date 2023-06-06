---
title: 'Allegro 17.2 Back Drill背钻应用'
date: Wed, 19 Oct 2022 09:31:47 +0000
draft: false
tags: ['Allegro']
---

[演示视频播放地址](https://www.ixigua.com/7158729037064438279)
------------------------------------------------------

背钻简介
----

如果你已经了解背钻工艺，请直接跳过这个章节

高速电路设计由于 PCB 材质、走线长度及 Via Stub 对于高频信号所造成的损耗严重。因此Backdrill能够针对 Via Stub 的问题做为解决方案之一；V17.2 对 Backdrill 处理技术有多方面的提升,

Back Drill 是一种 PCB 板制造技术，目的在于去除用作连接的导通孔未被使用部分的无效镀通孔。这是一种二次受控深度钻孔的技术，用于降低所有电解电镀材料的 Stub 效应，并确保信号品质的完整性。因为Stub 是阻抗不连续的来源之一并会造成信号反射，这成为高速信号设计中必须注意的条件。Back Drill 处理可以从PCB的两侧，依需求进行多种深度的二次加工来刨削多余的 Stub 。且用于Back Drill的钻头尺寸通常比原始钻头尺寸大6-10 mils。因此这类的加工必须小心，钻孔深度不要计算得太紧迫或残留太多（留下不可接受的Stub长度）。Back Drill加工对信号质量和制造成本之间以及信号完整性和电路板可测性之间的权衡必须加以考虑。

背钻考虑
----

如果你已经充分了解背钻工艺，请直接跳过这个章节

在进行 Back Drill 处理前需要考虑钻孔深度，因此在 PCB 层叠材料的实际厚度需设定正确，否则会造成所分析出来的钻孔深度不正确 , 从菜单Setup->Cross-setion面板中Thickness列设定正确的材料厚度值。

如果压接器件的钻孔需要背钻，需考虑引脚的连接情况，元器件制造商通常会指定需要的最小电镀深度，以确保它的插销可被正确并稳定的固定到PCB。

![](https://a1024.synology.me:222/images/blog2022/backdrill.png)

![](https://a1024.synology.me:222/images/blog2022/backdrill2.png)

背钻属性
----

给需要背钻的net增加BACKDRILL\_MAX\_PTH\_STUB属性值（暂时不知道这个值的大小影响什么），此属性可以从net添加，这样这个net上所有的via或pin均被视为需要做背钻分析的对象；也支持从via或pin上添加，这样仅包含此属性的via或pin在背钻分析是被视为需要背钻分析的对象（尚存疑问，暂不推荐）

![](https://a1024.synology.me:222/images/blog2022/backdrill12.png)

如果某个网络上部分对象不要做背钻可以对其（SYMBOLS、PINS、VIAS）添加Backdrill\_exclude属性

![](https://a1024.synology.me:222/images/blog2022/backdrill13.png)

背钻焊盘预设
------

从菜单选择Manufacture->NC->Backdrill Setup and Analysis…

指定分别从TOP或BOT层允许的最大背钻深度，最深允许钻到哪个层，点击ok（也可以此处选择Skip跳过，从下一个界面进行调整）

![](https://a1024.synology.me:222/images/blog2022/backdrill5.png)

从背钻和分析界面可以再次调整（增加或删除）需要分析背钻的起始层、终止层、对象类型等信息

![](https://a1024.synology.me:222/images/blog2022/backdrill6.png)

从背钻和分析界面选择Padstack Parameters标签页，定义下图参数

![](https://a1024.synology.me:222/images/blog2022/backdrill7.png)

1.  背钻孔孔径超出钻孔孔径值
2.  负片antipad超出背钻孔径值
3.  正片keepout超出背钻孔径值
4.  背钻起始层焊盘相对背钻孔径內缩值
5.  背钻起始层阻焊相对背钻孔径外扩值
6.  这些推荐值填多少可参考文末推荐值

Tips：以上各值均为直径值，其中1是相对于钻孔孔径的的计算，2-5是相对于背钻孔径的计算，其中4和5部分处理PCB生产商会根据情况调整，设计中可以不做关注均填0即可。

点击Analyze按钮将生产背钻情况报告，检查所产出的报告是否符合预期设计。

点击Backdrill则相关背钻设置将反馈生产到PCB画布中，点击Purge为移除Via和Pins上面的背钻。

Tips：Padstack Parameters标签页中设置的所有值为全局设置，仅对未在Padstack Designer设置特别的相关背钻设置的对象有效（类似于Shape-Global Dynamic Params中对Shape的设置，仅对未指定特殊格式的Shape有效），这些值将在点击Backdrill时被应用

背钻焊盘参数
------

如果设计中需要设置不同类型的背钻信息可以通过再次编辑焊盘从Padstack Designer设置中对相应的焊盘，对其进行特别的设置，Padstack Designer中包含的项目基本和Padstack Parameters中的项目类似，但Padstack Designer中定义的值均为实际值而不是相对值

### 背钻孔孔径及符号

![](https://a1024.synology.me:222/images/blog2022/backdrill3.png)

### 焊盘值、负片antipad、正片keepout值

![](https://a1024.synology.me:222/images/blog2022/backdrill4.png)

### 起始层Solder Mask

![](https://a1024.synology.me:222/images/blog2022/backdrill8.png)

背钻可视化
-----

从设计选项中可以设置背钻孔图形和背钻符号的显示与否

![](https://a1024.synology.me:222/images/blog2022/backdrill9.png)

![](https://a1024.synology.me:222/images/blog2022/backdrill14.png)

文件输出
----

输出NC Drill时勾选Include backdrill，生成背钻钻孔数据，背钻文件名中会插入bd 字符串以便辨识。

![](https://a1024.synology.me:222/images/blog2022/backdrill11.png)

输出钻孔表数据时勾选Include backdrill则相关的背钻数据表将被一起生成

![](https://a1024.synology.me:222/images/blog2022/backdrill10.png)

如果有必要的话可以另附加工说明

```
背钻总数：548
钻孔数据中26-15，26-17，26-19，26-21，26-23是从26层往TOP方向背钻。
其中26-15为L26层到L15层的背钻孔可贯穿至L15层，L14层不可贯穿，L14层的PAD必须保留，否则会引起开路
其中26-17为L26层到L17层的背钻孔可贯穿至L17层，L16层不可贯穿，L16层的PAD必须保留，否则会引起开路。
以此类推
```

背钻配置参考值
-------

背钻孔比一般钻孔大0.2mm制作

via：内层铜厚0.5oz的情况下，背钻孔离线≥10mil，内层铜厚1oz的情况下，背钻孔离线≥11mil；

pin：内层铜厚0.5oz的情况下，背钻孔离线≥14mil，内层铜厚1oz的情况下，背钻孔离线≥15mil

信号速率的允许Stub长度要求：速率5Gbps以上stub长度（mil）≤300/速率（Gbps）。

### 背钻孔其他要求

*   背钻孔仅适用用通孔via和压接通孔pin，焊接通孔pin不适合做背钻
*   板厚3mm以下不建议做背钻
*   背钻孔到背钻孔的距离≥10mil
*   背钻深度控制建议至少保留0.2MM的Stub
*   钻孔深度一般最小需要大于0.6mm
*   5G及以上信号速率的信号可考虑使用背钻工艺