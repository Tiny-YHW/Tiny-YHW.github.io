---
title: 'AXL-SKILL User Interface Functions 用户界面交互函数'
date: Mon, 20 Feb 2023 08:24:36 +0000
draft: false
tags: ['Allegro Skill']
---

本章描述了用于确认动作意图的AXL/Skill功能，提示文本输入，显示ASCII文本文件，并刷新显示缓冲区中的待定更改。

axlCancelOff，axlCancelOn，axlCancelTest
--------------------------------------

在执行长时间操作时允许取消该操作

```
count = 0
axlCancelOn()
while ( count < 50000 && !axlCancelTest()
    printf("Count = %d\n" count)
    count++
)
axlCancelOff()
```

axlCursorGet，axlCursorWarp 获取，设置光标位置
------------------------------------

axlWindowBoxGet 获取当前PCB视图的对角坐标
------------------------------

axlMeterCreate，axlMeterDestroy 启动，关闭具有可选取消功能的进度条
------------------------------------------------

axlMeterIsCancelled 检查进度条是否已被取消
-------------------------------

axlMeterUpdate更新进度条信息
---------------------

```
axlMeterCreate("SigNoise Design Audit", "", t)
total = <total nets>
done = 0
while(<still next net> && (!axlMeterIsCancelled())
    < do work >
    axlMeterUpdate( (100 * ++done)/total
        sprintf(nil "Check %d of %d nets" done total))
)
axlMeterDestroy()
```

axlUIConfirm 弹出确认窗口显示字符串
------------------------

axlUIConfirmEx 附带一个Do not show again选项
--------------------------------------

```
axlUIConfirm(t_message [s_level]) ==> t
axlUIConfirm( "Returning to Allegro. Please confirm." )
axlUIConfirm( "Selected object has FIXED property." 'error )
axlUIConfirmEx( "Use this command at your own risk." "mynewcommand")
```

axlUIYesNo
----------

提供显示消息 t\_message 的对话框。 如果您选择 Yes，则返回 t，No 则返回 nil。

```
axlUIYesNo( "Overwrite module?" )
axlUIYesNo( "Overwrite module?" nil 'no )
axlUIYesNo( "Overwrite module?" "My Skill Program" )
axlUIYesNo("are you sure to delete all highlight shapes?" "Delete Shape Command")
```

axlUIYesNoCancel
----------------

基本和axlUIYesNo一样，选项增加到三个，返回值有区别

```
axlUIPrompt(t_message [t_default]/'password) ==> t_response/nil
```

x\_result: 0 for No, 1 for Yes and 2 for Cancel.

axlUIPrompt
-----------

提供了用户输入信息的功能，返回值为字符串

```
axlUIPrompt(t_message [t_default]/'password) ==> t_response/nil
axlUIPrompt( "Enter Your Name" "user name" )
axlUIPrompt( "Enter module name" "demo" )
```

axlUIMultipleChoice
-------------------

显示一个对话框，其中包含一个问题，其中包含一组两个或多个答案的列表。 您必须选择其中一个答案才能继续。 返回选择的答案的序号，0是第一个序号

```
listtype = '("Net Class" "Bus" "Net Group")
ret = axlUIMultipleChoice("Please select a group type to creat pinpairs" listtype "which one")
(case ret
	(0 allclass = axlDBGetDesign()->netclass selecttext = "Net Class")
	(1 allclass = axlDBGetDesign()->bus selecttext = "Bus")
	(2 allclass = axlDBGetDesign()->netGroup selecttext = "Net Group")
)

axlUIMultipleChoice => axlUIMultipleChoice("Pick a layer" '("top" "bottom" ) "View Layer")
```

axlUIWCloseAll 关闭所有临时窗口(对话框和文本视图窗口)
-----------------------------------

axlUIWMove 移动窗口位置
-----------------

axlUIWSize 返回窗口的外部大小
--------------------

axlUIViewFileCreate 打开视图窗口显示文件
------------------------------

```
axlUIViewFileCreate(t_file t_title g_deleteFile [lx_size] [lt_placement] [g_formToExpose])
logWindow = axlUIViewFileCreate("batch_drc.log" "Batch DRC Log" nil)
```

axlUIViewFileReuse
------------------

重新使用视图窗口显示文件(t\_file)

axlIsViewFileType
-----------------

测试对象是否为 a long message window type.

axlUIWExpose，axlUIWClose 打开并重新显示，关闭窗口
-------------------------------------

```
axlUIWExpose(logWindow)
axlUIWClose(logWindow)
```

axlUIWPrint 打印信息
----------------

将消息打印到主窗口以外的窗口。如果没有其它窗口，则输出到主窗口

```
axlUIWPrint(nil "Please enter a value:")
```

  
axlUIWRedraw 重绘窗口
--------------------

重绘指示的窗口。如果窗户_dbid_是无，重绘主窗口。

axlUIWBeep 向用户发送警报声
-------------------

axlUIWDisableQuit 禁用系统退出命令
--------------------------

axlUIWExposeByName 按名称查找窗口并打开它
------------------------------

axlUIWShow
----------

根据传递的选项显示或隐藏窗口。如果传递的窗口id为无，该功能适用于主窗口。

axlUIWUpdate
------------

强制更新窗口

axlUIWTimerAdd  
axlUIWTimerRemove
----------------------------------

axlUIDataBrowse
---------------

axlUIWPerm  
axlUIWSetHelpTag  
axlUIWSetParent
-----------------------------------------------

  
axlUIWBlock  
axlUIEditFile  
axlUIViewFileScrollTo
------------------------------------------------------

axlUIWHelpRegister
------------------

axlUIControl  
axlUIMenuChange  
axlUIMenuDebug  
axlUIMenuDelete  
axlUIMenuFind  
axlUIMenuInsert  
axlUIMenuRegister
-----------------------------------------------------------------------------------------------------------------------

axlUIMenuLoad
-------------

axlUIMenuDump
-------------

axlUIColorDialog
----------------