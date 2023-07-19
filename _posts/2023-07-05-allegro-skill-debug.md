---
layout: post
title: Allegro Skill调试常用函数
categories: Allegro Skill
date: 2023-07-05
permalink: allegro-skill-debug
excerpt: Skill调试常用函数
---

## 调用调试窗口

```lisp
axlShell("set telskill")
```

## 注册命令

```lisp
axlCmdRegister("pinconnect" 'pinconnect ?cmdType "interactive" ?doneCmd 'pinconnectDone ?cancelCmd 'pinconnectCancel) 
```

## 调用Command命令

```lisp
axlShell("slide")
```

## 信息输出

```lisp
;直接数据文本
axlMsgPut("debug")
;带变量
axlMsgPut("Processing: %s " txt->text)
axlMsgPut("Processing: %N " txt);按照原有类型输出（字符串会带引号）
;带多个变量
axlMsgPut("%s %s %d %d %d %d" item->name item2 length(setof(temp1 item->children temp1->layer == item2)) numseg numpath temp1)
```

## 窗口显示

```lisp
;在主窗口显示一条信息
axlUIWPrint(r_window/nil t_formatString [g_arg1 ...])
axlUIWPrint(nil "Command Finished.")
axlUIWPrint => axlUIWPrint(userDefinedForm "this is a pretty form"); 输出字符到form的最下面窗口 
```

## 弹出确认框

```lisp
axlUIConfirm(t_message[s_level])
axlUIConfirm( "Returning to Allegro. Please confirm." )
axlUIConfirm( "Selected object has FIXED property." 'error )
```

相似函数axlUIPrompt, axlUIYesNo, axlUIYesNoCancel, axlUIConfirmEx

## 读取元素

### 第一个元素

```lisp
db1 = car(db)
```

### 第n个元素

```lisp
nth( 1 '(a b c) )    => b
z = '(1 2 3)         => (1 2 3)
nth(2 z)             => 3
nth(3 z)             => nil

nthelem( 1 '(a b c) )  => a
z = '(1 2 3)
nthelem(2 z)           => 2

db1=nthelem(1 db)
db2=nthelem(2 db)
infor1=db1->??
infor2=db2->??
axlMsgPut("%L\n" infor1)
axlMsgPut("%L\n" infor2)
```


### 输出每个元素的详细属性

```lisp
(foreach item db
    t
    axlMsgPut("%L\n" item->??)
)
```

## 对象和属性


[Database Read Functions](https://a1024.synology.me:1024/?p=2942)

## 未定义变量


boundp 函数判断一个变量是否是 bound。boundp函数具有以下功能：

如果变量为 bound ，返回 t

如果不是 bound ，返回 nil

```lisp
x = 5                ; Binds x to the value 5.
y = 'unbound         ; Unbind y
boundp( 'x )
=> t
boundp( 'y )
=> nil
y = 'x               ; Bind y to the constant x.
boundp( y )
=> t                 ; Returns t because y evaluates to x, 
                     ; which is bound.
```