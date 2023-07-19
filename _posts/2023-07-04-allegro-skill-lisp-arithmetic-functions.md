---
layout: post
title: Arithmetic （Trigonometric） Functions 算术（三角）函数
categories: Allegro Skill
date: 2023-07-04
permalink: allegro-skill-lisp-arithmetic-functions
excerpt: 数学运算功能函数
---


![](https://a1024.synology.me:222/images/blog2023/suanshuyunxuan.png)


## 基本算法

### abs 取绝对值

`(abs number) => n_result`

*number：* 任意数字。

*n_result：* 参数的绝对值。


```lisp
(abs 100) returns 100
(abs -100) returns 100
(abs -99.25) returns 99.25
abs( -209.625)=> 209.625

abs( -23)=> 23
```

### plus，xplus ，+ 加法

xplus 是一个纯整数算术函数，而 plus 可以处理整数和浮点数。 xplus 在整数算术计算中运行速度比 plus 稍快。

```lisp
plus(5 4 3 2 1) => 15
plus(-12 -13)   => -25
plus(12.2 13.3) => 25.5

xplus(12 13)   => 25
xplus(-12 -13) => -25

3+4 => 7
```

### difference，xdifference，- 减法

xdifference 是一个纯整数算术函数，而 difference 可以处理整数和浮点数。 xdifference 在整数算术计算中的运行速度略快于 difference。

```lisp
difference(5 4 3 2 1) => -5
difference(-12 13)    => -25
difference(12.2 -13)  => 25.2

xdifference(12 13)  => -1
xdifference(-12 13) => -25

12-13  => -1
```

### times，xtimes ，\* 乘法

xtimes 是一个纯整数算术函数，而 times 可以处理整数和浮点数。 xtimes 在整数算术计算中运行速度比 times 稍快。

```lisp
times(5 4 3 2 1)  => 120
times(-12 -13)    => 156
times(12.2 -13.3) => -162.26

xtimes(12 13)   => 156
xtimes(-12 -13) => 156

12*13   => 156
```

### quotient，xquotient , / 除法

xquotient 是一个纯整数算术函数，而 quotient 可以处理整数和浮点数。 在整数算术计算中，xquotient 比 quotient 运行得稍快。

```lisp
quotient(5 4 3 2 1) => 0
quotient(-10 -2)    => 5
quotient(10.8 -2.2) => -4.909091

xquotient(10 2)   => 5
xquotient(-10 -2) => 5

10/2   => 5
```

### modulo，remainder 余数

```lisp
modulo( 13 4)         => 1
remainder( 13 4)      => 1

modulo( -13 4)        => 3
remainder( -13 4)     => -1

modulo( 13 -4)        => -3
remainder( 13 -4)     => 1

modulo( -13 -4)       => -1
remainder( -13 -4)    => -1
```

### sqrt 开方

```lisp
sqrt( 49 )=> 7.0
sqrt( 43942 )=> 209.6235
```

### expt 数值乘方（次方）运算

```lisp
expt(2 3)   => 8
expt(-2 3)  => -8
expt(3.3 2) => 10.89
2**3   => 8
```

### max 最大值 min 最小值

```lisp
max(6)       => 6
max(3 2 1)       => 3
max(-3 -2 -1)    => -1

min(3)        => 3
min(1 2 3)        => 1
min(-1 -2.0 -3)   => -3.0
```

### minus 数值取反

```lisp
minus( 10 )   => -10
minus( -1.0 ) => 1.0
minus( -0 )   => 0
```

### exp 自然常数e的多次方

```lisp
exp( 1 )  => 2.718282
exp( 3.0) => 20.08554
```

### add1，sub1 数值加1，减1

```lisp
add1( 59 )=> 60

sub1( 59 )=> 58
```

## 转换

### atof atoi 文本转数字

将一个字符串转换成数字

atof浮点型包含小数，atoi只取整数部分

```
atof( t_string [t]) => f_result / nil
```

*t_string：* 要转化为实数的字符串

*[t]：*如果*t_string：*包含非数字字符，则强制返回*nil*

*f_result：*浮点字符对应的浮点数值

*nil：t_string：*包含非数字字符则强制返回*nil*

```lisp
atof("123")              => 123.0
atof("abc")              => nil
atof("123.456")          => 123.456
atof("123abc")           => 123.0

atoi("123")      => 123
atoi("abc")      => nil
atoi("123.456")  => 123
atoi("123abc")   => 123
```

### float

整型数转换为浮点数

```lisp
float(3)    => 3.0
float(1.2)  => 1.2
```

## 舍入


### ceiling 向上取整

```lisp
(ceiling -4.3)  => -4
(ceiling 3.5)   => 4
```

### int 向下（舍）取整

```lisp
int(2.7)=>2

int(.7)=>0
```

### round，round2 四舍五入

取整或保留有效小数

```lisp
round(1.5)        => 2
round(-1.49)      => -1
round(1.49)       => 1

val=-0.2865
round(val/0.001)*0.001=> -0.286
round2(val/0.001)*0.001=> -0.287
```

### truncate 截断取整

```lisp
truncate( 1234.567)=> 1234
round( 1234.567)=> 1235
truncate( -1.7)=> -1
```

### fix fix2 floor 不大于给定参数的最大整数

```lisp
fix(1.9)      => 1
fix(-5.6)     => -6
fix(100)      => 100
fix(4.1 * 100)      => 409

fix2(4.1 * 100)=> 410

(floor -4.3) => -5
(floor 3.5)  => 3
```

## 判断

### fixp 判断是否为整数

```lisp
fixp(3)     => t
fixp(3.0)   => nil
```

### floatp，realp 判断是否为浮点数

```lisp
floatp(3)    => nil
floatp(3.0)  => t

realp( 2789987)=> nil
realp( 2789.987)=> t
```

### minusp，negativep 判断是否为负数

```lisp
minusp( 3 )    => nil
minusp( -3 )   => t
negativep( 3 )    => nil
negativep( -3 )   => t
```

### onep，zerop 数值是否等于1，数值是否等于0

```lisp
onep( 1 ) => t
onep( 7 ) => nil
onep( 1.0 ) => t

zerop( 0 )=> t

zerop( 7 )=> nil
```

### plusp 是否为正数

```lisp
plusp( -209.623472)=> nil

plusp( 209.623472)=> t
```

### evenp，oddp 判断是否为偶数，奇数

```lisp
evenp( 59 )=> nil

evenp( 60 )=> t

evenp( 2.0 )=> nil             ; Number is even, but not an integer.

oddp( 7 )=> t

oddp( 8 ) => nil
```

## 三角函数


### sin asin 正弦 反正弦

```lisp
sin(3.14/2)        => 0.9999997
sin(3.14159/2)     => 1.0

asin(0.3) => 0.3046927
```

### cos acos 余弦 反余弦

```lisp
cos(0.3)         => 0.9553365
cos(3.14/2)      => 0.0007963

acos(0.3)        => 1.266104
```

### tan atan atan2 正切 反正切

```lisp
tan( 3.0 ) => -0.1425465

atan(0.3) => 0.2914568

atan2(1 1) => 0.7853982
atan2(0 0) => 0.0
```

### 其它

### random 0到给定数取随机数

```lisp
random( 93 )=> 26
```

### sort 按指定方式排序

```lisp
y = '(c a d b)
(sort y nil)        => (a b c d)
y                   => (c d)  ;no longer points to head of list
y = '(c a d b)
y = (sort y nil)    => (a b c d)
y => (a b c d)                ;reassignment points y to sorted list.
```

### sortcar 对list第一个值 排序list

```lisp
sortcar( '((4 four) (3 three) (2 two)) 'lessp )
=> ((2 two) (3 three) (4 four)

sortcar( '((d 4) (b 2) (c 3) (a 1)) nil )
=> ((a 1) (b 2) (c 3) (d 4))
```

### defMathConstants

### isInfinity

### isNaN

### leftshift

### rightshift

### log 数值的自然对数值

### log10

### srandom

### zxtd


