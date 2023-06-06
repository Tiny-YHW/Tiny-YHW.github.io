---
title: 'Command Control Functions 控制和命令'
date: Tue, 25 Jan 2022 02:12:27 +0000
draft: false
tags: ['Allegro Skill']
---

用来注册一些skill的函数为allegro中的命令，以及设置各种工作模式

### axlCmdRegister 注册命令

```
axlCmdRegister(
    t_allegroCmd
    ts_callback
    ?cmdType        t_cmdType
    ?doneCmd        ts_doneCmd
    ?cancelCmd      ts_cancelCmd
    ) ==> t/nil
```

注册一个名为_t\_allegroCmd_的命令调用ts\_callback skill程序

_**t\_cmdType**_

"interactive"：Allegro PCB Editor 默认交互命令  
"general"：立即命令，在调用该命令时立即执行，即使在另一个命令。

"sub\_cmd"：必须在"interactive"命令中调用。用于弹出窗口。

_**ts\_doneCmd**_：当用户键入Done或从弹出窗口中选择Done时，调用的完成回调函数。 可以是符号或字符串。 如果为 nil，Allegro PCB Editor 默认调用 axlFinishEnterFun

_**ts\_cancelCmd**_：当用户键入Cancel或从弹出窗口中选择Cancel时，调用的取消回调函数。 可以是符号或字符串。 如果为 nil，Allegro PCB Editor 默认调用 axlCancelEnterFun。

### axlEndSkillMode 结束skill状态，回到command line

```
axlEndSkillMode()
```

### axlFlushDisplay刷新屏幕更新缓存

```
mypath = axlPathStart( list(8900:4400))
axlPathArcRadius(mypath, 12., 8700:5300, nil, nil, 500)
myline = axlDBCreatePath( mypath, "etch/top" nil); Arc is not yet visible
axlFlushDisplay(); Now arc is visible
```

### axlOKToProceed检测当前是不是有另外的交互式操作命令在运行

```
(when axlOKToProceed
    ;; do AXL interactive command
    )
```

### axlUIPopupDefine 定义右键菜单的各个选项 axlUIPopupSet将定义好的菜单设置到右键中

```
procedure( aa println("I- you select A")) procedure( bb println("I- you select B"))
pop=axlUIPopupDefine( nil '(("A" aa) ("B" bb)  )   )
axlUIPopupSet( pop )
```

运行了上面的程序以后在allegro中单击鼠标右键就会看到一个popup，就像我们常见的Done，Cancel，Opps那个popup，只是这里 的是A和B。 axlUIPopupSet( nil ) 这个命令来将刚刚的设置清除

```
popid = axlUIPopupDefine(nil
    (list(list "Complete" 'axlMyComplete)
        (list "Rotate" 'axlMyRotate)
        (list "Something" 'axlMySomething)
        (list "Cancel" 'axlCancelEnterFun)
        )
    )
axlUIPopupSet(popid)
``````
(setq popId (axlUIPopupDefine nil
                    (list (list "Complete" 'axlMyComplete) 
                          (list "Rotate" 'axlMyRotate) 
                          (list "Something" 'axlMySomething))))
axlUIPopupSet( popid)
```

### axlVisibleUpdate更新视图显示

### 其他

axlCmdUnregister  
axlSetLineLock  
axlSetRotateIncrement  
axlUIGetUserData  
axlBuildClassPopup  
axlBuildSubclassPopup  
axlSubclassFormPopup  
axlWindowFit