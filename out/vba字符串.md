---
title: 'VBA字符串'
date: Thu, 16 Apr 2020 09:43:06 +0000
draft: false
tags: ['Excel+VBA']
---

字符串是一个字符序列，可以由字母，数字，特殊字符或全部字符组成。 如果一个变量被包含在双引号`""`中，则被认为是一个字符串。

[官方教程](https://support.office.com/zh-tw/article/%E5%AD%97%E4%B8%B2%E5%87%BD%E6%95%B8%E5%8F%8A%E5%85%B6%E4%BD%BF%E7%94%A8%E6%96%B9%E6%B3%95-965efa84-7009-4603-9765-2eb4a099ec72)

**语法**

```
variable_name = "this is a string"
```

**简单示例**

```
str1 = "string"   ' Only Alphabets
str2 = "132.45"   ' Only Numbers
str3 = "!@#$;*"  ' Only Special Characters
Str4 = "Asc23@#"  ' Has all the above
```

字符串函数
-----

预定义的VBA字符串函数可以帮助开发人员非常有效地处理字符串。以下是VBA中支持的字符串的方法。请点击每个方法来详细了解。

编号

函数

描述

1

[InStr](http://www.yiibai.com/vba/vba_instr_function.html)

返回指定子字符串的第一个匹配项。从左到右搜索。

2

[InstrRev](http://www.yiibai.com/vba/vba_instrrev_function.html)

返回指定子字符串的第一个匹配项。从右到左搜索。

3

[Lcase](http://www.yiibai.com/vba/vba_lcase_function.html)

返回指定字符串的小写字母。

4

[Ucase](http://www.yiibai.com/vba/vba_ucase_function.html)

返回指定字符串转为大写字母的形式。

5

[Left](http://www.yiibai.com/vba/vba_left_function.html)

返回在左侧指定数量字符的字符串。

6

[Right](http://www.yiibai.com/vba/vba_right_function.html)

返回在右侧指定数量字符的字符串

7

[Mid](http://www.yiibai.com/vba/vba_mid_function.html)

根据指定的参数从字符串中返回特定数量的字符。

8

[Ltrim](http://www.yiibai.com/vba/vba_ltrim_function.html)

删除指定字符串左侧的空格后返回一个字符串。

9

[Rtrim](http://www.yiibai.com/vba/vba_rtrim_function.html)

删除指定字符串右侧的空格后返回一个字符串。

10

[Trim](http://www.yiibai.com/vba/vba_trim_function.html)

删除开头和结尾空格后返回一个字符串值。

11

[Len](http://www.yiibai.com/vba/vba_len_function.html)

返回给定字符串的长度。

12

[Replace](http://www.yiibai.com/vba/vba_replace_function.html)

用另一个字符串替换字符串后返回字符串。

13

[Space](http://www.yiibai.com/vba/vba_space_function.html)

用指定数量的空格填充字符串。

14

[StrComp](http://www.yiibai.com/vba/vba_strcomp_function.html)

比较两个指定的字符串后返回一个整数值。

15

[String](http://www.yiibai.com/vba/vba_string_function.html)

返回指定次数的字符的字符串。

16

[StrReverse](http://www.yiibai.com/vba/vba_strreverse_function.html)

反转给定字符串的字符序列后，返回一个字符串。

功能…

使用…

例如…

结果

传回字串开头的字元

[Left 的函数](https://msdn.microsoft.com/en-us/library/gg251556.aspx)

\=Left(\[SerialNumber\],2)

如果\[SerialNumber\] 为“CD234”，则结果为“CD”。

传回字串结尾的字元

[Right 函数](https://msdn.microsoft.com/en-us/library/gg278801.aspx)

\=Right(\[SerialNumber\],3)

如果\[SerialNumber\] 为“CD234”，则结果为“234”。

寻找字元在字串中的位置

[InStr 函数](https://msdn.microsoft.com/en-us/library/gg264811.aspx)

\=InStr(1,\[FirstName\],"i")

如果\[FirstName\] 为“Colin”，则结果为4。

传回字串中间的字元

[Mid 函数](https://msdn.microsoft.com/en-us/library/gg251677.aspx)

\=Mid(\[SerialNumber\],2,2)

如果\[SerialNumber\] 为“CD234”，则结果为“D2”。

修剪字串的前置或结尾空格

[LTrim、 RTrim 和Trim 函数](https://msdn.microsoft.com/en-us/library/gg278916.aspx)

\=Trim(\[FirstName\])

如果\[FirstName\] 为“ Colin ”，则结果为“Colin”。

将两个字串结合在一起

加号(+) 运算子\*

\=\[FirstName\] + \[LastName\]

如果\[FirstName\] 为“Colin” 且\[LastName\] 为Wilcox，则结果为“ColinWilcox”

将两个字串结合在一起，并以一个空格区隔

加号(+) 运算子\*

\=\[FirstName\] + “ “ + \[LastName\]

如果\[FirstName\] 为“Colin” 且\[LastName\] 为Wilcox，则结果为“Colin Wilcox”

将字串的大小写变更为大写或小写

[UCase函数](https://msdn.microsoft.com/en-us/library/gg264252.aspx)或[LCase函数](https://msdn.microsoft.com/en-us/library/gg264497.aspx)

\=UCase(\[FirstName\])

如果\[FirstName\] 为“Colin”，则结果为“COLIN”。

判定字串的长度

[Len 函数](https://msdn.microsoft.com/en-us/library/gg251657.aspx)

\=Len(\[FirstName\])

如果\[FirstName\] 为“Colin”，则结果为5。

LCase 函数（UCase）
---------------

返回指定字符串的小写字母。

**Lcase(String)**

所需的**_字串_**引数为任何有效的字串运算式。如果**_string_**包含Null，就会传回Null。

只有大写字母会转换成小写;所有小写字母及nonletter 字元都会保持不变。

```
Dim UpperCase, LowerCase
Uppercase = "Hello World 1234"    ' String to convert.
Lowercase = Lcase(UpperCase) ' Returns "hello world 1234"
```

**Ucase**逻辑一致，返回大写字母

Split 函数
--------

返回包含指定数目的子字符串的从零开始的一维[数组](https://docs.microsoft.com/zh-cn/office/vba/language/glossary/vbe-glossary#array)。

### 语法

**Split**（_expression_，\[_定界符_，\[ _limit_，\[ _compare_ \]\]\]）

**TimeSerial** 函数语法具有以下[命名参数](https://docs.microsoft.com/zh-cn/office/vba/language/glossary/vbe-glossary#named-argument)：

Part

说明

_expression_

必需。 包含子字符串和分隔符的[字符串表达式](https://docs.microsoft.com/zh-cn/office/vba/language/glossary/vbe-glossary#string-expression)。 如果 _expression_ 是零长度字符串 ("")，则 **Split** 返回空数组，即不包括任何元素和数据的数组。

_分隔符_

可选。 用于标识子字符串限制的 String 字符。 如果省略，则假定空格符 (" ") 为分隔符。 如果 _delimiter_ 是零长度字符串，则返回包含完整 _expression_ 字符串的只含单一元素的数组。

_数_

可选。 要返回的子字符串的数目;-1 表示返回所有子字符串。

_compare_

可选。 指示计算子字符串时使用的比较类型的数值。 请参阅“设置”部分以了解各个值。

### 设置

_compare_ 参数可以包含以下值：

常量

值

说明

**vbUseCompareOption**

\-1

使用 **[Option Compare](https://docs.microsoft.com/zh-cn/office/vba/language/reference/user-interface-help/option-compare-statement)** 语句的设置来执行比较。

**vbBinaryCompare**

0

执行二进制比较。

**vbTextCompare**

1

执行文本比较。

**vbDatabaseCompare**

双面

仅用于 Microsoft Access。 根据数据库中的信息执行比较。

### 示例

本示例演示如何使用**Split**函数。VB复制

```
Dim strFull As String
Dim arrSplitStrings1() As Variant
Dim arrSplitStrings2() As Variant
Dim strSingleString1 As String
Dim strSingleString2 As String
Dim strSingleString3 As String
Dim i As Long

strFull = "Some - Old - Hags - Can - Always - Hide - Their - Old - Age"    ' String that will be used. 

arrSplitStrings1 = Split(strFull, "-")      ' arrSplitStrings1 will be an array from 0 To 8. 
                                            ' arrSplitStrings1(0) = "Some " and arrSplitStrings1(1) = " Old ". 
                                            ' The delimiter did not include spaces, so the spaces in strFull will be included in the returned array values. 

arrSplitStrings2 = Split(strFull, " - ")    ' arrSplitStrings2 will be an array from 0 To 8. 
                                            ' arrSplitStrings2(0) = "Some" and arrSplitStrings2(1) = "Old". 
                                            ' The delimiter includes the spaces, so the spaces will not be included in the returned array values. 

'Multiple examples of how to return the value "Can" (array position 3). 

strSingleString1 = arrSplitStrings2(3)      ' strSingleString1 = "Can". 

strSingleString2 = Split(strFull, " - ")(3) ' strSingleString2 = "Can".
                                            ' This syntax can be used if the entire array is not needed, and the position in the returned array for the desired value is known. 

For i = LBound(arrSplitStrings2, 1) To UBound(arrSplitStrings2, 1)
    If InStr(1, arrSplitStrings2(i), "Can", vbTextCompare) > 0 Then
        strSingleString3 = arrSplitStrings2(i)
        Exit For
    End If 
Next i
```

### 另请参阅

*   [函数 (Visual Basic for Applications)](https://docs.microsoft.com/zh-cn/office/vba/language/reference/functions-visual-basic-for-applications)