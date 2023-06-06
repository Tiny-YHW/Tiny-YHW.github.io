---
title: 'VBA 流程控制'
date: Thu, 16 Apr 2020 09:38:46 +0000
draft: false
tags: ['Excel+VBA']
---

条件语句
----

经常地，当我们编写代码时，我们需要根据不同的判断执行不同操作。我们可以使用条件语句完成这个工作。

### 在 VBScript 我们可以使用三种条件语句：

if 语句假如你希望在条件为 true 时执行一系列的代码，可以使用这个语句。if...then...else 语句假如你希望执行两套代码其中之一，可以使用这个语句。if...then...elseif 语句假如你希望选择多套代码之一来执行，可以使用这个语句。select case 语句假如你希望选择多套代码之一来执行，可以使用这个语句。

VBA提供了以下类型的决策声明。 点击以下链接来查看它们的详细信息。

编号

语句

描述

1

[if语句](http://www.yiibai.com/vba/vba_if_statement.html)

一个`if`语句由一个布尔表达式和一个或多个语句组成。

2

[if…else语句](http://www.yiibai.com/vba/vba_if_else_statement.html)

`if else`语句由一个布尔表达式和一个或多个语句组成。如果条件为`True`，则执行`If`语句下的语句。如果条件为`false`，则执行脚本的`Else`部分。

3

[if…elseif…else语句](http://www.yiibai.com/vba/vba_if_elseif_else_statement.html)

一个if语句，后跟一个或多个`else...if`语句，它由布尔表达式组成，接着是一个可选的`else`语句，当所有条件变为`false`时执行`else`语句块。

4

[嵌套if语句](http://www.yiibai.com/vba/vba_nested_if_statements.html)

一个`if`或`elseif`语句中可以嵌套另一个`if`或`elseif`语句。

5

[switch语句](http://www.yiibai.com/vba/vba_switch_statement.html)

一个`switch`语句允许一个变量与一个值列表进行测试。

If....Then.....Else
-------------------

在下面的情况中，您可以使用 If...Then...Else 语句：

*   在条件为 true 时，执行某段代码
*   选择两段代码之一来执行时

如果需要在条件为 true 时只执行一行语句，可以把代码写为一行：

```
`if` i=10 `Then` msgbox "Hello"
```

在上面的代码中，没有 .else.. 语句。我们仅仅让代码在条件为 true 时执行一项操作（当 i 为 10 时）。

假如我们需要在条件为 true 时执行不止一条语句，那么就必须在一行写一条语句，然后使用关键词 "End If" 来结束这个语句：

```
if i=10 Then
   msgbox "Hello"
   i = i+1
`end If`
```

在上面的代码中，同样没有 .else.. 语句。我们仅仅让代码在条件为 true 时执行了多项操作。

假如我们希望在条件为 true 时执行某条语句，并当条件不为 true 时执行另一条语句，就必须添加关键词 "Else"：

```
if i=10 then
   msgbox "Hello"
`else`
   msgbox "Goodbye"
end If
```

当条件为 true 时会执行第一段代码，当条件不成立时执行第二段代码（当 i 不等于 10 时）。

If....Then.....Elseif
---------------------

假如你希望选择多套代码之一来执行，可以使用if...then...elseif语句：

```
if payment="Cash" then
   msgbox "You are going to pay cash!"
 elseif payment="Visa" then
   msgbox "You are going to pay with visa."
 elseif payment="AmEx" then
   msgbox "You are going to pay with American Express."
 else
   msgbox "Unknown method of payment."
end If
```

Select Case
-----------

假如你希望选择多套代码之一来执行，可以使用 SELECT 语句：

```
select case payment
 case "Cash"
   msgbox "You are going to pay cash"
 case "Visa"
   msgbox "You are going to pay with visa"
 case "AmEx"
   msgbox "You are going to pay with American Express"
 case Else
   msgbox "Unknown method of payment"
end select
```

以上代码的工作原理：首先，我们需要一个简单的表达式（常常是一个变量），并且这个表达式会被做一次求值运算。然后，表达式的值会与每个 case 中的值作比较，如果匹配，被匹配的 case 所对应的代码会被执行。

Looping 语句
----------

经常地，当编写代码时，我们希望将一段代码执行若干次。我们可以在代码中使用循环语句来完成这项工作。

VBA提供以下类型的循环来处理循环需求。点击以下链接查看详细信息。

编号

循环类型

描述

1

[for循环](http://www.yiibai.com/vba/vba_for_loop.html)

多次执行一系列语句，缩写管理循环变量的代码。

2

[for…each循环](http://www.yiibai.com/vba/vba_foreach_loop.html)

如果组中至少有一个元素并为组中的每个元素重复执行，则执行此操作。

3

[while…wend循环](http://www.yiibai.com/vba/vba_while_wend_loop.html)

这在执行循环体之前测试条件。

4

[do…while循环](http://www.yiibai.com/vba/vba_do_while_loop.html)

`do..while`语句只要条件为`True`就会被执行(即，)循环应该被重复直到条件为`False`。

5

[do…until循环](http://www.yiibai.com/vba/vba_do_until_loop.html)

只要条件是`False`，`do..Until`语句就会被执行(即，)循环应该被重复直到条件为真。

循环控制语句
------

循环控制语句从正常顺序改变执行。 当执行离开一个作用域时，循环中的所有其余语句都不会被执行。

VBA支持以下控制语句。点击以下链接查看详细信息。

编号

控制语句

描述

1

[Exit For语句](http://www.yiibai.com/vba/vba_exit_for_statement.html)

终止For循环语句并将执行转移到循环之后的语句

2

[Exit Do语句](http://www.yiibai.com/vba/vba_exit_do_statement.html)

终止`Do While`语句并将执行转移到循环之后的语句

### 在 VBScript 中，我们可以使用四种循环语句：

For...Next 语句运行一段语句指定的次数For Each...Next 语句针对集合中的每个项目或者数组中的每个元素来运行某段语句。Do...Loop 语句运行循环，当条件为 true 或者直到条件为 true 时。While...Wend 语句不要使用这个语句 - 请使用 Do...Loop 语句代替它。

For...Next 循环
-------------

如果您已经确定需要重复执行代码的次数，那么您可以使用 For...Next 语句来运行这段代码。

我们可以使用一个计数器变量，这个变量会随着每次循环递增或递减，例如这样：

```
For i=1 to 10
  some code
Next
```

For 语句规定计数变量以及它的开始值和结束值。

Next 语句会以 1 作为步进值来递增变量i。

### Step 关键词

通过使用 Step 关键词，我们可以规定计数变量递增或递减的步进值。

在下面的例子中，计数变量i每次循环的递增步进值为 2。

```
For i=2 To 10 Step 2
  some code
Next
```

如果要递减计数变量，就必须负的步进值。并且需要规定小于开始值的结束值。

在下面的例子中，计数变量i每次循环的递减步进值为 2。

```
For i=10 To 2 Step -2
  some code
Next
```

### 退出 For...Next

如需退出 For...Next 语句，可以使用 Exit 关键词。