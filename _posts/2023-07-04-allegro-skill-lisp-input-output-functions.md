---
layout: post
title: Input Output And Environment Functions
categories: Allegro Skill
date: 2023-07-04
permalink: allegro-skill-lisp-input-output-functions
excerpt: 数据输入输出,文件内容读写,文件、文件夹读写和更改
---

This section introduces how to Display values using default formats and application-specific formats本节介绍如何使用默认格式和特定于应用程序的格式显示值

关联axl文件处理函数[22 File Access Functions](https://tiny-yhw.github.io//allegro-skill-file-access-functions){:target="_blank"}


## getWorkingDir 获得当前活动文件所在路径，当前工作目录

```lisp
getWorkingDir();=> t_currentDir
getWorkingDir();=> "C:/project/Layout/brd"
```

返回值:当前打开文件所在的工作目录

说明:该函数与使用"./"的目录一致。在平时layout过程中，往往需要频繁打开当前的brd文件夹，可以通过下面代码设置简单快捷键快速打开。

```lisp
funckey sss skill 'axlShell(strcat("http " getWorkingDir()))'
```

将上面代码添加到ENV文件中，重启allegro，按下sss即可打开当前工作目录

## isDir 判断路径是否存在

```lisp
isDir(strcat(axlGetVariable("localenv") "\\dts_site\\hdcnet"));注意文件路径最后不能有\否则返回nil
```

## createDir 创建文件夹

```lisp
unless(isDir("./OUTPUT") createDir("./OUTPUT")) 
```

## deleteDir 删除路径

```lisp
createDir("/usr/tmp/test") => t
deleteDir("/usr/tmp/test") => t
deleteDir("/usr/bin")
```

## getDirFiles 获取文件夹下文件清单

```lisp
getDirFiles(car(getInstallPath()))
getDirFiles(".");获得当前工作目录所有文件
getDirFiles(getWorkingDir());获得当前工作目录所有文件
```

## isFile 判断文件是否存在

```lisp
 (files = getDirFiles("./")) 
	foreach(file files 
	    if(((isFile(file) == t) && (nth(1 
				parseString(file ".")
			    ) == "drl") ) then 
		(axlOSFileMove file strcat("./OUTPUT/" file))
	    )
	)
```


## deleteFile 删除文件

```lisp
deleteFile("./drill_file.scr")
```


## system

生成一个单独的 UNIX （批处理，CMD指令）进程来执行命令。

```lisp
system("step_out 000.brd -o 000 -m -n -d -z")
```

```lisp
system( "date" )  =>Wed Dec 14 15:14:53 PST 1994 0
system( "daa" ) => sh: daa: not found 1
```


## 从文件中读数据

*   使用inflie函数获得一个输入端口
*   使用gets函数一次读取一行  
*   使用fscanf函数在输入时转换文本字段
*   关闭端口

使用infile获得文件的输入端口，gets函数读取文件的下一行。这个例子打印"~/.cshrc文件的每一行。

```lisp
inPort = infile("~/.cshrc")
when(inPort
	while(
		gets(nextLine inPort)
		println(nextLine)
		)
	close(inPort)
	)
```

```lisp
lst=nil
hdcnetfile = strcat(axlGetVariable("localenv") "\\dts_site\\hdcnet\\hdcnet.ini")
inPort = infile(hdcnetfile)
if(inPort then
while(
    gets(nextLine inPort) 
    println(nextLine)
    lst = append1(lst nextLine)
    )
else
println("error: file not found")
)
close(inPort)
```


## Displaying Data（显示数据）


显示数据使用 print 和 println函数 或 printf 函数

SKILL解释器对于每种数据有默认的显示格式The*print*and*println*函数就是使用这种格式显示数据

* integer:5
* floating point: 1.3
* text string: "Mary learned SKILL"
* variable: bBox
* list: ( 1 2 3 )

### print、println

接收任意的数据类型，并打印到 CIW

与`print`区别在于`println`打印一个数据后会自动换行

```lisp
for( i 1 3 print( "hello" ))     ;Prints hello three times.
"hello""hello""hello"
for( i 1 3 println( "hello" ))   ;Prints hello three times.
"hello"
"hello"
"hello"
```

### printf

*   格式化输出字符串
*   第一个参数定义输出字符串格式 format，例如下面能够识别其中的**转义符**(`\`) 和**字符串占位符**(`%s`)
*   从第二个参数开始会依次替换 format 中定义的**占位符**
*   输出成功，返回`t`，输出不成功都是报 error。

```lisp
x = 197.9687
printf("The test measures %10.2f.\n" x)
```

printf函数带格式输出，这个例子显示报告中的一行。

```lisp
printf("\n%-15s %-15s %-10d %-10d %-10d %-10d" layerName purpose rectCount labelCount lineCount miscCount)
```

The first argument is a conversion control string containing directives.

包含指令符的第一个参数控制字符串转换。

```
%\[-\]\[width\]\[.precision\]conversion\_code
\[-\]= left justify 左对齐
\[width\]  = minimum number of character positions 字符位最小数目       \[.precision\] = number of characters to be printed 精度
conversion\_code  
d - decimal(integer) 整型
f - floating point 浮点型
s - string or symbol 字符串 或 symbol
c - character 字符
n - numeric 数字
L - list (Ignores width and precision fields.) 列表（忽略宽度与精度）
P - point list (Ignores width and precision fields.)点列表 （忽略宽度与精度）
B - Bounding box list (Ignores width and precision.)边界框list（忽略宽度与精度）
```

The %L directive specifies the default format. %L 指令符指定一个默认格式。

This directive is a convenient way to intersperse application-specific formats with default formats. 

### fprintf

将格式化的内容写入接口

与printf基本一致，fprintf比其多一个输出接口，一般用于向文件内写文本内容

下文有案例

## Writing Data to a File（在一个文件中写入数据）

要写文本数据到一个文件需要使用*outfile*函数获得一个文件输出端口。

```lisp
p = outfile("/tmp/out.il" "w")
```

使用一个必需的参数给fprintf（就是fprintf函数必需要有该参数），也可以使用printf或println

```lisp
for(i 0 15 fprintf(p "%20d %-20d\n" 2**i 3**i))
```

关闭输出端口

```lisp
close(p)
```

Both _print_ and _println_ accept an optional second argument, which should be an output port associated with the target file. Use the _outfile_ function to obtain an output port for a file. Once you are finished writing data to the file, use the _close_ function to release the port. The following code

```lisp
p = outfile( "/tmp/myFile" )
for( i 1 3  println( list( "Number:" i) p ))
close( p )
```

写数据给文件 `/tmp/myFile`

```lisp
("Number:" 1) ("Number:" 2) ("Number:" 3)
```

outfile函数使用完整的路径。记住如果路径未被指定或不能访问到文件，outfile返回 nil，如果端口参数是 nil，print和println函数显示一个错误。注意类型模板使用 _p_ 来指定。

```lisp
println( "Hello" nil )
;Message: *Error* println: argument #2 should be an I/O port(type template = "gp") - nil
```

不像print和println函数，printf函数不接受一个可选的端口参数，使用printf函数向文件中写入格式数据，其第一个参数应该是关联文件的输出端口，具体看下面的代码：

```lisp
myPort = outfile( "/tmp/myFile" ) 
for( i 1 3       
	fprintf( myPort "Number: %d\n" i )
	) 
close( myPort )
```

writes this data to the file `/tmp/myFile`.

```
Number: 1 Number: 2 Number: 3
```

### sprintf

与`fprintf`的区别是，不直接打印结果，而是将结果作为函数的输出，你可以赋值给`变量`

```lisp
sprintf( variable "My name is %s and weight is %d kg\n" "YEUNGCHIE" 999 )
variable = sprintf( nil "My name is %s and weight is %d kg\n" "YEUNGCHIE" 999 )
; "My name is YEUNGCHIE and weight is 999 kg"
```

上面两句的效果是一样的，`variable`将会被赋值为格式化后的字符串。

成功格式化即返回字符串内容

### lsprintf

与 `sprintf` 的区别是，第一个参数不用于指定被赋值的变量。

```lisp
string = lsprintf( "My name is %s and weight is %d kg\n" "YEUNGCHIE" 999 )
```

*   成功格式化即返回字符串内容
*   当输出的参数数量不确定的时候这个函数非常好用，举个例子：

```lisp
format = "My name is %s and weight is %d kg\n"
args   = list( "YEUNGCHIE" 999 )
string = apply( 'lsprintf format args )
; "My name is YEUNGCHIE and weight is 999 kg"
```

当然 `sprintf` 也不是做不到，只不过会比较麻烦。

```lisp
string = apply(
  lambda(( a \@rest b )
    apply( 'sprintf nil a b )
  )
  format
  args
)
; "My name is YEUNGCHIE and weight is 999 kg"
```

### infile 获得输入句柄，读文件。

假设现有一个文件`file.txt`

获取一个输入句柄，打开这个文件。

```lisp
inHandle = infile( "file.txt" )
```

### gets 行读取

用`gets`可以将按**行**迭代文件内容（一行一行读取），全部内容读取完会返回`nil`。

```lisp
gets( string inHandle )
close( inHandle )；读取结束后记得关闭这个句柄。
```

上面这个操作将第一行的内容赋值给了 string 变量。

```lisp
printf( "%s\n" string )
```

也可以将第一个参数指定为`nil`，不赋值给变量，通过函数返回值的读取内容，类似`sprintf`
再次使用`gets`则会继续读取第二行内容。

```lisp
printf( "%s\n" gets( nil inHandle ))
```

### getc字读取

用`getc`可以将按**单个字符**迭代文件内容（一个字一个字读取），全部内容读取完会返回`nil`。  
和`gets`有点不同，`getc`返回 symbol 类型，且第一个变量为句柄。

```lisp
printf( "%s\n" getc( inHandle ))
```

读取完剩下内容，并打印出来。

```lisp
while( char = getc( inHandle )
  printf( "%s\n" char )
)
close( inHandle )；读取结束后记得关闭这个句柄。
```

fscanf函数通过格式指令符从文件中读取数据。这个例子打印`~/.cshrc文件中的每个字。`

```lisp
inPort = infile("~/.cshrc")
when(inPort
	while(
		fscanf(inPort "%s" word)
		println(word)
		)
	close(inPort)
	)
```

gets函数从文件读取下一行。gets的参数是来自下一行和输入端口的变量。gets返回文本字符串，或当文件结束时，返回nil

fscanf函数根据转换控制指令符从文件中读取数据。fscanf的参数是：

1.  输入端口
2.  转换控制字符串
3.  收到匹配数据值的变量Variable(s) that will receive the matching data values


fscanf返回匹配数据项的数量。格式指令符一般如下：

| Format Specification | Data Type      | Scans Input Port        |
|----------------------|----------------|-------------------------|
| %d                   | nteger         | for next integer        |
| %f                   | floating point | for next floating point |
| %s                   | text string    | for next text string    |
| %e                   | floating point | for next floating point |
| %g                   | floating point | for next floating point |


**Skill中的通用输出格式规范**

| Format Specification | Type(s) of Argument | Prints | Example |
| --- | --- | --- | --- |
| %d | fixnum | 输出为十进制整数 | printf("%d" 15)  \=>15 |
| %o | fixnum | 输出为八进制整数 | printf("%o" 15)  \=>17 |
| %x | fixnum | 输出为十六进制整数 | printf("%o" 15)  \=>f |
| %f | flonum | 浮点数（默认6位小数） | printf("%f" 10.0)  \=>10.000000  printf("%0.3f" 10.0)  \=>10.000 |
| %e | flonum | 以科学计数输出浮点数 | printf("%0.1e" 10.0)  \=>1.0e+01 |
| %g | flonum | 简化浮点数的输出 | printf("%g" 10.0)  \=>10  printf("%g" 10.10)  \=>10.1 |
| %s | string, symbol | 输出字符串或symbol类型（不带引号） | printf("%s" "hellow,world")  \=>hellow,world |
| %c | string, symbol | 输出字符串或symbol的第一个字节 | printf("%c" "hellow,world")  \=>h |
| %n | fixnum, flonum | 输出数字（浮点数默认6位小数） | printf("%n" 10)  \=>10  printf("%n" 10.0)  \=>10.000000 |
| %P | list | 输出Point格式 | printf("%P" list(1 2))  \=>1:2 |
| %B | list | 输出Box格式 | printf("%B" \`((0 0) (1 1)))  \=>(0:0 1:1) |
| %N | any | 按照原有类型输出（字符串会带引号） | printf("%N" "hellow,world")  \=>"hellow,world" |
| %L | list | 输出List格式 | printf("%L" list(1 2 3))  \=>(1 2 3) |
| %A | any | 匹配任意类型输出（字符串会带引号） | printf("%A" "hellow,world")  \=>"hellow,world" |




11

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
fscanf, scanf, sscanf
get_filename
getOutstring
include
info
inportp
instring
isExecutable
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
outportp
portp
pprint
printlev
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

14
Environment Functions
cdsGetInstPath
cdsGetToolsPath
cdsPlat
changeWorkingDir
cputime
createDirHier
csh
exit
getCurrentTime
getInstallPath
getLogin
getPrompts
getShellEnvVar
getSkillPath
getTempDir
prependInstallPath
setShellEnvVar
setSkillPath
sh, shell
unsetShellEnvVar
vi, vii, vil