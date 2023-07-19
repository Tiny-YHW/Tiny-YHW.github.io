---
layout: post
title: Data Operator Functions
categories: Allegro Skill
date: 2023-07-04
permalink: allegro-skill-lisp-data-operator-functions
excerpt: Data Operator Functions
---
# 3 Data Operator Functions

## setf 给指定位置替换一个新值

```lisp
setf( g_place g_value ) ;=> g_result
setf( g_place := g_value);=> g_result

x = '(a b c d e)
setf( (car x) 42);; here x changes to (42 b c d e)
;=> (42 b c d e)
x = '(a b c d e)
(car x) := 42
;x => (42 b c d e)
```

**setf Helper Functions**
```
setf_arrayref
setf_caaar
setf_caadr
setf_caar
setf_cadar
setf_caddr
setf_cadr
setf_car
set_cdaar
setf_cdadr
setf_cdar
setf_cddar
setf_cdddr
setf_cddr
setf_cdr
setf_get
setf_getSG
setf_getSGq
setf_getShellEnvVar
setf_getd
setf_getq
setf_getqq
setf_last
setf_leftEdge
setf_lowerLeft
setf_nth
setf_nthcdr
setf_nthedr
setf_nthelem
setf_rightEdge
setf_slotValue
setf_topEdge
setf_bottomEdge
setf_upperRight
setf_xCoord
setf_yCoord
```

```lisp
myList = '(1 2 3 4); A user-defined list 
setf(nth(2  myList) 0); Set the 2nd element (zero-based) of myList 
myList is now modified: 
(1 2 0 4)
setf(nthelem(1 myList) 6); set the 1st element of myList (assuming one-based index)
myList is now modified:
(6 2 0 4)
```

alphaNumCmp
concat
copy_<name>
copyDefstructDeep
get
getSG
getq
getqq
importSkillVar
integerp
make_<name>
otherp
plist
popf
postArrayDec
postArrayInc
postArraySet
postdecrement
postincrement
preArrayDec
preArrayInc
preArraySet
predecrement
preincrement
pushf
putprop
putpropq
putpropqq
quote
remprop
rotatef
set
setguard
setplist
setq
setSG
symbolp
symeval
symstrp