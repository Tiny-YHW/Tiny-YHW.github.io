---
title: 'Tool->Artwork Set+Mark光绘层添加标识及自动设置'
date: Mon, 16 Jan 2023 08:20:42 +0000
draft: false
tags: ['TY-Skill']
---

功能说明
----

按固定模版设置光绘层，在各光绘层添加标识便于Gerber数据的识别

操作说明
----

![](https://a1024.synology.me:222/images/blog2023/LMSF.png)

从菜单或命令调用Skill程序

### 设置Outline

从页面Outline Layer下拉框选择本设计使用的板框层，基于Allegro17.X和16.X对板框的默认定义层默认不一致，特设定此项以适用于不同设计需求

*   Outline（默认值）：仅使用BG/Outline作为板框层
*   Design\_Outline+Cutout：使用BG/Design\_Outline和BG/Cutout作为板框层
*   Outline+Design\_Outline+Cutout：包含上述两项

### 设置哪些层需要包含板框层

从页面Films With Outline选择哪些层需要包含板框层，如果没有特殊要求，其实选择任何一个都可以，有要求的请按需选择

*   None：所有层都不包含板框层，因为自动层叠时会输出单独的板框层，所以其实其它任何层不包含板框层都可以，建议需要使用Valor检查数据时使用此选项设置层叠
*   Only Drill：部分设计习惯使用Drill放置生产信息，此时板框放到此层是合情合理的
*   All Nonconductor（默认值）：所有非导体层均放置，这是大众意义上最长使用的方式（即便我个人认为这并不合理）

### 增加标识

页面左侧输入框可以修改增加标识的内容，非导体层的标识内容将被添加在板框右上角位置，对应的标识层在非导体层则放置在其对应的PG class层中，导体层放置在其对应的Etch class层中。

点击Add Mark按钮对应的标识内容将被添加到对应的层上

### 光绘层叠设置

钻孔标识层作为一个特殊的存在，在板上放置钻孔表格（Drill Legend）时其才会被新建出来，所有在第一次创建光绘层叠时建议先至少手动放置一次钻孔表格，这样对应的层才会被添加到Drill光绘层中，否则钻孔表将不能被此程序添加到Drill层中

点击Drill\_table直接调用Drill Customization用于配置钻孔标识

点击Drill\_legend用于放置（更新）钻孔表

点击Set Films程序将按指定配置自动创建光绘层叠，具体层叠包含的层见下文

除设置指定的层叠外，程序将设置指定光绘层的正负片设置与设计中的设置相同，所有层未定定义线宽指定为7mil，Shape bounding box指定为100mil

点击Arkwork按钮可以打开Arkwork Control Form再次查阅设置是否符合预期

#### 导体层

所有导体层，光绘层名称与层名称相同，包含以下几个Class对应的层

*   ETCH
*   VIA CLASS
*   PIN

![](https://a1024.synology.me:222/images/blog2023/artworkdaoti.png)

#### 丝印层

丝印顶层使用的光绘层名为SA其层叠包含以下几个层，丝印底层类似光绘层名为SB

*   "REF DES/SILKSCREEN\_TOP"
*   "PACKAGE GEOMETRY/SILKSCREEN\_TOP"
*   "BOARD GEOMETRY/SILKSCREEN\_TOP"
*   如果Films With Outline选择是All Nonconductor，则同时包含设置Outline中设置的板框层

#### 阻焊层

阻焊顶层使用的光绘层名为RA其层叠包含以下几个层，阻焊底层类似光绘层名为RB

*   "PIN/SOLDERMASK\_TOP"
*   "PACKAGE GEOMETRY/SOLDERMASK\_TOP"
*   "BOARD GEOMETRY/SOLDERMASK\_TOP"
*   "VIA CLASS/SOLDERMASK\_TOP"
*   如果Films With Outline选择是All Nonconductor，则同时包含设置Outline中设置的板框层

#### 钢网层

钢网顶层使用的光绘层名为PA其层叠包含以下几个层，钢网底层类似光绘层名为PB

*   "PIN/PASTEMASK\_TOP"
*   "PACKAGE GEOMETRY/PASTEMASK\_TOP"
*   如果Films With Outline选择是All Nonconductor，则同时包含设置Outline中设置的板框层

#### 钻孔表层

钻孔表层使用的光绘层名为DRILL其层叠包含以下几个层

*   MANUFACTURING/NCDRILL\_LEGEND
*   "MANUFACTURING/NCLEGEND-1-n" n为总层数
*   如果Films With Outline选择是All Nonconductor，则同时包含设置Outline中设置的板框层

钻孔表层默认仅支持通孔数据，如果需要背钻孔或埋盲孔表请自行手动添加

#### 板框层

包含设置Outline中设置的板框层