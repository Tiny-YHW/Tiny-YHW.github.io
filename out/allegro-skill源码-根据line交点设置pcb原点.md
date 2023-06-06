---
title: 'Allegro Skill源码-根据line交点设置PCB原点'
date: Sat, 11 Jun 2022 07:38:48 +0000
draft: false
tags: ['Allegro Skill']
---

以下代码由网友Wakki提供

```
axlCmdRegister("Origin" 'set_origin)
defun( set_origin ()
   popup = axlUIPopupDefine(nil (list
     (list "Done" `axlFinishEnterFun)
         (list "Cancel" `axlcancelEnterFun)))
         axlUIPopupSet(popup)
   axlClearSelSet()
   axlSetFindFilter( ?enabled list("noall" "LINESEGS") ?onButtons list("noall" "LINESEGS"))
   axlSingleSelectPoint()
        line1 = car(axlGetSelSet())
        axlClearSelSet()
        axlHighlightObject(line1)
        when(line1
                axlSetFindFilter( ?enabled list("noall" "LINESEGS") ?onButtons list("noall" "LINESEGS"))
                axlSingleSelectPoint()
                line2 = car(axlGetSelSet())
                axlClearSelSet()
                axlDehighlightObject(line1)
        )
        when(line1 && line2 && line1->layer == line2->layer
                point = axl_ol_ol2(line1->startEnd line2->startEnd)
              axlDBChangeDesignOrigin(list(minus(xCoord(car(point))) minus(yCoord(cadr(point)))))
         )
 )
```