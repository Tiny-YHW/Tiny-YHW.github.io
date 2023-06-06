---
title: 'Export->Final Output'
date: Wed, 29 Dec 2021 05:50:48 +0000
draft: false
tags: ['TY-Skill']
---

[返回主菜单](https://a1024.synology.me:1024/?p=2217)
-----------------------------------------------

功能说明
----

检查部分Artwork光绘设置是否存在可能的错误，如有则给出提示

输出光绘/钻孔/坐标/IPC几项最终输出文件,部分输出包含一些简单的设置

将输出文件分类打包放置到指定路径

![](https://a1024.synology.me:222/images/blog2022/Snipaste_2021-12-29_10-13-23.png)

操作说明
----

左上区域三个按钮一般在输出最终数据前需确认是否均为最终状态，放到此处仅为方便查看

*   **Status**：状态面板查看设计中器件／网络／Shape/DRC等信息是否均为最终形态
*   **Drill\_legend**：更新设计钻孔表数据
*   **LayerMark+SetFilms**：调用另一个层叠设置和层叠标识的skill程序，进行相应的设置

左侧中间复选框区域勾选则进行此项,不勾选则不进行此项，每个项目在进行的同时可能包含一些指定设置项目，如下文描述的设定与你的预期不符，请不要选择对应的项目

### Gerber

勾选此项将输出设计Artwork数据，输出同时包含一些默认设置值

*   Format指定值为5：5
*   Device type为Gerber RS274X
*   输出的artwork为所有已经设置的所有层叠（如不需要某层，可在输出文件中删除）
*   检查DBCheck
*   输出文件移动到brd同级目录OUTPUT文件夹下
*   其它各项均保持默认或原用户设置不进行更改

### ArtworkCheck

勾选此项将对Artwork设置进行部分检查，如果可能的错误给出相应提示

检查需识别artwork层叠名以匹配层，要求用户使用的层叠名称为 \*RA\*.art（\*SOLDT\*.art）、\*RB\*.art（\*SOLDB\*.art）、\*SA\*.art（\*SILKT\*.art）、\*SB\*.art（\*SILKB\*.art）、\*PA\*.art（\*PASTT\*.art）、\*PB\*.art（\*PASTB\*.art）否则不能识别到哪层对应这些数据

*   每个导体层正负片设置是否与设计中一致
*   丝印、阻焊、铅锡、钻孔表中包含的层是否完整
*   Artwork层叠是否有缺失（比如10层改12层，漏了新增的两个层的artwork）

### NC\_Drill

勾选此项将输出设计钻孔数据，输出同时包含一些默认设置值

*   Format指定值为5：5
*   输出文件名指定为NC.drl（否则如果文件名包含空格则.drl后缀不能生成）
*   输出文件移动到brd同级目录OUTPUT文件夹下
*   其它各项均保持默认或原用户设置不进行更改

如果设计包含槽形孔将同时输出.rout文件 ，输出同时包含一些默认设置值

*   Format指定值为5：5
*   输出文件名指定为NC.rout（否则如果文件名包含空格则.routl后缀不能生成）
*   输出文件移动到brd同级目录OUTPUT文件夹下
*   其它各项均保持默认或原用户设置不进行更改

### Placement

勾选此项将输出设计器件坐标数据， 输出同时包含一些默认设置值

*   Placement原点使用Body Center
*   输出文件移动到brd同级目录OUTPUT文件夹下
*   其它各项均保持默认或原用户设置不进行更改

### IPC\_Netlist

勾选此项将输出设计IPC网表数据， 输出同时包含一些默认设置值

*   输出文件名指定为IPC.ipc（否则如果文件名包含空格则.ipc后缀不能生成）
*   输出文件移动到brd同级目录OUTPUT文件夹下
*   其它各项均保持默认或原用户设置不进行更改

### Pack\_File

对输出数据进行分类打包，并将数据分类打包放在在brd同级目录OUTPUT文件夹下，要求丝印层、阻焊层、铅锡层名称按下面的命名格式，否则文件不能被成功分包

*   ASM：\*RA\*.art（\*SOLDT\*.art）、\*RB\*.art（\*SOLDB\*.art）、\*SA\*.art（\*SILKT\*.art）、\*SB\*.art（\*SILKB\*.art）
*   SMT：ASM所有文件 + \*PA\*.art（\*PASTT\*.art）、\*PB\*.art（\*PASTB\*.art）、nc\_param.txt、place\_txt.txt
*   CAM：上文输出到OUTPUT文件夹下的\*.art、\*.drl、\*.rou、\*.txt、\*.ipc所有文件

选择完成后，点击Create按钮接按对应的选项进行输出或分包数据

![](https://a1024.synology.me:222/images/blog2022/Finaloutput.gif)

[返回主菜单](https://a1024.synology.me:1024/?p=2217)
-----------------------------------------------