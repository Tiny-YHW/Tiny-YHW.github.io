---
layout: post
title: Allegro Skill Database Create Functions
categories: Allegro Skill
date: 2023-07-05
permalink: allegro-skill-database-create-functions
excerpt: 用Allegro Skill在板中创建一个对象
---

## Path Functions

### axlPathStartCircle 创建一个指定圆心半径的圆形的Path

```lisp
axlPathStartCircle(l_location f_width); ==> r_path/nil
```

* l_location:center and radius as ((X Y) R)
* f_width:edge width of the circle

```lisp
path3=axlPathStartCircle( list(100:200 20) 0.0)
axlDBCreateShape(path3 t "ROUTE KEEPOUT/ALL")
```

## axlDBCreateShape 创建一个Shape


axlPathStart
axlPathArcRadius
axlPathArcAngle
axlPathArcCenter
axlPathLine
axlPathGetWidth
axlPathSegGetWidth
axlPathGetPathSegs
axlPathGetLastPathSeg
axlPathSegGetEndPoint
axlPathSegGetArcCenter
axlPathSegGetArcClockwise
axlPathOffset
axlDB2Path
axlDBCreatePath
axlDBCreateLine
axlDBCreateCircle

## Create Shape Interface

axlDBCreateOpenShape
axlDBCreateCloseShape
axlDBActiveShape
axlDBCreateVoidCircle
axlDBCreateVoid

axlDBCreateRectangle

## Nonpath DBCreate Functions

axlCreateBondFinger
axlCreateBondWire
axlDBCreateExternalDRC
axlDBCreatePadStack
axlDBCreatePin
axlDBCreateSymbol
axlDBCreateSymbolSkeleton
axlDBCreateText
axlDBCreateVia
axlDBCreateSymbolAutosilk
axlCreateWirebondGuide

## Property Functions

axlDBCreatePropDictEntry
axlDBAddProp

## Load and Save Functions

axlLoadPadstack
axlLoadSymbol
axlPadstackToDisk
axlRefreshSymbol