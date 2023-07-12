---
layout: post
title: Parameter Management Functions
categories: Allegro Skill
date: 2023-07-05
permalink: allegro-skill-parameter-management-functions
excerpt: 
---

# Overview

## axlDBGridGet


axlDBGridGet(
nil)
==> lt_grids

axlDBGridGet(
t_gridName)
==> og_grid

描述

该函数用于获取当前Grid（格点）的值。函数共两种模式:
如果gridname 为 nil 则返回格点设置的所有layer列表。
如果gridname 传递了层layer的值，则直接返回该layer的格点设置的值。

注意: 格点设置中预留了一个"non-etch"层，用于设置非电气属性层的格点，其余的层为ETCH下的subclass层面。

使用 axlDBDisplayControl 函数可控制格点颜色及是否显示。

格点具有以下属性:

Name                Type                Description
objType        string                格点属性，始终为grids
readOnly        nil                是否可修改
name                string                格点layer名
xOrigin        dbrep                X origin of grid X偏移量
yOrigin        dbrep                Y origin of grid Y偏移量
xMajor                dbrep                Major X spacing of grid (read-only)值为XGrids的总和
yMajor                dbrep                Major Y spacing of grid (read-only)值为YGrids的总和
xGrids                l_dbrep                Spacings X of grid (always a list of dbreps)X方向格点间距
yGrids                l_dbrep                Spacings Y of grid (always a list of dbreps)Y方向格点间距


参数
t_gridName 格点的layer名（比如"non-etch" "TOP"）或者 nil （获取所有格点layer名）


返回值

lt_gridds - 格点layer列表
og_grid - 层面的格点属性

相关函数

axlDBGridSet

例子

获取所有layer的格点属性。

grids = axlDBGridGet(nil)
=>("non-etch" "TOP" "GND02" "POWER03" "BOTTOM")
foreach(g grids
grd = axlDBGridGet(g)
printf("GRID name=%s values=%L\n", grd->name, grd))

=>
GRID name=non-etch values=(nil name "non-etch" objType "grids" readOnly nil xOrigin 0.0 yOrigin 0.0 xMajor 5.0 yMajor 5.0 xGrids (5.0) yGrids (5.0))
GRID name=TOP values=(nil name "TOP" objType "grids" readOnly nil xOrigin 0.0 yOrigin 0.0 xMajor 25.0 yMajor 25.0 xGrids (5.0 5.0 5.0 5.0 5.0) yGrids (5.0 5.0 5.0 5.0 5.0))
GRID name=GND02 values=(nil name "GND02" objType "grids" readOnly nil xOrigin 0.0 yOrigin 0.0 xMajor 25.0 yMajor 25.0 xGrids (5.0 5.0 5.0 5.0 5.0) yGrids (5.0 5.0 5.0 5.0 5.0))
GRID name=POWER03 values=(nil name "POWER03" objType "grids" readOnly nil xOrigin 0.0 yOrigin 0.0 xMajor 25.0 yMajor 25.0 xGrids (5.0 5.0 5.0 5.0 5.0) yGrids (5.0 5.0 5.0 5.0 5.0))
GRID name=BOTTOM values=(nil name "BOTTOM" objType "grids" readOnly nil xOrigin 0.0 yOrigin 0.0 xMajor 25.0 yMajor 25.0 xGrids (5.0 5.0 5.0 5.0 5.0) yGrids (5.0 5.0 5.0 5.0 5.0))

* axlcreate


* axlDBGridSet
* axlDBTextBlockCreate
* axlExportXmlDBRecords
* axlImportXmlDBRecords
* axlPadSuppressGet
* axlPadSuppressOkLayer
* axlPadSuppressSet
* axlGetParam
* axlSetParam

# Color Access

* axlColorDoc
* axlColorGet
* axlColorShadowGet
* axlColorShadowSet
* axlColorLoad
* axlColorOnGet - Obsolete Command
* axlColorOnSet - Obsolete Command
* axlColorPriorityGet - Obsolete Command
* axlColorPrioritySet - Obsolete Command
* axlColorSave
* axlColorSet
* axlCVFColorChooserDlg
* axlClearObjectCustomColor
* axlCustomColorObject
* axlLayerPriorityClearAll
* axlLayerPriorityGet
* axlLayerPriorityRestoreAll
* axlLayerPrioritySaveAll
* axlLayerPrioritySet
* axlIsCustomColored


# Database Layer Management

## axlVisibleLayer 开关图层

打开或关闭指定图层显示状态

用于打开或关闭allegro中的某一个层。基本格式为class/subclass，如果只指定了class而未指定subclass，那么就显示或不显示当前class下所有的层。注意，执行该函数后，需要使用axlVisibleUpdate函数更新当前显示。

```lisp
axlVisibleLayer(t_layer g_makeVis);=>t/nil
```

*t_layer* 需要显示或不显示的层，格式为class/subclass，或者class
*g_makeVis* t显示层，nil不显示层
*t* 执行层面显示或不显示成功
*nil* 执行失败

```lisp
axlVisibleDesign(nil);关闭所有层
axlVisibleDesign(t);打开所有层
axlVisibleLayer( "REF DES/SILKSCREEN_TOP" t );打开指定Subclass
axlVisibleLayer( "REF DES/SILKSCREEN_TOP" nil );关闭指定Subclass
axlVisibleLayer( "REF DES" t );打开Class的所有层
axlVisibleLayer( "REF DES" nil );关闭Class的所有层
axlVisibleUpdate(t);更新视图,否则需要用户手动更新
```

## axlVisibleGet

该函数的返回值是命令运行当前design的可见性 - 哪些层可见/不可见

```
visList = axlVisibleGet();找个设计查看结果输出
```

## axlVisibleSet

该函数使用axlVisibleGet()函数的返回结果，重置design的显示状态。

```lisp
(vis = (axlVisibleGet));将当前显示存为vis
;do sth
(axlVisibleSet vis);恢复存储的vis显示状态
```


**axlGetXSection**()，这是获取design的**crosssection**(层叠结构)的函数；

**axlLayerGet**(t\_layer)，这是获得指定层t\_layer的dbid的函数；

**axlIsLayer**(t\_layer)，判断指定的层t\_layer存不存在；

```lisp
when(axlIsLayer("Board Geometry/Design_Outline")
        axlVisibleLayer("Board Geometry/Design_Outline" t)
        )
```


**axlIsVisibleLayer**(t\_layer)，判断指定层t\_layer是不是显示状态(visible)；

**axlVisibleDesign**(g\_makeVis)，设置design的状态是显示还是不显示；


* axlClasses
* axlDBGetLayerType
* axlLayerCreateCrossSection
* axlLayerCreateNonConductor
* axlConductorBottomLayer
* axlConductorTopLayer
* axlDBCreateFilmRec
* axlSetPlaneType
* axlSubclasses
* axlSubclassRoute