---
title: '【skill源码】Allegro Skill创建ShapeKeepout'
date: Thu, 03 Dec 2020 05:07:48 +0000
draft: false
tags: ['Allegro', 'Allegro Skill']
---

#### 经常局部改版，又不想修改动态铜皮，想了下这样方便点

```
 /**
  * @author #hyper
  * @desc #描述
  * @date 2020-12-03 12:18:59
  */
(procedure CreateShapeKeepOut()	
    prog((rect layer)	
        layer = "ROUTE KEEPOUT/ALL"
        (axlVisibleLayer layer t)
        rect = axlDBCreateRectangle(
            axlEnterBox(?prompts
                list("First rectangle point, please..."
                    "Second rectangle point, please...")
                ) 
            t
            layer
            )
        axlDBAddProp(car(rect),  list("ROUTES_ALLOWED"))
        axlDBAddProp(car(rect),  list("VIAS_ALLOWED"))
        axlShell("done")
    return()
    );end prog
);end procedure
```

![](http://a1024.synology.me:222/images/blog2022/ShapeKeepout1.jpg)

![](http://a1024.synology.me:222/images/blog2022/ShapeKeepout2.jpg)