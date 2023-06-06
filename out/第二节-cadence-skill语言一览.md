---
title: 'Cadence SKILL 第二节 语言一览'
date: Thu, 02 Apr 2020 05:20:46 +0000
draft: false
tags: ['Allegro', 'Allegro Skill']
---

摘录自[电子布局网](http://www.eelayout.com/)

本节将介绍新的术语，并概览一下Cadence的框架环境。它探讨了SKILL数据，函数调用，变量和运算符，然后告诉你如何解决一些常见问题。虽然每个应用程序都定义了SKILL接口的详细信息，但是当给出实例时，这个文件通常指向Cadence Design Framework II（设计框架II）环境

SKILL是在Cadence环境的命令语言。每当你使用forms, menus, and bindkeys（窗体，菜单和bindkeys），Cadence的软件触发SKILL函数来完成您的任务。

其他SKILL函数计算或获取来自Cadence的框架环境或设计的数据。例如，SKILL函数可以检索当前窗口的边框或获取层面上的所有shape（Allegro中的数据对象之一）的list（列表）。  
您可以直接在命令行中输入SKILL函数绕过图形用户界面。

1 术语与定义
-------

### **output**

SKILL输出的目标可以是一个xterm屏幕，设计窗口，文件，或在许多情况下的命令解释器窗口（CIW）。

### ****CIW  （Linux环境下）****

许多Cadence应用的启动窗口，包含一个输入行，输出区域，启动各种工具命令的菜单栏，以及一般信息的提示。 CIW的输出区域是许多本手册中使用的例子的目的地。

### ****SKILL interpreter （SKILL解释器）****

技能解释器执行Cadence环境中的SKILL程序。解释器将SKILL程序的文本源代码转换成内部数据结构，在程序执行期间，which it actively consults。

### ****compiler （编译器）****

A compiler translates source code into a target representation, which might be machine instructions or an intermediate instruction set .  
一个编译器将源代码转换成目标代码，这或许是机器指令抑或中间指令集。

### ****SKILL Function （SKILL函数）****

A named, parameterizable body of one or more SKILL expressions. You can invoke any SKILL function from the command input line available in the application by using its name and providing appropriate parameters.  
一个命名的包含一条或多条SKILL语句的参数体。您可以在应用程序中通过命令输入行使用它的名字或提供正确的参数来调用任何SKILL函数。

### ****SKILL procedure****

  This term is used interchangeably with SKILL function.

**2 SKILL函数调用**
---------------

有许多方法来提交一个SKILL函数到SKILL解释器进行赋值。在许多应用中，只要您使用forms, menus, and bindkeys，Cadence的软件触发相应的SKILL函数来完成你的任务。通常情况下，你不需要关注SKILL函数或任何语法问题。

### ****Bindkeys （捆绑键---就是快捷键）****

一个bindkey将SKILL函数关联到一个键盘事件。当您激发键盘事件，Cadence的软件将SKILL函数发送SKILL解释器进行赋值执行。

### ****form（窗体）****

有些函数需要你提供数据在弹出窗体填写。 

### ****menu（菜单）****

当您在菜单中选择一个项目时，系统会发送SKILL函数发送SKILL解释器进行赋值执行。

### ****CIW****

您可以在CIW直接输入一个SKILL函数即时赋值执行。

### ****SKILL  Process****

您可以启动一个独立的UNIX进程，可以直接提交SKILL函数到SKILL解释器。 您可以通过加载SKILL源代码文件提交Skill函数的集合来赋值执行。

**3 返回值是什么**
------------

所有SKILL函数计算数据值被作为函数的返回值。您可以将返回值赋值给一个SKILL变量或将返回值传递给另一个SKILL函数，任何类型的数据可以是一个返回值。SKILL支持多种数据类型，包括integers, text strings, and lists（整数，文本字符串和列表）。

4 Simplest SKILL Data
---------------------

 最简单的SKILL语句是一个数据项. SKILL数据区分大小写。You can enter data in many familiar ways, including the following。

**Data Type**

**Syntax Example**

integer

5

floating point

5.3

text string

"Mary had a little lamb"

**5 如何调用一个函数？**
---------------

函数名是区分大小写的。要调用一个函数，要说明其名称和一对括号中的参数。“=>”后面的内容为执行后的内容

```
strcat( "Mary" " had" " a" " little" " lamb" )
=> "Mary had a little lamb"
```

*   在函数名和左括号之间不允许有空格。
*   几个函数调用可以在一行上。使用空格将它们分开。
*   你可以在命令行或者一个源代码文件中跨越多行。
*   当您输入在一行中的几个函数调用，系统只显示来自最后一个函数调用返回的结果。

6 运算符
-----

SKILL提供许多运算符。每个运算符对应一个SKILL函数.下面是运算符的一些例子：

**Operators in  
Descending  
Precedence**

**Underlying  
Function**

**Operation**

\*\*

expt （乘方）

arithmetic

\*  
/

times  
quotient

arithmetic

+  
\-

plus  
difference

arithmetic

++s  
s++

preincrement  
postincrement

arithmetic

\==  
!=

equal  
nequal

tests for equality  
tests for inequality

\=

setq

assignment

下面的例子显示在单行用运算符对几个函数/功能的调用 。调用通过**空格**彼此独立。 系统只显示最后调用函数的返回值。

```
x = 5 y = 6 x+y
=> 11
```

**7 使用变量**
----------

你并不需要在SKILL中声明变量。SKILL创建一个变量，在一个session（会话）中第一次遇到该变量时。变量名可以包含字母数字字符、下划线（\_）、问号

 变量的第一个字符不能是数字。使用赋值运算符来给一个变量存储一个值。你可以输入变量名来或得它的值。该类型的SKILL函数返回变量的当前值的数据类型。

```
lineCount = 4            => 4
lineCount                => 4
type( lineCount )        => fixnum
lineCount = "abc"        => "abc"
lineCount                => "abc"
type( lineCount )        => string 
```

**8 另一种方式输入功能**
---------------

除了通过声明函数名字以及一对括号中的参数调用一个函数外，如下面所示，你可以使用另外两种语法形式来调用SKILL函数。

```
strcat( "Mary" " had" " a" " little" " lamb" ) 
```

您可以将左括号放到函数名的左边(Lisp 方式语法).

```
( strcat "Mary" " had" " a" " little" " lamb" ) => "Mary had a little lamb"
```

在SKILL函数处于顶层时，您可以省略外部的括号（if the SKILL function is the first element at your SKILL prompt, that is, at the top level.）除了通过声明函数名字以及一对括号中的参数调用一个函数外，如下面所示，你可以使用另外两种语法形式来调用SKILL函数。

```
strcat "Mary" " had" " a" " little" " lamb" => "Mary had a little lamb"
```

以上三种样式皆可以用，编程时建议一致，推荐第一种样式。

9 处理几个常见问题
----------

### **1.系统不响应**

如果您键入一个函数且触发返回后什么都没有发生，那很可能存在下面问题。 

*   不平衡的括号 
*   不平衡的字符串引号

您或许输入的左括号多余右括号。下面的步骤大部分情况下都能触发系统响应。

*   键入右方括号( \] ) 。 这个符号可以代替所有外部的右括号；
*   如果还不能获得响应，您可以键入双引号(")后跟着键入右方括号 ( \] )，也就是("\])

### **2.不恰当的空格**

不要在函数名和左括号间输入空格. 注意下面的错误不提示多余的空格

```
strcat ( "Mary" " had" " a" " little" " lamb") Message: \*Error\* eval: not a function - "Mary"
``````
greeting = strcat ( "happy" " birthday" ) Message: \*Error\* eval: unbound variable - strcat
```

### **3.数据类型不匹配**

 当您输入一个不正确的数据给一个SKILL函数会发生错误。 错误信息会提示数据类型错误。

```
strcat( "Mary had a" 5 ) Message: \*Error\* strcat: argument #2 should be either a string or a symbol (type template = "S") - 5
```