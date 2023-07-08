---
layout: post
title: Allegro Skill Database Read Functions
categories: Allegro Skill
date: 2023-07-05
permalink: allegro-skill-database-read-functions
excerpt: 
---
[Skill Database User Model数据库（对象）类型属性及关系](https://tiny-yhw.github.io//allegro-skill-database-user-model){:target="_blank"}


## axlDBGetDesign

获取板中所有对象的ID

```lisp
axlDBGetDesign() => dbid
axlDBGetDesign()->symbols;所有放置在PCB上的器件,包括所有Package Sym和Mech Sym
axlDBGetDesign()->symdefs;所有放置在PCB上的Package
axlDBGetDesign()->nets
axlDBGetDesign()->xnet;List of Xnets (no nets with VOLTAGE property)
axlDBGetDesign()->bus
axlDBGetDesign()->netGroup
axlDBGetDesign()->matchgroup
axlDBGetDesign()->netclass
axlDBGetDesign()->text
axlDBGetDesign()->pins;If a.dra, list of pins, else nil
axlDBGetDesign()->padstacks;所有Database中的padstacks，包含未放置到PCB中的
axlDBGetDesign()->drcs
axlDBGetDesign()->diffpair
axlDBGetDesign()->compdefs;List of component definitions
axlDBGetDesign()->components;所有Database中包含的器件，包含未放置到PCB中的
axlDBGetDesign()->bBox

axlDBGetDesign()->objType: Type of object, in this case "design"
axlDBGetDesign()->drcState;
axlDBGetDesign()->ecsets;List of Electrical Csets
axlDBGetDesign()->groups;List of groups
axlDBGetDesign()->module;List of module instances in the design
axlDBGetDesign()->region;List of regions
axlDBGetDesign()->waived;List of waived DRCs

obj=axlDBGetDesign()->symbols;包括所有Package Sym和Mech Sym
obj = setof(x obj x->type == "PACKAGE");提取所有的Package Sym
```

当前design的dbid，基本上来说整个design的所有信息都可以通过这个dbid得到。比如design有多少个 component，每个component的dbid；比如design有多少drc，每个drc又分别是什么等等。

可以用下述命令
```lisp
item=car(axlDBGetDesign()->symbols)->??;查看第一个symbols的固有属性名和属性值

```

可以用下述命令在上面的基础上继续过滤获得dbid

```
Obj = setof(x Obj x->layer == "BOARD GEOMETRY/OUTLINE")
```



## axlDBGetDesignUnits 获得设计的单位和精度

```
axlDBGetDesignUnits => ("mils" 2)
cadr((axlDBGetDesignUnits)) ;设计精度
car(axlDBGetDesignUnits()) ;设计单位
```

## skill 对象属性

### Find面板名称

text

```
axlSetFindFilter( ?enabled '("noall" "alltypes" "nameform")
 ?onButtons "alltypes")
```

## 查看提取属性

查看对象固有属性和值 `object->??`

查看对象固有属性的值 `object->?`

查看对象的附加属性和值 `object ->prop -> ??` 或者 `axlDBGetProperties(object)`

案例

```lisp
axlClearSelSet()
axlSetFindFilter( ?enabled (list "noall" "linesegs") , ?onButtons (list "linesegs"))
axlSelect;选择对象
objsel = (axlGetSelSet)
item = car(objsel)
item->??

car((axlGetSelSet))->??
nth(0 obj1)->??
```

```
axlVisibleLayer( "PACKAGE GEOMETRY/Place_Bound_Top" t )
axlVisibleUpdate(t)
axlSetFindFilter( ?enabled list("noall" "shapes") ?onButtons list("noall" "shapes"))
axlClearSelSet()
selObj = axlGetSelSet(axlAddSelectAll())
selObjs = setof(x selObj x->layer == "PACKAGE GEOMETRY/PLACE_BOUND_TOP")
selObjs2 = car(selObjs)
hi = selObjs2 ->prop ->PACKAGE_HEIGHT_MAX
```

提取属性符合要求的序列

```
symdefsdb = setof(symdefsdb axlDBGetDesign()->symdefs symdefsdb->type == "PACKAGE")
```

### 增加属性

```
axlDBAddProp(lo_attach ll_name_value_)
```

增加属性默认只能增加已经有的属性名，如需增加自定义属性名可使用axlDBCreatePropDictEntry先定义一个属性名，才能继续对齐进行增加自定义属性

### 删除属性

```
axlDBDeleteProp(lo_attach lt_name)
```

### 删除所有属性

```
axlDBDeletePropAll(t_name)
```

axlDBGetDrillPlating  

axlIsDBIDType  

axlDBGetAttachedText  

axlDBGetPad  

axlDBGetPropDictEntry  

axlDBGetProperties  

axlDBRefreshId  

axlDBGetLonelyBranches  

axlDBGetConnect  

axlDBIsFixed  

axlDBIsPackagePin  

axlGetModuleInstanceDefinition  

axlGetModuleInstanceLocation  

axlGetModuleInstanceLogicMethod  

axlGetModuleInstanceNetExceptions  

axlIsDummyNet  

axlIsLayerNegative  

axlIsPinUnused  

axlIsitFill  

axlOK2Void  

axlDBDynamicShapes  

axlDBGetShapes  

axlDBTextBlockCompact