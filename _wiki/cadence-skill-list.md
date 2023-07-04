---
layout: wiki
title: Lisp语法
cate1: Cadence Skill
cate2: 
keywords: 
---

##

*  [5 String Functions 字符串函数](https://tiny-yhw.github.io//allegro-skill-lisp-string-functions){:target="_blank"}
*  [6 Arithmetic （Trigonometric） Functions 算术（三角）函数](https://tiny-yhw.github.io//allegro-skill-lisp-arithmetic-functions){:target="_blank"}







1
List Functions
append
append1
caar, caaar, caadr, cadr, caddr, cdar, cddr, ...
car
cdr
cons
constar
copy
dtpr
last
lconc
length
lindex
list
listp
nconc
ncons
nth
nthcdr
nthelem
pairp
range
remd
remdq
remove
removeListDuplicates
remq
reverse
rplaca
rplacd
setcar
setcdr
tailp
tconc
xcons
xCoord
yCoord
2
Data Structure
arrayp
arrayref
assoc, assq, assv
declare
defprop
defstruct
defstructp
defvar
makeTable
makeVector
setarray
tablep
type, typep
vector
vectorp
3
Data Operator Functions
alphaNumCmp
concat
copy_<name>
copyDefstructDeep
get
getSG
getq
getqq
importSkillVar
integerp
make_<name>
otherp
plist
popf
postArrayDec
postArrayInc
postArraySet
postdecrement
postincrement
preArrayDec
preArrayInc
preArraySet
predecrement
preincrement
pushf
putprop
putpropq
putpropqq
quote
remprop
rotatef
set
setf
setf_<helper>
setguard
setplist
setq
setSG
symbolp
symeval
symstrp
4
Type Conversion Functions
charToInt
intToChar
listToVector
stringToFunction
stringToSymbol
stringToTime
symbolToString
tableToList
timeToString
timeToTm
tmToTime
vectorToList



## 7 Bitwise Operator Functions
band
bitfield
bitfield1
bnand
bnor
bnot
bor
bxnor
bxor
setqbitfield
setqbitfield1
8
Trigonometric Functions
asin
atan
atan2
cos
sin
tan
acos
9
Logical and Relational Functions
alphalessp
and
compareTime
eq
equal
eqv
geqp
greaterp
leqp
lessp
member, memq, memv
neq
nequal
null
numberp
or
sxtd
10
Flow Control Functions
case
caseq
catch
cond
decode
do
exists
existss
for
fors
forall
foralls
foreach
foreachs
if
go
map
mapc
mapcan
mapcar
mapcon
mapinto
maplist
not
regExitAfter
regExitBefore
remExitProc
return
setof
setofs
throw
unless
when
while
11
Input Output Functions
close
compress
display
drain
ed
edi
edit
edl
encrypt
expandMacroDeep
fileLength
fileSeek
fileTell
fileTimeModified
fprintf
fscanf, scanf, sscanf
get_filename
getc
getDirFiles
getOutstring
gets
include
infile
info
inportp
instring
isExecutable
isFile
isFileEncrypted
isFileName
isLargeFile
isLink
isPortAtEOF
isReadable
isWritable
lineread
linereadstring
load
loadi
loadPort
loadstring
outstring
makeTempFileName
newline
numOpenFiles
openportp
outfile
outportp
portp
pprint
print
printf
printlev
println
putc
read
readTable
renameFile
simplifyFilename
simplifyFilenameUnique
truename
which
write
writeTable
12
Core Functions
arglist
assert
atom
bcdp
booleanp
boundp
describe
fdoc
gc
gensym
getMuffleWarnings
getSkillVersion
get_pname
get_string
getVersion
getWarn
help
inScheme
inSkill
isVarImported
makeSymbol
measureTime
muffleWarnings
needNCells
restoreFloat
saveFloat
schemeTopLevelEnv
setPrompts
sstatus
status
theEnvironment
unbindVar
13
Function and Program Structure
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
let
letrec
letseq
mprocedure
nlambda
nprocedure
procedure
procedurep
prog
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
14
Environment Functions
cdsGetInstPath
cdsGetToolsPath
cdsPlat
changeWorkingDir
cputime
createDir
createDirHier
csh
deleteDir
deleteFile
exit
getCurrentTime
getInstallPath
getLogin
getPrompts
getShellEnvVar
getSkillPath
getTempDir
getWorkingDir
isDir
prependInstallPath
setShellEnvVar
setSkillPath
sh, shell
system
unsetShellEnvVar
vi, vii, vil
15
Namespace Functions
makeNamespace
findNamespace
useNamespace
unuseNamespace
importSymbol
findSymbol
addToExportList
getSymbolNamespace
removeFromExportList
addToNamespace
shadow
shadowImport
removeShadowImport
unimportSymbol
16
Scheme/SKILL++ Equivalents Tables
Lexical Structure
Expressions
Functions
17
Mapping Symbols to Values
18
setf Helper Functions
setf_<helper>
19
Type Introspection Functions


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