---
title: 'Cadence Skill 字串（Text）'
date: Mon, 11 May 2020 07:48:31 +0000
draft: false
tags: ['Allegro Skill']
---

字串可视为一维的字阵列，在本节中介绍 SKILL 提供常用之字串处理的函式。

### 字串按分隔符拆分为list

```
parseString(
S_string
[ S_breakCharacters ]
)
=> l_strings
``````
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

### list拼接为字串

```
buildString(
l_strings
[ S_glueCharacters ]
)
=> t_string
``````
buildString( '("test" "il") ".")      => "test.il"
buildString( '("usr" "mnt") "/")      => "usr/mnt"
buildString( '("a" "b" "c"))          => "a b c"
buildString( '("a" "b" "c") "")       => "abc"
buildString( '("A" "B") 'and)         => "AandB"
```

### 关联串列

### 字串串接

```
strcat(
S_string1
[ S_string2 ... ]
)
=> t_result
``````
strcat( 'ab "xyz" )        => "abxyz"
strcat( "l" "ab" "ef" )    => "labef"
```

### 字串长度

```
strlen(
t_string
)
=> x_length
``````
strlen( "abc" )    => 3
strlen( "\007" )   => 1  ; Backslash notation used.
```

### 处理字串中之字符

按位数提取字串中的字串

```
substring(
S_string
x_index
[ x_length ]
)
=> t_result | nil
``````
substring("abcdef" 2 4)    => "bcde"
substring("abcdef" 4 2)    => "de"
substring("abcdef" -4 2)   => "cd"
```

### 建立子字串

### 字串转换

string to integer 字符转换为整数 atoi 提取文本中的整数

```
atoi("123")      => 123
atoi("abc")      => nil
atoi("123.456")  => 123
atoi("123abc")   => 123
```

string to floating-point number 字符转换为小数 atof 提取文本中的小数

```
atof("123")              => 123.0
atof("abc")              => nil
atof("123.456")          => 123.456
atof("123abc")           => 123.0
```

integer to string 数值转文本

```
a = 100
sprintf(a "%d" a) => a = "100"
a = 100.00
sprintf(b "%f" a) => b = "100.000000"
sprintf(b "%0.2f" a) => b = "100.00"

sprintf(b "%0.2n" a) => b = "100.00"
```

大小写转换 upperCase、lowerCase

```
upperCase("Hello !")    => "HELLO !"
sym = "Hi"              => "Hi"
upperCase(sym)          => "HI"
lowerCase("Hello !")    => "hello !"
```

### 字串反向排列

```
tName = "a1b3"
rName = ""
nt = strlen(tName)
for( i 1 nt 
tt = substring(tName i 1) 
rName = strcat(tt rName) 
)
rName
```

### 字串的查找

```
rexMatchp("[0-9]*[.][0-9][0-9]*" "100.001")    => t
rexMatchp("[0-9]*[.][0-9]+" ".001")            => t
rexMatchp("[0-9]*[.][0-9]+" ".")               => nil
rexMatchp("[0-9]*[.][0-9][0-9]*" "10."          => nil

rexMatchp("GND" "DGND")  => t
rexMatchp("GND" "ND") => nil
```

### 字串的查找与替换

```
rexCompile( "[0-9]+" )               => t
rexReplace( "abc-123-xyz-890-wuv" "(*)" 1)
                                    => "abc-(*)-xyz-890-wuv"
rexReplace( "abc-123-xyz-890-wuv" "(*)" 2)
                                    => "abc-123-xyz-(*)-wuv"

rexReplace( "abc-123-xyz-890-wuv" "(*)" 3)
                                    => "abc-123-xyz-890-wuv"
rexReplace( "abc-123-xyz-890-wuv" "(*)" 0)
                                    => "abc-(*)-xyz-(*)-wuv"

rexCompile( "xyz" )                 => t
rexReplace( "xyzzyxyzz" "xy" 0)
                                   => "xyzyxyz" ; no rescanning!
rexCompile("[A-Za-z]+")
rexReplace( "abc-123-xyz-890-wuv" "(*)" 0)
                                    => "(*)-123-(*)-890-(*)
```