---
layout: post
title: Allegro Skill Command Shell Functions
categories: Allegro Skill
date: 2023-07-08
permalink: allegro-skill-command-shell-functions
excerpt: This chapter describes the AXL-SKILL functions that access the Allegro PCB Editor environment and command shell
---

## axlSetAlias axlSetFunckey指定

axlSetFunckey定义的命令允许数字或字母键在不输Enter键的情况被直接使用
axlSetAlias定义的命令需要输入命令后按Enter键才会被执行

```lisp
axlSetAlias(t_alias g_value); ==> t/nil
```

```lisp
axlSetAlias( "F2" "save");设置"F2"键为"save"命令
axlSetAlias( "F2" nil);取消"F2"当前定义的命令
axlSetAlias( "~S" nil);取消Ctrl+S当前定义的命令
```


axlGetAlias
axlGetFuncKey
axlGetVariable
axlGetVariableList
axlJournal
axlProtectAlias
axlIsProtectAlias
axlReadOnlyVariable
axlSetAlias
axlSetAlias
axlSetFunckey
axlSetVariable
axlSetVariableFile
axlShell
axlShellPost
axlUnsetVariable
axlUnsetVariableFile