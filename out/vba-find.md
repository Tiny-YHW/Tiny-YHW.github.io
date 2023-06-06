---
title: 'VBA find'
date: Tue, 26 May 2020 01:05:47 +0000
draft: false
tags: ['Excel+VBA']
---

[https://docs.microsoft.com/en-us/office/vba/api/excel.range.find](https://docs.microsoft.com/en-us/office/vba/api/excel.range.find)

VBA中的Find方法相当于我们在工作表中的查找功能。**Find 方法**在区域中查找特定信息。

语法
--

```
<单元格区域>.Find (What，[After]，[LookIn]，[LookAt]，[SearchOrder]，[SearchDirection]，[MatchCase]，[MatchByte]，[SearchFormat])
```

\[参数说明\]
--------

*   (1)<单元格区域>，必须指定，返回一个Range对象。
*   (2)参数What，必需指定。代表所要查找的数据，可以为字符串、整数或者其它任何数据类型的数据。对应于“查找与替换”对话框中，“查找内容”文本框中的内容。
*   (3)参数After，可选。指定开始查找的位置，即从该位置所在的单元格之后向后或之前向前开始查找(也就是说，开始时不查找该位置所在的单元格，直到Find方法绕回到该单元格时，才对其内容进行查找)。所指定的位置必须是单元格区域中的单个单元格，如果未指定本参数，则将从单元格区域的左上角的单元格之后开始进行查找。
*   (4)参数LookIn，可选。指定查找的范围类型，可以为以下常量之一：xlValues、xlFormulas或者xlComments，默认值为xlFormulas。对应于“查找与替换”对话框中，“查找范围”下拉框中的选项。
*   (5)参数LookAt，可选。可以为以下常量之一：XlWhole或者xlPart，用来指定所查找的数据是与单元格内容完全匹配还是部分匹配，默认值为xlPart。对应于“查找与替换”对话框中，“单元格匹配”复选框。
*   (6)参数SearchOrder，可选。用来确定如何在单元格区域中进行查找，是以行的方式(xlByRows)查找，还是以列的方式(xlByColumns)查找，默认值为xlByRows。对应于“查找与替换”对话框中，“搜索”下拉框中的选项。
*   (7)参数SearchDirection，可选。用来确定查找的方向，即是向前查找(XlPrevious)还是向后查找(xlNext)，默认的是向后查找。
*   (8)参数MatchCase，可选。若该参数值为True，则在查找时区分大小写。默认值为False。对应于“查找与替换”对话框中，“区分大小写”复选框。
*   (9)参数MatchByter，可选。即是否区分全角或半角，在选择或安装了双字节语言时使用。若该参数为True，则双字节字符仅与双字节字符相匹配；若该参数为False，则双字节字符可匹配与其相同的单字节字符。对应于“查找与替换”对话框中，“区分全角/半角”复选框。
*   (10)参数SearchFormat，可选，指定一个确切类型的查找格式。对应于“查找与替换”对话框中，“格式”按钮。当设置带有相应格式的查找时，该参数值为True。
*   (11)在每次使用Find方法后，参数LookIn、LookAt、SearchOrder、MatchByte的设置将保存。如果下次使用本方法时，不改变或指定这些参数的值，那么该方法将使用保存的值。
*   在VBA中设置的这些参数将更改“查找与替换”对话框中的设置；同理，更改“查找与替换”对话框中的设置，也将同时更改

**返回值**
-------

一个 **[Range](ms-help://MS.EXCEL.DEV.12.2052/EXCEL.DEV/content/HV10036198.htm)** 对象，它代表第一个在其中找到该信息的单元格。

**说明**
------

如果未发现匹配项，则返回 **Nothing**。**Find** 方法不影响选定区域或当前活动的单元格。

每次使用此方法后，参数 _LookIn_、_LookAt_、_SearchOrder_ 和 _MatchByte_ 的设置都将被保存。如果下次调用此方法时不指定这些参数的值，就使用保存的值。设置这些参数将更改**“查找”**对话框中的设置，如果省略这些参数，更改**“查找”**对话框中的设置将更改使用的保存值。要避免出现这一问题，每次使用此方法时请明确设置这些参数。

使用 **[FindNext](ms-help://MS.EXCEL.DEV.12.2052/EXCEL.DEV/content/HV10035848.htm)** 和 **[FindPrevious](ms-help://MS.EXCEL.DEV.12.2052/EXCEL.DEV/content/HV10035849.htm)** 方法可重复搜索。

当搜索到指定查找区域的末尾时，此方法将绕回到区域的开始位置继续搜索。发生绕回后，要停止搜索，可保存第一个找到的单元格地址，然后测试后面找到的每个单元格地址是否与其相同。

若要对单元格进行模式更为复杂的搜索，请结合使用 `For Each...Next` 语句和 **Like** 运算符。例如，下列代码在单元格区域 A1:C5 中搜索字体名称以“Cour”开始的单元格。当 Microsoft Excel 找到匹配单元格以后，就将其字体改为 Times New Roman。

```
For Each c In [A1:C5] 
 If c.Font.Name Like "Cour*" 
 Then c.Font.Name = "Times New Roman" 
 End If
Next
```

**示例**
------

本示例在第一个工作表的单元格区域 A1:A500 中查找包含值 2 的所有单元格，并将这些单元格的值更改为 5。

```
With Worksheets(1).Range("a1:a500")
    Set c = .Find(2, lookin:=xlValues)
    If Not c Is Nothing Then
        firstAddress = c.Address
        Do
            c.Value = 5
            Set c = .FindNext(c)
        Loop While Not c Is Nothing And c.Address <> firstAddress
    End If
End With
```

### 模糊搜索多项并输出

```
Sub mm()

    Range("B7").Select
    Range(Selection, Selection.End(xlDown)).Select
    Selection.ClearContents
    Range("B4").Select

x = Sheet1.Range("A65536").End(3).Row 'x的值为A列中最来后一自个非空单元格行号
ft = Sheet3.Range("B4") '要查找的内容
Set Rng = Sheet1.Range("a2:a" & x).Find(what:=ft, lookat:=xlPart) '开始模糊查找
aaa = 7
Do Until Rng Is Nothing
rr = Rng.Row
rt = Rng.Text

Sheet3.Range("B" & aaa) = rt
aaa = aaa + 1

rr = rr + 1

Set Rng = Sheet1.Range("a" & rr & ":a" & x).FindNext
Loop


End Sub
```