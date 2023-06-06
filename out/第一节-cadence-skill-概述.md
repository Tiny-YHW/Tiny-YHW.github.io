---
title: 'Cadence Skill 第一节 概述'
date: Thu, 02 Apr 2020 03:42:16 +0000
draft: false
tags: ['Allegro Skill']
---

Cadence 提供二次开发的 SKILL 语言，它是一种基于通用人工智能语言 — LISP 的交互式高级编程语言。

Skill 语言是Cadence 公司自己开发的一种类似于leap 语言的编程语言。Cadence公司不仅开发了全套的Skill 语言语法，还开发了一个完整的Skill 语言的编译器。整个Cadence 软件都是基于Skill 语言的，所有的Cadence 的工具都是用Skill 语言编写的，甚至各种设置辅助文件都是遵从Skill 语言的语法。此外，Cadence 公司为其每个产品都提供Skill 语言访问函数，这使得用户可以通过Skill 语言访问Cadence 的产品。由于Skill 提供编程接口及与C 语言的接口，这使得Cadence可以在原有的基础上进行各种扩展，甚至允许用户开发自己的基于Cadence 平台的工具。因此学习一些基本的Skill 语言的知识及基本的编程技巧对于学习Cadence是大有益处的

skill语言亦支持更传统的类似C语言语法，这种支持允许一个新手用户能够快速学会使用系统，而专业程序员可以访问和Lisp编程语言一样的强大功能。简单地说，Skill像计算器一样易于使用；进一步来讲，一款功能强大的编程语言，它的应用几乎是无限的。

下文CIW窗口通过在Allegro Command窗口输入set telskill可以访问

最简单的Skill 编程方法是利用CIW 窗口中的命令解释行可以将其看为Skill语言的行编译器例如在其中输入

```
printf(“HI”);
```

再回车在CIW 的显示区就会出现HI 字符串。除了输入单行的Skill 命令外也可先用任一文本编辑器将一系列命令组成一个skill 文件，例如myskill.il ，然后  
利用load 命令将文件导入Skill 编译器具体方法为在CIW 命令解释行中输入load(“myskill.il”)。如果文件不在当前目录还需在文件名前加上路径。

SKILL通过命令行功能接口连接到底层的子系统。

SKILL让您快速，轻松地自定义现有的CAD应用程序 ，并帮助您开发新应用程序。

SKILL通过应用程序的功能来访问每个Cadence的工具编程接口。

Skill的功能，适用于所有Cadence工具，无论是在图形或非图形环境下。

****数据操作    ****
----------------

由于Skill程序和Lisp程序一样，是以lists（这里翻译为列表）形式表示，故它们可以像数据一样操作。您可以动态地创建，修改，或选择性地赋值函数定义和表达式。这种数据操作能力是选择Lisp成为人工智能应用语言主要原因之一。因为它充分利用了Lisp语言的“程序就是数据”的概念，所以SKILL可以用来编写灵活且强大的应用程序。

许多SKILL List（列表）操作函数都是可用的。这些功能操作，在大多数情况下，类似Lisp中的同名函数，尤其是弗兰兹的Lisp语支。

