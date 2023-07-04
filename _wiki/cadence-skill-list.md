---
layout: wiki
title: Lisp语法
cate1: Cadence Skill
cate2: 
keywords: 
---



### abs 参数的绝对值

`(abs number) => n_result`

*number：* 任意数字。

*n_result：* 参数的绝对值。

```lisp
(abs 100) returns 100
(abs -100) returns 100
(abs -99.25) returns 99.25
```

acos

add1

addDefstructClass

alias

alphalessp

alphaNumCmp

and

append

append1

apply

argc

argv

arrayp

arrayref

asin

assoc, assq, assv

atan

atan2

### atof 将一个字符串转换成实数

函数用法：
将一个字符串转换成实数
     (atof string)
参数
         string:要转化为实数的字符串。
返回值
       实数。
示例
       命令： (atof "97.1")
                   97.1
       命令： (atof "3")
                    3.0
       命令： (atof "3.9")
                   3.9


atoi

atom

band

bcdp

begin - SKILL mode

begin - SKILL++ mode

bitfield1

bitfield

blankstrp

bnand

bnor

bnot

booleanp

bor

boundp

buildString

bxnor

bxor

caar, caaar, caadr, cadr, caddr, cdar, cddr, ...

car

case, caseq

cdr

cdsGetInstPath

cdsGetToolsPath

cdsPlat

ceiling

changeWorkingDir

charToInt

clearExitProcs

close

compareTime

compress

concat

cond

cons

constar

copy

copy_<name>

copyDefstructDeep

cos

cputime

createDir

csh

declare

declareLambda

declareNLambda

declareSQNLambda

define - SKILL++ mode

defmacro

defMathConstants

defprop

defstruct

defstructp

defun

defUserInitProc

defvar - SKILL mode only

deleteDir

deleteFile

difference

display

do - SKILL++ mode only

drain

dtpr

ed

edi

edit

edl

envobj

eq

equal

eqv

err

error

errset

errsetstring

eval

evalstring

evenp

exists

exit

exp

expandMacro

expt

fboundp

fileLength

fileSeek

fileTell

fileTimeModified

fix

fixp

float

floatp

floor

for

forall

foreach

fprintf

fscanf, scanf, sscanf

funcall

funobj

gc

gensym

geqp

get

get_filename

get_pname

get_string

getc

getchar

getCurrentTime

getd

getDirFiles

getFnWriteProtect

getFunType

getInstallPath

getLogin

getPrompts

getq

getqq

getTempDir

gets

getShellEnvVar

getSkillPath

getSkillVersion

getVarWriteProtect - SKILL mode only

getVersion

getWarn

getWorkingDir

go

greaterp

help

if

importSkillVar - SKILL++ mode

index

infile

inportp

inScheme

inSkill

instring

integerp

intToChar

isCallable

isDir

isExecutable

isFile

isFileEncrypted

isFileName

isInfinity

isLargeFile

isLink

isMacro

isNaN

isPortAtEOF

isReadable

isWritable

lambda

last

lconc

leftshift

length

leqp

lessp

let - SKILL mode

let - SKILL++ mode

letrec - SKILL++ mode

letseq - SKILL++ mode

lineread

linereadstring

list

listp

listToVector

load

loadi

loadstring

log

log10

lowerCase

make_<name>

makeTable

makeTempFileName

makeVector

map

mapc

mapcan

mapcar

maplist

max

measureTime

member, memq, memv

min

minus

minusp

mod

modf

modulo

mprocedure

nconc

ncons

needNCells

negativep

neq

nequal

newline

nindex

nlambda - SKILL mode only

not

nprocedure - SKILL mode only

nth

nthcdr

nthelem

null

numberp

numOpenFiles

oddp

onep

openportp

or

otherp

outfile

outportp

pairp

parseString

pcreCompile

pcreExecute

pcreGenCompileOptBits

pcreGenExecOptBits

pcreListCompileOptBits

pcreListExecOptBits

pcreMatchAssocList

pcreMatchList

pcreMatchp

pcrePrintLastMatchErr

pcreReplace

pcreSubstitute

plist

plus

plusp

portp

postdecrement

postincrement

pprint

predecrement

preincrement

prependInstallPath

print

printf

printlev

println

procedure

procedurep

prog

prog1

prog2

progn

putd

putprop

putpropq

putpropqq

quote

quotient

random

range

read

readstring

readTable

realp

regExitAfter

regExitBefore

remainder

remd

remdq

remExitProc

remove

remprop

remq

renameFile

return

reverse

rexCompile

rexExecute

rexMagic

rexMatchAssocList

rexMatchList

rexMatchp

rexReplace

rexSubstitute

rightshift

rindex

round

rplaca

rplacd

schemeTopLevelEnv

set

setarray

setcar

setcdr

setFnWriteProtect

setguard

setof

setplist

setPrompts

setq

setqbitfield1

setqbitfield

setShellEnvVar

setSkillPath

setVarWriteProtect - SKILL mode only

sh, shell

simplifyFilename

sin

sort

sortcar

sprintf

sqrt

srandom

sstatus

status

strcat

strcmp

stringp

stringToFunction

stringToSymbol

stringToTime

strlen

strncat

strncmp

sub1

subst

substring

sxtd

symbolp

symbolToString

symeval

symstrp

system

tablep

tableToList

tailp

tan

tconc

theEnvironment - SKILL++ mode only

times

timeToString

timeToTm

tmToTime

truncate

type, typep

unalias

unless

upperCase

vector

vectorp

vectorToList

vi, vii, vil

warn

