---
layout: post
title: TY-Skill Export->Final Output最终生产数据输出
categories: TY-Skill
date: 2023-08-10
permalink: ty-skill-export-final-output
excerpt: 
---
功能说明
----

![skillfinaloutput.jpg](https://tiny-yhw.github.io//images/TY-skill/skillfinaloutput.jpg)

用于设计完成后输出最终生产数据

## 操作说明

1.  使用菜单或者命令启动
2.  左上几个按钮用于输出最终生产数据前的确认项（如已确认完成可直接跳过）
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

层数量检查，本章节下文所有层如果没有被找到也会提示内容XXX layer is not standard or found

### 信号层设置检查

Artwork层叠名称是否与设计数据一致，如果不一致做提示，提示内容为 XXX layer is not standard or found

Artwork中正负片设置是否与设计一致，如果不一致做提示，提示内容为 XXX layer plot mode setting is incorrect

每个层中包含的Layer是否正确，应该必须包含对应层的PIN、VIA、ETCH，如果不一致做提示，提示内容为 XXX layer incorrect gerber setup

### 丝印层检查

顶层光绘层叠名称必须包含("SA" "SILKT" "SILK\_T")中的任意一段字符才能被识别到，否则报缺失层XXX layer is not standard or found

顶层光绘层叠必须包含("REF DES/SILKSCREEN\_TOP" "PACKAGE GEOMETRY/SILKSCREEN\_TOP" "BOARD GEOMETRY/SILKSCREEN\_TOP")几个层（可以更多但不能少），否则提示内容XXX layer is not standard or found

底层光绘层叠名称必须包含("SB" "SILKB" "SILK\_B")中的任意一段字符才能被识别到，否则报缺失层XXX layer is not standard or found

底层光绘层叠必须包含("REF DES/SILKSCREEN\_BOTTOM" "PACKAGE GEOMETRY/SILKSCREEN\_BOTTOM" "BOARD GEOMETRY/SILKSCREEN\_BOTTOM")几个层（可以更多但不能少），否则提示内容XXX layer is not standard or found

Artwork中正负片设置若为负片时，提示内容为 XXX layer plot mode setting is incorrect

### 阻焊层检查

逻辑与丝印层一致，下文进行简写

层叠名称识别("RA" "SOLDT" "SOLD\_T" "SOLDERT" "SOLDER\_T")、("RB" "SOLDERB" "SOLDER\_B")

必须包含的层有("PIN/SOLDERMASK" "PACKAGE GEOMETRY/SOLDERMASK" "BOARD GEOMETRY/SOLDERMASK")

Artwork中正负片设置若为负片时，提示内容为 XXX layer plot mode setting is incorrect

### 铅锡层检查

层叠名称识别("PA" "PASTET" "PASTE\_T" "PASTT" "PAST_T")、("PB" "PASTEB" "PASTE\_B" "PASTB" "PAST_B")

必须包含的层有("PIN/PASTEMASK" "PACKAGE GEOMETRY/PASTEMASK")

Artwork中正负片设置若为负片时，提示内容为 XXX layer plot mode setting is incorrect

### 钻孔层检查

层叠名称识别("DRILL" "NC")

必须包含的层有("MANUFACTURING/NCLEGEND-1-层数")

Artwork中正负片设置若为负片时，提示内容为 XXX layer plot mode setting is incorrect

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