SKILL 提供一个特殊符号来创建模板列表。这个符号借鉴于Common List，并允许within a quoted form（在一个 引用表单里）选择性地赋值。选择性赋值消除长序列对 list 和 append 的调用。具体见第二章 Backquote（\`）----主键盘数字键那一行最左边一个或ESC下方那个带波浪线的键，直接按就是, Comma（,）---逗号, and Comma-At（@）。

不像许多其他的编程语言，包括Common Lisp，Skill没有独立的字符数据类型。字符通过单个字符符号来替代。例如，字符“A”，也是符号“A”。不可打印的字符可以使用转义序列表示。

注释
--

单行注释使用分号，分号后面的内容不被编译

多行注释见下面代码，被\*括起来的内容不被编译

```
;这是单行注释
/*
  这是
  多行注释
*/
```

语法风格（程序标识）
----------

由于 Skill 语言是基于 LISP ，因此它除了支持 函数表示法 同时也支持 前缀表示法 来编写代码。

在SKILL中，函数调用是可以写成下列符号的。

*   代数标识【大部分语言方式】，也就是 func（ARG1 ARG2… ）。
*   前缀标识【Lisp编程语言方式】，也就是（func ARG1 ARG2…）前缀符号。

函数表示法 类似 C，注意函数名和括号之间不能有空格。

```
func( arg1 arg2 )
```

前缀表示法 类似 Tcl

```
( func arg1 arg2 )
```

以上的两种表示法可以同时存在

命名风格
----

其次函数和变量的命名风格，Skill 中一般是使用 驼峰命名法 ( Camel-Case )，命名以小写开头，之后的每一个逻辑断点（单词）首字母大写，一般代表类别

驼峰命名法也是官方使用的命名方式，现在一些主流的编程语言也比较流行使用这种命名方式。

当然如何选择取决于你自己，下面是一个对比：

驼峰命名法

```
geGetEditCellView()
dbOpenCellViewByType(libName cellName viewName nil mode)
```

蛇形命名法（下划线）

```
ge_get_edit_cell_view()
db_open_cell_view_by_type(lib_name cell_name view_name nil mode)
```

真 / 假 (boolean)
---------------

Skill 中 真用 t 来表示，假用 nil 来表示。

其实参与判断中的值，除了 nil 和空链表以外都可以认为是真，例如：

```
when( t
  println( "True" )
)
; t 为真，打印 "True"

when( 10
  println( "True" )
)
; 10 为真，打印 "True"

when( "YEUNGCHIE"
  println( "True" )
)
; "YEUNGCHIE" 为真，打印 "True"

when( nil
  println( "True" )
)
; nil 为假，不运行 println 语句

