---
layout: post
title: List Functions List函数
categories: Allegro Skill
date: 2023-07-04
permalink: allegro-skill-lisp-list-functions
excerpt: List是Cadence SKILL中常用的数据类型。可以把List可以有多种类型的常量组成的列表。理解为一个数据结构表，它可以是空的，也可以有多种类型的常量组成的列表
---

List是Cadence SKILL中常用的数据类型。可以把List可以有多种类型的常量组成的列表。理解为一个数据结构表，它可以是空的，也可以有多种类型的常量组成的列表

List是SKILL数据对象的一个有序集合。list数据结构是SKILL的核心，可以以多种方式应用。

*   一个list的元素可以是任何数据类型，包括变量和其他list
*   一个list可以包含任何数字对象（或者空值）
*   空列表可以以"()"或者"nil"来表示
*   list必须括在括号中
*   Lists可以包含其他lists形成任意复杂的数据结构
*   下面是一些例子：

`(123)`：Alistcontainingtheintegerconstants1,2,and3包含整数1、2、3的一个列表

`(1)`：Alistcontainingthesingleelement1包含单个元素1的一个列表

`()`：Anemptylist(sameasthespecialatomnil)一个空列表（等同于nil）

`(1(23)4)`：Alistcontaininganotherlistasitssecondelement包含另一个列表作为其第二个元素的一个列表

**SampleLists**

SKILL显示一个括号围绕在列表成员两旁的列表。下面的例子将一个list赋值给一个变量shapeTypeList，然后从变量之中获取。

```
shapeTypeList = '( "rect" "polygon" "rect" "line" )
shapeTypeList => ( "rect" "polygon" "rect" "line" )
```

SKILL提供很多函数用来创建和操作list，许多SKILL函数返回list，SKILL可以使用多行来显示list。

SKILLinthe\_itemsperlineglobalvariable（在\_itemsperline全局变量中）存储合适的整型值


## 创建 List 数据

有几种主要方式可以用来创建一个list。

