---
layout: post
title: TY-Skill Display->Key Layer Visibility 使用键盘按键切换常用设计视图
categories: Allegro Skill
date: 2023-08-03
permalink: ty-skill-display-key-layer-visibility
excerpt: 设计时使用键盘按键切换常用设计视图
---

## 功能说明

设计时使用键盘按键切换常用设计视图

## 使用方法


[加载此skill功能](https://a1024.synology.me:1024/allegro-skill%e5%8a%a0%e8%bd%bd/)

保持鼠标在PCB绘图窗口或command窗口，输入对应层命令按回车键确认即可

默认输入命令及对应层如下，可自行更改命令

切换信号层后面增加+ 代表同时打开其相邻参考层

*   如下例20位输入命令，所切换的层别为底层布线
*   axlCmdRegister( "2111" 'alllayeron);开所有层
*   axlCmdRegister( "2000" 'alllayeroff);关所有层
*   axlCmdRegister( "20" 'BOTTOM);底层布线
*   axlCmdRegister( "21" 'TOP);顶层布线
*   axlCmdRegister( "210" 'place);顶底层同时布线
*   axlCmdRegister( "22" 'L2);第2层布线
*   ……;省略3-9层
*   axlCmdRegister( "2.0" 'L10);第10层布线
*   axlCmdRegister( "2.1" 'L11));第11层布线
*   ……;省略12-19层
*   axlCmdRegister( "200" 'bottomm);底层布局
*   axlCmdRegister( "211" 'topp);顶层布局
*   axlCmdRegister( "2100" 'placee);顶底层同开布局
*   axlCmdRegister( "st" 'skt) ;顶层丝印
*   axlCmdRegister( "sb" 'skb) ;底层丝印
*   axlCmdRegister( "stb" 'sktb);顶底层同开丝印
*   axlCmdRegister( "art" 'allart);所有光绘相关层叠
*   axlCmdRegister( "20+" 'BOTTOMadd);底层布线
*   axlCmdRegister( "21+" 'TOPadd);顶层布线
*   axlCmdRegister( "22+" 'L2add);第2层布线
*   ……;省略3-9层
*   axlCmdRegister( "2.0+" 'L10add);第10层布线
*   axlCmdRegister( "2.1+" 'L11add);第11层布线
*   ……;省略12-19层

功能演示
----

抖音：[https://v.douyin.com/LgYCrFc](https://v.douyin.com/LgYCrFc)

更新说明
----
### 20230725更新V5.0

*   增加开所有层和关所有层快捷键功能

### 20220120更新V4.0

*   增加同时打开指定层及其相邻参考层的功能
*   切换信号层增加对应层的对应的BOUNDARY层（Shape边框）

### 20200820更新V3.0

*   新增为布局布线层增加Plan/layer层，方便查看规划视图
*   简化代码

### 20160509更新到V2.0

*   增加功能呢切换到对应布线层同时设置当前活动层为对应层
*   eg：按23回车，层显示为L3层相关内容同时设置活动层为L3

程序代码
----

```lisp
axlCmdRegister( "2111" 'alllayeron);开所有层
axlCmdRegister( "2000" 'alllayeroff);关所有层
axlCmdRegister( "210" 'TOPBOT);顶底层同时布线
axlCmdRegister( "20" 'BOTTOM);底层布线
axlCmdRegister( "21" 'TOP);顶层布线
axlCmdRegister( "22" 'L2);第2层布线
axlCmdRegister( "23" 'L3)
axlCmdRegister( "24" 'L4)
axlCmdRegister( "25" 'L5)
axlCmdRegister( "26" 'L6)
axlCmdRegister( "27" 'L7)
axlCmdRegister( "28" 'L8)
axlCmdRegister( "29" 'L9)
axlCmdRegister( "2.0" 'L10);第10层布线
axlCmdRegister( "2.1" 'L11);第11层布线
axlCmdRegister( "2.2" 'L12)
axlCmdRegister( "2.3" 'L13)
axlCmdRegister( "2.4" 'L14)
axlCmdRegister( "2.5" 'L15)
axlCmdRegister( "2.6" 'L16)
axlCmdRegister( "2.7" 'L17)
axlCmdRegister( "2.8" 'L18)
axlCmdRegister( "2.9" 'L19)
axlCmdRegister( "200" 'bottomplace);底层布局
axlCmdRegister( "211" 'topplace);顶层布局
axlCmdRegister( "2100" 'topbotplace);顶底层同开布局
axlCmdRegister( "200+" 'bottomplacesilk);底层布局
axlCmdRegister( "211+" 'topplacesilk);顶层布局
axlCmdRegister( "2100+" 'topbotplacesilk);顶底层同开布局
axlCmdRegister( "st" 'skt) ;顶层丝印
axlCmdRegister( "sb" 'skb) ;底层丝印
axlCmdRegister( "stb" 'sktb);顶底层同开丝印
axlCmdRegister( "art" 'allart);所有光绘相关层叠

axlCmdRegister( "20+" 'BOTTOMadd);底层布线
axlCmdRegister( "21+" 'TOPadd);顶层布线
axlCmdRegister( "22+" 'L2add);第2层布线
axlCmdRegister( "23+" 'L3add)
axlCmdRegister( "24+" 'L4add)
axlCmdRegister( "25+" 'L5add)
axlCmdRegister( "26+" 'L6add)
axlCmdRegister( "27+" 'L7add)
axlCmdRegister( "28+" 'L8add)
axlCmdRegister( "29+" 'L9add)
axlCmdRegister( "2.0+" 'L10add);第10层布线
axlCmdRegister( "2.1+" 'L11add);第11层布线
axlCmdRegister( "2.2+" 'L12add)
axlCmdRegister( "2.3+" 'L13add)
axlCmdRegister( "2.4+" 'L14add)
axlCmdRegister( "2.5+" 'L15add)
axlCmdRegister( "2.6+" 'L16add)
axlCmdRegister( "2.7+" 'L17add)
axlCmdRegister( "2.8+" 'L18add)
axlCmdRegister( "2.9+" 'L19add)


defun( alllayeroff ()
    axlVisibleDesign(nil)
    axlVisibleUpdate(t)
    )

defun( alllayeron ()
    axlVisibleDesign(t)
    axlVisibleUpdate(t)
    )


defun( allart ()
    axlVisibleDesign(nil)
    items = axlGetParam("paramLayerGroup:ETCH")->groupMembers
    sum = length(items)
    foreach(db items
        axlVisibleLayer(sprintf(nil "ETCH/%s" db) t)
        axlVisibleLayer(sprintf(nil "VIA class/%s" db) t)
        axlVisibleLayer(sprintf(nil "PIN/%s" db) t)
        )
    axlVisibleLayer(sprintf(nil "MANUFACTURING/NCLEGEND-1-%d" length(items)) t)
    axlVisibleLayer( "BOARD GEOMETRY/OUTLINE" t )  
    axlVisibleLayer( "BOARD GEOMETRY/SILKSCREEN_TOP" t )
    axlVisibleLayer( "PIN/TOP" t )
    axlVisibleLayer( "via class/TOP" t )
    axlVisibleLayer( "etch/TOP" t )
    axlVisibleLayer( "via class/BOTTOM" t )
    axlVisibleLayer( "etch/BOTTOM" t )
    axlVisibleLayer( "REF DES/SILKSCREEN_TOP" t )
    axlVisibleLayer( "PACKAGE GEOMETRY/SILKSCREEN_TOP" t ) 
    axlVisibleLayer( "PIN/SOLDERMASK_TOP" t ) 
    axlVisibleLayer( "via class/SOLDERMASK_TOP" t )  
    axlVisibleLayer( "PACKAGE GEOMETRY/SOLDERMASK_TOP" t ) 
    axlVisibleLayer( "BOARD GEOMETRY/SOLDERMASK_TOP" t ) 
    axlVisibleLayer( "BOARD GEOMETRY/SILKSCREEN_BOTTOM" t )
    axlVisibleLayer( "PIN/BOTTOM" t )
    axlVisibleLayer( "REF DES/SILKSCREEN_BOTTOM" t )
    axlVisibleLayer( "PACKAGE GEOMETRY/SILKSCREEN_BOTTOM" t ) 
    axlVisibleLayer( "PIN/SOLDERMASK_BOTTOM" t ) 
    axlVisibleLayer( "via class/SOLDERMASK_BOTTOM" t )  
    axlVisibleLayer( "PACKAGE GEOMETRY/SOLDERMASK_BOTTOM" t ) 
    axlVisibleLayer( "BOARD GEOMETRY/SOLDERMASK_BOTTOM" t ) 
    axlVisibleLayer( "PIN/PASTEMASK_TOP" t ) 
    axlVisibleLayer( "PIN/PASTEMASK_BOTTOM" t ) 
    axlVisibleLayer( "PACKAGE GEOMETRY/PASTEMASK_TOP" t ) 
    axlVisibleLayer( "PACKAGE GEOMETRY/PASTEMASK_BOTTOM" t ) 
    axlVisibleLayer( "manufacturing/photoplot_outline" t )
    axlVisibleLayer( "manufacturing/NCDRILL_LEGEND" t )
    axlVisibleUpdate(t))


defun( sktb ()
    axlVisibleDesign(nil)
    axlVisibleLayer( "BOARD GEOMETRY/OUTLINE" t )  
    axlVisibleLayer( "BOARD GEOMETRY/SILKSCREEN_TOP" t )
    axlVisibleLayer( "PIN/TOP" t )
    axlVisibleLayer( "REF DES/SILKSCREEN_TOP" t )
    axlVisibleLayer( "PACKAGE GEOMETRY/SILKSCREEN_TOP" t ) 
    axlVisibleLayer( "PIN/SOLDERMASK_TOP" t ) 
    axlVisibleLayer( "via class/SOLDERMASK_TOP" t )  
    axlVisibleLayer( "PACKAGE GEOMETRY/SOLDERMASK_TOP" t ) 
    axlVisibleLayer( "BOARD GEOMETRY/SOLDERMASK_TOP" t ) 
    axlVisibleLayer( "BOARD GEOMETRY/SILKSCREEN_BOTTOM" t )
    axlVisibleLayer( "PIN/BOTTOM" t )
    axlVisibleLayer( "REF DES/SILKSCREEN_BOTTOM" t )
    axlVisibleLayer( "PACKAGE GEOMETRY/SILKSCREEN_BOTTOM" t ) 
    axlVisibleLayer( "PIN/SOLDERMASK_BOTTOM" t ) 
    axlVisibleLayer( "via class/SOLDERMASK_BOTTOM" t )  
    axlVisibleLayer( "PACKAGE GEOMETRY/SOLDERMASK_BOTTOM" t ) 
    axlVisibleLayer( "BOARD GEOMETRY/SOLDERMASK_BOTTOM" t ) 
    axlVisibleLayer( "package keepout/top" t )
    axlVisibleLayer( "package keepout/all" t )
    axlVisibleLayer( "package keepout/bottom" t )
    axlVisibleLayer( "PACKAGE GEOMETRY/PASTMASK_TOP" t ) 
    axlVisibleLayer( "PACKAGE GEOMETRY/PASTMASK_BOTTOM" t ) 
    axlVisibleLayer( "DRC ERROR CLASS/SOLDERMASK_bottom" t )
    axlVisibleLayer( "DRC ERROR CLASS/SOLDERMASK_TOP" t )
    axlVisibleUpdate(t)) 

defun( skb ()
    axlVisibleDesign(nil)
    axlVisibleLayer( "BOARD GEOMETRY/OUTLINE" t )
    axlVisibleLayer( "BOARD GEOMETRY/SILKSCREEN_BOTTOM" t )
    axlVisibleLayer( "PIN/BOTTOM" t )
    axlVisibleLayer( "REF DES/SILKSCREEN_BOTTOM" t )
    axlVisibleLayer( "PACKAGE GEOMETRY/SILKSCREEN_BOTTOM" t ) 
    axlVisibleLayer( "PIN/SOLDERMASK_BOTTOM" t ) 
    axlVisibleLayer( "via class/SOLDERMASK_BOTTOM" t ) 
    axlVisibleLayer( "PACKAGE GEOMETRY/SOLDERMASK_BOTTOM" t ) 
    axlVisibleLayer( "BOARD GEOMETRY/SOLDERMASK_BOTTOM" t ) 
    axlVisibleLayer( "package keepout/bottom" t )
    axlVisibleLayer( "package keepout/all" t )
    axlVisibleLayer( "MANUFACTURING/REFDES bottom DRC" t ) 
    axlVisibleLayer( "DRC ERROR CLASS/SOLDERMASK_bottom" t )  

    axlVisibleUpdate(t))

defun( skt ()
    axlVisibleDesign(nil)
    axlVisibleLayer( "BOARD GEOMETRY/OUTLINE" t )
    axlVisibleLayer( "BOARD GEOMETRY/SILKSCREEN_TOP" t )
    axlVisibleLayer( "PIN/TOP" t )
    axlVisibleLayer( "REF DES/SILKSCREEN_TOP" t )
    axlVisibleLayer( "PACKAGE GEOMETRY/SILKSCREEN_TOP" t ) 
    axlVisibleLayer( "PIN/SOLDERMASK_TOP" t ) 
    axlVisibleLayer( "via class/SOLDERMASK_TOP" t ) 
    axlVisibleLayer( "PACKAGE GEOMETRY/SOLDERMASK_TOP" t ) 
    axlVisibleLayer( "BOARD GEOMETRY/SOLDERMASK_TOP" t ) 
    axlVisibleLayer( "package keepout/top" t )
    axlVisibleLayer( "package keepout/all" t )
    axlVisibleLayer( "MANUFACTURING/REFDES TOP DRC" t )
    axlVisibleLayer( "DRC ERROR CLASS/SOLDERMASK_TOP" t )
    axlVisibleUpdate(t))

defun( topplace ()
    axlVisibleDesign(nil)
    axlVisibleLayer( "BOARD GEOMETRY/OUTLINE" t )
    axlVisibleLayer( "PIN/TOP" t )
    axlVisibleLayer( "VIA class/top" t )
    axlVisibleLayer( "etch/TOP" t )
    axlVisibleLayer( "BOUNDARY/TOP" t )
    axlVisibleLayer( "PACKAGE GEOMETRY/SILKSCREEN_TOP" t )
    axlVisibleLayer( "BOARD GEOMETRY/SILKSCREEN_TOP" t )
    axlVisibleLayer( "DRC ERROR CLASS/top" t )
    axlVisibleLayer( "package keepout/top" t )
    axlVisibleLayer( "package keepout/all" t )
    axlVisibleLayer( "route keepout/top" t )
    axlVisibleLayer( "route keepout/all" t )
    axlVisibleLayer( "route keepin/all" t )
    axlVisibleLayer( "PACKAGE GEOMETRY/Place_Bound_Top" t )
    axlVisibleLayer( "PACKAGE GEOMETRY/Pin_Number" t )
    axlVisibleLayer( "DRC ERROR CLASS/package_top" t )
    axlVisibleLayer( "PACKAGE keepin/all" t )
    axlVisibleLayer( "via keepout/top" t)
    axlVisibleLayer( "CONSTRAINT REGION/top" t)
    axlVisibleLayer( "CONSTRAINT REGION/ALL" t )
    axlVisibleLayer( "manufacturing/mech_top" t )
    planlayer = "PLAN/TOP"
    when(axlLayerGet(planlayer)
        axlVisibleLayer( planlayer t ))

    axlVisibleUpdate(t))

defun( topplacesilk ()
    axlVisibleDesign(nil)
    axlVisibleLayer( "BOARD GEOMETRY/OUTLINE" t )
    axlVisibleLayer( "PIN/TOP" t )
    axlVisibleLayer( "VIA class/top" t )
    axlVisibleLayer( "etch/TOP" t )
    axlVisibleLayer( "BOUNDARY/TOP" t )
    axlVisibleLayer( "PACKAGE GEOMETRY/SILKSCREEN_TOP" t )
    axlVisibleLayer( "BOARD GEOMETRY/SILKSCREEN_TOP" t )
    axlVisibleLayer( "DRC ERROR CLASS/top" t )
    axlVisibleLayer( "package keepout/top" t )
    axlVisibleLayer( "package keepout/all" t )
    axlVisibleLayer( "route keepout/top" t )
    axlVisibleLayer( "route keepout/all" t )
    axlVisibleLayer( "route keepin/all" t )
    axlVisibleLayer( "PACKAGE GEOMETRY/Place_Bound_Top" t )
    axlVisibleLayer( "PACKAGE GEOMETRY/Pin_Number" t )
    axlVisibleLayer( "DRC ERROR CLASS/package_top" t )
    axlVisibleLayer( "PACKAGE keepin/all" t )
    axlVisibleLayer( "via keepout/top" t)
    axlVisibleLayer( "CONSTRAINT REGION/top" t)
    axlVisibleLayer( "CONSTRAINT REGION/ALL" t )
    axlVisibleLayer( "manufacturing/mech_top" t )
    axlVisibleLayer( "manufacturing/mech_top" t )
    axlVisibleLayer( "REF DES/SILKSCREEN_TOP" t )
    planlayer = "PLAN/TOP"
    when(axlLayerGet(planlayer)
        axlVisibleLayer( planlayer t ))

    axlVisibleUpdate(t))

defun( bottomplace ()
    axlVisibleDesign(nil)
    axlVisibleLayer( "BOARD GEOMETRY/OUTLINE" t )
    axlVisibleLayer( "PIN/bottom" t )
    axlVisibleLayer( "VIA class/bottom" t )
    axlVisibleLayer( "etch/bottom" t )
    axlVisibleLayer( "BOUNDARY/BOTTOM" t )
    axlVisibleLayer( "PACKAGE GEOMETRY/SILKSCREEN_bottom" t )
    axlVisibleLayer( "BOARD GEOMETRY/SILKSCREEN_BOTTOM" t )
    axlVisibleLayer( "DRC ERROR CLASS/bottom" t )
    axlVisibleLayer( "package keepout/bottom" t )
    axlVisibleLayer( "package keepout/all" t )
    axlVisibleLayer( "route keepout/bottom" t )
    axlVisibleLayer( "route keepout/all" t )
    axlVisibleLayer( "PACKAGE GEOMETRY/Place_Bound_Bottom" t )
    axlVisibleLayer( "PACKAGE GEOMETRY/Pin_Number" t )
    axlVisibleLayer( "DRC ERROR CLASS/package_bottom" t )
    axlVisibleLayer( "PACKAGE keepin/all" t )
    axlVisibleLayer( "route keepin/all" t )
    axlVisibleLayer( "via keepout/bottom" t)
    axlVisibleLayer( "CONSTRAINT REGION/bottom" t)
    axlVisibleLayer( "CONSTRAINT REGION/ALL" t )
    axlVisibleLayer( "manufacturing/mech_bottom" t )    
    planlayer = "PLAN/BOTTOM"
    when(axlLayerGet(planlayer)
        axlVisibleLayer( planlayer t ))

    axlVisibleUpdate(t))


defun( bottomplacesilk ()
    axlVisibleDesign(nil)
    axlVisibleLayer( "BOARD GEOMETRY/OUTLINE" t )
    axlVisibleLayer( "PIN/bottom" t )
    axlVisibleLayer( "VIA class/bottom" t )
    axlVisibleLayer( "etch/bottom" t )
    axlVisibleLayer( "BOUNDARY/BOTTOM" t )
    axlVisibleLayer( "PACKAGE GEOMETRY/SILKSCREEN_bottom" t )
    axlVisibleLayer( "BOARD GEOMETRY/SILKSCREEN_BOTTOM" t )
    axlVisibleLayer( "DRC ERROR CLASS/bottom" t )
    axlVisibleLayer( "package keepout/bottom" t )
    axlVisibleLayer( "package keepout/all" t )
    axlVisibleLayer( "route keepout/bottom" t )
    axlVisibleLayer( "route keepout/all" t )
    axlVisibleLayer( "PACKAGE GEOMETRY/Place_Bound_Bottom" t )
    axlVisibleLayer( "PACKAGE GEOMETRY/Pin_Number" t )
    axlVisibleLayer( "DRC ERROR CLASS/package_bottom" t )
    axlVisibleLayer( "PACKAGE keepin/all" t )
    axlVisibleLayer( "route keepin/all" t )
    axlVisibleLayer( "via keepout/bottom" t)
    axlVisibleLayer( "CONSTRAINT REGION/bottom" t)
    axlVisibleLayer( "CONSTRAINT REGION/ALL" t )
    axlVisibleLayer( "manufacturing/mech_bottom" t )    
    axlVisibleLayer( "REF DES/SILKSCREEN_BOTTOM" t )
    planlayer = "PLAN/BOTTOM"
    when(axlLayerGet(planlayer)
        axlVisibleLayer( planlayer t ))

    axlVisibleUpdate(t))



defun( topbotplace ()
    axlVisibleDesign(nil)
    axlVisibleLayer( "BOARD GEOMETRY/OUTLINE" t )
    axlVisibleLayer( "PIN/bottom" t )
    axlVisibleLayer( "VIA class/bottom" t )
    axlVisibleLayer( "etch/bottom" t )
    axlVisibleLayer( "BOUNDARY/BOTTOM" t )
    axlVisibleLayer( "DRC ERROR CLASS/bottom" t )
    axlVisibleLayer( "package keepout/bottom" t )
    axlVisibleLayer( "package keepout/all" t )
    axlVisibleLayer( "route keepout/bottom" t )
    axlVisibleLayer( "route keepout/all" t )
    axlVisibleLayer( "BOARD GEOMETRY/OUTLINE" t )
    axlVisibleLayer( "PIN/TOP" t )
    axlVisibleLayer( "VIA class/top" t )
    axlVisibleLayer( "etch/TOP" t )
    axlVisibleLayer( "BOUNDARY/TOP" t )
    axlVisibleLayer( "PACKAGE GEOMETRY/SILKSCREEN_TOP" t )
    axlVisibleLayer( "PACKAGE GEOMETRY/SILKSCREEN_bottom" t )
    axlVisibleLayer( "PACKAGE GEOMETRY/Pin_Number" t )
    axlVisibleLayer( "BOARD GEOMETRY/SILKSCREEN_BOTTOM" t )
    axlVisibleLayer( "BOARD GEOMETRY/SILKSCREEN_TOP" t )
    axlVisibleLayer( "DRC ERROR CLASS/top" t )
    axlVisibleLayer( "package keepout/top" t )
    axlVisibleLayer( "package keepout/all" t )
    axlVisibleLayer( "route keepout/top" t )
    axlVisibleLayer( "route keepout/all" t )
    axlVisibleLayer( "route keepin/all" t )
    axlVisibleLayer( "package keepin/all" t )
    axlVisibleLayer( "PACKAGE GEOMETRY/place_bound_bottom" t )
    axlVisibleLayer( "DRC ERROR CLASS/package_bottom" t )
    axlVisibleLayer( "PACKAGE GEOMETRY/place_bound_top" t )
    axlVisibleLayer( "DRC ERROR CLASS/package_top" t )
    axlVisibleLayer( "manufacturing/pen24" t )
    axlVisibleLayer( "manufacturing/pen57" t )
    axlVisibleLayer( "manufacturing/mech_top" t )
    axlVisibleLayer( "manufacturing/mech_bottom" t )
    axlVisibleLayer( "manufacturing/photoplot_outline" t )
    axlVisibleLayer( "BOARD GEOMETRY/Dimension" t )
    axlVisibleLayer( "via keepout/top" t)
    axlVisibleLayer( "CONSTRAINT REGION/top" t)
    axlVisibleLayer( "via keepout/bottom" t)
    axlVisibleLayer( "CONSTRAINT REGION/bottom" t)
    axlVisibleLayer( "CONSTRAINT REGION/ALL" t )
    planlayer = "PLAN/BOTTOM"
    when(axlLayerGet(planlayer)
        axlVisibleLayer( planlayer t ))
    planlayer = "PLAN/TOP"
    when(axlLayerGet(planlayer)
        axlVisibleLayer( planlayer t ))

    axlVisibleUpdate(t))

defun( topbotplacesilk ()
    axlVisibleDesign(nil)
    axlVisibleLayer( "BOARD GEOMETRY/OUTLINE" t )
    axlVisibleLayer( "PIN/bottom" t )
    axlVisibleLayer( "VIA class/bottom" t )
    axlVisibleLayer( "etch/bottom" t )
    axlVisibleLayer( "BOUNDARY/BOTTOM" t )
    axlVisibleLayer( "DRC ERROR CLASS/bottom" t )
    axlVisibleLayer( "package keepout/bottom" t )
    axlVisibleLayer( "package keepout/all" t )
    axlVisibleLayer( "route keepout/bottom" t )
    axlVisibleLayer( "route keepout/all" t )
    axlVisibleLayer( "BOARD GEOMETRY/OUTLINE" t )
    axlVisibleLayer( "PIN/TOP" t )
    axlVisibleLayer( "VIA class/top" t )
    axlVisibleLayer( "etch/TOP" t )
    axlVisibleLayer( "BOUNDARY/TOP" t )
    axlVisibleLayer( "PACKAGE GEOMETRY/SILKSCREEN_TOP" t )
    axlVisibleLayer( "PACKAGE GEOMETRY/SILKSCREEN_bottom" t )
    axlVisibleLayer( "PACKAGE GEOMETRY/Pin_Number" t )
    axlVisibleLayer( "BOARD GEOMETRY/SILKSCREEN_BOTTOM" t )
    axlVisibleLayer( "BOARD GEOMETRY/SILKSCREEN_TOP" t )
    axlVisibleLayer( "DRC ERROR CLASS/top" t )
    axlVisibleLayer( "package keepout/top" t )
    axlVisibleLayer( "package keepout/all" t )
    axlVisibleLayer( "route keepout/top" t )
    axlVisibleLayer( "route keepout/all" t )
    axlVisibleLayer( "route keepin/all" t )
    axlVisibleLayer( "package keepin/all" t )
    axlVisibleLayer( "PACKAGE GEOMETRY/place_bound_bottom" t )
    axlVisibleLayer( "DRC ERROR CLASS/package_bottom" t )
    axlVisibleLayer( "PACKAGE GEOMETRY/place_bound_top" t )
    axlVisibleLayer( "DRC ERROR CLASS/package_top" t )
    axlVisibleLayer( "manufacturing/pen24" t )
    axlVisibleLayer( "manufacturing/pen57" t )
    axlVisibleLayer( "manufacturing/mech_top" t )
    axlVisibleLayer( "manufacturing/mech_bottom" t )
    axlVisibleLayer( "manufacturing/photoplot_outline" t )
    axlVisibleLayer( "BOARD GEOMETRY/Dimension" t )
    axlVisibleLayer( "via keepout/top" t)
    axlVisibleLayer( "CONSTRAINT REGION/top" t)
    axlVisibleLayer( "via keepout/bottom" t)
    axlVisibleLayer( "CONSTRAINT REGION/bottom" t)
    axlVisibleLayer( "CONSTRAINT REGION/ALL" t )
    axlVisibleLayer( "REF DES/SILKSCREEN_BOTTOM" t )
    axlVisibleLayer( "REF DES/SILKSCREEN_TOP" t )
    planlayer = "PLAN/BOTTOM"
    when(axlLayerGet(planlayer)
        axlVisibleLayer( planlayer t ))
    planlayer = "PLAN/TOP"
    when(axlLayerGet(planlayer)
        axlVisibleLayer( planlayer t ))

    axlVisibleUpdate(t))

defun( TOPBOT ()
    axlVisibleDesign(nil)
    axlVisibleLayer( "BOARD GEOMETRY/OUTLINE" t )
    axlVisibleLayer( "PIN/bottom" t )
    axlVisibleLayer( "VIA class/bottom" t )
    axlVisibleLayer( "etch/bottom" t )
    axlVisibleLayer( "BOUNDARY/BOTTOM" t )
    axlVisibleLayer( "DRC ERROR CLASS/bottom" t )
    axlVisibleLayer( "package keepout/bottom" t )
    axlVisibleLayer( "package keepout/all" t )
    axlVisibleLayer( "route keepout/bottom" t )
    axlVisibleLayer( "route keepout/all" t )
    axlVisibleLayer( "BOARD GEOMETRY/OUTLINE" t )
    axlVisibleLayer( "PIN/TOP" t )
    axlVisibleLayer( "VIA class/top" t )
    axlVisibleLayer( "etch/TOP" t )
    axlVisibleLayer( "BOUNDARY/TOP" t )
    axlVisibleLayer( "PACKAGE GEOMETRY/SILKSCREEN_TOP" t )
    axlVisibleLayer( "PACKAGE GEOMETRY/SILKSCREEN_bottom" t )
    axlVisibleLayer( "DRC ERROR CLASS/top" t )
    axlVisibleLayer( "package keepout/top" t )
    axlVisibleLayer( "package keepout/all" t )
    axlVisibleLayer( "route keepout/top" t )
    axlVisibleLayer( "route keepout/all" t )
    axlVisibleLayer( "route keepin/all" t )
    axlVisibleLayer( "package keepin/all" t )
    axlVisibleLayer( "via keepout/top" t)
    axlVisibleLayer( "CONSTRAINT REGION/top" t)
    axlVisibleLayer( "via keepout/bottom" t)
    axlVisibleLayer( "CONSTRAINT REGION/bottom" t)
    axlVisibleLayer( "CONSTRAINT REGION/ALL" t )

    planlayer = "PLAN/BOTTOM"
    when(axlLayerGet(planlayer)
        axlVisibleLayer( planlayer t ))
    planlayer = "PLAN/TOP"
    when(axlLayerGet(planlayer)
        axlVisibleLayer( planlayer t ))

    axlVisibleUpdate(t))


defun( BOTTOM ()
    axlVisibleDesign(nil)
    axlVisibleLayer( "BOARD GEOMETRY/OUTLINE" t )
    axlVisibleLayer( "PIN/bottom" t )
    axlVisibleLayer( "VIA class/bottom" t )
    axlVisibleLayer( "etch/bottom" t )
    axlVisibleLayer( "BOUNDARY/BOTTOM" t )
    axlVisibleLayer( "PACKAGE GEOMETRY/SILKSCREEN_bottom" t )
    axlVisibleLayer( "DRC ERROR CLASS/bottom" t )
    axlVisibleLayer( "package keepout/bottom" t )
    axlVisibleLayer( "package keepout/all" t )
    axlVisibleLayer( "route keepout/bottom" t )
    axlVisibleLayer( "route keepout/all" t )
    axlVisibleLayer( "PACKAGE keepin/all" t )
    axlVisibleLayer( "route keepin/all" t )
    axlVisibleLayer( "via keepout/bottom" t)
    axlVisibleLayer( "CONSTRAINT REGION/bottom" t)
    axlVisibleLayer( "CONSTRAINT REGION/ALL" t )

    planlayer = "PLAN/BOTTOM"
    when(axlLayerGet(planlayer)
        axlVisibleLayer( planlayer t ))

    axlVisibleUpdate(t)
    axlSetActiveLayer( "etch/bottom")

    ) 

defun( TOP ()
    axlVisibleDesign(nil)
    axlVisibleLayer( "BOARD GEOMETRY/OUTLINE" t )
    axlVisibleLayer( "PIN/TOP" t )
    axlVisibleLayer( "VIA class/top" t )
    axlVisibleLayer( "etch/TOP" t )
    axlVisibleLayer( "BOUNDARY/TOP" t )
    axlVisibleLayer( "PACKAGE GEOMETRY/SILKSCREEN_TOP" t )
    axlVisibleLayer( "DRC ERROR CLASS/top" t )
    axlVisibleLayer( "package keepout/top" t )
    axlVisibleLayer( "package keepout/all" t )
    axlVisibleLayer( "route keepout/top" t )
    axlVisibleLayer( "route keepout/all" t )
    axlVisibleLayer( "route keepin/all" t )
    axlVisibleLayer( "PACKAGE keepin/all" t )
    axlVisibleLayer( "via keepout/top" t)
    axlVisibleLayer( "CONSTRAINT REGION/top" t)
    axlVisibleLayer( "CONSTRAINT REGION/ALL" t )

    planlayer = "PLAN/TOP"
    when(axlLayerGet(planlayer)
        axlVisibleLayer( planlayer t ))

    axlVisibleUpdate(t)
    axlSetActiveLayer( "etch/Top")
    )

defun( L2 (@optional (layer "")) 
    layer = 2 
    layerchange()
    )

defun( L3 (@optional (layer ""))
    layer = 3
    layerchange()
    )

defun( L4 (@optional (layer ""))
    layer = 4
    layerchange()
    )

defun( L5 (@optional (layer ""))
    layer = 5
    layerchange()
    )

defun( L6 (@optional (layer ""))
    layer = 6
    layerchange()
    )

defun( L7 (@optional (layer ""))
    layer = 7
    layerchange()
    )

defun( L8 (@optional (layer ""))
    layer = 8
    layerchange()
    )

defun( L9 (@optional (layer ""))
    layer = 9
    layerchange()
    )

defun( L10 (@optional (layer ""))
    layer = 10
    layerchange()
    )

defun( L11 (@optional (layer ""))
    layer = 11
    layerchange()
    )

defun( L12 (@optional (layer ""))
    layer = 12
    layerchange()
    )

defun( L13 (@optional (layer ""))
    layer = 13
    layerchange()
    )

defun( L14 (@optional (layer ""))
    layer = 14
    layerchange()
    )

defun( L15 (@optional (layer ""))
    layer = 15
    layerchange()
    )

defun( L16 (@optional (layer ""))
    layer = 16
    layerchange()
    )

defun( L17 (@optional (layer ""))
    layer = 17
    layerchange()
    )

defun( L18 (@optional (layer ""))
    layer = 18
    layerchange()
    )

defun( L19 (@optional (layer ""))
    layer = 19
    layerchange()
    )

defun(layerchange ()
    allLayer = axlGetParam("paramLayerGroup:ETCH")->groupMembers
    axlVisibleDesign(nil)
    axlVisibleLayer(strcat("ETCH/" nthelem(layer allLayer)) t)
    axlVisibleLayer(strcat("BOUNDARY/" nthelem(layer allLayer)) t)
    axlVisibleLayer(strcat("anti ETCH/" nthelem(layer allLayer)) t)
    axlVisibleLayer(strcat("PIN/" nthelem(layer allLayer)) t)
    axlVisibleLayer(strcat("VIA CLASS/" nthelem(layer allLayer)) t)    
    axlVisibleLayer(strcat("DRC ERROR CLASS/" nthelem(layer allLayer)) t)
    axlVisibleLayer(strcat("route keepout/" nthelem(layer allLayer)) t)
    axlVisibleLayer(strcat("via keepout/" nthelem(layer allLayer)) t)
    axlVisibleLayer(strcat("CONSTRAINT REGION/" nthelem(layer allLayer)) t)
    ;axlVisibleLayer( "CONSTRAINT REGION/ALL" t )
    axlVisibleLayer( "BOARD GEOMETRY/OUTLINE" t )
    axlVisibleLayer( "route keepout/all" t )
    axlVisibleLayer( "route keepin/all" t )

    etchlayer = strcat("ETCH/" nthelem(layer allLayer))
    when(axlDBGetLayerType(etchlayer) == "PLANE"
        axlVisibleLayer( "ANTI ETCH/ALL" t ))

    planlayer = strcat("PLAN/" nthelem(layer allLayer))
    when(axlLayerGet(planlayer)
        axlVisibleLayer( planlayer t ))
    axlSetActiveLayer(strcat("ETCH/" nthelem(layer allLayer)))
    axlVisibleUpdate(t)
    )

defun(layerchangeadd ()
    allLayer = axlGetParam("paramLayerGroup:ETCH")->groupMembers

    axlVisibleDesign(nil)
    axlVisibleLayer(strcat("ETCH/" nthelem(layer allLayer)) t)
    axlVisibleLayer(strcat("BOUNDARY/" nthelem(layer allLayer)) t)
    axlVisibleLayer(strcat("ETCH/" nthelem(layer-1 allLayer)) t)
    axlVisibleLayer(strcat("BOUNDARY/" nthelem(layer-1 allLayer)) t)
    axlVisibleLayer(strcat("ETCH/" nthelem(layer+1 allLayer)) t)
    axlVisibleLayer(strcat("BOUNDARY/" nthelem(layer+1 allLayer)) t)
    axlVisibleLayer(strcat("anti ETCH/" nthelem(layer allLayer)) t)
    axlVisibleLayer(strcat("PIN/" nthelem(layer allLayer)) t)
    axlVisibleLayer(strcat("PIN/" nthelem(layer-1 allLayer)) t)
    axlVisibleLayer(strcat("PIN/" nthelem(layer+1 allLayer)) t)
    axlVisibleLayer(strcat("VIA CLASS/" nthelem(layer allLayer)) t) 
    axlVisibleLayer(strcat("VIA CLASS/" nthelem(layer-1 allLayer)) t) 
    axlVisibleLayer(strcat("VIA CLASS/" nthelem(layer+1 allLayer)) t)
    axlVisibleLayer(strcat("DRC ERROR CLASS/" nthelem(layer allLayer)) t)
    axlVisibleLayer(strcat("route keepout/" nthelem(layer allLayer)) t)
    axlVisibleLayer(strcat("via keepout/" nthelem(layer allLayer)) t)
    axlVisibleLayer(strcat("CONSTRAINT REGION/" nthelem(layer allLayer)) t)
    ;axlVisibleLayer( "CONSTRAINT REGION/ALL" t )
    axlVisibleLayer( "BOARD GEOMETRY/OUTLINE" t )
    axlVisibleLayer( "route keepout/all" t )
    axlVisibleLayer( "route keepin/all" t )

    etchlayer = strcat("ETCH/" nthelem(layer allLayer))
    when(axlDBGetLayerType(etchlayer) == "PLANE"
        axlVisibleLayer( "ANTI ETCH/ALL" t ))

    planlayer = strcat("PLAN/" nthelem(layer allLayer))
    when(axlLayerGet(planlayer)
        axlVisibleLayer( planlayer t ))
    axlSetActiveLayer(strcat("ETCH/" nthelem(layer allLayer)))
    axlVisibleUpdate(t)
    )

defun( BOTTOMadd ()
    (let (items sum layeradd planlayer)
    items = axlGetParam("paramLayerGroup:ETCH")->groupMembers
    sum = length(items)
    layeradd = nth(sum-2 items)

    axlVisibleDesign(nil)

    axlVisibleLayer(sprintf(nil "ETCH/%s" layeradd) t)
    axlVisibleLayer(sprintf(nil "BOUNDARY/%s" layeradd) t)
    axlVisibleLayer(sprintf(nil "VIA class/%s" layeradd) t)
    axlVisibleLayer(sprintf(nil "PIN/%s" layeradd) t)
    axlVisibleLayer( "BOARD GEOMETRY/OUTLINE" t )
    axlVisibleLayer( "PIN/bottom" t )
    axlVisibleLayer( "VIA class/bottom" t )
    axlVisibleLayer( "etch/bottom" t )
    axlVisibleLayer( "PACKAGE GEOMETRY/SILKSCREEN_bottom" t )
    axlVisibleLayer( "DRC ERROR CLASS/bottom" t )
    axlVisibleLayer( "package keepout/bottom" t )
    axlVisibleLayer( "package keepout/all" t )
    axlVisibleLayer( "route keepout/bottom" t )
    axlVisibleLayer( "route keepout/all" t )
    axlVisibleLayer( "PACKAGE keepin/all" t )
    axlVisibleLayer( "route keepin/all" t )
    axlVisibleLayer( "via keepout/bottom" t)
    axlVisibleLayer( "CONSTRAINT REGION/bottom" t)
    axlVisibleLayer( "CONSTRAINT REGION/ALL" t )

    planlayer = "PLAN/BOTTOM"
    when(axlLayerGet(planlayer)
        axlVisibleLayer( planlayer t ))

    axlVisibleUpdate(t)
    axlSetActiveLayer( "etch/bottom")
    )

    ) 


defun( TOPadd ()
    items = axlGetParam("paramLayerGroup:ETCH")->groupMembers
    layeradd = cadr(items)

    axlVisibleDesign(nil)

    axlVisibleLayer(sprintf(nil "ETCH/%s" layeradd) t)
    axlVisibleLayer(sprintf(nil "BOUNDARY/%s" layeradd) t)
    axlVisibleLayer(sprintf(nil "VIA class/%s" layeradd) t)
    axlVisibleLayer(sprintf(nil "PIN/%s" layeradd) t)

    axlVisibleLayer( "BOARD GEOMETRY/OUTLINE" t )
    axlVisibleLayer( "PIN/TOP" t )
    axlVisibleLayer( "VIA class/top" t )
    axlVisibleLayer( "etch/TOP" t )
    axlVisibleLayer( "PACKAGE GEOMETRY/SILKSCREEN_TOP" t )
    axlVisibleLayer( "DRC ERROR CLASS/top" t )
    axlVisibleLayer( "package keepout/top" t )
    axlVisibleLayer( "package keepout/all" t )
    axlVisibleLayer( "route keepout/top" t )
    axlVisibleLayer( "route keepout/all" t )
    axlVisibleLayer( "route keepin/all" t )
    axlVisibleLayer( "PACKAGE keepin/all" t )
    axlVisibleLayer( "via keepout/top" t)
    axlVisibleLayer( "CONSTRAINT REGION/top" t)
    axlVisibleLayer( "CONSTRAINT REGION/ALL" t )

    planlayer = "PLAN/TOP"
    when(axlLayerGet(planlayer)
        axlVisibleLayer( planlayer t ))

    axlVisibleUpdate(t)
    axlSetActiveLayer( "etch/Top")
    )

defun( L2add (@optional (layer "")) 
    layer = 2 
    layerchangeadd()
    )

defun( L3add (@optional (layer ""))
    layer = 3
    layerchangeadd()
    )

defun( L4add (@optional (layer ""))
    layer = 4
    layerchangeadd()
    )

defun( L5add (@optional (layer ""))
    layer = 5
    layerchangeadd()
    )

defun( L6add (@optional (layer ""))
    layer = 6
    layerchangeadd()
    )

defun( L7add (@optional (layer ""))
    layer = 7
    layerchangeadd()
    )

defun( L8add (@optional (layer ""))
    layer = 8
    layerchangeadd()
    )

defun( L9add (@optional (layer ""))
    layer = 9
    layerchangeadd()
    )

defun( L10add (@optional (layer ""))
    layer = 10
    layerchangeadd()
    )

defun( L11add (@optional (layer ""))
    layer = 11
    layerchangeadd()
    )

defun( L12add (@optional (layer ""))
    layer = 12
    layerchangeadd()
    )

defun( L13add (@optional (layer ""))
    layer = 13
    layerchangeadd()
    )

defun( L14add (@optional (layer ""))
    layer = 14
    layerchangeadd()
    )

defun( L15add (@optional (layer ""))
    layer = 15
    layerchangeadd()
    )

defun( L16add (@optional (layer ""))
    layer = 16
    layerchangeadd()
    )

defun( L17add (@optional (layer ""))
    layer = 17
    layerchangeadd()
    )

defun( L18add (@optional (layer ""))
    layer = 18
    layerchangeadd()
    )

defun( L19add (@optional (layer ""))
    layer = 19
    layerchangeadd()
    )
```