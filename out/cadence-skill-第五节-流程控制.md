---
title: 'Cadence Skill 第五节 流程控制 条件判断和循环控制'
date: Thu, 09 Apr 2020 01:03:49 +0000
draft: false
tags: ['Allegro Skill']
---

这部分介绍：

*   Relational Operators: <, <=, >, >=, ==, !=  关系运算符
*   Logical Operators: !, &&, ||      逻辑运算符
*   Branching: if, when, unless      条件（分支）运算符
*   Multi-way Branching: case        多路分支运算符
*   Iteration: for, foreach              循环（迭代）

Iteration refers to repeatedly executing a collection of SKILL expressions by changing - usually incrementing or decrementing - the value of one or more loop variables.    

循环涉及重复执行一个SKILL语句集---通过一个活多个递增或递减的循环变量。

赋值运算
----

直接赋值

```
a=1
setq( a 1 )
```

自增1，自减1

```
++a
add1( a )
a++
postincrement( a )

--a
sub1( a )
a--
postdecrement( a )
```

*   假设 a = 1
*   `++a` 会将 a 加一后的值返回，返回值是 2
*   `a++` 会先返回 a 的值后加一，返回值是 1
*   `add1( a )` 会返回 2，但不改变 a 的值
*   `postincrement( a )` 会返回 1，a 的值会加一变成 2
*   自减同理

比较运算
----

相等，不相等

```
a == b
equal( a b )

a != b
nequal( a b )
```

大小比较

```
a < b
lessp( a b )

a <= b
leqp( a b )

a > b
greaterp( a b )

a >= b
geqp( a b )
```

几乎相等

```
nearlyEqual( a b )
```

关系运算符
-----

Use the following operators to compare data values. SKILL generates an error if the data types are inappropriate. These operators all return _t_ or _nil_.

使用下面的操作符来比较数据值。如果数据类型不恰当，SKILL会生成一个错误。这些操作符都返回 t  或者 nil

It is helpful to know the function name because error messages mention the function (_greaterp_ below) instead of the operator ( > ).

知道函数名是非常有用的，因为错误信息涉及函数名（_greaterp _）代替操作符（>）

```
1 > "abc" Message: *Error* greaterp: can't handle (1 > "abc")
```

逻辑运算符
-----

SKILL considers _nil_ as FALSE and any other value as TRUE. The and (&&) and or (||) operators only evaluate their second argument if they need to determine the return result.

SKILL指定 nil 作为 FLASE ，其他值为 TRUE。 与（&&）和或（||）操作符如果需要确定返回结果，仅需评估其第二个参数。

### && and 与

```
a && b
and( a b )

3 && 5 => 5
5 && 3 => 3
t && nil => nil
nil && t => nil
```

### || or 或

```
a || b
or( a b )
3 || 5 => 3
5 || 3 => 5
t || nil => t
nil || t => t
```

### ! not 非

```
!a
not(a)

!t => nil
nil => t
```

The && and || operators return the value last computed. Consequently, both && and || operators can be used to avoid cumbersome _if_ or _when_ expressions.

与（&&）和或（||）操作符返回最后计算的值，所以与和或操作符可以用来避免繁琐的if 或者when表达式

IF函数
----

Use the _if_ function to selectively evaluate two groups of one or more expressions. The condition in an _if_ expression evaluates to _nil_ or non-_nil_. The return value of the _if_ expression is the value last computed.

使用IF函数来选择性地评估两组中的一或多个表达式。一个if表达式中的条件判断为nil （假）或 非nil（真）。if表达式的返回值为最后计算的值。

```
if( shapeType == "rect"   then 
println( "Shape is a rectangle" ) 
++rectCount 
else 
println( "Shape is not a rectangle" ) 
++miscCount 
)

if( a > b
then
  c = 1
  println( "Yes" )
else
  c = 0
  println( "No"  )
)
```

Skill 不能用 `if-elsif-else` 这种简化的写法，但是逻辑是一样的，后级的 `if` 需要在上一级的 `else`中。

```
if( a > b then
  println( "Yes" )
 else
  if( a > c then
    println( "Yes" )

    else
    println( "No"  )
  )
)
```

这还有一个问题，当需要判断多个条件的时候 `if` 的写法就太不好看了，这时就可以使用 `case` 或者 `cond`

SKILL does most of its error checking during execution. Error messages involving _if_ expressions can be obscure. Be sure to

SKILL在执行期间，做大部分的错误检查。错误信息表明if表达式可能是模糊的。确定：

Be aware of the placement of the parentheses: _if( ... then ... else ... )_.注意圆括号的放置

