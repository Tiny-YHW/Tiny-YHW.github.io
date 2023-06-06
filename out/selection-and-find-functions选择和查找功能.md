---
title: 'Selection and Find Functions 选择和查找功能'
date: Tue, 25 Jan 2022 02:36:37 +0000
draft: false
tags: ['Allegro Skill']
---

### 点选函数

axlSingleSelectPoint() => 运行该命令之后，allegro将提示你点选一个design中的对象。

axlAddSelectPoint()

axlSubSelectPoint()

### 框选函数

axlSingleSelectBox() => 在allegro中框选

axlAddSelectBox()

axlSubSelectBox()

### 通用选择函数

axlSelect() => 支持多种选择方式于一身，单选，框选，Temp Group

```
(defun showElement ()
mypopup = axlUIPopupDefine( nil
	 (list (list "Done" 'axlFinishEnterFun)
	 (list "Cancel" 'axlCancelEnterFun)))
axlUIPopupSet( mypopup)
axlSetFindFilter( ?enabled list( "NOALL" "ALLTYPES" "NAMEFORM")
	 ?onButtons "ALLTYPES")
while( axlSelect()
	 axlShowObject( axlGetSelSet()))
)
```

### 其它选择函数

axlAddSelectAll() =>不需要用户交互的选择方式，只根据Find Filter的条

axlSubSelectAll()

axlSingleSelectName()

axlAddSelectName()

axlSubSelectName()

axlSingleSelectObject()

axlAddSelectObject()

axlSubSelectObject()

### 获取和清除函数

axlGetSelSet() => 获取之前的选择函数选择的dbid

axlGetSelSetCount()

axlClearSelSet() => 清除之前选择函数选择的dbid(注：当一个对象被选择了以后，将会被自动的以Temp Highlight的方式高亮，而该函数运行以后将会清除这个对象的选择状态，同时该对象也不再高亮)

Find面板控制
--------

axlSetFindFilter：第一个list是允许勾选项，第二个list是默认勾选项，关键字包括pins、vias、clines、clinesegs、lines、linesegs、drcs、text、shapes、shapesegs、boundary\_shapes、voids、voidsegs、symbols、figures、components、functions、nets、bondwires、fingers、groups、groupmembers、autoform、equivlogic、invisible、nameform、dynthemals、bondsmart、alltypes、all

```
(axlSetFindFilter ?enabled (list "vias" "pins" "nets") ?onButtons (list "vias" "pins"))
```

axlGetFindFilter 当前Find面板选项
---------------------------

```
ret = axlGetFindFilter(t);勾选的项目
ret = axlGetFindFilter(nil);允许勾选的项目
ret = axlGetFindFilter();默认值为nil允许勾选的项目
```

axlDBFindByName 按指定名称获取dbid
---------------------------

s\_type支持'net、'refdes、'padstack

```
axlDBFindByName(s_type t_name)
db = axlDBFindByName('net "GND")
db = axlDBFindByName('padstack "VIA")
db = axlDBFindByName('refdes "U1")
```

axlSelectByName按名称选择对象
----------------------

t\_objectType支持"NET"、"COMPONENT"、"FUNCTION"、"DEVTYPE"、"SYMTYPE"、"PIN"、"REFDES"、"COMPREFDES"、"GROUP"、"BUS"、"DIFF\_PAIR"、"NETCLASS"、"NET\_GROUP"、"REGION"、"XNET"、"MATCH\_GROUP"、"MODULE"

支持使用通配符

```
axlSelectByName (t_objectType t_name/lt_name [g_wildcard])

p = axlSelectByName("NET" '("GND" "NET1"))
p = axlSelectByName("COMPONENT" "C1")
p = axlSelectByName("FUNCTION" "TF-326")
p = axlSelectByName("DEVTYPE" "CAP1")
p = axlSelectByName("SYMTYPE" "dip14_3")
p = axlSelectByName("PIN" "U1.1")
p = axlSelectByName("REFDES" "U3")
p = axlSelectByName("GROUP" "BAR")
p = axlSelectByName("PIN" "U1.*" t)
p = axlSelectByName("PIN" "U1.?" t)
p = axlSelectByName("NET" "N*" t)

car(p)->??
```

axlSingleSelectPoint  
axlAddSelectPoint  
axlSubSelectPoint  
axlSingleSelectBox  
axlAddSelectBox  
axlSubSelectBox  
axlAddSelectAll  
axlSubSelectAll  
axlSingleSelectName  
axlAddSelectName  
axlSubSelectName  
axlSingleSelectObject  
axlAddSelectObject  
axlSubSelectObject  
axlSelect  
axlGetSelSet  
axlGetSelSetCount  
axlClearSelSet  
axlSetFindFilter  
axlAutoOpenFindFilter  
axlOpenFindFilter  
axlCloseFindFilter  
axlFindFilterIsOpen  
axlSelectByProperty  
axlSnapToObject  
axlLastPickIsSnapped