---
title: 'Design Control Functions 设计控制功能'
date: Tue, 14 Feb 2023 03:22:38 +0000
draft: false
tags: ['Allegro Skill']
---

axlCurrentDesign 获取当前设计的文件名
---------------------------

```
(setq design_file (axlCurrentDesign))
(printf "The current design file name is: %s\n" design_file)
```

axlDesignType 获取当前设计的设计类型
-------------------------

```
(axlDesignType design_file)
```

`design_file` 参数是一个设计文件对象。函数将返回以下之一的字符串：

axlSetSymbolType 设置Sym类型
------------------------

```
axlSetSymbolType(t_symbolType)
axlSetSymbolType("package")
```

t\_symbolType可以是"package", "mechanical", "format" "shape" "flash"

axlDBControl 查询或设置数据库
---------------------

```
;关闭DRC
old = axlDBControl('drcEnable, nil)
;Gets current value of pin-2-pin ratsnest.
current = axlDBControl('ratsnestDistance)
;Gets all names supported by this interface.
listOfNames = axlDBControl(nil)
```

  
axlDBGetExtents 提供数据库对象的范围  
axlDBIgnoreFixed 忽略锁定属性
-------------------------------------------------------

```
; 选择一起对象
p = ashOne()
; 对其增加锁定属性
axlDBAddProp(p, '("FIXED" t))
; 删除它失败
axlDeleteObject(p) 
; 忽略锁定再删除即可删除
axlDBIgnoreFixed(t)
axlDeleteObject(p) 
; 记得恢复忽略锁定选项
axlDBIgnoreFixed(nil)
```

axlDBIsReadOnly 数据库对象是否是只读的
---------------------------

axlGetDrawingName 获取当前设计的完整路径
-----------------------------

```
axlGetDrawingName()
```

axlInTrigger 回调器
----------------

axlIsSymbolEditor 判断是否为SYM编辑状态
------------------------------

加载自定义菜单时，您可能希望区分SYM编辑器和Design编辑。

axlKillDesign
-------------

axlOpenDesign 打开新设计
-------------------

打开设计。新设计将取代当前设计。

```
 axlOpenDesign(
	 ?design t_design
	 ?mode t_mode
	 ?noMru g_noMru
 )
 ==> t_design/nil
```

t\_design：新设计的名称

t\_mode：w或者wf 或者再增加一个“l”禁用文件锁定，如wl

g\_noMru：t则不更新到最近文件列表，默认值为nil更新

axlOpenDesignForBatch 和上面类似
---------------------------

axlRenameDesign 重命名设计
---------------------

axlSaveDesign 保存设计
------------------

axlSaveEnable 设置File-Save 是否可用  
axlDBChangeDesignExtents 更改设计画布范围  
axlDBChangeDesignOrigin 更改设计原点  
axlDBChangeDesignUnits 更改设计单位  
axlDBCheck  
axlDBCopyPadstack  
axlDBDelLock  
axlDBGetLock  
axlDBMemoryReclaim  
axlDBSetLock  
axlDBTuneSectorSize  
axlTechnologyType  
axlTriggerClear  
axlTriggerPrint  
axlTriggerSet  
axlGetActiveLayer 获取当前设计活动层  
axlGetActiveTextBlock 后去当前设计活动字号  
axlSetActiveLayer 设置设计活动层  
axlWFMAnyExported  
axlDBDisplayControl

axlCompileSymbol