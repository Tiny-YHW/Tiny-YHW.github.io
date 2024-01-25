---
layout: post
title: TY-Skill Export->Final Output最终生产数据输出
categories: TY-Skill
date: 2024-01-25
permalink: ty-skill-export-final-output
excerpt: 
---
功能说明
----

![skillfinaloutput.jpg](https://tiny-yhw.github.io//images/TY-skill/skillfinaloutput.jpg)

用于设计完成后输出最终生产数据

## 操作说明

1.  使用菜单或者命令启动
2.  上几个按钮用于输出最终生产数据前的确认项（如已确认完成可直接跳过）
    *   DB Check：运行Database Check命令
    *   Status：打开设计状态面板，确认设计完成情况
    *   Drill\_table和Drill\_legend：用于更新钻孔图形及钻孔表
    *   LayerMark+SetFilms：用于确认层叠标识和光绘层叠数据
3.  从下方多选框选择需要完成的事项（下文详述）
4.  点击Create程序按上面选择的事项完成输出
5.  输出完成后打来输出文件所在的文件夹
6.  如果输出过程存在问题，程序将在右侧窗口、Command面板、弹Log文件等方式进行提示

## ArtworkCheck

对ArtWork设置进行检查

### 光绘层缺失检查

如果有光绘叠层没做如顶层丝印层或L3层这种会提示内容 XXX layer not found maybe named incorrectly
对于信号层要求层叠名称和信号层名称一致，如果不一致也会认定为未找到

### 正负片层设置检查

Artwork中正负片设置是否与设计一致，如果不一致做提示，提示内容为 XXX layer plot mode setting is incorrect

### 信号层叠层内容检查

检查每个信号层中包含的Layer是否正确

* 信号层应该必须包含对应层的PIN、VIA、ETCH
* 信号层可以包含"BOARD GEOMETRY/OUTLINE","BOARD GEOMETRY/DESIGN_OUTLINE","BOARD GEOMETRY/CUTOUT"
* 如果不一致做提示，提示内容为 XXX layer incorrect gerber setup
* 同时查看command会报告哪些层有缺失或多于的内容
    - XXX layer maybe has Missing XXX layers
    - XXX layer maybe has extra  XXX layers

### 丝印层检查

顶层光绘层叠名称必须包含("SA" "SILKT" "SILK_T"  "SILK-T")中的任意一段字符才能被识别到，否则认定为光绘层缺失

顶层光绘层叠必须包含("REF DES/SILKSCREEN_TOP" "PACKAGE GEOMETRY/SILKSCREEN_TOP" "BOARD GEOMETRY/SILKSCREEN_TOP")几个层（可以更多但不能少），否则提示内容XXX layer incorrect gerber setup.

同时查看command会报告哪些层有缺失或多于的内容

BOT层同理层叠名称识别("SB" "SILKB" "SILK_B"  "SILK-B")

BOT层同理必须包含的层有("REF DES/SILKSCREEN_BOTTOM" "PACKAGE GEOMETRY/SILKSCREEN_BOTTOM" "BOARD GEOMETRY/SILKSCREEN_BOTTOM")


### 阻焊层检查

逻辑与丝印层一致，下文进行简写

层叠名称识别

* TOP：("RA" "SOLDT" "SOLD_T" "SOLDERT" "SOLDER_T" "SOLD-T" "SOLDER-T")
* BOT：("RB" "SOLDB" "SOLD_B" "SOLDERB" "SOLDER_B"  "SOLD-B" "SOLDER-B")

必须包含的层

* ("PIN/SOLDERMASK" "PACKAGE GEOMETRY/SOLDERMASK" "BOARD GEOMETRY/SOLDERMASK")


### 铅锡层检查

层叠名称识别

* TOP：("PA" "PASTET" "PASTE_T" "PASTT" "PAST_T" "PASTE-T" "PAST-T")
* BOT：("PB" "PASTEB" "PASTE_B" "PASTB" "PAST_B" "PASTE-B" "PAST-B")

必须包含的层

* ("PIN/PASTEMASK" "PACKAGE GEOMETRY/PASTEMASK")


### 钻孔层检查

层叠名称识别("DRILL" "NC")

必须包含的层("MANUFACTURING/NCLEGEND-1-层数")


Gerber 光绘输出
-----------

对应多选框Gerber项，如果勾选此项程序将输出设计在Artwork中设计的层叠Gerber数据

输出Gerber数据会做一些固定设置项目并输出，流程如下

*   format指定为5 5
*   Device Type指定为gerber\_rs274x
*   选择所有Artwork光绘层叠
*   database\_check选择勾选
*   其它设置均保持不动
*   进行输出
*   将生成的.art文件移动到OUTPUT文件夹
*   将配置的art\_param.txt复制到OUTPUT文件夹

如果光绘层存在，但并没有对应的.art文件被生成，则提示（红底）Error:Gerber file is wrong, please check it carefully!和Incomplete output file!并弹出log文件报告那个层叠没有被输出出来

如果所有光绘层都成功生成.art，则提示（绿底）Gerber files are successfully created…

钻孔文件输出
------

对应多选框NC\_Drill项，如果勾选此项程序将输出设计drill钻孔数据

输出drill钻孔数据会做一些固定设置项目并输出，流程如下

1.  钻孔文件名设置为NC-1-x.drl
2.  Format指定为5 5
3.  其它设置均保持不动（**注意背钻，若需要背钻需自行打开设置界面勾选一次**）
4.  进行输出
5.  将当前文件夹下所有的.drl文件移动到OUTPUT文件夹（**如有背钻则包含背钻，请注意确认是否有多余的文件，可以通过查看文件的修改时间查看**）
6.  将配置的art\_param.txt复制到OUTPUT文件夹
7.  自动判断设计中是否有椭圆形孔，如果有则进行NC Route的输出，没有则就此结束
    1.  Route数据文件名设置为NC.rou
    2.  进行输出

钻孔文件输出完成，提示Drill files are successfully created…

坐标文件输出
------

对应多选框Placement项，如果勾选此项程序将输出坐标数据

输出坐标数据会做一些固定设置项目并输出，流程如下

1.  输出Placement Origin选择为Body Center
2.  其它选项均默认
3.  进行输出
4.  将输出的place\_txt.txt文件移动到OUTPUT文件夹

坐标文件输出完成，提示Placement files are successfully created…

IPC网表文件输出
---------

对应多选框IPC\_Netlist项，如果勾选此项程序将输出IPC网表

输出IPC网表会做一些固定设置项目并输出，流程如下

1.  输出文件名指定为IPC.ipc
2.  其所以选项均默认
3.  进行输出
4.  将输出的IPC.ipc文件移动到OUTPUT文件夹

坐标文件输出完成，提示IPC files are successfully created…

生产数据分包打包
--------

对应多选框Pack\_File项，如果勾选此项程序将把上文输出到OUTPUT文件夹下的文件继续分包（如果指定的层不存在则跳过此层）

坐标文件输出完成，提示The files has been output to the OUTPUT folder

### ASM文件夹

丝印和阻焊.art文件

### SMT文件夹

丝印、阻焊、铅锡.art文件 + 钻孔 + 钻孔配置nc\_param.txt + 坐标文件place\_txt.txt

### CAM文件夹

所有.art + .drl +.rou + .txt + .ipc文件