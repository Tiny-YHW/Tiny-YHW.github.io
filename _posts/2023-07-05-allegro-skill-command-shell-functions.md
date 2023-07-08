---
layout: post
title: Allegro Skill Command Shell Functions
categories: Allegro Skill
date: 2023-07-08
permalink: allegro-skill-command-shell-functions
excerpt: This chapter describes the AXL-SKILL functions that access the Allegro PCB Editor environment and command shell
---

## axlSetAlias axlSetFunckey axlGetAlias axlGetFuncKey 指定快捷命令 获取快捷命令

axlSetFunckey定义的命令允许数字或字母键在不输Enter键的情况被直接使用
axlSetAlias定义的命令需要输入命令后按Enter键才会被执行

```lisp
axlSetAlias(t_alias g_value); ==> t/nil
axlSetFunckey(t_alias g_value); ==> t/nil

axlGetAlias(t_alias/nil); ==> t_value/nil
axlGetFuncKey(t_alias/nil); ==> t_value/nil
```

```lisp
axlSetAlias( "F2" "save");设置"F2"键为"save"命令
axlSetAlias( "F2" nil);取消"F2"当前定义的命令
axlSetAlias( "~S" nil);取消Ctrl+S当前定义的命令
axlSetFunckey( "m" "move" t)
axlSetFunckey( "m" nil)
```

## axlShell 在 Skill 环境使用 cammand 命令

```lisp
axlShell(t_command);==> t
```

```lisp
axlShell("status")
```


## axlGetVariable axlGetVariableList axlSetVariable axlUnsetVariable axlSetVariableFile axlUnsetVariableFile 获取和设动用户变量值

```lisp
axlGetVariable(t_variable/nil);==> t_value/nil
axlGetVariableList(t_variable/nil);==> t_value/lt_value/nil

axlSetVariable(t_variable g_value );==> t_value/nil 临时设置变量，不会存储到env
axlUnsetVariable(t_variable);==> t 临时设置变量，不会存储到env

axlSetVariableFile(t_variable g_value);==> t/nil 设置变量，会存储到env
axlUnsetVariableFile(t_variable );==> t 设置变量，会存储到env
```

```lisp
menu = axlGetVariable("menuload"); ==> "geometry"
psmpath = axlGetVariable("psmpath"); ==> ". symbols"

axlSetVariable("libpath" "/mytools/library");==> t
libraryPath = axlGetVariable("libpath");==> "/mytools/library"
axlSetVariable("psmpath" '("." "symbols"));==> t
axlGetVariableList("psmpath");==> ("." "symbols")

(axlUnsetVariable "libpath");==> "/mytools/library"
libraryPath = (axlGetVariable "libpath");==> nil

path = axlGetVariableList("psmpath");==> ( "." "symbols" "/cds/root/share/pcb/allegrolib/symbols")

```


axlJournal

axlProtectAlias

axlIsProtectAlias

axlReadOnlyVariable

axlShellPost