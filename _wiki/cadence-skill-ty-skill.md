---
layout: wiki
title: TY-Skill
cate1: Cadence Skill
cate2: 
keywords: 
---
本文章将持续补充TB-Skill收录的功能使用说明

部分已经整理的功能将在后面的分链接中进行说明

常用辅助功能
------

设计过程中较为常用功能，但与设计本身无关主要方便设计过程中需要的一些辅助功能。

## Open CurrentFile

打开当前Allegro软件当前操作对象文件所在文件夹。

## Save Copy As To Bakfile

备份当前Allegro软件当前操作对象文件到父级目录bak文件夹，并在文件名末尾加上时间戳。

## Calculation

![](https://a1024.synology.me:222/images/blog2023/Calculation.png)

mil和mm的单位互转和常规数值运算，支持加减乘除和()。

**逻辑运算**

1.  在计算器公式左侧输入需要运算的公式
2.  按键盘Enter或鼠标点到其它输入框右侧将显示计算结果

**单位转换**

1.  在单位转换左侧输出mm单位的数值或在右侧输入mil单位数值
2.  按键盘Enter或鼠标点到其它输入框则在mil或mm单位的输入框内显示置换单位的数值

## Skill Debug

调试skill程序用

## Edit

具体设计中对设计元素对象的编辑功能

### [Zcopy Pro](https://a1024.synology.me:1024/?p=229)

将设计中的Pins、Via、Clines、Lines、Shape、Void元素转换为外扩或内缩的Shape，并移动或复制到任意层。

### Change Pro

将设计中的Clines、Lines、Shape、Void、Text元素移动或复制到任意层。

基于设计原Change的功能升级，突破智能Change到同Class的限制，增加移动复制、保留复制功能。

常用于Logo层面改变，部分图形需要换层或复制到其他层时使用。

使用方法和ZcopyPro类似，不再赘述

### [Mirror Pro](https://a1024.synology.me:1024/?p=352)

将设计中的Symbol、Vias、Clines、Lines、Shape、Text进行镜像操作。

### [Cut Pro](https://a1024.synology.me:1024/?p=614)

将设计中的Clines、Lines、Shape、进行切割或切片复制。

### Change Clines Width

批量调整指定层或指定区域指定线宽值，也常用于查看设计各层线宽值（阻抗）情况

### Change Obj Net

为PCB设计的Vias、Clines、Shapes（Pins）重新定义网络名

1.  使用菜单或者命令启动
2.  从Find面板选择需要操作的对象类别，默认值为Vias、Clines、Shapes；同时支持Pins，但修改Pins网络涉及网表更改（需慎重），请在确实需要使用时再勾选此类别。
3.  Command提示选择对象，通过点击单选或者框选多个对象
4.  Command提示选择网络，通过点击选择需要指定的Net
5.  程序自动完成，为选择的对象赋予指定的Net名
6.  Clines不能独立存在网络，所以调整Clines网络时必须修改为与它有物理连接的网络名

### [Spread\_Clines](https://a1024.synology.me:1024/?p=2976)

通过选择PCB中已完成的平行Clines segs对其进行等距分布

### [Align Obj](https://a1024.synology.me:1024/?p=2221)

将设计中被选中的的Symbols、Vias、Texts进行对齐或等距排放

### [Swap Pro](https://a1024.synology.me:1024/?p=849)

有调管脚需求的设计更方便的管脚调整，通过点击两个网络任意地方交换可调管脚的网络

### Pin Connect

用于编辑部分焊盘引脚与铜皮的连接方式

*   从菜单选择命令
*   从Options中指定需要的连接方式
*   单击选择或框选指定Pin改变其与铜皮的连接方式

![Pinconnect.gif](https://a1024.synology.me:222/images/blog2023/Pinconnect.gif)

## Add

为当前设计增加设计要求需要元素或增加设计需要的辅助元素辅助设计

### Label Dim

在PCB中标注出板框尺寸，单位MM和mil。层BG/Dimension

### [Outline/RKI By AntiEtch](https://a1024.synology.me:1024/?p=3546)

根据shape形状（一般为板框或Route Keepin）分层创建AntiEtch

常用于设计中平面层内缩或电源层相对地层做20H时使用

### [RKO By Diff Vias+Pins](https://a1024.synology.me:1024/?p=2226)

针对高速差分线，对选择的2个Pins或Vias增加ShapeKeepout

### [RKO For 2SMD SymPin](https://a1024.synology.me:1024/?p=2237)

为设计中所有2个表贴pin的器件在其器件面两个焊盘之间增加一个 ShapeKeepout，避免整版铺铜灌入其中

### [RKO For Hole](https://tiny-yhw.github.io//ty-skill-add-rko-for-hole){:target="_blank"}

筛选指定类型的通孔pin，对其添加指定尺寸的禁布层

### Route Pin to Via

自动连接器件pin到附近的via 尤其方便处理BGA背面电容连线

### GND Ring

自动沿板框创建屏蔽地Shape和地Via

设计要求做屏蔽地铜或屏蔽地孔时使用

### [Import Logo](http://www.allegro-skill.com/forum.php?mod=viewthread&tid=2660&highlight=logo)

将各种logo导入到allegro中，包括文字、图形等

设计时需要添加图形或中文字符时使用

### [Chinese Text](https://a1024.synology.me:1024/?p=2784)

直接在板中增加中文文字功能

### Refdes Silk

对缺少丝印位号的器件增加丝印位号（针对误删）

选择命令后再从PCB画布中选择需要添加丝印位号的器件即可

Display
-------

### Color Altium

设置Allegro中常用的层颜色配置与Altium软件的默认配色方案一致，建议使用Altium的默认配色方案作为设计习惯可使用此命令。

设置的层包括以下几种：TOP和BOT层，丝印层，Solder层，Paste层，ANTI ETCH层，ASSEMBLY层

直接从菜单执行命令即可。

### [Key Net Assign Color](https://tiny-yhw.github.io//ty-skill-display-key-net-assign-color){:target="_blank"}

为包含指定文本的网络增加颜色功能，可用于为不用电压值的网络赋予不同的颜色，或包含指定文本的网络名赋予颜色

### [Highlight Object](https://a1024.synology.me:1024/?p=3591)

按类别高亮对象，常用于针对某些类别的对象的查找与检查

### Custom Colors Enable \[F5\]

针对下图选项定制的快捷键,可以通过此菜单命令或者直接按键盘F5键，开启或关闭(切换)用户通过assign color或hilight命令定义的颜色

![Snipaste_2023-08-03_10-12-19.png](https://a1024.synology.me:222/images/Snipaste_2023-08-03_10-12-19.png)

### [Layer Visibility](https://a1024.synology.me:1024/?p=3594)

层叠显示快捷切换，另支持自定义层叠的保存及调用

### [View Drill+Pad](https://a1024.synology.me:1024/?p=2242)

分类查看设计中不同孔径的Vias和Pins、分类查看设计中不同焊盘名称的Vias或Pads

### [Key Layer Visibility](https://a1024.synology.me:1024/?p=1104)

设计时使用键盘按键切换常用设计视图

Setup
-----

### Board Origin

设置原点到PCB左下角，不保证100%正确，程序运行完自查一下

### [Layer Stackup](https://a1024.synology.me:1024/?p=3642)

快速设置多层板常用层叠，多层板叠多层时套用模版直接生成多层板

### [Stackup Swap](https://a1024.synology.me:1024/?p=3645)

层叠顺序调整，层面互换

### [Pinpair By Class or Bus](https://a1024.synology.me:1024/?p=1113)

根据板中已创建的Class、Bus或Net Group，批量创建Pinpair并生成Matchgroup

### [Manage Grids](https://a1024.synology.me:1024/?p=1108)

多功能设定格点工具

*   按指定值设定格点
*   自定义任何值或单位
*   支持命令行直接输入
*   支持按选择点设定和分割格点
*   支持将格点对齐到对象

Create
------

### [Auto diff](https://a1024.synology.me:1024/?p=3666)

自动创建删除（查看）差分对

### Flash

按输入参数自动创建Flash文件

![CreateFlash.png](https://a1024.synology.me:222/images/blog2023/CreateFlash.png)

### Pad

按输入参数自动创建Pad文件

![CreatePad.png](https://a1024.synology.me:222/images/blog2023/CreatePad.png)

Place
-----

### [Package Snap Place](https://a1024.synology.me:1024/?p=3698)

依次放置选择的器件，并支持吸附到pin放置，主要应用于BGA背面电容批量依次放置时使用

### [Align Comp Pin](https://a1024.synology.me:1024/?p=3702)

将选择的两个器件按指定pin对齐

### [TO Grid](https://a1024.synology.me:1024/?p=3711)

将选择的元器件对齐到指定格点上

### [Smart Place Tool](https://a1024.synology.me:1024/?p=3716)

此工具支持多种布局功能详见内文

*   按页放置器件
*   高亮指定类别器件
*   按飞线布局
*   按原理图器件位置布局

### [Place By Capture XY](https://a1024.synology.me:1024/?p=3721)

适用于Capture格式原理图，按原理图中元器件的相对位置分页布局PCB

### Place By HDL XY

适用于HDL格式原理图，按原理图中元器件的相对位置分页布局PCB，除选择的exp格式文件处直接为工程cpm文件外，其它操作及效果基本与[Place By Capture XY](https://a1024.synology.me:1024/?p=3721)一致不再赘述

## Tool

### [Artwork Set+Mark](https://a1024.synology.me:1024/?p=3728)

按固定模版设置光绘层，在各光绘层添加标识便于Gerber数据的识别

### Cut Silk

用于切断靠近及与soldermask交叉的丝印线，最小丝印线长度和丝印线距离阻焊距离均默认为0.12mm

PCB模式和DRA模式均可用，PCB较大时运行时间可能较长（计算量比较大），请耐心等待

使用菜单或者命令启动，程序弹出确认框，点击“是”执行程序，点击“否”取消执行

### Del Gnd Via

删除指定区域内网络名称中包含GND字段或无网络的Via

使用菜单或者命令启动，从PCB中单击选择或者框选区域即删除区域内网络名称中包含GND字段或无网络的Via

### Del Useless File

除brd所有路径无用文件功能,支持自选择指定后缀

使用菜单或者命令启动，勾选需要删除的指定后缀的文件类型，点击Del Checked File即可

### [Diff Adjust](https://a1024.synology.me:1024/?p=3752)

根据选定的规则和设定值修改对应的差分线宽、间距和规则

### [Manage Library](https://a1024.synology.me:1024/?p=3731)

全面的PCB library的变更和管理工具，详见内文

### Manufacture Para

按模版设计为PCB指定层增加生产信息或设计标注等信息

![](https://a1024.synology.me:222/images/blog2023/manufapara.png)

1.  使用菜单或者命令启动后弹出对话框
2.  填写相关参数
3.  点击创建后放置到PCB指定位置，新增内容放置的层为BG/DIMENSION

ty-skill-tool-pdf-link

### [PDF Link](https://tiny-yhw.github.io//ty-skill-tool-pdf-link){:target="_blank"}

Allegro与PDF原理图交互

### Replace All Pad

统一替换阻焊小于指定值的pad，替换新pad使用固定外扩值solder；可选Paste与pad同大，并使用新的焊盘名称

替换完成后列表区域将报告哪些焊盘被替换掉了

![](https://a1024.synology.me:222/images/blog2023/Snipaste_2023-01-18_16-24-06.png)

### Taper

在不同的线宽连接点之间创建圆滑的锥形过度

1.  使用菜单或者命令启动后，从Option面板配置功能选项。
2.  支持参数较多，具体含义待测试，典型应用为单击Add select后框选需要增加过度的Clines即为Clines增加过度shape。

![](https://a1024.synology.me:222/images/blog2023/Snipaste_2023-01-18_16-44-35.png)

Check
-----

### PCB Checker

多功能查板功能，具体可检查项目详见功能界面，支持中文

### [Pad Check](https://a1024.synology.me:1024/?p=3804)

PCB中所有Pad参数合理性检查

### Danglings

检查PCB设计中的DangingLines、Dangling Vias、Island Shapes并支持批量删除

![](https://a1024.synology.me:222/images/blog2023/dlings.png)

1.  使用菜单或者命令启动
2.  根据要检查的对象选择对应标签
3.  单选，拖动连续选择或按住Ctrl键多选对象
4.  被选择的对象在PCB设计上被高亮
5.  单击Delete可删除或批量删除被选择的对象

### Etch Cross Plane

走线跨参考平面分割的检查

![](https://a1024.synology.me:222/images/blog2023/kuafenge.png)

1.  使用菜单或者命令启动
2.  选择自定模式或手动模式，自动模式将根据叠层属性和顺序自动分析跨分割的线，手动模式则按要求选择信号层和参考层，对选择的层面进行检查分析，一般选择自动分析模式即可。
3.  点击检查，程序自动执行，跨分割的Clines将全被高亮，从检查列表中点击对应网络名将跳转到对应的对象，可对对象进行调整后继续检查。

### Etch Cross Crossstalk

检查相邻层面信号线重叠且平行走线

![](https://a1024.synology.me:222/images/blog2023/pingxingxianglin.png)

1.  使用菜单或者命令启动
2.  选择自定模式或手动模式，自动模式将根据叠层属性和顺序自动分析相邻层面的信号线，手动模式则按要求选择相邻信号层，对选择的层面进行检查分析，一般选择自动分析模式即可，设置允许平行走线指定长度。
3.  点击检查，程序自动执行，相邻信号层重叠平行布线长度超出指定值的将全被高亮，从检查列表中点击对应网络名将跳转到对应的对象，可对对象进行调整后继续检查。

### Short Seg

高亮检查折线（Clines交错较小的）布线

![](https://a1024.synology.me:222/images/blog2023/shortsegment.png)

1.  使用菜单或者命令启动
2.  输出指定长度，默认为2mil
3.  长度小于指定值的Clines将被分析出来
4.  点击指定坐标，对应的Clines将被高亮，视图跳转到指定位置

### Compare

比较并显示两个PCB设计之间所有的图形和元器件的变化

1.  使用菜单或者命令启动后。
2.  对相关设置进行配置，配置项较多，后续测试后继续补充。
3.  点击Run selected程序将按设置项进行差异比较并在PCB上显示结果

### Browse

对设计检查时按元素依次查看检查做记录等操作

![](https://a1024.synology.me:222/images/blog2023/dalbrowse.png)

1.  使用菜单或者命令启动后选择检查对应的标签页
2.  每种标签会实时显示对应元素的部分信息便于查阅
3.  依次选择对应标签内的元素在PCB中查看。
4.  在Status中记录检查结果
5.  在Comment中记录描述内容（不支持不支持中文）
6.  再次打开本设计允许此程序记录内容仍然存在
7.  记录内容可在Option页面内导出和导入

![](https://a1024.synology.me:222/images/blog2023/dalbrowseexp.png)

### [Footprint Elements](https://tiny-yhw.github.io//ty-skill-check-footprint-elements){:target="_blank"}

如果板中器件与其对应的封装内相应层对象的数量存在不同则输出差异数量报告，如误删丝印层一脚标识，器件Placebound等

## Text

### [Quick Change Text Size](https://a1024.synology.me:1024/?p=3879)

功能说明：几项针对与字号的大小调整和设置

1.  重置设置Text字号1-20号的各个参数，字号大小渐进
2.  将所有Pin\_number放置到其对应焊盘原点处，角度调整为0
3.  几个常用层Text的字号调整

### Move Ref To Body Center

将指定层的元器件位号或Values旋转到指定方向，调整大小，并对齐到元器件中心

尤其适用于调整装配图丝印层

老功能了，现在几乎没用了，已经被[Label Tune](https://a1024.synology.me:1024/?p=803)功能完全取代了，不做过多介绍了

### [Ref Local Rotate](https://a1024.synology.me:1024/?p=2790)

用于将元器件位号（仅）水平和垂直方向统一为相同的方向且位置不变

比如BOT层垂直方向存在90和270两种方向（或者仅270），程序指定为90运行后，所有BOT层垂直方向将全更改为90度

### Auto Adjust Silk

设计完成后，丝印层丝印预放置

![zidongsiyin.png](https://a1024.synology.me:222/images/blog2023/zidongsiyin.png)

1.  使用菜单或者命令启动
2.  指定要调整的层面和丝印号大小设置（配合Quick Change Text Size直接使用3号字即可）
3.  从Layer处选择需要调整的层面、从dir选框选择底层丝印垂直方向的角度
4.  点击按钮By\_Select，框选需要局部丝印，丝印将自动调整，多次操作需要多次点击按钮，适用于设计局部改动时的丝印调整
5.  点击By\_Layer程序将批量自动调整整层丝印
6.  完成后输出完成率，未成功放置的丝印将居中到元器件中心并高亮，需要再次调整
7.  所有丝印调整仅用于辅助使用不做正确性保证，应自行复查

### [Manage Text](https://a1024.synology.me:1024/?p=3886)

1.  Edit标签页：Package symbol的引脚编号自动化
2.  Edit标签页：两个设计Text的位置比较和更新，可用于协作时导入协作者的丝印调整
3.  Add标签页：增加网络名（引脚号）丝印，并关联到该symbol
4.  更多功能请自行探索

### Silk Checks

检查丝印文本放置的合理性

不怎么好用，暂时保留，后面有机会迭代更新掉，感兴趣的可以自己研究一下

### [Silk Checks2](https://a1024.synology.me:1024/?p=2974)

辅助检查丝印合理性

*   丝印与其它图形干涉
*   丝印方向检查
*   器件无丝印检查
*   丝印交叉辅助查看
*   丝印非法镜像检查

Export
------

### Lib By Select Package

允许用户选择一个或多个器件（而不是整板）导出其对应的lib文件

1.  使用菜单或者命令启动
2.  从板中选择一个或多个器件
3.  右键选择done
4.  选择输出路径完成输出

### Place DXF

按指定模版层（布局相关的层）输出DXF文件，常用于布局完成后结构校对时使用，同时支持输出3D Step

本功能没有太多功能设置，基本都是调用的软件自身的命了，只是为了方便快捷做了整合

如果你用手动的方法不能成功输出，用本功能也照样不能输出，遇到不能输出的情况自己查找自身原因

1.  使用菜单或者命令启动
2.  界面选择指定项目
3.  选择Export输出

TOP/BOTTOM/Step:输出项目选项，被指定的项目将被导出

输出单位支持多种选择，但仍然建议使用MM输出

层选项控制

*   PACKAGE\_GEOMETRY：PACKAGE GEOMETRY/SILKSCREEN；PACKAGE GEOMETRY/SOLDERMASK层是否输出
*   BOARD\_GEOMETRY：BOARD GEOMETRY/SILKSCREEN；BOARD GEOMETRY/SOLDERMASK层是否输出
*   REF\_DES：REF DES/SILKSCREEN层是否输出
*   PIN：PIN；PIN/SOLDERMASK层是否输出
*   Dimension：BOARD GEOMETRY/DIMENSION层是否输出

### [Final Output](https://a1024.synology.me:1024/?p=3942)

用于设计完成后输出最终生产数据

Report
------

### Brd Info

参数获取插件，从设计中获取设计统计信息，方便填入我司设计信息表单内容

从菜单命令直接访问执行

程序将调出信息统计报告对话框

点击Viewlog按钮可以文本形式查看统计信息，所有文本可以选择复制，文本信息所在位置与设计相关表单填写位置类似

### BOM Report For TB

输出指定格式的BOM表内容（Excel格式）

### Rout Path length

用于查看生产锣长值，计算方式为板框层所有lines或shape的线长总和，计算结果仅供参考

### 后面几个功能直接调用，软件自身的功能，方便快捷查找调用

*   Bill of Material Report (Condensed)：BOM表
*   Component Pin Report：器件Pin报告
*   Dangling Lines Report：悬空线报告
*   Film Area Short Report：信号层残铜率（铜皮占比）报告
*   Net Loop Report：信号回路报告
*   Net Single Pin and No Pin：单点pin报告
*   Summary Drawing Report：设计统计报告

Footprint
---------

### Quick View

打开封装各层属性，检验各层图形设置是否完备

1.  使用菜单或者命令启动此功能。
2.  点击各层名称，显示对应层图形进行查看。

### Add Body center

放置Body Center和添加Placebound工具

### Auto Silk

丝印层、装配层图形互相拷贝

丝印层图形缺失时，该指令可以实现将装配层的图形完整复制到丝印层，位号字符缺失时自动在原点位置添加丝印/装配位号。反之装配层为空时，丝印层图形可完整复制到装配层。

### Dim Size

丝印长宽尺寸、Placebound高度，自动标注。

标注尺寸所在层自动分配到BOARD GEOMETRY/DIMENSION

### Optimization

多功能封装优化工具

添加数字、字母、长短线等不同类型的管脚标识，表贴器件添加器件中心-Body Center

1.  使用菜单或者命令启动此功能。
2.  命令窗口包含3个功能栏，Globle TexBlock、Standard、Connector，分别对应字体编辑、标准器件、非标准排布管脚（连接器）。
3.  Tri\_Mark按钮用于1脚位置添加三角标识，方向默认横向。
4.  BodyCenter按钮用于添加表贴器件中心。
5.  Connector功能栏，可以实现A面、B面字符自由选择，全标、缝5、缝10标注自由选择，勾选后点击CONNECT按钮，然后框选对应管脚放置到适当位置即可。

### Pin infor View+Eidt

以表的形式管理封装内的pin信息，针对某些特殊情况，通过表管理更加方便操作

### Renumber Pin

实现批量编辑Pin Number

根据需要，设置起始值、步进值参数，固定后缀信息可选无后缀不填，功能参数设置完成后框选或者点选需要修改的PIN，即可实现Pin Number顺序编辑。

### [Package批处理](https://a1024.synology.me:1024/?p=2788)

Batch DRA To SYM+Pad：批量将当前文件夹内所有dra文件批量创建sym文件和输出焊盘文件  
Batch SYM To DRA：批量将当前文件夹内所有sym文件（需要.pad支持）放入PCB批量创建DRA文件  
Batch Downrev Symbol 17 to 16：批量将当前文件夹内所有sym和pad文件从17.X降版本到16.5

TB-Help
-------

### Documentation

打开使用说明文档

### Reload

重新加载skill程序

### About

查看版本号