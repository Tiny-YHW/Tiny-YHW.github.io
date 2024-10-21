---
layout: post
title: Allegro 版本查看和降版本
categories: Allegro
permalink: allegro-downrev
date: 2023-12-19
---

## 23.1 to 22.1

执行菜单File > Export > Downrev design可以将设计另存为17.4版本

## 22.1 to 17.4

除了22.X有新增的东西外，其它可完全兼容，无需任何版本也可相互切换

## 17.4 to 17.2

17.4可以从User Preferences中设置Database_compatibility_mode改为17.2兼容，不过此功能也仅是支持可用17.2浏览，如果17.4中的设计使用的Footprint是17.4环境的产物，则它仍然是17.4的。不能通过下述17.2 to 16.6向下降版本

17.4中执行菜单File > Export > Downrev design可以将设计另存为17.2版本

## 17.2 to 16.6

需要电脑同时安装17.2和16.6，且17.2安装了最新的更新补丁

[EDA365 deargds 编写的SKill](https://www.eda365.com/thread-229646-1-1.html)，不支持设计规则转换

[电路精灵工具](http://www.jiloukeji.com/index.html)（推荐1）

[吴川斌的降版本工具](https://www.mr-wu.cn/downgrading-allegro-file-to-an-earlier-version/)（推荐2）

### **allegro_downrev_library**

allegro_downrev_library 是一个批处理程序，主要应用于将library parts从17.x（可能只是17.2）降至16.5，此功能为17.2的更新版本功能，需要更新补丁，具体哪一号不清楚了。
支持格式：.psm, .bsm, .osm, .fsm, .ssm, and .pad
不支持 board (.brd) and drawing (.dra)

#### **语法**

```clike
allegro_downrev_library  <input design(s)> [-outfile <output design>]
```

- input design(s)：输入文件全路径（不是文件夹），支持通配符
- output design：Specify the output design name. If not defined, the input design is saved with .orig extension.Using wildcard downrev will overwrite design file names.output design：输出文件名称，如果包含通配符通配符部分将覆盖原文件
- output design 参数可缺省，此时默认输入路径=输入路径，且原文件将增加.orig继续保留

此处语法测试有点疑问 记录结果如下


```clike
allegro_downrev_library *.pad *.?sm    覆盖且不生成.orig
allegro_downrev_library *.pad 或 allegro_downrev_library *.?sm  覆盖且生成生成orig
allegro_downrev_library 4-65mm.pad -outfile 4-65mm.pad  覆盖不生成orig
allegro_downrev_library 4-65mm.pad -outfile 4-65-166mm.pad  覆盖不生成orig
```

#### **转换结果详情**

**Padstack数据的变化：可用于16.6，但以下数据将会被删除**

- Adjacent keepout definitions
- Same layer keepout definitions
- Anti-route keepout (ARK) definitions
- Backdrill information
- Counter bore/sink settings
- Coverlay pad definitions
- New padstack usage types
- Any properties associated with padstack

**如果pad文件包含以下信息，程序将转换失败**

- 新的焊盘形状：圆角焊盘、倒角焊盘、环形盘、多边形焊盘
  方形钻孔
- Flash symbol in place of thermal pads
- More than 16 user-defined mask layer

**Symbols数据的变化 (.psm, .bsm, .ssm, .fsm, and .osm)**

- DESIGN_OUTLINE or CUTOUT class层图形转换到BOARD_GEOMETRY/OUTLINE层
- IGID_FLEX or SURFACE_FINISHES classes 将被删除
- Contains pins which are specified for Chip on Board connection.程序将转换失败

**使用方法案例：Footprint降版本**

1. 切换Cadence为17.X环境。
2. 直接准备17.x的 pad文件或Symbols文件，或从17.2的设计中导出。
3. 将文本内容为allegro_downrev_library \*.pad \*.?sm的bat文件放置在焊盘图形同目录下执行，若使用skill方式参考命令如下shell(strcat(allegro_downrev_library   lib\\\\*.pad   lib\\\\*.?sm)) 注意修改为你的焊盘图形路径。
4. 3中的输出是不包含drawing (.dra)文件的，需要的话需要放到16.6的设计中再导出。

## 16.X to 16.X

最高版本16.6，最低版本16.01

- 16.6选择菜单 File > Export > Downrev design可以直接输出16.5或16.3的版本
- 16.5选择菜单 File > Export > Downrev design可以直接输出16.3或16.2的版本
- 16.3选择菜单File > Export > Downrev design可以直接输出16.2或16.01的版本
- 16.2选择菜单File > Export > Downrev design可以直接输出16.01的版本

## 16.X to 15.7

[EDA365 deargds 编写的SKill](https://www.eda365.com/thread-68764-1-1.html)

所谓Skill不过是把一堆功能做了集合，或者使用了更内层的软件接口或算法而已，Skill能实现的手动都能实现，不过可能需要更多时间而已

![/](https://tiny-y.asia/images/blog/2022/1601-157.png)以下介绍不通过Skill可以如何实现

- 当前%CDSROOT%为16.x（切版本到16.X，17.X和15.X没有DOWNREV15.exe程序）
- 将设计通过16.X to 16.X的方法输出16.01版本
- 通过DOWNREV15.exe程序将16.01版本转换为15.7版本

DOWNREV15.exe 需要通过DOS或批处理执行 语法如下

```clike
@echo off
set DOWNREV_16_TO_15=%CDSROOT%\tools\pcb\bin\vc5
%DOWNREV_16_TO_15%\downrev15.exe 1601.brd -outfile 157.brd
pause
::1601.brd和157.brd分别代表对应版本设计的文件名
```

- DOWNREV15.exe在%CDSROOT%\\tools\\pcb\\bin\\vc5这个路径下
- 1601.brd是相对路径的写法，如不适用相对路径可使用绝对路径
- 同时生成log文件报告版本差异，注意查看

[参考案例](https://layouto.lanzouj.com/iJPVi1foulif)

## 15.X to 15.X

15.7选择菜单File > Export 可选另存为15.2或15.0的版本

## 查看Allegro brd的设计版本号

Win+R输入CMD回车 进度CMD 输入如下指令

```clike
dbstat <你的brd所在路径>
::报告当前文件夹下brd使用的版本和设计平台（NT代表Windows）
dbstat *.brd
::报告当前文件夹下brd使用的产品选项（-t）和一些编辑信息（-e）
dbstat -t -e *.brd
```


```clike
dbstat [-v] [-p] [-t] <filename.ext> ... <designM>
```


报告了Allegro设计版本和平台架构.

支持格式

- .brd .mcm .sip
- .mdd .dpf .dpm .dps .scf
- .pad .dra .mcm .psm .ssm .fsm, .bsm

选项:

-v - Database version of design

-t - Report last saved tiering level. This is NOT the same as the last
product/option(s) active during saving the design. Instead it is the
equivalent product and options that match the DRC in effect when the
design was saved.

-p - The architecture on which the design was last saved (UNIX or NT)
UNIX: big-endian systems (SPARC, PA-RISC)
NT: Little-endian systems (Intel or AMD) (Windows, Linux, Sol86)
This means it reports NT for saved designs on Linux.

-e - Reports design meta data on a single line:
USER=\
EDIT_TIME_MINUTES=
VERSION_ID=
User name is shown in quotes to allow for spaces
If a design lack some of the meta data it is shown as 0 or an empty string
Future software versions may add additional attributes.

The reported database version of the design may NOT be the same as the
version of Allegro used to save the database. The version reported by
dbstat is the earliest version of Allegro that can open the design. If
you do not use the capability of latter Allegro dot releases then
the database revision is not changed.

Dbstat accepts the wildcard character \*. to report on multiple designs.

Note: For padstack (.pad) designs saved prior to version 10, dbstat
returns the message, Pre-rev 10 pad file.

Example:
dbstat test.brd
returns information similar to the following:
test.brd: 16.0 NT
dbstat -e test.brd
returns
USER=fxf EDIT_TIME_MINUTES=5 VERSION_ID=1397491497