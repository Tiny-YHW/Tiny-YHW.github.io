---
title: 'VBA 转义字符 和 格式转换'
date: Thu, 14 May 2020 06:23:13 +0000
draft: false
tags: ['Excel+VBA']
---

转义字符
----

成员

常数

等效

说明

CrLf

vbCrLf

Chr(13) + Chr(10)

回车/换行组合符。

Cr

vbCr

Chr(13)

回车符。

Lf

vbLf

Chr(10)

换行符。

NewLine

vbNewLine

Chr(13) + Chr(10)

换行符。

NullChar

vbNullChar

Chr(0)

值为 0 的字符。

n/a

vbNullString

值为 0 的字符串

与零长度字符串 ("") 不同；用于调用外部过程。

n/a

vbObjectError

\-2.1E+09

错误号。用户定义的错误号应当大于该值。例如：Err.Raise(Number) = vbObjectError + 1000

Tab

vbTab

Chr(9)

Tab 字符。

Back

vbBack

Chr(8)

退格字符。

类型转换函数
------

[https://docs.microsoft.com/zh-cn/office/vba/language/concepts/getting-started/type-conversion-functions](https://docs.microsoft.com/zh-cn/office/vba/language/concepts/getting-started/type-conversion-functions)

该函数名称确定了返回类型，如下所示：

功能

返回类型

\_表达式\_参数的范围

**CBool**

[Boolean](https://docs.microsoft.com/zh-cn/office/vba/language/reference/user-interface-help/boolean-data-type)

任何有效的“字符串”\*\*\*\* 或数值型表达式。

**CByte**

[Byte](https://docs.microsoft.com/zh-cn/office/vba/language/reference/user-interface-help/byte-data-type)

0 到 255.

**CCur**

[Currency](https://docs.microsoft.com/zh-cn/office/vba/language/reference/user-interface-help/currency-data-type)

\-922,337,203,685,477.5808 到 922,337,203,685,477.5807。

**CDate**

[Date](https://docs.microsoft.com/zh-cn/office/vba/language/reference/user-interface-help/date-data-type)

任何有效的日期表达式。

**CDbl**

[Double](https://docs.microsoft.com/zh-cn/office/vba/language/reference/user-interface-help/double-data-type)

负值为 -1.79769313486231E308 到 -4.94065645841247E-324；正值为 4.94065645841247E-324 到 1.79769313486232E308。

**CDec**

[Decimal](https://docs.microsoft.com/zh-cn/office/vba/language/reference/user-interface-help/decimal-data-type)

零缩放数（即数字中没有小数位）为 79,228,162,514,264,337,593,543,950,335。 有 28 个小数位的数字的范围为 7.9228162514264337593543950335。 最小的非零数字为 0.0000000000000000000000000001。

**CInt**

[Integer](https://docs.microsoft.com/zh-cn/office/vba/language/reference/user-interface-help/integer-data-type)

\-32,768 到 32,767；分数四舍五入。

**CLng**

[Long](https://docs.microsoft.com/zh-cn/office/vba/language/reference/user-interface-help/long-data-type)

\-2,147,483,648 到 2,147,483,647；分数四舍五入。

**CLngLng**

[LongLong](https://docs.microsoft.com/zh-cn/office/vba/language/reference/user-interface-help/longlong-data-type)

\-9,223,372,036,854,775,808 至 9,223,372,036,854,775,807，分数四舍五入。 （仅在 64 位平台上有效。）

**CLngPtr**

[LongPtr](https://docs.microsoft.com/zh-cn/office/vba/language/reference/user-interface-help/longptr-data-type)

32 位系统上为 -2,147,483,648 到 2,147,483,647，64 位系统上为 -9,223,372,036,854,775,808 到 9,223,372,036,854,775,807；32 位系统和 64 位系统分数都四舍五入。

**CSng**

[Single](https://docs.microsoft.com/zh-cn/office/vba/language/reference/user-interface-help/single-data-type)

负值为 -3.402823E38 到 -1.401298E-45；正值为 1.401298E-45 到 3.402823E38。

**CStr**

[String](https://docs.microsoft.com/zh-cn/office/vba/language/reference/user-interface-help/string-data-type)

CStr 的返回值取决于 _expression_ 参数。

**CVar**

[Variant](https://docs.microsoft.com/zh-cn/office/vba/language/reference/user-interface-help/variant-data-type)

和“Double”\*\*\*\* 针对数值型的范围相同。 和“字符串”\*\*\*\* 针对非数值型的范围相同。