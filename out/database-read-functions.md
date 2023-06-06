---
title: 'Database Read Functions'
date: Thu, 15 Sep 2022 01:44:10 +0000
draft: false
tags: ['Allegro Skill']
---

[Skill Database User Model数据库（对象）类型属性及关系](https://a1024.synology.me:1024/?p=2926)

### axlDBGetDesign

获取板中所有对象的ID

*   bus: List of busses
*   compdefs: List of component definitions
*   components: List of components
*   diffpair: List of differential pairs
*   drcs: List of DRCs
*   ecsets: List of Electrical Csets
*   groups: List of groups
*   matchgroup: List of match groups in the design
*   module: List of module instances in the design
*   nets: List of nets
*   netclass: List of netclass constraints group
*   netgroup: List of netgroups in the design
*   objType: Type of object, in this case "design"
*   region: List of regions
*   padstacks: List of padstacks
*   pins: If a .dra, list of pins, else nil
*   symbols: List of symbol instances ,包括所有Package Sym和Mech Sym
*   symdefs: List of symbol defs ，所有Package
*   waived: List of waived DRCs
*   xnet: List of Xnets (no nets with VOLTAGE property)

```
axlDBGetDesign() => dbid
axlDBGetDesign()->text
axlDBGetDesign()->pins
axlDBGetDesign()->symdefs
axlDBGetDesign()->bus
axlDBGetDesign()->netGroup
axlDBGetDesign()->matchgroup
axlDBGetDesign()->netclass
axlDBGetDesign()->nets
axlDBGetDesign()->xnet
axlDBGetDesign()->padstacks
axlDBGetDesign()->drcs
axlDBGetDesign()->diffpair
axlDBGetDesign()->compdefs
axlDBGetDesign()->components
axlDBGetDesign()->bBox
axlDBGetDesign()->objType

obj=axlDBGetDesign()->symbols;包括所有Package Sym和Mech Sym
obj = setof(x obj x->type == "PACKAGE");提取所有的Package Sym
```

当前design的dbid，基本上来说整个design的所有信息都可以通过这个dbid得到。比如design有多少个 component，每个component的dbid；比如design有多少drc，每个drc又分别是什么等等。

可以用下述命令在上面的基础上继续过滤获得dbid

```
Obj = setof(x Obj x->layer == "BOARD GEOMETRY/OUTLINE")
```

### axlDBGetDesignUnits

获得设计的单位和精度

```
axlDBGetDesignUnits => ("mils" 2)
cadr((axlDBGetDesignUnits)) ;设计精度
car(axlDBGetDesignUnits()) ;设计单位
```

skill 对象属性
==========

### Find面板名称

text

```
axlSetFindFilter( ?enabled '("noall" "alltypes" "nameform")
 ?onButtons "alltypes")
```

查看提取属性
------

查看对象固有属性和值 object->??

查看对象固有属性的值 object->?

查看对象的附加属性和值 object ->prop -> ?? 或者 axlDBGetProperties(_object_)

案例

```
axlClearSelSet()
axlSetFindFilter( ?enabled (list "noall" "linesegs") , ?onButtons (list "linesegs"))
axlSelect;选择对象
objsel = (axlGetSelSet)
item = car(objsel)
item->??

foreach( x obj1
lengthss = axlDBGetLength(x)
sumlength = sumlength + lengthss
)

car((axlGetSelSet))->??
nth(0 obj1)->??
``````
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

增加属性
----

axlDBAddProp(_lo\_attach ll\_name\_value_)

增加属性默认只能增加已经有的属性名，如需增加自定义属性名可使用axlDBCreatePropDictEntry先定义一个属性名，才能继续对齐进行增加自定义属性

删除属性
----

axlDBDeleteProp(_lo\_attach lt\_name_)

删除所有属性
------

axlDBDeletePropAll(t\_name)

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