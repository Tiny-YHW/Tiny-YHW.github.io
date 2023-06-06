---
title: 'VBA数组'
date: Thu, 16 Apr 2020 09:43:53 +0000
draft: false
tags: ['Excel+VBA']
---

我们都知道，一个变量是一个存储值的容器。 有时，开发人员希望一次可以在一个变量中保存多个值。 当一系列值存储在单个变量中时，则称为数组变量。

数组声明
----

数组声明的方式与声明变量相同，只是数组变量的声明使用括号。 在下面的例子中，括号里提到了数组的大小。参考以下示例 -

```
'Method 1 : Using Dim
Dim arr1()    'Without Size

'Method 2 : Mentioning the Size
Dim arr2(5)  'Declared with size of 5

'Method 3 : using 'Array' Parameter
Dim arr3
arr3 = Array("apple","Orange","Grapes") 
```

在上面代码中，

*   虽然数组大小被指定为`5`，但是当数组索引从零开始时，它可以保持`6`个值。
*   数组索引不能是负数。
*   VBScript数组可以在数组中存储任何类型的变量。因此，一个数组可以在一个数组变量中存储一个整数，字符串或字符。

赋值给数组
-----

通过为每个要分配的值指定一个数组索引值，将这些值分配给数组。它可以是一个字符串。

#### **例子**

添加一个模块并添加以下代码 -

```
Private Sub Constant_demo_Click()
   Dim arr(5)
   arr(0) = "1"           'Number as String
   arr(1) = "VBScript"    'String
   arr(2) = 100            'Number
   arr(3) = 2.45            'Decimal Number
   arr(4) = #10/07/2013#  'Date
   arr(5) = #12.45 PM#    'Time

   msgbox("Value stored in Array index 0 : " & arr(0))
   msgbox("Value stored in Array index 1 : " & arr(1))
   msgbox("Value stored in Array index 2 : " & arr(2))
   msgbox("Value stored in Array index 3 : " & arr(3))
   msgbox("Value stored in Array index 4 : " & arr(4))
   msgbox("Value stored in Array index 5 : " & arr(5))
End Sub 
```

当执行上面的函数时，它会产生下面的输出。

```
Value stored in Array index 0 : 1
Value stored in Array index 1 : VBScript
Value stored in Array index 2 : 100
Value stored in Array index 3 : 2.45
Value stored in Array index 4 : 7/10/2013
Value stored in Array index 5 : 12:45:00 PM 
```

多维数组
----

数组不仅限于一个维度，但它们最多可以有`60`个维度。 二维数组是最常用的数组。

#### 例子

在下面的例子中，一个多维数组被声明为`3`行`4`列。

```
Private Sub Constant_demo_Click()
   Dim arr(2,3) as Variant    ' Which has 3 rows and 4 columns
   arr(0,0) = "Apple" 
   arr(0,1) = "Orange"
   arr(0,2) = "Grapes"           
   arr(0,3) = "pineapple" 
   arr(1,0) = "cucumber"           
   arr(1,1) = "beans"           
   arr(1,2) = "carrot"           
   arr(1,3) = "tomato"           
   arr(2,0) = "potato"             
   arr(2,1) = "sandwitch"            
   arr(2,2) = "coffee"             
   arr(2,3) = "nuts"            

   msgbox("Value in Array index 0,1 : " &  arr(0,1))
   msgbox("Value in Array index 2,2 : " &  arr(2,2))
End Sub 
```

当执行上面的函数时，它会产生下面的输出。

```
Value stored in Array index : 0 , 1 : Orange
Value stored in Array index : 2 , 2 : coffee 
```

ReDim语句
-------

`ReDim`语句用于声明动态数组变量并分配或重新分配存储空间。

```
ReDim [Preserve] varname(subscripts) [, varname(subscripts)] 
```

**参数说明**

*   _Preserve_ - 一个可选参数，用于在更改最后一个维度的大小时保留现有数组中的数据。
*   _Varname_ - 必需的参数，表示变量的名称，应遵循标准变量命名约定。
*   _Subscripts_ - 必需的参数，表示数组的大小。

#### 例子

在下面的例子中，数组已经被重新定义，当数组的现有大小发生改变时，这些值被保存下来。

> 注意 - 调整数组的大小时，删除的元素中的数据将丢失。

```
Private Sub Constant_demo_Click()
   Dim a() as variant
   i = 0
   redim a(5)
   a(0) = "XYZ"
   a(1) = 41.25
   a(2) = 22

   REDIM PRESERVE a(7)
   For i = 3 to 7
   a(i) = i
   Next

   'to Fetch the output
   For i = 0 to ubound(a)
      Msgbox a(i)
   Next
End Sub 
```

当执行上面的函数时，它会产生下面的输出。

```
XYZ
41.25
22
3
4
5
6
7 
```

数组方法
----

VBScript中有各种内置函数，可以帮助开发人员有效地处理数组。 下面列出了与数组一起使用的所有方法。请点击方法名称来详细了解它们如何应用。

编号

方法

描述

1

[LBound](http://www.yiibai.com/vba/vba_lbound_function.html)

它返回一个整数，对应于给定数组的最小下标。

2

[UBound](http://www.yiibai.com/vba/vba_ubound_function.html)

它返回一个整数，对应于给定数组的最大下标。

3

[Split](http://www.yiibai.com/vba/vba_split_function.html)

它返回一个包含指定数量值的数组。根据分隔符分割。

4

[Join](http://www.yiibai.com/vba/vba_join_function.html)

它返回一个包含数组中指定数量的子串的字符串。这是`Split`方法的一个完全相反的功能。

5

[Filter](http://www.yiibai.com/vba/vba_filter_function.html)

它返回一个基于零的数组，该数组包含基于特定过滤条件的字符串数组的子集。

6

[IsArray](http://www.yiibai.com/vba/vba_isarray_function.html)

它返回一个布尔值，表示输入变量是否是一个数组。

7

[Erase](http://www.yiibai.com/vba/vba_erase_function.html)

为数组变量恢复分配的内存。

数组合并
----

```
Private Sub Constant_demo_Click()
   i = 0
   ReDim arr1(2)
   arr1(0) = "XYZ"
   arr1(1) = 41.25
   arr1(2) = 22

   ReDim arr2(5)
   For i = 0 To 5
   arr2(i) = i
   Next

   
ReDim arr(UBound(arr1) + UBound(arr2) + 1)
For i1 = 0 To UBound(arr1)
arr(i1) = arr1(i1)
Next
   
For i2 = i1 To UBound(arr2) + i1
arr(i2) = arr2(i2 - i1)
Next

End Sub
```