when

which

while

write

writeTable

xcons

xCoord

xdifference

xplus

xquotient

xtimes

yCoord

zerop

zxtd

一、数学运算功能函数

1.1（十 数值 数值…）返回：累计实数或整数数值

1.2（一 数值 数值…）返回：差值

1.3（* 数值 数值…）返回：所有数值乘积

1.4（/ 数值 数值…）返回：第一个数值除以第二个以后数值的商

1.5（l十 数值）返回：数值十l

1. 6（1— 数值）返回：数值一l

1.7（abs 数值）返回：数值的绝对值

1.8（atan 数值）返回：反正切值

1.9（cos 角度）返回：角度的余弦值，角度值为弧度

1.10（exp 数值）返回：数值的指数

1.11（expt 底数指数）返回：底数的指数值

1.12（fix 数值）返回：将数值转换为整数值

1.14（gcd 数值1 数值2）返回：两数值的最大公因数

1.15（log 数值）返回：数值的自然对数值

1.16（max 数值 数值…）返回：数值中的最大值

1.17（min 数值 数值…）返回：数值中的最小值

1.18 pi 常数∏，其值约为3.1415926

1.19（rem 数值 1数值 2）返回：M数值的相除的余数

1.20（sin 角度）返回：角度的正旋值，角度值为弧度

1.21（sqrt 数值）返回：数值的平方根

二、检验与逻辑运算功能函数

2.1（= 表达式1 表达式2）比较表达式1是否等于式2，适用数值及字符串

2.2 （／= 表达式1 表达式2）比较表达式1是否大于等于表达式2 2.3（＜ 表达式1 表达式2）比较表达式1是否＜小于表达式2

2.4（＜= 表达式1 表达式2）比较表达式1是否＜一小于等于表达式2

2.5（＞ 表达式1 表达式2）比较表达式1是否＞大于表达式2

2.6（＞= 表达式1 表达式2） 比较表达式1是否大于等于表达式2

2.7 （～ 数值）返回：数值的位 not值，（1的补码）

2.8 （and 表达式1 表达式2…）返回：逻辑and的结果

2.9（boole 函数 整数 整数…）返回：位式布尔运算

2.10（eq 表达式1 表达式2）比较表达式1与表达式2是否相同，适用列表比较（实际相同）

2.11（equal 表达式 1表达式 2［差量］）比较表达式 1与表达式 2是否相同，差量可省略（内容相同）

三、转换运算功能函数

3.1（angtof 字符串［模式］）返回：角度值的字符串转成实数

3.2（angtos 角度［模式［精度］］）返回：角度转成的字符串值

3.3（atof 字符串）返回：字符串转成实数值

3.4 （atoi 字符串）返回：字符串转成整数值

3.5 （cvunit 数值 原始单位 转换单位）返回：数值转换单位后的值转换根据acad.nut文件

3.6（distof 字符串 ［模式］）返回：根据模式将字符串转成实数值

3.7（itoa 整数）返回：整数转成字符串

3.8（rtos 数值 模式［精度］）返回：实数转成字符串

3.9 （trans 点 原位置 新位置［位移］） 返回：转换坐标系统值

四、列表处理功能函数

4.1 （append 列表 列表……） 结合所有列表成一个列表

4.2（assoc 关键元素 联合列表）根据关键元素找寻联合列表中关系信息

4.3 （car 列表）返回列表中的第一个元素，通常用来求X坐标

4.4（cadr 列表）返回列表中的第二个元素，通常用来求y坐标

4.5（caddr 列表）返回列表中的第三个元素，通常用来求Z坐标

4.6（cdr 列表）返回：除去第一个元素后的列表

4.7（cons 新元素 列表）返回：将新元素添加到列表

4.8（foreach 名称 列表 表达式）返回：将列表的每一元素对应至名称再根据表达式执行响应

4.9（length 列表）返回：列表内的元素数量

4.10（list 元素 元素…）返回：将所有元素合并为一列表

4.11（listp 元素）返回：判断元素是否为一串

4.12（mapcar函数 列表1列表2…）返回：将列表1、列表2列表的元素配合函数，求得新列表

4.13（member 关键元素列表）返回：根据关键元素（含似后的列表

4.14（nth n 列表）返回：列表的第n个元素

4.15（reverse 列表）返回：将列表元素根据顺序颠倒过来的列表

4.16（subst 新项旧项列表）返回：替换新旧列表后的列表

五、字符串、字符、文件处理函数

5.1（ascii 字符串）返回：字符串第一个字符的“ASCII”码

5.2 （chr 整数）返回：整数所对应的ASCII单一字符串

5.3（close 文件 名称）关闭文件

5.4（open 文件名 模式）返回：打开文件代码，准备读取或写入信息

5.5（read 字符串）返回：列表中的字符串的第一组元素

5.6（read－char［文件代码］）返回：通过键盘或文件中读取单一字符

5.7（read－line ［文件代码］）返回：经由键盘或文件中读取一行字符串

5.8（strcase 字符串［字样］）返回：转换字符串大小写

5.9（strcat 字符串1字符串2…）返回：将各字符串合并为一个字符串

5.10（strlen 字符串）返回：字符串构成的字符数（即字符串长度）

5.11（substr 字符串 起始 长度）返回：取出于字符串‘

5.12（wcmatch 字符串 格式）返回：T或 nil，将字符串与通用字符进行比较

5.13（write－char数值［文件代码］）返回：将一ASCII字符写到文件或屏幕

5.14（write－line字符串［文件代码］）返回：将字符串写到文件或屏幕上