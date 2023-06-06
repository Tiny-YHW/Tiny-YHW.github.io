---
title: 'Excel & VBA错误值处理'
date: Sat, 11 Apr 2020 05:58:26 +0000
draft: false
tags: ['Excel+VBA']
---

EXCEL
-----

excel在计算过程中，会出现一些错误，并且这些错误可以进行判断，根据这些错误还可以进行别的应用，

几种错误类型，包括#DIV/0!  #NAME?    #NULL!    #NUM!    #REF!   #VALUE!    #N/A!  

三种错误判断函数，分别是ISERROR（适用于所有错误类型）   ISERR  （适用于前六种） ISNA（适用于最后一种）

ISBLANK(value) ISBLANK 值为空白单元格。

ISNUMBER(value) ISNUMBER 值为数字。

ISTEXT(value) ISTEXT 值为文本。

IS 类函数的参数 value 是不可转换的。例如，在其他大多数需要数字的函数中，文本值“19”会被转换成数字 19。然而在公式 ISNUMBER("19") 中，“19”并不由文本值转换成别的类型的值，函数 ISNUMBER 返回 FALSE。

VBA
---

用isna()函数，true代表结果是 #N/A

或者iserror()是包含所有错误。包含以下这几个值。

单元格数值为下面任意一个则结果为True。

*   NULL!
*   DIV/0!
*   VALUE!
*   REF!
*   NAME?
*   NUM!
*   N/A