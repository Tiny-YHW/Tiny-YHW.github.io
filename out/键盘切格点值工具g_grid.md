---
title: 'Setup->Manage Grids多功能设定格点工具'
date: Thu, 20 Aug 2020 02:58:28 +0000
draft: false
tags: ['TY-Skill']
---

功能说明
----

![Managegrids.png](https://a1024.synology.me:222/images/blog2023/Managegrids.png)

多功能设定格点工具

*   按指定值设定格点
*   自定义任何值或单位
*   支持命令行直接输入
*   支持按选择点设定和分割格点
*   支持将格点对齐到对象

Grids On复选框可用于打开或关系格点显示

本程序所有行为仅改变格点位置和大小，不改变设计单位或原点位置，请放心使用

视频演示抖音扫描下方二维码观看

![Managegrids1.png](https://a1024.synology.me:222/images/blog2023/Managegrids1.png)

按指定值设定格点
--------

*   从菜单或命令启动程序（命令为g）
*   从Grid Units后面选择指定格点值使用的单位
*   从Gird Value中选择指定值，则格点被设置为X=Y=选择的值和单位

自定义格点值和单位
---------

从Custom Grids后面的输入框可以输入值用于设定格点，输入规则如下

只输入一个值时，格点X=Y等于设定值  
Command > 12

输入两个值时，中间用一个空格分隔，第一个值为格点X，第二个值为格点Y  
Command > 20 40

值输入支持包含单位，不写单位时默认和当前设计单位一致  
值输入包含单位时，按输入单位执行，目前程序仅支持输入mil和mm单位  
Command > 1mm 2mm  
Command > 20 3mm  
Command > 30mil 1.5mm

**可以输入gg命令，调用格点设置miniform（参考Altium软件），按上面的命令设定格点**  
Command > gg

**支持命令行直接输入**

**可以不从UI界面设置格点，直接在Command界面输入g+空格+上面对应的命令效果一致**  
Command > g 1mm 2mm  
Command > g 12  
Command > g 20 40  
Command > g 30mil 1.5mm

通过选择对象设定格点位置或大小
---------------

**Align+** 将格点对齐到指定点

**Dvd2x** 根据选择的两个点的X坐标改变X格点，选择的点在格点上，并分割指定分属的格点

**Dvd2xy** 同上，改变Y格点

**Dvd2xy** 同上，改变X和Y格点  
若选择的两个点X值相同，则仅改变Y  
若选择的两个点Y值相同，则仅改变X

**SEG Vertex**：将格点对齐到线头  
**SEG MID**：将格点对齐到线中点

**Symbol Pins：**将格点对齐到选择的器件Pin的指定脚号，识别的引脚号为以下几组（1，2）（A，C）（A，K）（B1，A2），分割分数为2

* * *

此功能已全面更新为上文状态，下文是之前的说明，此处仍做保留
-----------------------------

功能说明
----

设计时使用键盘按键切换常用格点或指定格点

使用方法
----

[加载此skill功能](https://a1024.synology.me:1024/allegro-skill%e5%8a%a0%e8%bd%bd/)

保持鼠标在PCB绘图窗口或command窗口，输入对应层命令按回车键确认即可

格点值单位与设计当前单位一致

**直接切换配置值命令，以下数字均为数字键区数字（小键盘），Ctrl建议使用右手边按键**

*   CTRL + 0 = 设置格点为0.1
*   CTRL + 1 = 设置格点为1
*   CTRL + 2 = 设置格点为25
*   CTRL + 5 = 设置格点为5

**指定格点值**：直接在命令栏输入“g 20”回车确认即格点设置为20

![](http://a1024.synology.me:222/images/blog2022/ggrid.gif)

程序代码
----

```
;Vision:V3.0
;Data:20200820
;Author:Tiny_Y
;skill load("g_grids.il")

axlCmdRegister("g" 'set_grids ?cmdType "interactive")
axlCmdRegister("~e" 'set_grids5 ?cmdType "interactive")
axlCmdRegister("~b" 'set_grids25 ?cmdType "interactive")
axlCmdRegister("~a" 'set_grids1 ?cmdType "interactive")
axlCmdRegister("~" 'set_grids0_1 ?cmdType "interactive")

procedure(set_grids(@optional (grids ""))
	if(grids != ""
		then
			gird_value = atof(grids)
			if(gird_value
				then
					SetGridsScriptCreate(gird_value)
				else
					axlUIWPrint(nil "Sorry,You enter the wrong grid.... Grid set failed...")
			)
		else
			axlUIWPrint(nil "Please Input argument...")
	);end if 
);end procedure
procedure(SetGridsScriptCreate(InGrid)
grid = axlDBGridGet("TOP")
grid->name = 'all
grid->xGrids = InGrid
grid->yGrids = InGrid
axlDBGridSet(grid)
printf("^_^ Set all grid to %.2f Successful\n" InGrid)
);end procedure

procedure(set_grids5(@optional (grids "5.0"))
	SetGridsScriptCreate(5.0))

procedure(set_grids1(@optional (grids "1.0"))
	SetGridsScriptCreate(1.0))

procedure(set_grids25(@optional (grids "25.0"))
	SetGridsScriptCreate(25.0))

procedure(set_grids0_1(@optional (grids "0.1"))
	SetGridsScriptCreate(0.1))
```