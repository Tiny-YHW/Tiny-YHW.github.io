---
layout: post
title: Allegro Skill Interface Functions
categories: Allegro Skill
date: 2023-07-05
permalink: allegro-skill-interface-functions
excerpt: This chapter describes the AXL/SKILL functions that give access to the Allegro PCB Editor interface. These include display control, cursor setup, and soliciting user input, such as text and mouse picks.
---


## axlHighlightObject、axlDehighlightObject

高亮对象和取消高亮对象

两个函数中的t参数，如果设置代表使用永久高亮颜色，如果不设置则使用临时高亮颜色

```lisp
axlHighlightObject( axlGetSelSet() t)
axlDehighlightObject( axlGetSelSet() t)
```

```lisp
(axlDehighlightObject ((axlDBGetDesign)->symbols))
(axlVisibleDesign nil) 
(axlVisibleLayer "ETCH" t) 
(axlClearSelSet)
(axlSetFindFilter ?enabled '("NOALL" "clinesegs") ?onButtons '("NOALL" "clinesegs")) 
(lSeg = (axlGetSelSet (axlAddSelectAll))) 
(axlClearSelSet) 
(axlDehighlightObject lSeg)
```

## axlZoomToDbid 显示视图缩放到指定对象

```lisp
axlZoomToDbid(o_dbid/lo_dbid g_always [x_window]);==> t/nil
```

对象数大于20时，将不会缩放视图

* o_dbid  - list of DBIDS or one DBID
* g_always - if t then ignores NO_ZOOM_TO_OBJECT environment variable
* x_window: optional window id or nil to currently active window (see axlZoomBbox) If not provided uses active window.
* t - Something was done.
* nil - No valid DBID's or all objects already at desired display state.

```lisp
sym = axlDBFindByName('refdes "U1")
axlZoomToDbid(sym t)
```

axlClearDynamics

axlAddSimpleRbandDynamics

axlAddSimpleMoveDynamics

axlDesignFlip

axlEnterPoint

axlEnterString

axlEnterAngle

axlCancelEnterFun

axlFinishEnterFun

axlGetDynamicsSegs

axlGetLineLock

axlEnterBox

axlEnterPath

axlMiniStatusLoad

axlDrawObject

axlDynamicsObject

axlEraseObject

axlControlRaise

axlEnterEvent

axlEventSetStartPopup

axlGetTrapBox

axlRatsnestBlank

axlRatsnestDisplay

axlSetDynamicsMirror

axlSetDynamicsRotation

axlShowObjectToFile

axlUICmdPopupSet

axlMakeDynamicsPath