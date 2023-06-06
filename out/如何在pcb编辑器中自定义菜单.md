---
title: '如何在PCB编辑器中自定义菜单'
date: Thu, 23 Jul 2020 02:17:44 +0000
draft: false
tags: ['Allegro', 'Allegro Skill', '设计技巧']
---

通过skill加载
---------

下面是一个示例skill将在PCB编辑器中构建自定义菜单，而不考虑版本，因此您不必担心Cadence在发行之间进行的菜单更改。 可以将此skill粘贴到il文件（例如menu.il）中，并在allegro.ilinit文件加载此skill文件。 然后由PCB编辑器自动加载该skill并构建菜单。

```
custMenu = '(
(popup "User-Defi&ned")
("&LogoMaker" "logomaker")
("&Height" "upd_fe_height")
("&SMD Pin Count" "smd_count")
(separator)
("&Missing Paste/Solder Pad" "smd pad check")
("Fin&d Component" "find component")
("Find &Net" "find net")
("Change Net of Vias" "change_vianet")
("Assign Dummy Nets" "cns_dummy_net")
)
procedure( menuTrig1()
; add a new menu item before the help menu
res = axlUIMenuRegister(-1 custMenu)
)
; To see axlUIMenuRegister uncomment the following line
menuTrig1()
``````
 ; This demostrates the options of menu editing
;
; See axlUIMenuFind for baseline documentation

procedure( menuTest1()
 let( (q l z)

 ; add a line before add rect 
 q = axlUIMenuFind( nil "add rect")
 z = axlUIMenuInsert(q 'separator )

 ;add a new command at bottom of add menu
 q = axlUIMenuFind(nil 3 'bottom)
 z = axlUIMenuInsert(q "add hello" "echo hello add" )

 ; add a web link at the top of the help menu
 q = axlUIMenuFind( nil -1 'top)
 ;    shows how to embed double quotes in string
 z = axlUIMenuInsert(q "Google" "http \"http://google.com\"")

 ; add a new menubar item -- list method
 q = axlUIMenuFind( nil -1)
 l = '((popup "Drop1") ("hello1" "echo hello1") ("hello2" "echo hello2"))
 z = axlUIMenuInsert(q l)

 ; add a new menubar item -- individual calls
 q = axlUIMenuFind( nil -1)
 z = axlUIMenuInsert(q 'popup "Drop2")
 z = axlUIMenuInsert(nil "hello3"  "echo hello 3")
 z = axlUIMenuInsert(nil "hello4"  "echo hello 4")
 z = axlUIMenuInsert(nil 'popup "Pull1")
 printf("Menu popup id %L\n" z)
 z = axlUIMenuInsert(nil "hello5" "echo hello 5" )
 z = axlUIMenuInsert(nil 'end)
 z = axlUIMenuInsert(nil "hello6" "echo hello 6" )


 ; disable about and add check
 q = axlUIMenuFind( nil "about")
 axlUIMenuChange(q 'enable nil 'check t)

 ; delete first menu item in add menu
 q = axlUIMenuFind(nil 3 'top)
 axlUIMenuDelete(q)

 ; delete edit menu
 q = axlUIMenuFind(nil 1)
 axlUIMenuDelete(q)
))


;--------------------------------------------------------------------------
; the following two examples demostrate adding menu items via the menu trigger
; load this file via the allegro.ilinit file and you should see the menus
; items after allegro starts

; create a menu list
menuList = '(
     (popup "MenuBar")
	("hello" "echo hello")
	(popup "Pull") 
	   ("hello1" "echo hello1") 
	   ("hello2" "echo hello2")
	   (popup "Pull 2") 
	      ("hello3" "echo hello3") 
	   (end)
	end
	(separator)
	("hello4" "echo hello4")
     )

; The following demos additional Allegro script capabilites:
;   - command chaining via the ";" allows multiple commands on 1 line
;   - "scriptmode +i" to make forms invisible; scriptmode value restored at
;	end of command chain
;   - "toggle" value for checkbox form fields will switch the checkbox state
;   - "form_next" for enum fields (or checkboxes) will switch to next enum
;	item (form_prev also availale). Change "FORM" to form_next and
;	remove value 
ml2 = '(
     (popup "QuickKeys")
	   ("EndCaps" "scriptmode +i; prmed; FORM prmedit display_enhance toggle; FORM prmedit done ") 
	   ("Ratsnest" "scriptmode +i; prmed; form_next prmedit ratsnest_display; FORM prmedit done ") 
	)

procedure( menuTrig1()
    ; add to bottom of tool menu
    res = axlUIMenuRegister("reports" menuList 'bottom)

    ; add a new menu item before the help menu
    res = axlUIMenuRegister(-1 ml2)
)

procedure( menuTrig2(t_menufile)
    let( (q)
    printf("MENU FILE= %s\n" t_menufile)
    q = axlUIMenuFind(nil -1)
    res = axlUIMenuInsert(q menuList)
))


;   only 1 line should be uncommented at a time

; To see axlUIMenuRegister uncomment the following line
;menuTrig1()

; Using the trigger function directly
;axlTriggerSet('menu  'menuTrig2) 
```

关于16.X和17.X axlUIMenuInsert在一级菜单指定命令的区别记录

1、在16.X和17.X axlUIMenuInsert 在一级菜单中指定命令确实存差异，17.X不能事项在一级菜单调用命令  
2、16X和17X的帮助文件看了，其中关于axlUIMenuInsert的说明没有差别  
3、帮助文件包括示例文件没有任意一个案例给的在1级菜单做命令的情况

通过替代系统菜单
--------

### 注意事项

重要提示：由于该软件使用的是用户定义的菜单结构，因此只有复制了安装目录中的菜单文件并重新应用了所有用户编辑后，才会显示任何新的修补程序或发行版。

否则如果在软件更新换代后系统菜单文件将不被更新（仍使用用户定义的）新的菜单将不会被应用

### 执行方法

请转到计算机上的以下目录 \\ share \\ pcb \\ text \\ cuimenus，然后将allegro.men（Allegro）或orcad.men（OrCAD）复制到你指定的自定义文件夹。

使用文本编辑器打开men文件，您可以参考已有菜单格式编辑添加到此新菜单 下面的示例添加了一个名为User-Defined的用户菜单

```
POPUP "User-Defi&ned"
BEGIN
MENUITEM "&X Section Block", "XSection2"
MENUITEM "&LogoMaker", "logomaker"
MENUITEM "&Height", "upd_fe_height"
MENUITEM "&SMD Pin Count", "smd_count"
END
```

打开软件用户设置中 Setup>User Preferences>Paths>Editor 如图. 增加一个你你指定的自定义文件夹 ，并重启软件后生效.

![](http://a1024.synology.me:222/images/blog2022/PCB_Editor_customization.jpg)