---
title: 'Excel VBA对象'
date: Thu, 02 Apr 2020 03:24:05 +0000
draft: false
tags: ['Excel+VBA']
---

使用VBA进行编程时，用户将要处理的重要对象很少。下面是一些常见的对象 -

*   应用程序对象
*   工作簿对象
*   工作表对象
*   范围对象

应用程序对象
------

应用程序对象由以下部分组成 -

*   应用程序范围的设置和选项。
*   返回顶级对象的方法，比如`ActiveCell`，`ActiveSheet`等等。

**示例**

```
'Example 1 :
Set xlapp = CreateObject("Excel.Sheet") 
xlapp.Application.Workbooks.Open "C:\test.xls"

'Example 2 :
Application.Windows("test.xls").Activate

'Example 3:
Application.ActiveCell.Font.Bold = True 
```

工作簿对象
-----

`Workbook`对象是`Workbooks`集合的成员，并包含当前在_Microsoft Excel_中打开的所有`Workbook`对象。

**示例**

```
'Ex 1 : To close Workbooks
Workbooks.Close

'Ex 2 : To Add an Empty Work Book
Workbooks.Add

'Ex 3: To Open a Workbook
Workbooks.Open FileName:="Test.xls", ReadOnly:=True

'Ex : 4 - To Activate WorkBooks
Workbooks("Test.xls").Worksheets("Sheet1").Activate 
```

工作表对象
-----

工作表对象是工作表集合的成员，并包含工作簿中的所有工作表对象。

**示例**

```
'Ex 1 : To make it Invisible
Worksheets(1).Visible = False

'Ex 2 : To protect an WorkSheet
Worksheets("Sheet1").Protect password:=strPassword, scenarios:=True 
```

范围对象
----

`Range`对象表示单元格，行，列或包含一个或多个连续单元格块的单元格的选择。

```
'Ex 1 : To Put a value in the cell A5
Worksheets("Sheet1").Range("A5").Value = "5235"

'Ex 2 : To put a value in range of Cells
Worksheets("Sheet1").Range("A1:A4").Value = 5
```

### sheet表达

```
Sheet1.Select
ThisWorkbook.Sheets(2).Select  ’2表示第2个Sheet，下标从1开始
```

### 单元格

```
[A1]
Range("A1").Select
Cells(1, 1)
ThisWorkbook.Sheets(1).Cells(rowNum, colNum)
ThisWorkbook.Sheets(7).Range("A" & rowNum)
```

### Excel所在路径

```
fn = ThisWorkbook.Path
```

### **范围**

```
Arr = [a1].CurrentRegion'选中a1，Ctrl+A
```

### 为对象增加超链接

Hyperlinks.Add 方法

向指定的区域或形状添加超链接。

#### 语法

_expression_.**Add** (_Anchor_, _Address_, _SubAddress_, _ScreenTip_, _TextToDisplay_)

_expression_：一个表示 **[Hyperlinks](https://docs.microsoft.com/zh-cn/office/vba/api/excel.hyperlinks)** 对象的变量。

#### Parameters

名称

必需/可选

数据类型

说明

_Anchor_

必需

**Object**

超链接的定位标记。 可为 **[Range](https://docs.microsoft.com/zh-cn/office/vba/api/excel.range(object))** 或 **[Shape](https://docs.microsoft.com/zh-cn/office/vba/api/excel.shape)** 对象。

_Address_

必需

**String**

超链接的地址。

_SubAddress_

可选

**Variant**

超链接的子地址。

_ScreenTip_

可选

**Variant**

当鼠标指针停留在超链接上时所显示的屏幕提示。

_TextToDisplay_

可选

**Variant**

要为超链接显示的文本。

#### 返回值

一个 **[Hyperlink](https://docs.microsoft.com/zh-cn/office/vba/api/excel.hyperlink)** 对象，它代表新的超链接。

#### 注解

指定 **TextToDisplay** 参数时，文本必须是字符串。

#### 示例

此示例向单元格 A5 添加超链接。VB复制

```
With Worksheets(1) 
 .Hyperlinks.Add Anchor:=.Range("a5"), _ 
 Address:="https://example.microsoft.com", _ 
 ScreenTip:="Microsoft Web Site", _ 
 TextToDisplay:="Microsoft" 
End With 
```

此示例向单元格 A5 添加一个电子邮件超链接。VB复制

```
With Worksheets(1) 
 .Hyperlinks.Add Anchor:=.Range("a5"), _ 
 Address:="mailto:someone@example.com?subject=hello", _ 
 ScreenTip:="Write us today", _ 
 TextToDisplay:="Support" 
End With 
```