*   单引号操作符(')
*   list函数list()或者(list)

以下函数允许您构建新的list，并与现有的list以不同方式工作。

### list从给定元素制作list

```
'( 1 2 3 )    => ( 1 2 3 )
a = 1         => 1
b = 2         => 2
list( a b 3 ) => ( 1 2 3 )
```

```
aList = '( 1 2 a b c) => (1 2 a b c)
bList = list( 1 2 'a 'b 'd) => (1 2 a b d)
cList = '( 1 ( 2 a a ) b ) => (1 (2 a a) b)
```




*   cons函数给已存在的list增加一个元素
*   append函数合并两个list

cons和append函数将返回一个新的list。您应该将返回结果存储在一个变量中，否则后面没法引用list.



## 读取 List 元素

### car 获取 list 第一个元素

```
numbers = '( 1 2 3 )         => ( 1 2 3 )
car( numbers )               => 1
```

### cdr 获取除去第一个元素的list

```
numbers = '( 1 2 3 )         => ( 1 2 3 )
cdr( numbers )               => ( 2 3 )
```

### nth nthelem 按元素序号读取 List 中的元素

nth读取第一个元素为序号0，nth(0 numbers)相当于car( numbers).

`nthelem` 读取第一个元素为序号1，`nthelem(1l_list)` 相当于 `car(l_list)`.

```
numbers = '( 1 2 3 )         => ( 1 2 3 )
nth( 1 numbers )             => 2
```

```
nth( 1 '(a b c) )    => b
z = '(1 2 3)         => (1 2 3)
nth(2 z)             => 3
nth(3 z)             => nil
```

```
nthelem( 1 '(a b c) )  => a
z = '(1 2 3)
nthelem(2 z)           => 2
```

### last 读取 List 中最后一个元素

```
last( '(a b c) ) => (c)
z = '( 1 2 3 )
last( z ) => (3)
```

## 修改List

### rplaca 替换 List 中的第一个元素

```
aList = '( 1 2 3) => ( 1 2 3 )
bList = rplaca( aList 4 ) => ( 4 2 3 )
aList => ( 4 2 3 )
eq( aList bList ) => t
```

### rplacd 替换List中后面的List

从list的第二个元素到尾部的值替换为新的值。 此函数不会创建新列表； 它改变了输入列表。 与 setcdr 相同。

这是一个破坏性操作，这意味着对列表的任何其他引用也将看到更改。

```
x = '(a b c)
rplacd( x '(d e f))  => (a d e f)
x                    => (a d e f) 
```

### tconc、lconc 给 List 增加元素

创建一个list，其 car 指向正在构造的元素列表，其 cdr 指向正在构造的列表的最后一个列表单元。

在将新元素添加到列表末尾时，tconc 和 lconc 比 append 快得多。 append 函数要慢得多，因为它遍历并复制列表以到达末尾，而 tconc 和 lconc 只操作指针。

tconc 在序列后方添加元素，将新的序列放到前方

```
x = tconc(nil 1)        ; x is now ((1) 1)
tconc(x 2)              ; x is now ((1 2) 2)
tconc(x 3)              ; x is now ((1 2 3) 3)
x = car(x)              ; x is now (1 2 3)
```

```
x = tconc(nil 1)      ; x is initialized ((1) 1)
lconc(x '(2 3 4))     ; x is now ((1 2 3 4) 4)
lconc(x nil)          ; Nothing is added to x.
lconc(x '(5))         ; x is now ((1 2 3 4 5) 5)
x = car( x )          ; x is now (1 2 3 4 5)
```

```
components = axlDBGetDesign()->components
componentsnamelist = nil
    (foreach component components
        componentsnamelist = tconc(componentsnamelist component->name)
    )
componentsnamelist = car(componentsnamelist)
```

### cons 在list前面增加元素

增加的元素会成为新list的第一个元素。

```
result = '( 2 3 )             => ( 2 3 )
result = cons( 1 result )     => ( 1 2 3 )
```

cons函数的参数位置只能是往前面加不能往后面加，如果需要顺序使用 reverse 做反向

### append1 在List 后添加元素

```
append1('(1 2 3) 4) => (1 2 3 4)
```

### append nconc 合并 list

Append合并的一定为list，请注意。

```
oneList = '( 4 5 6 )             => ( 4 5 6 )
aList = '( 1 2 3 )               => ( 1 2 3 )
bList = append( oneList aList)   => ( 4 5 6 1 2 3 )
```

append函数只能合并两个List，并且不改变所合并List变量的值。

```
cList = '( 1 2 )
dList = '( 3 4 5 )
eList = '( 6 7 )
append( cList dList ) => ( 1 2 3 4 5 )
cList => ( 1 2 )
dList => ( 3 4 5 ) 
```

nconc函数可以合并多个List，但会改变所合并List 变量的值。

```
nconc( cList dList eList ) => ( 1 2 3 4 5 6 7 )
cList => ( 1 2 3 4 5 6 7 )
dList => ( 3 4 5 6 7 )
eList => ( 6 7 ) 
```

**cons与append之间的不同**

*   cons函数仅需要其第二个参数是list，返回list长度比原来的list长1；
*   append函数两个参数皆为list，返回长度是两个list长度之和。
*   Append的效率要低于cons（largelist情况下）

### 移除List元素remove

remove函数可以移除List 中所指定的元素，如果List 中没有所指定的元素，那么返回原List。remove 函数不会改变原List变量的值。

```
aList = '( 1 2 3 4 5 )
remove( 3 aList ) => ( 1 2 4 5 )
aList => ( 1 2 3 4 5 )
remove( '( 1 2 ) '( 1 ( 1 2 ) 3 )) => ( 1 3 )
```

### reverse list反向

```
reverse( '(1 2 3) )        => (3 2 1)
reverse( '(a b (c d) e) )  => '(e (c d) b a)
```

### unique list去重

```
a = list("1" "2" "1" "2" "3" "3" "4" "4" "4" "4" "5" "5")
b = unique(a) =>("1" "2" "3" "4" "5")
unique(list('abc 'aa 'ac 'aa)) =>(abc aa ac)
```

## 查询与统计

### 计算list长度(length) 元素个数

length函数确定list（列表）、array（数组）或者关联表的长度。

```
numbers = '( 1 2 3 )         => ( 1 2 3 )
length( numbers )            => 3
```

### xCoord yCoord 坐标

一个xy坐标是由两个元素的列表表示。冒号（:)二元运算符通过x值和y值生成坐标。

```
xValue = 300 
yValue = 400 
aCoordinate = xValue:yValue => ( 300 400 )
```

函数*xCoord*和*yCoord*访问 x坐标 和y坐标。

```
xCoord( aCoordinate ) => 300 
yCoord( aCoordinate ) => 400
```

