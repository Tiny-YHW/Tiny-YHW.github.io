---
layout: post
title: Function and Program Structure
categories: Allegro Skill
date: 2023-07-04
permalink: allegro-skill-lisp-functions-and-Program-Structure
excerpt: Function and Program Structure。
---

## prog let 局部变量声明函数

SKILL 可以使用 prog 和 let来声明局部变量。但它们之间有区别，在程序中应选择合适的函数来声明。区别如下：

* let函数不能通过使用return返回一个值，而 prog 能够 使用 return 返回一个值，当使用prog声明局部变量时，当执行到return时，程序会返回 return的值，并跳出prog函数。
* 两个函数的返回值不一样。prog的返回值为return指定的值，当没使用return返回任何值时，将返回nil。而let始终返回函数中最后执行的值。
* let的运行速度要快于prog，当函数中不使用go或者return时，建议最好使用let

### prog

prog后的参数仅在Functions内部时有效，跳出时则不再生效

允许局部变量绑定并允许在控制跳转时突然退出。 这是一种语法形式。

prog 的第一个参数是在 prog 的上下文中声明为局部变量的列表。 除非遇到 go 或 return 等控制转移语句之一，否则 prog 后面的表达式将按顺序执行。 如果没有执行 return 语句，并且在执行最后一个表达式后控制只是“落入”prog，那么 prog 的计算结果为 nil。 如果在 prog 中执行 return，则 prog 立即返回并返回给 return 语句的参数值。

prog 中的任何语句前面都可以有一个符号作为语句的标签。 除非需要多个返回点或者您正在使用 go 函数，否则应该在 prog 上使用更快的绑定局部变量的构造 let 。

```lisp
x = "hello"

prog( (x y)                ; Declares local variables x and y.
    x = 5                  ; Initialize x to 5.
    y = 10                 ; Initialize y to 10.
    return( x + y )
);=> 15

x;=> "hello"                ; The global x keeps its original value.
```

### let - SKILL mode

为仅绑定局部变量的 prog 提供更快的替代方案。这是一种语法形式。

Let定义的变量仅在其程序局部有效，不影响也不继承外部或全局变量

```lisp
x = 5
let( ((x '(a b c)) y)
    println( y )               ; Prints nil.
    x)
=> (a b c)                     ; Returns the value of x.

procedure( test( x y )
    let( ((x 6) (z "return string"))
        if( (equal x y)
            then z 
            else nil)))
test( 8 6 )                    ; Call function test.
=> "return string"             ; z is returned because 6 == 6.

```

## return

强制封闭程序退出并返回给定值。 return 语句仅在 prog 语句中使用时才有意义。

go 和 return 都不是纯粹的功能，因为它们以非标准方式转移控制权。 也就是说，它们不会返回给调用者。

```lisp
procedure( summation(l)
    prog( (sum temp)
        sum = 0
        temp = l
        while( temp
            if( null(car(temp))
            then
                return(sum)
            else
                sum = sum + car(temp)
                temp = cdr(temp)
            )
        )
    )
) 
Returns the summation of previous numbers if a nil is encountered.

summation( '(1 2 3 nil 4)) 
=> 6                  ; 1+2+3
summation( '(1 2 3 4)) 
=> nil                ; prog returns nil if no explicit return)
```

addDefstructClass
alias
apply
argc
argv
begin
clearExitProcs
declareLambda
declareNLambda
declareSQNLambda
defdynamic
defglobalfun
define
define_syntax
defmacro
defsetf
defun
defUserInitProc
destructuringBind
dynamic
dynamicLet
err
error
errset
errsetstring
eval
evalstring
expandMacro
fboundp
flet
funcall
getd
getFnWriteProtect
getFunType
getVarWriteProtect
globalProc
isCallable
isMacro
labels
lambda
letrec
letseq
mprocedure
nlambda
nprocedure
procedure
procedurep
prog1
prog2
progn
putd
setf_dynamic
setFnWriteProtect
setVarWriteProtect
unalias
unwindProtect
warn