when( 0
  println( "false" )
)
; 0 为假
```

数据类型
----

可以用函数 `type` 查看一个数据的类型标识。

```
type( 'YEUNGCHIE )          ; symbol
type( "YEUNGCHIE" )         ; string
type( list( "YEUNGCHIE" ))  ; list
```

用 `println` 打印一个数据的内容，同时也能够从打印结果观察到数据类型。

```
println( 'YEUNGCHIE )          ; YEUNGCHIE
println( "YEUNGCHIE" )         ; "YEUNGCHIE"
println( list( "YEUNGCHIE" ))  ; ( YEUNGCHIE )
```

字符串(string)
-----------

字符串用双引号括起来都是字符串，更多内容见[Cadence Skill 字串（Text）](https://a1024.synology.me:1024/?p=616)

数字(number)
----------

数字分为 整数 和 浮点数。

整数也可以直接编写成 二进制 ( `0b` 前缀 )、八进制 ( `0` 前缀 )、十六进制 ( `0x` 前缀 )，但默认会输出成 十进制

```
18
0b10010    ; 18
024        ; 20
0xFE       ; 254
```

浮点数浮点数也可以使用 科学计数法 和 单位后缀 来表示

```
3.14
1e-06    ; 0.000001
1u       ; 0.000001
```

数字的判断、算法等函数详见[Arithmetic （Trigonometric） Functions 算术（三角）函数](https://a1024.synology.me:1024/?p=3816)

链表 (list)
---------

下面这些都是List，关于list的等过处理详见[Cadence Skill List](https://a1024.synology.me:1024/?p=150)

```
list( arg1 arg2 list( arg3 arg4 ) ... )
'( "value1" sym1 (1 2) ... )
arg1 : arg2
```

符号 (symbol)
-----------

symbol 的写法是用一个单引号开头，例如：`'a`、`'b`、`'c`，这个类型比较抽象，刚接触知道有这么个东西就行，重点是需要用到的时候知道如何去使用。

symbol 实际上是一种指针，每个 symbol 都存在以下几个组成部分（slot）：

*   Print name ( name )
*   Value
*   Function binding
*   Property list

只有 name 是必要的，其他的部分都可以为空，当一个 **文本引用** 产生时，会创建一个 symbol ，且 Value 会默认为 `'unbound`。

这段话不知道怎么讲更好，贴一下原文：  
The system creates a symbol whenever it encounters a text reference to the symbol for the first time. When the system creates a new symbol, the value of the symbol is set to unbound.

当我们创建一个变量会自动生成与之对应的一个 symbol ，默认值为 `'unbound`，这个过程是非显式的。

这样，如果需要将一个变量设置为 未定义/未绑定 的状态，则可以将它赋值为 `'unbound`。

举个例子 ( 重点是这里 )：

*   给 arg 赋值为 12，然后打印出来。`arg = 12 println( arg ) ; 终端会打印 12`
*   给 arg 再赋值为 `'unbound`，然后尝试 print 一下。`arg = 'unbound println( arg ) ; 终端会提示 *Error* eval: unbound variable - arg`

当一个变量没有被定义过的时候，引用它但是不赋值时运行会报 **Error** ，但如果只是想判断某个变量是否被定义了，可以使用函数 `boundp` 去检测目标变量的 symbol name。

例如，检测一下变量 arg 是否被定义：

*   arg 已经被赋值为 `'unbound` 现在是未定义的状态。`boundp( 'arg ) ; 结果是 nil`
*   再给它赋值一个值。`arg = 1 boundp( 'arg ) ; 结果是 t`

判断一个函数是否存在的时候也需要利用到 symbol。

例如，判断一下函数 `dbCreateRect` 是否存在：

> dbCreateRect 是 Virtuoso 自带函数。

```
fboundp( 'dbCreateRect )
; 结果是 lambda:dbCreateRect
```

判断一下，函数 `QWE123` 是否存在：

```
fboundp( 'QWE123 )
; 不存在，结果是 nil 
```

对照表 / 哈希 `(table)`
------------------

Table 是 **key / value** 对的集合。类似于 Python 中的字典，但又更加强大，Python 字典的 key 只能是不可变数据类型，无法将列表、字典、对象等作为 key。

而在 Skill 中，Table 的 key 和 value 都可以是任意的数据类型：string、symbol、number、list、table、id 等都可以。

*   定义 `makeTable``HASH = makeTable( "Skill HASH" )`
*   赋值`HASH[ 1 ] = "ONE" HASH[ "2" ] = 2 HASH[ cvId ] = "cellName" HASH[ 'myName ] = "YEUNGCHIE"`
*   访问
    *   通过 key 查看`HASH[ 1 ] ; "ONE" HASH[ "2" ] ; 2`
    *   如果 key 是 symbol这时你还可以使用箭头符号 `~>` 来访问，非常舒服。`HASH~>myName ; "YEUNGCHIE"` 也可以使用函数 `get`，不过这个一般不用。`get( HASH "myName" ) ; "YEUNGCHIE"`
    *   查看一个哈希的所有 key / value`HASH~>? ; ( myName "2" 1 db:0x21cfda1a ) HASH~>?? ; ( myName "YEUNGCHIE" "2" 2 1 "ONE" db:0x21cfda1a "cellName" )`
    *   遍历一个哈希所有元素`foreach( key HASH printf( "key: %A , value: %A\n" key HASH[ key ] ) ) ; key: db:0x21cfda1a , value: "cellName" ; key: 1 , value: "ONE" ; key: "2" , value: 2`

数组 / 向量
-------

> 数组 和 向量 不常用，简单了解一下就行。

### 数组 `(array)` `(不常用)`

*   定义declare`declare( ARRAY[10] )`
*   赋值`ARRAY[2] = 4 ARRAY[3] = 5`
*   访问`println( ARRAY[2] * ARRAY[3] ) ; 20 println( ARRAY[0] ) ; unbound println( ARRAY[10] ) ; *Error* arrayref: array index out of bounds - ARRAY[10]`

### 向量 `(vector)` `(不常用)`

*   定义makeVector`VECTOR = makeVector( 10 )`
*   赋值`VECTOR[2] = 4 VECTOR[3] = 5`
*   访问`println( VECTOR[2] * VECTOR[3] ) ; 20 println( VECTOR[0] ) ; unbound println( VECTOR[10] ) ; *Error* arrayref: array index out of bounds - VECTOR[10]`

条件判断和循环控制
---------

[Cadence Skill 第五节 流程控制](https://a1024.synology.me:1024/?p=207)

定义子程序 `(函数)`
------------

*   子程序代码块以 `procedure` 函数来声明。
*   一个子程序由三个部分组成：名称、参数、代码块。
*   代码块中以最后一段语句的运算结果作为子程序的返回值。

下面举个例子：

```
procedure( myAdd( a b )
  a + b
); myAdd 
```

这个子程序用来实现输入变量 `a` 和 `b` ，返回 `a + b` 的值。

*   `myAdd` 就是子程序的名称。
*   `a` 和 `b` 是定义需要两个参数，这两个参数会作为子程序的局部变量，局部变量等会再细讲。
*   `a + b` 是代码块部分，仅有一行也作为最后一行，因此会返回两个变量相加之后的值。

下面看下如何调用这个 `myAdd`：

```
myAdd( 1 2 )
; 返回 3 
```

参数不是必须的，也可以提供一个空列表（括号里空着不写）作为参数的定义，意味着这个子程序不需要参数。

```
procedure( myAddOneAndTwo()
  3
); 这个子程序直接返回 3
myAddOneAndTwo()
; 3 
```

p

局部变量
----

### let

*   `let` 用来定义局部变量，定义变量的改动不会影响到代码块外的同名变量。
*   也是代码块中以最后一段语句的运算结果作为返回值。

用法：

```
a = 5
let(( a )
  a = 7
  println( a )
)
println( a ) 
```

返回的结果是：

```
7
5 
```

如果想给 `let` 中的变量赋值一个默认值，出了在开头写一个赋值语句，上面的 `let` 还可以这样简化：

```
let(( a( 7 ) )
  println( a )
) 
```

### prog

*   `prog` 相对于 `let` 增加了 `return` 和 `go` 函数的支持。
*   `prog` 的默认返回值是 `nil`

#### return

由于 `prog`默认的返回值是 `nil`，因此需要一个方法能够指定返回值是什么。而 `return` 就能够实现在一个 `prog` 中的任意位置跳出，并指定返回值。

示范一下：

```
prog(( a )
  a = 1
  when( a < 5
    return( t )
  )
  return() ; 当 return 不指定的返回值的时候等同于 return( nil )
) 
```

上面的程序由于 `a` 为 1 ，小于 5，因此执行 when 中的语句，跳出 prog 并返回 t 。

运用 `prog + return` 可以更加灵活的控制 `while` 、 `foreach` 等循环结构。

例如下面两段相似的代码中，`prog` 的位置不同对程序运行的影响：

*   满足条件提前跳出循环`a = 0 prog(( ) while( a <= 3 a++ when( a == 2 return()) print( a ) ); while ); prog` 当前 a == 2 时，跳出 `prog` ，由于 `prog` 在 `while` 循环外部，因此整个循环会结束。结果打印 `1` 。
*   满足条件直接运行下一个循环`a = 0 while( a <= 3 prog(( ) a++ when( a == 2 return()) print( a ) ); prog ); while` 当前 a == 2 时，跳出 `prog` ，由于 `prog` 在 `while` 循环内部，因此当前循环结束，不执行 `print` 直接进入下一次循环。结果打印 `134` 。

#### go

`go` 用来实现在一个 `prog` 内部，跳转到指定的 `标签`。

```
prog(( a )
  a = 0
  LABEL          ; 打个标签
  print( a++ )
  when( a <= 3
    go( LABEL )  ; 跳转到标签的位置
  )
); prog 
```

上面的例子实现一个循环，判断 `++a` 的值小于等于 3 时回到 `LABEL` 标记的位置重复运行，结果打印 `0123` 。

`go` 的使用存在一些限制，不能在多个 `prog` 之间跳转，不能往循环内跳转：

*   可以从循环内往循环外跳转
*   不能从循环外往循环内跳转
*   不能从循环内往循环内跳转（除非循坏内部再加一个 `prog`）

输入类型限制
------

上面我们已经定义了一个 `myAdd` 函数，由于执行的过程是做加法，因此它有一个隐含的要求是：输入的两个变量都必须是数字，否则运行会报错

can't handle

我们可以在子程序的定义中加入这个变量类型的判断：

```
procedure( myAdd( a b )
  unless( numberp( a ) && numberp( b )
    error("myAdd: Argument should be number.")
  )
  a + b
); myAdd 
```

运行上面的函数试试：

```
myAdd( "1" "2" )
; *Error* myAdd: Argument should be number. 
```

不过我们不需要这么麻烦去直接写每个参数的判断，Skill 已经提供了更简单的方法：

```
procedure( myAdd( a b "nn")
  a + b
); myAdd 
```

再运行上面的函数试试：

```
myAdd( "1" "2" )
; *Error* myAdd: argument #1 should be a number (type template = "nn") - "1" 
```

可以看到仅仅是在参数定义之后追加了 `"n"` 就可以起到效果，第一个 n 声明第一个参数需要为数字（number 缩写成 n），第二个 n 同理声明第二个参数。

不过这个写法还能简化：`... ( a b "n") ...` ，像这样只写一个 `n` 就代表所有的参数都必须为数字类型。

### 常见数据类型

下面举例一些常见的用于声明数据类型的缩写：

缩写

内部命名

数据类型

d

dbobject

id ， Cadence 数据对象

x

integer

整数

f

flonum

浮点数

n

number

整数 或者 浮点数

g

general

通用的 ， 任何数据类型

l

list

链表

p

port

I / O 句柄

t

string

字符串

s

symbol

symbol（符号）

S

stringSymbol

symbol 或者 字符串

u

function

函数对象 ， 函数名 或者 lambda 对象

...

...

...

可选的输入参数
-------

定义输入参数时候，可以使用一些 **修饰** 符号来做到类似 Getopt 的效果，常用的如下：

*   **@rest**定义 **不限数量** 的输入
*   **@optional**定义 **可有可无** 的输入，需要按顺序
*   **@key**定义 **可有可无** 的输入，需要指定参数名

> 注意 🍉：语法上 @optional 和 @key 不能同时使用，功能上 @rest 和 @optional 同时使用会存在矛盾。

### @rest

还是用上面的子程序 `myAdd` 来举例。

> 场景：现在这个程序，只能接受两个参数做加法，如果输入是 3 个或者更多怎么办？ 我不知道有多少个参数需要一次性输入。这时候就需要用到 @rest

优化一下 `myAdd`：

```
procedure( myAdd( @rest args ) ; 修饰符号写在被修饰参数的前面
  prog(( result )
    result = 0
    foreach( num args
      printf( "myAdd: %n + %n\n" result num )
      result += num
    )
    return( result )
  )
); myAdd 
```

运行一下：

```
myAdd( 1 2 3 )
; myAdd: 0 + 1
; myAdd: 1 + 2
; myAdd: 3 + 3
; => 6 
```

例子中只定义了一个输入参数，被声明 `@rest` 后，`args` 会变成一个 list 参与子程序内部运行，接着遍历所有元素加起来就行了。

### @optional

> 场景：`myAdd` 现在只能做加法，如果我想自定义运算类型，且要求不指定运算类型的时候默认做加法怎么办？这时候就需要用到 @optional

下面的例子为了避免矛盾，就不使用 `@rest` 了，将 `args` 用一个 list 来输入。

```
procedure( myCalc( args @optional opt("+") )  ; 参数后面的括号内写上默认值，也可以写成 ( opt "+" )
  prog(( result )
    result = car( args )
    args   = cdr( args )
    foreach( num args
      printf( "myCalc: %n %s %n ; " result opt num )
      case(opt
        ("+"  result += num )
        ("-"  result -= num )
        ("*"  result *= num )
        ("/"  result /= num )
      ); 按照不同的 opt 执行不同的操作
    )
    return( result )
  )
); myCalc 
```

运行一下：

```
myCalc( list( 1 2 3 ))
; myCalc: 1 + 2 ; myCalc: 3 + 3 ; 
; => 6

myCalc( list( 1 2 3 ) "-")
; myCalc: 1 - 2 ; myCalc: -1 - 3 ; 
; => -4

myCalc( list( 1 2 3 ) "*")
; myCalc: 1 * 2 ; myCalc: 2 * 3 ; 
; => 6

myCalc( list( 1.0 2 3 ) "/")
; myCalc: 1.000000 / 2 ; myCalc: 0.500000 / 3 ; 
; => 0.1666667 
```

### @key

> 场景：上面 @optional 的要求是输入的参数必须按顺序，即 先 `args` 后 `opt`，我不想固定这个顺序怎么办？这时候就需要用到 @key

使用格式：

*   定义`procedure( function( @key key1 key2 ) ... )` 不指定默认值的时候，默认值就是 nil
*   运行：`function( ?key1 arg1 ?key2 arg2 ... )`

在上面 `myCalc` 的基础上改一下：

```
procedure( myCalc( @key args opt("+") )
  ; prog ... 过程完全一致，这里就不写了
); myCalc 
```

运行一下：

1.  这里没有指定参数名称( keyword )，会报错

```
myCalc( list( 1 2 3 ) "+") 
```

\*Error\* myCalc: extra arguments or keyword missing - ((1 2 3) "+")

2.  正确用法

```
myCalc( ?args list( 1 2 3 ) ?opt "+")
; myCalc: 1 + 2 ; myCalc: 3 + 3 ; 
; => 6 
```

3.  输入参数不需要按顺序

```
myCalc( ?opt "+" ?args list( 1 2 3 ))
; myCalc: 1 + 2 ; myCalc: 3 + 3 ; 
; => 6 
```

匿名函数 `(lambda)`
---------------

匿名函数，顾名思义没有名字的函数，不同于 `procedure` 需要指定一个函数名，`lambda` 不需要指定一个函数名，它会返回一个 lambda 对象。

```
sum = lambda(( a b )
  a + b
) 
```

funcall
-------

上面已经定义了一个匿名函数，并将 lambda 对象赋值给了 `sum` 变量。 接下来就可以用 `funcall` 函数来使用它：

```
funcall( sum 1 2 )
; 3 
```

`funcall` 的第一个参数接收一个函数对象 `sum`，后面的参数依次作为输入。

apply
-----

如果待输入的变量保存在一个 list 中，也可以用 `apply` 函数来使用它：

```
apply( sum list( 1 2 ))
; 3 
```

可以看到，`apply` 的第一个参数接收一个函数对象 `sum`，第二个参数是一个 list ，list 中的元素依次对应 `sum` 需要接收的参数。

> 这里需要注意的是，并不是 `sum` 需要接收一个 list，而是 `apply` 接收一个 list，再把其中的元素依次作为 `sum` 的输入进行传参。`sum` 接收到的依然是两个参数。

此外 `funcall`、`apply` 不光可以接收 lambda，也可以接收一个 symbol 变量，前面讲到 symbol 存在一个 slot 是 **Function binding** ，因此也可以调用非匿名的子程序。

```
apply( 'plus list( 1 2 ))
; 3 
```

> 这里的 `'plus` 就作为 `plus` 函数的引用。

mapcar
------

`mapcar` 的效果其实也是循环，之所以放到 《子程序》 章节来讲，是因为使用这个函数需要先了解子程序是什么。

假设现在有一个 list：

```
numbers1 = list( 1 3 2 4 5 7 ) 
```

现在要将这个 list 中的每个元素都 `+1` ，用 `foreach` 可以这样做：

```
numbers2 = nil
foreach( x numbers1
  numbers2 = append1( numbers2 ++x )
)
println( numbers2 )
; ( 2 4 3 5 6 8 ) 
```

可以看到还是比较啰嗦的，换做 `mapcar` 就很方便了：

```
numbers3 = mapcar( 'add1 numbers1 )
; ( 2 4 3 5 6 8 ) 
```

也可以接受一个 `lambda` 匿名函数：

```
numbers4 = mapcar( lambda(( a ) a++ ) numbers1 )
; ( 2 4 3 5 6 8 ) 
```

另外前面讲到 `foreach` 的返回值是第一个 list，配合 `mapcar` 后可以将每次循环的结果作为返回值。

```
numbers5 = foreach( mapcar x numbers1
  x++
)
; ( 2 4 3 5 6 8 ) 
```