可以使用单引号(')操作符或者*list*函数建立一个坐标list。

可以使用`car`函数访问x坐标和`car(cdr(...))`函数访问y坐标。



## 遍历

### forall判断List中所有的元素是否全部满足表达式

forall函数判断List中所有的元素是否全部满足表达式，全部满足返回t，不是就返回nil。

```
forall( x '(1 2 3 4) (x > 0) )=> t
forall( x '(1 2 3 4) (x < 4) )=> nil
forall( x '( 2 4 6 8 ) evenp( x ) ) => t
forall( x '( 2 4 7 8 ) evenp( x ) ) => nil
```

### foreach 遍历List 元素

foreach一次按list中的每一次元素给指定变量，并依次执行

```
foreach( x '(1 2 3 4) println(x))

1
2
3
4
=> (1 2 3 4)

foreach( (x y) '(1 2 3) '(4 5 6) (println x+y))

5
7
9
=> (1 2 3)
```

**mapc函数**

```
mapc( 'list '(1 2 3) '(9 8 7) ) => (1 2 3)
mapc( '(lambda (x y) (print (list x y))) '(1 2 3) '(9 8 7) )
(1 9) (2 8) (3 7)

=> (1 2 3)
```

ma**p 函数**

```
map( 'list '(1 2 3) '(9 8 7) )
=> (1 2 3)

map( '(lambda (x y) (print (append x y))) '(1 2 3) '(9 8 7) )
(1 2 3 9 8 7) (2 3 8 7) (3 7)
=> (1 2 3)
```

**mapcar 函数**

```
mapcar( 'plus '(1 2 3) '(9 8 7) )=> (10 10 10)
mapcar( 'list '(a b c) '(1 2 3) '(x y z) )=> ((a 1 x) (b 2 y) (c 3 z))
mapcar( 'lambda( (x) plus( x 1 )) '(2 4 6) )=> (3 5 7)
```

**maplist 函数**

```
maplist( 'length '(1 2 3) )
=> (3 2 1)

maplist( 'list '(a b c) '(1 2 3) )
=> (((a b c)(1 2 3))((b c)(2 3))((c)(3)))
```

**mapcan 函数**

```
mapcan( 'list '(1 2 3) '(a b c) )
=> (1 a 2 b 3 c)

mapcan( (lambda (n) (and (plusp n) (list n))) '(1 -2 3 -4 5))
=> (1 3 5)
```


## caar, caaar, caadr, cadr, caddr, cdar, cddr, ... BoundingBoxes（边界框）

Aboundingboxisrepresentedbyalistofthelower-leftandupper-rightcoordinates.

Usethe_list_functiontobuildaboundingboxthatcontainsCoordinatesspecifiedwiththebinaryoperator(:).

一个边界框由一个包含左下和右上坐标的list表示。使用list函数建立一个包含由二元操作符(:)指定的坐标的边界框。Coordinatesspecifiedbyvariables.（坐标通过变量指定）

```
bBox = list( 300:400 500:450 )
lowerLeft        = 300:400 
upperRight       = 500:450 
bBox             = list( lowerLeft upperRight )
```

如果坐标被已被逐个地以list方式指定，您可以使用单引号(')操作符建立一个边界框。

```
bBox = '(( 300 400 ) ( 500 450 ))
```

边界框是一个很好的范例相对于_car_和_cdr_函数。

Useanycombinationoffour_a_'s(each_a_executesanother_car_)or_d_'s(each_d_executesanother_cdr_).

### car

car(...)

lowerleftcorner 或 list的第一个元素

ll=car(bBox)

### cadr

car(cdr(...))

upperrightcorner 或 list的第二个元素

ur=cadr(bBox)

### caar

car(car(...))

x-coordof  
lowerleftcorner

llx=caar(bBox)

### cadar

car(cdr(car(...)))

y-coordof  
lowerleftcorner

lly=cadar(bBox)

### caadr

car(car(cdr(...)))

x-coordof  
upperrightcorner

urx=caadr(bBox)

### cadadr

car(cdr(car(cdr(...\]

y-coordof  
upperrightcorner

ury=cadadr(bBox)


## rexMatchList

创建给定列表中匹配正则表达式模式的那些字符串或符号的新列表。 提供的正则表达式模式会覆盖先前编译的模式，并用于后续匹配，直到提供下一个新模式。

```
rexMatchList("^[a-z][0-9]*" '(a01 x02 "003" aa01 "abc"))
=> (a01 x02 aa01 "abc")
rexMatchList("^[a-z][0-9][0-9]*" 
    '(a001 b002 "003" aa01 "abc"))
=> (a001 b002)
rexMatchList("box[0-9]*" '(square circle "cell9" "123"))
=> nil
```


### sort sortcar list排序

sort的书写格式为：sort(l\_data u\_comparefn)，其中第一个变量l\_data为List量变量，第二个变u\_comparefn为对比函数。对比函数也可以是自定义函数。

```
y = '(c a d b)
(sort y nil)        => (a b c d)
y                   => (c d)  ;no longer points to head of list
y = '(c a d b)
y = (sort y nil)    => (a b c d)
y => (a b c d)                ;reassignment points y to sorted list.
```

```
y = '(2 4 1 3)
y = sort(y 'lessp) => (1 2 3 4)
y = sort(y 'greaterp) => (4 3 2 1)
y = sort(y 'alphalessp) => error
```

```
sort( '(4 3 2 1) 'lessp ) => (1 2 3 4)
sort( '(d b c a) 'alphalessp) => (a b c d)
sort('("U5" "U10" "U1" "U5" "U2") 'axlStrcmpAlpNum)
=> ("U1" "U2" "U5" "U5" "U10")
```

当List元素都是由List组成的时候，还可以使用sortcar函数对比子List的第一个元素排序

```
sortcar( '((4 four) (3 three) (2 two)) 'lessp )=> ((2 two) (3 three) (4 four)
sortcar( '((d 4) (b 2) (c 3) (a 1)) nil )=> ((a 1) (b 2) (c 3) (d 4))
```

### member assoc查找list

确定一个数member 函数从List 到返回第一个元素查找到最后，如果找到返回找到的元素开始直到最后的元素，找不返回nil。

member 函数不能搜索所有分级的list，只能查找顶层元素。将查找到的元素及其右分支的所有元素输出

```
numbers = '( 1 2 3 )         => ( 1 2 3 )
member( 4 numbers )          => nil    说明Member第一个参数不能超过第二个参数list的长度
member( 2 numbers )          => ( 2 3 )
```

```
x = "c"                          => "c"
member( x '("a" "b" "c" "d"))    => ("c" "d")
memq('c '(a b c d c d))          => (c d c d)
memq( concat( x ) '(a b c d ))   => (c d)
memv( 1.5 '(a 1.0 1.5 "1.5"))    => (1.5 "1.5")
```

assoc函数的书写格式为：assoc(g\_key l\_alist)，g\_key变量为所查找的关键值，l\_alist是为一个由多个List组成的List，格式为：((key1 value1) (key2 value2) (key3 alue3) ...)。

assco返回查找到的子List。

```
aList = '(( 1 "one" )( 2 "two" )( 3 "three" ))
assoc( 2 aList ) => ( 2 "two" )
assoc( 5 aList ) => nil
```

### setof 过滤满足条件的 List 元素

按条件过滤List 元素(setof)

setof函数的书写格式为：setof( s\_formalVar l\_valueList g\_predicateExpression )

*   s\_formalVar变量为局部变量，作用于g\_predicateExpression 表达式中
*   \_valueList 变量为要过滤的List变量
*   g\_predicateExpression变量为自定义表达式

setof函数会把l\_valueList历赋值给变量中的所有元素，遍s\_formalVar局部变量，带入到g\_predicateExpression表达式中，如果表达式返回的值为nil输出的新，在List中会将其元素过滤。

```
setof( x '(1 2 3 4) (x > 2) ) => (3 4)
setof( x '(1 2 3 4) (x < 3) ) => (1 2)
setof( x '( 1 2 3 4 5 6 ) oddp(x)) => ( 1 3 5 )
```

```
obj = list(xxx)
objt = setof(x obj1 x->layer == "REF DES/SILKSCREEN_TOP")
```

### exists 查找第一个满足条件的元素

exists 函数和setof 函数区别在于exists 函数查找List 满足条件的第一个元素，输出它和它之后的元素

```
exists( x '(1 2 3 4) (x > 2) ) => (3 4)
exists( x '(4 3 4 5) (x < 4) ) => (3 4 5)
exists( x '(1 2 3 4) (x > 4) ) => nil
```


### List转向量（数组）

```
V = listToVector( '( 1 2 3 ) ) => array[3]:1954920
V[0] => 1
V[1] => 2
V[2] => 3
V[3]
*Error* arrayref: array index out of bounds - V[3]
```



## 常见问答

### nil和'(nil)的区别

nil是一个空list，长度为0；'(nil)是一个包含一个空list(作为元素)的list,，长度为1


constar
copy
dtpr
lindex
listp
ncons
nthcdr
pairp
range
remd
remdq
removeListDuplicates
remq
setcar
setcdr
tailp
xcons