Avoid white space immediately after the _if_ keyword. if关键字后避免空格 

Use _then_ and _else_ when appropriate to your logic.  使用 then 和 else 来符合您的逻辑

Consider the error message when you accidentally put white space after the _if_ keyword.如果if关键字后不小心输入空格将产生错误信息

```
shapeType = "rect" 
if ( shapeType == "rect"       then             
println( "Shape is a rectangle" )             
++rectCount       
else             
println( "Shape is not a rectangle" )             
++miscCount 
) Message: *Error* if: too few arguments (at least 2 expected, 1 given)... 
```

Consider the error message when you accidentally drop the _then_ keyword, but include an _else_ keyword, and the condition returns _nil_.

如果您不小心丢掉 then 关键字但包含else关键字，将产生错误信息，且条件将返回 nil

```
shapeType = "label" 
if( shapeType == "rect"             
println( "Shape is a rectangle" )             
++rectCount       
else             
println( "Shape is not a rectangle" )             
++miscCount       
) Message: *Error* if: too many arguments ...
```

when 和 unless 函数
----------------

when 当判断条件为 t 时，进行对应语句

```
when( shapeType == "rect"             
println( "Shape is a rectangle" )            
 ++rectCount 
 ) ; when 
when( shapeType == "ellipse" 
println( "Shape is an ellipse" ) 
++ellipseCount
) ; when

when( a > b
  println( "Yes" )
)
```

unless 当判断条件为nil时，进行对应语句

```
unless( shapeType == "rect" || shapeType == "line" 
println( "Shape is miscellaneous" ) 
++miscCount 
) ; unless

unless( a > b
  println( "No" )
)
``````
x = -123
unless( x >= 0 println("x is negative") -x)
=> 123            ;Prints "x is negative" as side effect.
unless( x < 0 println("x is positive") x)
=> nil
```

The _when _and _unless_ functions both return the last value evaluated within their body or _nil_.

when和unless函数都返回其体内运算的最后的值 或者 nil.

While
-----

对满足条件的值持续执行，指导条件不被满足时调出循环向下执行

```
i = 0  
while( (i <= 10) printf("%d\\n" i++) )   
\=> t
```

case 函数 caseq
-------------

The _case_ function offers branching based on a numeric or string value.

case函数基于一个数值的或字符串的值提供分支。

`case`/`cond` 可以用来优化多条件下的 `if` 

```
case( shapeType
("rect"
++rectCount
println( "Shape is a rectangle" )
)
( "line"
++lineCount
println( "Shape is a line" )
) 
( "label"
++labelCount
println( "Shape is a label" )
) 
(t
++miscCount
println( "Shape is miscellaneous" )
)
) ; case

case( arg
    ( "a"
        println( "It is a" )
    )
    (( "b" "c" )
        println( "It is b or c" )
    )
    ( "d"
        println( "It is d" )
    )
    ( t
        println( "Unmatch" )
    )
)
```

The optional value _t_ acts as a catch-all and should be handled last. The _case_ function returns the value of the last expression evaluated. In this example:

可选的t 充当所有其他的条件，应该被最后处理。case函数返回最后赋值表达式的值。在这个例子里： 

The value of the variable _shapeType_ is compared against the values _rect_, _line_, and _label. _If SKILL finds a match, the several expressions in that arm are evaluated. 

变量_shapeType_的值跟值_rect_, _line_, and _label_比较，SKILL发现匹配的值，执行匹配分支的表达式。

If no match is found, the final arm is evaluated. 如果没有匹配的，最后的分支被执行。

When an arm's target value is actually a list, SKILL searches the list for the candidate value. If SKILL finds the candidate value, all the expressions in the arm are evaluated.

当一个手臂的目标值实际上是一个列表，技巧搜索列表中的候选值。如果SKILL发现候选值，在分支上所有表达式被执行。

```
nameofmonth = "February"
month = case( nameofmonth
                ("January" 1)
                ("February" 2)
                (t 'Other))
=> 2
procedure( testCase( selector )
    caseq(selector 
        (0 println("selector is 0"))
        (1 println("selector is 1"))
        ((2 3) println("selector is either 2 or 3"))
        ((a b) println("selector is either the symbol a or b"))
        (t println("selector is none of the above"))
))
testCase( 1 )
=> testCase
"selector is 1"                      ; Printed by caseq statement.
=> nil                               ; Value returned by println.
testCase( 'b )
"selector is either the symbol a or b" ; Printed by caseq.
=> nil                                 ; Value returned by println.
```

cond
----

`case` 的使用情景比较单一，当条件多且判断的对象或者逻辑不唯一的时候可以 `cond`。

