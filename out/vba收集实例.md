---
title: 'VBA+EXCEL收集实例'
date: Fri, 17 Apr 2020 09:49:20 +0000
draft: false
tags: ['Excel+VBA']
---

[VBA函数](https://docs.microsoft.com/zh-cn/office/vba/api/overview/)

模糊匹配

```
=LOOKUP(1,0/FIND(目标值,目标区域),目标区域对应行)
```

统计
--

#### 非空单元格数量

```
cellall = Application.WorksheetFunction.CountA(ThisWorkbook.Sheets("sheet1").Range("G:G"))
```

#### 工作簿使用最大行和列

```
activesheet.usedrange.rows.count
activesheet.usedrange.Columns.count
```

#### 数组长度

padn = UBound(pad)+1

Range.Find
----------

[官网解释](https://docs.microsoft.com/zh-cn/office/vba/api/excel.range.find)

案例

```
With Sheet01封装待校对.Range("e1:e" & rr1)
    Set Rng = .Find(what:=PartNumber, lookat:=xlWhole) '开始精确查找
    If Not Rng Is Nothing Then
    fadd = Rng.Address
        Do
        rr = Rng.Row
 
        Set Rng = .FindNext(Rng)
        Loop While Not Rng Is Nothing And Rng.Address <> fadd
    End If
End With
```

读写文件
----

#### 从文件读取内容

```
Open file For Input As #1
ttext = Split(StrConv(InputB(LOF(1), #1), vbUnicode), vbCrLf)
Close #1
```

#### 将写内容到文件

```
Open padmfile For Output As #1
For i = 0 To padn
Print #1, pad(i)
Next
Close #1
```

#### 将内容增加到文件

```
Open padmfile For Append  As #1
For i = 0 To padn
Print #1, pad(i)
Next
Close #1
```

读取另外一个Excel的数据内容
----------------

#### 不打开Excel

```
Set dataExcel = CreateObject("Excel.Application")
file = "C:\Users\Administrator\Desktop\Book3.xlsx"
Set Workbook = dataExcel.Workbooks.Open(file，ReadOnly)'只读读取
Set Sheet = Workbook.Worksheets(1)shee = Sheet.Cells(1, 1)
Workbook.Close 0'不保存
```

#### 为单元格添加超链接

```
ThisWorkbook.Sheets("sheet1").Hyperlinks.Add Anchor:=Cells(1, 2), Address:=Cells(1, 2) 
```

#### 字典去重

```
Set dic = CreateObject("Scripting.Dictionary")
i = Range("B65536").End(xlUp).Row
arr = Range("B2:B" & i)
For ii = 1 To UBound(arr)
ra = dic(arr(ii, 1))
Next
'[e1].Resize(dic.Count, 1) = Application.Transpose(dic.Keys)
padnamelist = Application.Transpose(dic.Keys)
```

#### 弹出对话框

[更多详情](https://a1024.synology.me:1024/vba%e6%b6%88%e6%81%af%e6%a1%86%ef%bc%88msgbox%ef%bc%89/)

```
MsgBox ("已生成文件名为name_new.hkp的新文件")
```

#### vba获取子目录或其所有文件遍历getSubDirs

[vba获取子目录或其所有文件遍历getSubDirs](https://a1024.synology.me:1024/wp-content/uploads/2020/04/vba获取子目录或其所有文件遍历getSubDirs.zip)[下载](https://a1024.synology.me:1024/wp-content/uploads/2020/04/vba获取子目录或其所有文件遍历getSubDirs.zip)

EXCEL
=====

判断有无字母A-Z

\=IF(A2="","",IF(SUMPRODUCT((CODE(MID(A2,ROW(INDIRECT("1:"&LEN(A2))),1))>=65)\*(CODE(MID(A2,ROW(INDIRECT("1:"&LEN(A2))),1))<=122))>=1,"有","无"))