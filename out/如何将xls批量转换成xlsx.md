---
title: '如何将xls批量转换成xlsx'
date: Sat, 04 Jul 2020 09:20:06 +0000
draft: false
tags: ['Excel+VBA']
---

下面是单个xls转换成xlsx的步骤，相信大家都知道

1\. 点击“文件”，然后选择“另存为”，并保存到桌面

2.然后点击“保存类型”，选择“Excel 97-2003工作簿”，然后点“保存

但是我有100个文件，能不能批量操作？

答：当然可以，只要用VBA代码就能按上面的操作自动执行100次，帮你批量将.xls转化成.xlsx。

具体操作请看下方动图

![](http://leiniao-article.oss-cn-shanghai.aliyuncs.com/1536172871460_article "imageFile")

VBA代码如下（复制即可）：

```
'***********访问当前文件夹下所有子文件夹及文件,
Dim iFile(1 To 100000) As String
Dim count As Integer
Sub xls2xlsx()
    iPath = ThisWorkbook.Path
    On Error Resume Next
    count = 0
    zdir iPath
    For i = 1 To count
        If iFile(i) Like "*.xls" And iFile(i) <> ThisWorkbook.FullName Then
            MyFile = iFile(i)
            FilePath = Replace(MyFile, ".xls", ".xlsx")
            If Dir(FilePath, 16) = Empty Then
                Set WBookOther = Workbooks.Open(MyFile)
                Application.ScreenUpdating = False
                ActiveWorkbook.SaveAs Filename:=FilePath, FileFormat:=xlOpenXMLWorkbook, CreateBackup:=False
                WBookOther.Close SaveChanges:=False      '解决不能close 文件问题
                Application.ScreenUpdating = True
            End If
        End If
    Next
End Sub
Sub zdir(p)       '访问当前文件夹下所有子文件夹及文件
  Set fs = CreateObject("scripting.filesystemobject")
  For Each f In fs.GetFolder(p).Files
    If f <> ThisWorkbook.FullName Then count = count + 1: iFile(count) = f
  Next
  For Each m In fs.GetFolder(p).SubFolders
      zdir m
  Next
End Sub
```