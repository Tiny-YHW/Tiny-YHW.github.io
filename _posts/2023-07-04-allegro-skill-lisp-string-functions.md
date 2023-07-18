---
layout: post
title: String Functions 字符串函数
categories: Allegro Skill
date: 2023-07-04
permalink: allegro-skill-lisp-string-functions
excerpt: 字串可视为一维的字阵列，在本节中介绍 SKILL 提供常用之字串处理的函式。
---

字串可视为一维的字阵列，在本节中介绍 SKILL 提供常用之字串处理的函式。

### parseString 字串按分隔符拆分为list

```
parseString(S_string [ S_breakCharacters ])=> l_strings
```

```lisp
parseString( "Now is the time" )   => ("Now" "is" "the" "time")
Space is the default break character

parseString( "prepend" "e" )       => ("pr" "p" "nd" ) 
e is the break character.

parseString( "feed" "e")           => ("f" "d")
A sequence of break characters in S_string is treated as a single break character.

parseString( "~/exp/test.il" "./") => ("~" "exp" "test" "il")
Both . and / are break characters.

parseString( "abc de" "")          => ("a" "b" "c" " " "d" "e")
The single space between c and d contributes " " in the return result.
```

### buildString 将 list 拼接为字串

```
buildString(l_strings [ S_glueCharacters ]) => t_string
```

```lisp
buildString( '("test" "il") ".")      => "test.il"
buildString( '("usr" "mnt") "/")      => "usr/mnt"
buildString( '("a" "b" "c"))          => "a b c"
buildString( '("a" "b" "c") "")       => "abc"
buildString( '("A" "B") 'and)         => "AandB"
```

### 关联串列

### strcat 将多个字串串接

strcat函数可将输入参数的字符串连接起来，然后返回一个新的字符串

```
strcat(S_string1 [ S_string2 ... ]);=> t_result
```

```lisp
strcat( 'ab "xyz" )        => "abxyz"
strcat( "l" "ab" "ef" )    => "labef"
```

### strcat 获取字串长度

```
strlen(t_string) => x_length
```

```lisp
strlen( "abc" )    => 3
strlen( "\007" )   => 1  ; Backslash notation used.
```

## 处理字串中之字符

### substring 按位数提取字串中的字串

```
substring(S_string x_index [ x_length ] ) => t_result | nil
```

```lisp
substring("abcdef" 2 4)    => "bcde"
substring("abcdef" 4 2)    => "de"
substring("abcdef" -4 2)   => "cd"
```

### sprintf 数值转文本 integer to string

```lisp
a = 100
sprintf(a "%d" a) => a = "100"
a = 100.00
sprintf(b "%f" a) => b = "100.000000"
sprintf(b "%0.2f" a) => b = "100.00"

sprintf(b "%0.2n" a) => b = "100.00"
```

### upperCase、lowerCase大小写转换

```lisp
upperCase("Hello !")    => "HELLO !"
sym = "Hi"              => "Hi"
upperCase(sym)          => "HI"
lowerCase("Hello !")    => "hello !"
```


### rexMatchp 字串的查找

```lisp
rexMatchp("[0-9]*[.][0-9][0-9]*" "100.001")    => t
rexMatchp("[0-9]*[.][0-9]+" ".001")            => t
rexMatchp("[0-9]*[.][0-9]+" ".")               => nil
rexMatchp("[0-9]*[.][0-9][0-9]*" "10."          => nil

rexMatchp("GND" "DGND")  => t
rexMatchp("GND" "ND") => nil
```

### rexCompile rexReplace字串的查找与替换

```lisp
rexCompile( t_pattern ) ;=> t / nil 
rexReplace( t_source t_replacement x_index ) ;=> t_result
```

* *t_pattern:* 需要被替换的字符单元
* *t_source:* 源字符
* *t_replacement:* 替换为什么字符
* *x_index:* 指定要替换哪个匹配子字符串。 如果 <= 0，则进行全局替换。

```lisp
rexCompile( "[0-9]+" )
rexReplace( "abc-123-xyz-890-wuv" "(*)" 1) ;=> "abc-(*)-xyz-890-wuv"
rexReplace( "abc-123-xyz-890-wuv" "(*)" 2) ;=> "abc-123-xyz-(*)-wuv"
rexReplace( "abc-123-xyz-890-wuv" "(*)" 3) ;=> "abc-123-xyz-890-wuv"
rexReplace( "abc-123-xyz-890-wuv" "(*)" 0) ;=> "abc-(*)-xyz-(*)-wuv"

rexCompile( "xyz" )
rexReplace( "xyzzyxyzz" "xy" 0)            ;=> "xyzyxyz" ; no rescanning!
rexCompile("[A-Za-z]+")
rexReplace( "abc-123-xyz-890-wuv" "(*)" 0) ;=> "(*)-123-(*)-890-(*)
```

### 字串反向排列

```lisp
tName = "a1b3"
rName = ""
nt = strlen(tName)
for( i 1 nt 
tt = substring(tName i 1) 
rName = strcat(tt rName) 
)
rName
```

### blankstrp 判断是否为空字符

```lisp
blankstrp( "");=> t
blankstrp( " ");=> t
blankstrp( "a string");=> nil
```

### getchar 获取第指定位字符

```lisp
getchar("abc" 2)  ;=> b
getchar("abc" 4)  ;=> nil
```

### index 从指定字符到末尾

```lisp
index( "abc" "b" )            ;=> "bc"
index( "abcdabce" "dab" )    ;=> "dabce"
index( "abc" "cba" )         ;=> nil
index( "dandelion" "d")      ;=> "dandelion"
```


### nindex 从字串中查找字符出现在第几位

```lisp
nindex( "abc" 'b )            ;=> 2
nindex( "abcdabce" "dab" )    ;=> 4
nindex( "abc" "cba" )         ;=> nil
```

### stringp 判断是否为字串

```lisp
stringp( 93);=> nil
stringp( "93");=> t
```


### lsprintf

### outstringp
### pcreCompile
### pcreExecute
### pcreGenCompileOptBits
### pcreGenExecOptBits
### pcreGetRecursionLimit
### pcreListCompileOptBits
### pcreListExecOptBits
### pcreMatchAssocList
### pcreMatchList
### pcreMatchp
### pcreObjectp
### pcrePrintLastMatchErr
### pcreReplace
### pcreSetRecursionLimit
### pcreSubpatCount
### pcreSubstitute
### readstring
### rexExecute
### rexMagic
### rexMatchAssocList
### rexMatchList
### rexSubstitute
### rindex
### strcmp

### strncat
### strncmp
### strpbrk
### subst
