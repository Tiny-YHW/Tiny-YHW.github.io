---
title: 'Allegro 17.2 Pad Editor焊盘编辑器功能介绍'
date: Fri, 21 Apr 2023 03:23:14 +0000
draft: false
tags: ['Allegro']
---

最新版本17.2。其中焊盘制作软件的界面较之于之前版本有了大幅度的改变。下面就开始介绍17.2版本的PadEditor。点击开始->所有程序->Cadence17.2->ProductUtilities->PCBEditorUtilities->Padstackeditor启动软件后，就会看到如下界面。这就是17.2版本下的编辑器。下面具体介绍Pad Editor的组成部分

Padstack Overhaul焊盘编辑器大修
------------------------

新的焊盘编辑器通过现代易用的图像界面创建焊盘，大大提高您的设计效率。向导形式的工作方法可以轻松地定义焊盘及其所需属性。新的编辑器提供了许多新形状的焊盘，使复杂焊盘的设计变得更简单。有了这个版本，用户可以创建一些新形状的焊盘，例如环形形状，圆角矩形或倒角矩形。这些焊盘不仅容易创建，还使设计过程的其余部分更加顺畅。17.2 焊盘还可以把走线禁布区作为其定义的一部分，能够根据焊盘结构进行控制，可以控制每一层上或延伸到开始/结束层之外的相邻层上进行控制。

*   支持分层Keepout
*   支持分块Mask

### New Padstack Designer User Interface新的交互界面

重新设计了整个焊盘编辑器界面