例如，现在需要对变量 a 做几个判断：

*   当 a > b 时，打印 "Bigger than b"；
*   否则当 a > c 时，打印 "Bigger than c"；
*   都不成立时，打印 "Smallest"。

```
cond(
    ( a > b
        println( "Bigger than b" )
    )
    ( a > c
        println( "Bigger than c" )
    )
    ( t
        println( "Smallest" )
    )
)
```

for 函数
------

指定一个起始整数（initial）和终止整数（final），依次遍历从 initial 到 final 组成的 list 的每一个元素，间隔为 1。

The index in a _for_ expression is saved before the _for_ loop and is restored to its saved value after the _for_ loop is exited. SKILL does most of its error checking during execution. Error messages involving _for_ expressions can be obscure. Be sure to

for循环表达式的索引在for循环之前被存储且在for循环结束后返回一个已保存的值。SKILL在执行期间，做大部分的错误检查。错误信息表明for表达式可能是模糊的。确定：

*   Be aware of the placement of the parentheses: _for( ... )_. 注意圆括号的放置
*   Avoid white space immediately after the _for_ keyword. 避免for关键字后存在空格

The example below adds the integers from one to five to an intermediate _sum_. _i_ is a variable used as a counter for the loop and as the value to add to _sum_. Counting begins with one and ends with the completion of the fifth loop. _i_ increases by one for each iteration through the loop.

下面的例子将整数从1加到5相加，结果存入中间变量sum。 i是循环一个计数器，同时其值被加到sum这个变量。计数从1到5. i每循环一次增加1

```
for( i 1 5
      sum = sum + i
      println( sum )
      )
=> t
```

SKILL prints the value of _sum_ with a carriage return for each pass through the loop:

```
1 3 6 10 15
```

    The _for_ function always returns _t_. for 循环总返回 t

foreach函数
---------

指定一个 list ，依此遍历每一个元素。

```
foreach( x list( 0 1 2 )
    println( x )
)

foreach(( x y z ) list( 0 1 2 ) list( 3 4 5 ) list( 6 7 8 )
    printf( "%d %d %d\n" x y z )
)
```

The _foreach_ function is very useful for performing operations on each element in a list. Use the _foreach_ function to evaluate one or more expressions for each element of a list of values.

foreach函数对于操作list中放入每个元素是非常有用的。 使用foreach函数计算一个活多个表达式来获得list中每个元素的值。

```
rectCount = lineCount = polygonCount = 0
shapeTypeList = '( "rect" "polygon" "rect" "line" )
foreach( shapeType shapeTypeList
case( shapeType
( "rect"             ++rectCount )
( "line"             ++lineCount )
( "polygon"          ++polygonCount )
( t                  ++miscCount )
);case
);foreach
=> ( "rect" "polygon" "rect" "line" )
```

When evaluating a _foreach_ expression, SKILL determines the list of values and repeatedly assigns successive elements to the index variable, evaluating each expression in the _foreach_ body. The _foreach_ expression returns the list of values over which it iterates.

当执行一个foreach表达式，SKILL确定列表的值，在foreach循环内，重复将连续的元素赋值给索引变量。foreach返回循环的list

In the example: 在这个例子中：

The variable _shapeType_ is the index variable. Before entering the _foreach_ loop, SKILL saves the current value of _shapeType_. SKILL restores the saved value after completing the _foreach_ loop.

变量_shapeType_是索引变量，在输入foreach前，SKILL保存_shapeType的_当前值，在完成循环后则返回保存后的值

The variable _shapeTypeList_ contains the list of values. SKILL successively assigns the values in _shapeTypeList_ to _shapeType_, evaluating the body of the _foreach_ loop once for each separate value. 

变量_shapeTypeList_是包含一些值的list。SKILL连续将赋_shapeTypeList_值给_shapeType_，每个单独的值都将做一次循环

The body of the _foreach_ loop is a single case expression. 

foreach循环体是一个单一条件的表达式

The return value of the _foreach_ loop is the list contained in variable _shapeTypeList_. 

foreach循环的返回值是一个包含在变量_shapeTypeList_的list

If you have executed the example above, you can examine the effect of the iterations by typing the name of the counter:

如果您已执行上面的例子，你可以通过输入计数器的名称检查循环的效果

```
rectCount        => 2
lineCount        => 1
polygonCount     => 1
```

while
-----

指定一个条件，当条件为真时才会运行，当条件为假时跳出 while 循环。

下面用 `while` 打印从 0 到 2：

```
a = 0
while( a < 3
    println( a )
    a++
)
```