---
title: 'Cadence SKILL Language Reference <a rel="noreferrer noopener" href="https://a1024.synology.me:1024/?p=2143" target="_blank">skill语言函数</a>'
date: Thu, 11 Nov 2021 02:08:33 +0000
draft: false
tags: ['Allegro Skill']
---

Cadence® SKILL 是一种基于流行的人工智能语言 Lisp 的高级交互式编程语言。

[Cadence Skill List](https://a1024.synology.me:1024/?p=150)
-----------------------------------------------------------

[Cadence Skill 字串（Text）](https://a1024.synology.me:1024/?p=616)
---------------------------------------------------------------

[Cadence Skill 第五节 流程控制](https://a1024.synology.me:1024/?p=207)
---------------------------------------------------------------

[Allegro Skill对文件、文件夹操作、系统、环境命令](https://a1024.synology.me:1024/?p=2357)
------------------------------------------------------------------------

[Arithmetic （Trigonometric） Functions 算术（三角）函数](https://a1024.synology.me:1024/?p=3816)
---------------------------------------------------------------------------------------

局部变量声明函数
--------

SKILL 可以使用 prog 和 let来声明局部变量。但它们之间有区别，在程序中应选择合适的函数来声明。区别如下：

*   let函数不能通过使用return返回一个值，而 prog 能够 使用 return 返回一个值，当使用prog声明局部变量时，当执行到return时，程序会返回 return的值，并跳出prog函数。

*   两个函数的返回值不一样。prog的返回值为return指定的值，当没使用return返回任何值时，将返回nil。而let始终返回函数中最后执行的值。

*   let的运行速度要快于prog，当函数中不使用go或者return时，建议最好使用let

### prog

prog后的参数仅在Functions内部时有效，跳出时则不再生效

允许局部变量绑定并允许在控制跳转时突然退出。 这是一种语法形式。

prog 的第一个参数是在 prog 的上下文中声明为局部变量的列表。 除非遇到 go 或 return 等控制转移语句之一，否则 prog 后面的表达式将按顺序执行。 如果没有执行 return 语句，并且在执行最后一个表达式后控制只是“落入”prog，那么 prog 的计算结果为 nil。 如果在 prog 中执行 return，则 prog 立即返回并返回给 return 语句的参数值。

prog 中的任何语句前面都可以有一个符号作为语句的标签。 除非需要多个返回点或者您正在使用 go 函数，否则应该在 prog 上使用更快的绑定局部变量的构造 let 。

```
x = "hello"
=> "hello"
prog( (x y)                ; Declares local variables x and y.
    x = 5                  ; Initialize x to 5.
    y = 10                 ; Initialize y to 10.
    return( x + y )
)
=> 15
x
=> "hello"                ; The global x keeps its original value.
```

### let - SKILL mode

为仅绑定局部变量的 prog 提供更快的替代方案。这是一种语法形式。

Let定义的变量仅在其程序局部有效，不影响也不继承外部或全局变量

```
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

### return

强制封闭程序退出并返回给定值。 return 语句仅在 prog 语句中使用时才有意义。

go 和 return 都不是纯粹的功能，因为它们以非标准方式转移控制权。 也就是说，它们不会返回给调用者。

```
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

### makeTable

创建一个空的关联表

```
yTable = makeTable("atable1" 0)   => table:atable1
myTable[1]                         => 0
If you specify a default value when you create the table, the default value is returned if a nonexistent key is accessed.

myTable2 = makeTable("atable2")   => table:atable2
myTable2[1]                       => unbound
If you do not specify a default value when you create the table, the symbol unbound is returned if an undefined key is accessed.

myTable[1] = "blue"               => blue
myTable["two"] = '(r e d)         => (r e d)
myTable['three] = 'green          => green
You can refer to and set the contents of an association table with the standard syntax for accessing array elements.

myTable['three]                   => green
```

### defstruct

创建一个 defstruct，一个命名结构，它是一个或多个变量的集合。

Defstructs 可以具有不同类型的slots，这些 slots 组合在一个name下以进行处理。

defstruct 形式还创建了一个实例化function，名为 make\_<name>，其中 <name> 是提供给 defstruct 的结构体名称

defstruct 可以包含其他 defstruct 的instances；因此需要注意 defstruct 共享。如果不需要共享，可以使用特殊的复制功能来生成被插入 defstruct 的副本。 defstruct 形式还为给定的 defstruct 创建了一个名为 copy\_ <name> 的函数。这个函数接受一个参数，一个 defstruct 的实例。它创建并返回给定实例的副本。在其他 defstruct 函数的描述之后会出现一个示例。

```
defstruct(myStruct slot1 slot2 slot3) => t
struct = make_myStruct(?slot1 "one" ?slot2 "two" 
                       ?slot3 "three")
struct->slot1 => "one"
Returns the value associated with a slot of an instance.

struct->slot1 = "new" => "new"
Modifies the value associated with a slot of an instance.

struct->? => (slot3 slot2 slot1)
Returns a list of the slot names associated with an instance.

struct->?? => (slot3 "three" slot2 "two" slot1 "new")
Returns a property list (not a disembodied property list) containing the slot names and values associated with an instance.
```

### boundp

Skill中的变量可以不用提前声明。当程序在一段代码中遇到一个变量时，Skill 会自动创建该变量

当 SKILL 创建一个变量时，将会附一个 unbound 初值给变量表明该变量还未初始化。可使用 boundp 函数判断一个变量是否是 bound。boundp函数具有以下功能：

如果变量为 bound ，返回 t

如果不是 bound ，返回 nil

```
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

使用赋值操作符可以给变量赋一个值。我们可通过变量名获得变量的值。  
可通过使用 type 函数判断一个变量当前存储的数据类型。如下：

```
lineCount = 4 => 4
lineCount => 4
type( lineCount ) => fixnum
lineCount = "abc" => "abc"
lineCount => "abc"
type( lineCount ) => string
```

### sklint

检查 SKILL 文件并报告潜在错误和简化代码的方法。

```
sklint(?file "D:\\SPB_Data\\pcbenv\\ceshi.il")
```

### measureTime

测量计算表达式所需的时间并返回四个数字的列表。 这是一种语法形式。

第一个数字是用于进程的用户 CPU 时间量（以秒为单位）。

第二个数字是内核用于进程的 CPU 时间量。

第三个也是最重要的数字是计算表达式所花费的总时间，以秒为单位。

第四个数字是在计算表达式期间发生的页面错误数。

```
myList = nil            ; Initializes the variable myList.
measureTime( for( i 1 10000 myList = cons(i myList) ) )
=> (0.4 0.05 0.4465 0)
myList = nil            ; Initializes the variable myList.
measureTime( for( i 1 1000 myList = append1(myList i) ) )
=> (5.04 0.03 5.06 0)
```

### setof

```
setof(
s_formalVar
l_valueList
g_predicateExpression
)
=> l_result
setof(
s_formalVar
o_table
g_predicateExpression
)
=> l_result
```

setof函数可以将满足需要条件的元素过滤出来。返回值为过滤后的元素。

```
setof( x '(1 2 3 4) (x > 2) )    => (3 4)
setof( x '(1 2 3 4) (x < 3) )    => (1 2)
myTable = makeTable("atable" 0)  => table:atable
myTable["a"]="first"             => "first"
myTable["b"]=2                   => 2
setof(key myTable (and (stringp key)(stringp myTable[key])))
                                 => ("a") 
```

[addDefstructClass](chap1.html#1008271)

[alias](chap1.html#1008293)

[alphalessp](chap1.html#1008316)

[alphaNumCmp](chap1.html#1008336)

[and](chap1.html#1040726)

[apply](chap1.html#1008406)

[argc](chap1.html#1040774)

[argv](chap1.html#1040795)

[arrayp](chap1.html#1008428)

[arrayref](chap1.html#1008447)

[assoc, assq, assv](chap1.html#1008486)

[atom](chap1.html#1008570)

[band](chap1.html#1040847)

[bcdp](chap1.html#1008591)

[begin - SKILL mode](chap1.html#1008610)

[begin - SKILL++ mode](chap1.html#1008628)

[bitfield1](chap1.html#1040898)

[bitfield](chap1.html#1040934)

[blankstrp](chap1.html#1031722)

[bnand](chap1.html#1040970)

[bnor](chap1.html#1041016)

[bnot](chap1.html#1041057)

[booleanp](chap1.html#1031716)

[bor](chap1.html#1041097)

[bxnor](chap1.html#1041139)

[bxor](chap1.html#1041181)

[charToInt](chap1.html#1008849)

[clearExitProcs](chap1.html#1008867)

[compareTime](chap1.html#1008904)

[concat](chap1.html#1008946)

[cond](chap1.html#1008967)

[constar](chap1.html#1053425)

[copy](chap1.html#1009004)

[copy\_<name>](chap1.html#1009025)

[copyDefstructDeep](chap1.html#1009044)

[declare](chap1.html#1009131)

[declareLambda](chap1.html#1009165)

[declareNLambda](chap1.html#1009184)

[declareSQNLambda](chap1.html#1009202)

[define - SKILL++ mode](chap1.html#1009222)

[defmacro](chap1.html#1009254)

[defprop](chap1.html#1028057)

[defstructp](chap1.html#1009329)

[defun](chap1.html#1009350)

[defUserInitProc](chap1.html#1009381)

[defvar - SKILL mode only](chap1.html#1009400)

[do - SKILL++ mode only](chap1.html#1009493)

[dtpr](chap1.html#1009553)

[envobj](chap1.html#1009654)

[eq](chap1.html#1009675)

[equal](chap1.html#1009696)

[eqv](chap1.html#1009722)

[err](chap1.html#1009743)

[error](chap1.html#1009763)

[errset](chap1.html#1009787)

[errsetstring](chap1.html#1009809)

[eval](chap1.html#1009835)

[evalstring](chap1.html#1009861)

[exists](chap1.html#1028640)

[expandMacro](chap1.html#1009980)

[fboundp](chap1.html#1027923)

[funcall](chap1.html#1031891)

[funobj](chap1.html#1031148)

[gc](chap1.html#1010455)

[gensym](chap1.html#1048637)

[geqp](chap1.html#1041317)

[get](chap1.html#1010493)

[get\_pname](chap1.html#1010516)

[get\_string](chap1.html#1010534)

[getchar](chap1.html#1010573)

[getd](chap1.html#1010612)

[getFnWriteProtect](chap1.html#1010653)

[getFunType](chap1.html#1010673)

[getq](chap1.html#1032240)

[getqq](chap1.html#1010732)

[getSkillVersion](chap1.html#1010818)

[getVarWriteProtect - SKILL mode only](chap1.html#1010836)

[getVersion](chap1.html#1010856)

[getWarn](chap1.html#1165625)

[go](chap1.html#1010915)

[greaterp](chap1.html#1041381)

[help](chap1.html#1032013)

[if](chap1.html#1010935)

[importSkillVar - SKILL++ mode](chap1.html#1010963)

[index](chap1.html#1010983)

[inScheme](chap1.html#1011047)

[inSkill](chap1.html#1011067)

[integerp](chap1.html#1011105)

[intToChar](chap1.html#1011125)

[isCallable](chap1.html#1011144)

[isMacro](chap1.html#1011294)

[lambda](chap1.html#1011359)

[leqp](chap1.html#1041452)

[lessp](chap1.html#1041493)

[letrec - SKILL++ mode](chap1.html#1011487)

[letseq - SKILL++ mode](chap1.html#1011511)

[listp](chap1.html#1011597)

[make\_<name>](chap1.html#1011744)

[makeVector](chap1.html#1011809)

[mod](chap1.html#1012046)

[modf](chap1.html#1054212)

[mprocedure](chap1.html#1012088)

[nconc](chap1.html#1012113)

[ncons](chap1.html#1029619)

[needNCells](chap1.html#1012153)

[neq](chap1.html#1012194)

[nequal](chap1.html#1012215)

[nindex](chap1.html#1012254)

[nlambda - SKILL mode only](chap1.html#1012274)

[not](chap1.html#1012296)

[nprocedure - SKILL mode only](chap1.html#1012316)

[nthcdr](chap1.html#1012365)

[null](chap1.html#1012405)

[numberp](chap1.html#1012424)

[or](chap1.html#1041555)

[otherp](chap1.html#1012506)

[pairp](chap1.html#1012566)

[pcreCompile](chap1.html#1092526)

[pcreExecute](chap1.html#1012617)

[pcreGenCompileOptBits](chap1.html#1097128)

[pcreGenExecOptBits](chap1.html#1100712)

[pcreListCompileOptBits](chap1.html#1101340)

[pcreListExecOptBits](chap1.html#1101367)

[pcreMatchAssocList](chap1.html#1097154)

[pcreMatchList](chap1.html#1097922)

[pcreMatchp](chap1.html#1098810)

[pcrePrintLastMatchErr](chap1.html#1099253)

[pcreReplace](chap1.html#1099438)

[pcreSubstitute](chap1.html#1099917)

[plist](chap1.html#1099363)

[postdecrement](chap1.html#1041643)

[postincrement](chap1.html#1041683)

[predecrement](chap1.html#1041719)

[preincrement](chap1.html#1041759)

[procedure](chap1.html#1012805)

[procedurep](chap1.html#1012865)

[prog1](chap1.html#1012909)

[prog2](chap1.html#1012929)

[progn](chap1.html#1012950)

[putd](chap1.html#1012970)

[putprop](chap1.html#1012993)

[putpropq](chap1.html#1013014)

[putpropqq](chap1.html#1013035)

[quote](chap1.html#1041798)

[range](chap1.html#1041856)

[readstring](chap1.html#1013096)

[regExitAfter](chap1.html#1013166)

[regExitBefore](chap1.html#1013185)

[remd](chap1.html#1031856)

[remdq](chap1.html#1013246)

[remExitProc](chap1.html#1013266)

[remprop](chap1.html#1013313)

[remq](chap1.html#1013337)

[renameFile](chap1.html#1042471)

[rexExecute](chap1.html#1013479)

[rexMagic](chap1.html#1013500)

[rexMatchAssocList](chap1.html#1013518)

[rexSubstitute](chap1.html#1013605)

[rindex](chap1.html#1013624)

[rplaca](chap1.html#1013662)

[schemeTopLevelEnv](chap1.html#1013704)

[set](chap1.html#1013724)

[setarray](chap1.html#1013744)

[setcar](chap1.html#1013769)

[setcdr](chap1.html#1030319)

[setFnWriteProtect](chap1.html#1013813)

[setguard](chap1.html#1090990)

[setplist](chap1.html#1013859)

[setPrompts](chap1.html#1052176)

[setq](chap1.html#1013879)

[setqbitfield1](chap1.html#1041918)

[setqbitfield](chap1.html#1041961)

[setVarWriteProtect - SKILL mode only](chap1.html#1013952)

[sstatus](chap1.html#1101280)

[status](chap1.html#1014277)

[strcmp](chap1.html#1030491)

[stringp](chap1.html#1030516)

[stringToFunction](chap1.html#1014358)

[stringToSymbol](chap1.html#1014380)

[stringToTime](chap1.html#1014400)

[strncat](chap1.html#1014439)

[strncmp](chap1.html#1014459)

[subst](chap1.html#1014500)

[sxtd](chap1.html#1014545)

[symbolp](chap1.html#1014564)

[symbolToString](chap1.html#1014583)

[symeval](chap1.html#1014602)

[symstrp](chap1.html#1014623)

[tablep](chap1.html#1014661)

[tableToList](chap1.html#1014680)

[tailp](chap1.html#1014699)

[theEnvironment - SKILL++ mode only](chap1.html#1014759)

[timeToString](chap1.html#1014794)

[timeToTm](chap1.html#1014815)

[tmToTime](chap1.html#1014843)

[type, typep](chap1.html#1014892)

[unalias](chap1.html#1014912)

[vector](chap1.html#1014973)

[vectorp](chap1.html#1042040)

[vectorToList](chap1.html#1014992)

[warn](chap1.html#1027846)

[xcons](chap1.html#1015113)