![172-algPN-394.gif](https://a1024.synology.me:222/images/172-algPN-394.gif)

### Padstack Usage Types 焊盘用途类型

新的属性根据预期的使用类型分配给焊盘，新建焊盘时选择或者完成创建后修改均可

![172-algPN-395.gif](https://a1024.synology.me:222/images/172-algPN-395.gif)

焊盘类型包括

*   Thru Pin
*   SMD Pin
*   Via
*   BBVia
*   Microvia
*   Slot
*   Mechanical Hole
*   Tooling Hole
*   Mounting Hole
*   Fiducial
*   Bond Finger
*   Die Pad

这些焊盘类型可能会有不同的可编辑选项，这些焊盘类型也将作为标签传递给导出格式，如 IPC-2581。

### New Pad Geometries 新的焊盘形状

新增四种焊盘形状，这些焊盘形状受IPC-2581 标准的支持

Rounded Rectangle圆角矩形：在矩形的基础上增加圆角，可指定全部圆角或指定据图几个圆角所在位置

![172-algPN-396.gif](https://a1024.synology.me:222/images/172-algPN-396.gif)

Chamfered Rectangle倒角矩形：在矩形的基础上增加倒角，可指定全部倒角或指定据图几个倒角所在位置

![172-algPN-397.gif](https://a1024.synology.me:222/images/172-algPN-397.gif)

Donut圆环

![172-algPN-398.gif](https://a1024.synology.me:222/images/172-algPN-398.gif)

n-sided Polygon正多边形6-64

![172-algPN-399.gif](https://a1024.synology.me:222/images/172-algPN-399.gif)

### New Drill Features新的钻孔功能

#### Hole Type孔类型：允许使用方孔

![172-algPN-400.gif](https://a1024.synology.me:222/images/172-algPN-400.gif)

#### Drill tool size 钻具尺寸

新增一个Drill tool size字段，可用于定义电镀前钻孔的实际钻投尺寸，这个字段是可不写，如果有设置的话，输入到此字段中的数据仅传递到钻孔图例，而不会传递到钻孔输出格式（如 _Excellon_）。此字段中定义的值不会因设计单位的更改而更改。

![172-algPN-401.gif](https://a1024.synology.me:222/images/172-algPN-401.gif)

#### Finished diameter/Finished Size 成品孔径

先前版本的drill size已弃用，现使用finished diameter，16.X的数据迁移到本版本后drill size将被finished diameter取代

![172-algPN-402.gif](https://a1024.synology.me:222/images/172-algPN-402.gif)

#### Slot tolerance 槽形孔容差

槽形孔容差分为两组值，X 公差和 Y 容差。这些公差对彼此独立运行，并在使用时填充在钻孔图例中。

![172-algPN-403.gif](https://a1024.synology.me:222/images/172-algPN-403.gif)

#### Secondary Drill 二次钻孔

焊盘定义中添加了两个辅助钻孔选项_ -_ 埋头孔和沉头孔。沉孔需要沉孔直径和深度，可选配正负公差。埋头孔需要埋头孔直径和埋头孔角度，并具有可选的正负公差。

![172-algPN-404.gif](https://a1024.synology.me:222/images/172-algPN-404.gif)

### Multi-shape mask pad geometries 分块图形

现在可以将多个形状用于mask层定义。分块mask方案必须创建为flash symbols （. fsm文件），并在msk层定义中指定。

![172-algPN-405.gif](https://a1024.synology.me:222/images/172-algPN-405.gif)

### User Mask Layers Increased to 32

允许最多定义32个mask层，16.X仅支持6个

![172-algPN-406.gif](https://a1024.synology.me:222/images/172-algPN-406.gif)

### Keepout Features keepout图形

允许在焊盘中添加禁布图形，可以定义指定层或其相邻层禁布图形，若使用相邻层禁布需在PCB板中对引脚或过孔定义新的属性名

*   Adjacent\_layer\_void\_above
*   Adjacent\_layer\_void\_below

![172-algPN-407.gif](https://a1024.synology.me:222/images/172-algPN-407.gif)

### Padstack Options焊盘选项

Suppress unconnected internal pad (required for legacy artwork) ：此选项保留对删除先前版本中支持非功能焊盘。

Lock Layer Span ：锁定BB Via的层数，举例来说：一个L4开始再到L5的BB Via，如今在两层之间插入了一层L4A，有将Lock Layer Span选项打勾时，这颗BB Via会变成L4开始再到L4A；反之，则会延展变成从L4开始，然后跨过L4A再到L5。

![172-algPN-408.gif](https://a1024.synology.me:222/images/172-algPN-408.gif)

### Summary Report 总结报告

显示当前焊盘的值、定义和选项。此摘要可以以 HTML 格式保存到文件中，也可以打印。

![172-algPN-409.gif](https://a1024.synology.me:222/images/172-algPN-409.gif)

上文内容来源于Cadence官方文章，下文内容来源于一供应商提供的说明，可做参考学习，此处引用

1、2D Padstack Top Views，这个是焊盘的2D顶视图。

![06152110816.webp](https://a1024.synology.me:222/images/06152110816.webp)

2、2D Padstack Side Views。焊盘的2D侧视图以及正视图。通过top、side、front我们可以比较直观的了解到焊盘的封装，层叠信息、钻孔信息。

![06152129378.webp](https://a1024.synology.me:222/images/06152129378.webp)

3、Start界面。此界面用来选择焊盘类型以及焊盘默认的几何形状。

![06152142669.webp](https://a1024.synology.me:222/images/06152142669.webp)

4、Drill界面。钻孔界面：在这个界面中，我们定义钻孔的类型，尺寸，误差。与17.0版本不同的是，这一版本还可以定义钻孔的行与列，以及每个钻孔行与列之间的间隔。直接输入数字即可，单位在界面左下角的Units中通过下拉菜单选择。

![06152153280.webp](https://a1024.synology.me:222/images/06152153280.webp)

5、Secondary Drill。此界面可以选择板子的盲孔和埋孔。PCB设计中的孔分为三种，两面通透的成为过孔，从板子一边钻但是不通过所有层的称之为盲孔，在板子内层链接某几层，但是板子顶层和底层都看不到的称之为埋孔。通过右侧的示意图我们就可以很方便的理解。

![06152201115.webp](https://a1024.synology.me:222/images/06152201115.webp)

6、Drill Symbol。可以在此定义用哪种几何图形表示钻孔的大小。几何图形从下拉菜单中选择。Characters表示钻孔特性，figure diameter表示钻孔直径。

![06152211400.webp](https://a1024.synology.me:222/images/06152211400.webp)

7、Drill Offset。这一选项框比较简单，定义钻孔的中心离图示中心的距离。

![06152220317.webp](https://a1024.synology.me:222/images/06152220317.webp)

8、Design Layers。层面设置。与前版本相似。可以再此设置焊盘在每一层的信息。鼠标右击还可以添加和删除层。Regular Pad、Thermal Pad、Anti Pad、Keep Oot菜单分别表示焊盘几何图形、散热、隔离、阻焊。

![06152228894.webp](https://a1024.synology.me:222/images/06152228894.webp)

9、Mask Layers。阻焊层，阻焊层分为sold mask和paste mask，也可以认为是绿油层和锡膏防护层（钢网层）。值得注意的是Solder Mask是出负片，也就是说，设计图纸上绘制了图形的地方在实际生产的时候，是没有绿油的。Paste mask是出正片，有画东西的地方是会有锡膏的。

![06152243911.webp](https://a1024.synology.me:222/images/06152243911.webp)

  除此之外，我们还可以通过Add Layer 添加板层。最多可以顶层底层各添加16层。共32层。另外还有：filmmask（预留层）和coverlay(图覆层)。

10、Options。这里只有两个选项。Suppress unconnected internal pad; legacy artwork (不显示在当前层没有铜导线连接网络的焊盘，但是在gerber中保留)。Lock layer span(锁层，当加入新的层后，保证盲孔或埋孔不受干扰。比如说：埋孔连接层1和层2，当在层1和层2之间添加一个层1A，那么，在勾选这个选项后，这个埋孔就会将层1和层1A连接)

![06152252403.webp](https://a1024.synology.me:222/images/06152252403.webp)

11、Summary，一个简要的汇总表。简要列出了这个焊盘的各种信息。可以选择保存到本地，也可以选择直接打印输出。

![06152308778.webp](https://a1024.synology.me:222/images/06152308778.webp)