---
title: 'Skill 添加和修改对象'
date: Fri, 29 May 2020 02:56:14 +0000
draft: false
tags: ['Allegro', 'Allegro Skill']
---

Text
----

在设计中增加文本

axlDBCreateText(_t\_textl，anchorPointr，textOrientation_，\[_t\_layer_\]，\[_o\_attach_\])

_t\_text_：要增加的文本

_l\_anchorPoint_：增加文本的坐标点

_r\_textOrientation_：文本类型

_t\_layer_：增加到层

_o\_attach_：依附到对象

```
axlVisibleLayer( "PACKAGE GEOMETRY/Place_Bound_Top" t )
axlVisibleUpdate(t)
axlSetFindFilter( ?enabled list("noall" "shapes") ?onButtons list("noall" "shapes"))
axlClearSelSet()
selObj = axlGetSelSet(axlAddSelectAll())
selObjs = setof(x selObj x->layer == "PACKAGE GEOMETRY/PLACE_BOUND_TOP")
selObjs2 = car(selObjs)
height = selObjs2 ->prop ->PACKAGE_HEIGHT_MAX

myorient = make_axlTextOrientation(?textBlock "1", ?rotation 0,?mirrored nil, ?justify "center")
axlDBCreateText(height,0:0,myorient,"BOARD GEOMETRY/DIMENSION",selObjs2)
```

### 修改文本

### axlDBChangeText

```
 ;修改文本内容
cret = axlDBChangeText(text "Chamfer neither sides")
 
;修改字号
cret = axlDBChangeText(text nil 4)
 
;修改角度

myorient = make_axlTextOrientation(?textBlock nil, ?rotation nil,?mirrored nil, ?justify nil)
axlTextOrientationCopy(text myorient)
myorient->rotation = 0.0
cret = axlDBChangeText(text "New text" myorient)
```

改变位置使用axlTransformObject重命名位号使用axlRenameRefdes.

```
texthe = 100
textlength = 200
axlTransformObject(obj, ?move -texthe:textlength)
```

Line
----

在设计中增加线

axlDBCreateLine(_l\_points_，\[_f\_width_\]，\[_t\_layer_\]，\[_t\_netname_\]/\['line\]，\[_rd\_parent_\])

```
axlDBCreateLine( (list 1000:1250 2000:2250), 15, "etch/top")
Path1 = list((1000:1250) (2000:2250) （1000，2250）(1000:1250))
line_width = 1
linelayer = "PACKAGE GEOMETRY/PLACE_BOUND_TOP"
(axlDBCreateLine Path1 line_width linelayer)
```