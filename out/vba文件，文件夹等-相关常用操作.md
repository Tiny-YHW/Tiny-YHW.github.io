---
title: 'VBA文件，文件夹等 相关常用操作'
date: Fri, 17 Apr 2020 11:20:30 +0000
draft: false
tags: ['Excel+VBA']
---

[http://club.excelhome.net/thread-1258425-1-1.html](http://club.excelhome.net/thread-1258425-1-1.html)

判断文件，文件夹等是否存在
-------------

### 文件是否存在（File exists）：

```
Sub FileExists()
    Dim fso
    Set fso = CreateObject("Scripting.FileSystemObject")
    If fso.FileExists("D:\test.txt") = True Then
        MsgBox "The file is exists."
    Else
        MsgBox "The file isn't exists."
    End If
End Sub 
```

### 文件夹是否存在（Folder exists）：

```
Sub FolderExists()
    Dim fso
    Set fso = CreateObject("Scripting.FileSystemObject")
    If fso.FolderExists("D:\testFolder") = True Then
        MsgBox "The folder is exists."
    Else
        MsgBox "The folder isn't exists."
    End If
End Sub 
```

### 硬盘是否存在（Drive exists）：

```
Sub DriveExists()
    Dim fso
    Set fso = CreateObject("Scripting.FileSystemObject")
    If fso.DriveExists("D:\") = True Then
        MsgBox "The drive is exists."
    Else
        MsgBox "The drive isn't exists."
    End If
End Sub 
```

文件相关操作
------

### 文件复制（File copy）：

```
Sub CopyFile()
    Dim fso
    Set fso = CreateObject("Scripting.FileSystemObject")
    fso.CopyFile "c:\Makro.txt", "c:\Macros\"
End Sub
```

### 文件移动（File move）：

```
Sub MoveFile()
    Dim fso
    Set fso = CreateObject("Scripting.FileSystemObject")
    fso.MoveFile "c:\*.txt", "c:\Documents and Settings\"
End Sub 
```

### 文件删除（File delete）：

```
Sub DeleteFile()
    Dim fso
    Set fso = CreateObject("Scripting.FileSystemObject")
    fso.DeleteFile "c:\Documents and Settings\Macros\Makro.txt"
End Sub
```

### 获取某文件夹下的所有Excel文件

```
Sub getExcelFile(sFolderPath As String)
On Error Resume Next
Dim f As String
Dim file() As String
Dim x
k = 1
ReDim file(1)
file(1) = sFolderPath & ""
f = Dir(file(1) & "*.xlsx")     '通配符*.*表示所有文件，*.xlsx Excel文件
Do Until f = ""
   'Range("a" & x) = f
   Range("a" & x).Hyperlinks.Add Anchor:=Range("a" & x), Address:=file(i) & f, TextToDisplay:=f
    x = x + 1
    f = Dir
Loop
End Sub
```

### 获取某文件夹下的所有文件和子目录下的文件

```
Sub getAllFile(sFolderPath As String)
'Columns(1).Delete
On Error Resume Next
Dim f As String
Dim file() As String
Dim i, k, x
x = 1
i = 1
k = 1

ReDim file(1 To i)
file(1) = sFolderPath & ""

'-- 获得所有子目录
Do Until i > k
f = Dir(file(i), vbDirectory)
Do Until f = ""
If InStr(f, ".") = 0 Then
k = k + 1
ReDim Preserve file(1 To k)
file(k) = file(i) & f & ""
End If
f = Dir
Loop
i = i + 1
Loop

'-- 获得所有子目录下的所有文件
For i = 1 To k
f = Dir(file(i) & ".") '通配符.表示所有文件，*.xlsx Excel文件
Do Until f = ""
'Range("a" & x) = f
Range("a" & x).Hyperlinks.Add Anchor:=Range("a" & x), Address:=file(i) & f, TextToDisplay:=f
x = x + 1
f = Dir
Loop
Next
End Sub
```

### 获取指定路径下的文件夹名称

```
Sub getfoldername() 
Dim fs As Object
n = 1
Set fs = CreateObject("Scripting.FileSystemObject")
Set f = fs.getfolder("C:\Users\Administrator\Desktop")
For Each fd In f.subfolders
Cells(n, 1) = fd.Name
n = n + 1
Next
Set f = Nothing
Set fs = Nothing
End Sub
```

文件夹相关操作
-------

### 创建文件夹（Folder create）：

```
Sub CreateFolder()
    Dim fso as Scripting.FileSystemObject
    Set fso = CreateObject("Scripting.FileSystemObject")
    fso.CreateFolder "c:\Documents and Settings\NewFolder"
End Sub 
```

### 复制文件夹（Folder copy）：

```
Sub CopyFolder()
    Dim fso as Scripting.FileSystemObject
    Set fso = CreateObject("Scripting.FileSystemObject")
    fso.CopyFolder "C:\Documents and Settings\NewFolder", "C:\"
End Sub 
```

### 移动文件夹（Folder move）：

```
Sub MoveFolder()
    Dim fso as Scripting.FileSystemObject
    Set fso = CreateObject("Scripting.FileSystemObject")
    fso.MoveFolder "C:\Documents and Settings\NewFolder", "C:\"
End Sub 
```

### 文件夹重命名

```
Sub NA()
 Set aa = CreateObject("Scripting.FileSystemObject")
  aa.MoveFolder "D:\1", "D:\2"
End Sub
```

### 删除文件夹（Folder delete）：

```
Sub DeleteFolder()
    Dim fso as Scripting.FileSystemObject
    Set fso = CreateObject("Scripting.FileSystemObject")
    fso.DeleteFolder "C:\Documents and Settings\NewFolder"
End Sub 
```

### 打开文件夹

```
Sub exceloffice()
    Dim sPath As String
    sPath = "c:\test"
    Shell "explorer.exe " & sPath, vbMaximizedFocus
End Sub
```

其他操作（获取文件名等）
------------

### 获取文件全名，带有后缀（Get file name）

```
Sub GetFileName()
    Dim fso as Scripting.FileSystemObject
    Set fso = CreateObject("Scripting.FileSystemObject")
    MsgBox fso.GetFileName("c:\Documents and Settings\Makro.txt")   ' Makro.txt
End Sub 
```

### 获取文件名，无后缀（Get base name）

```
Sub GetBaseName()
    Dim fso as Scripting.FileSystemObject
    Set fso = CreateObject("Scripting.FileSystemObject")
    MsgBox fso.GetBaseName("c:\Documents and Settings\Makro.txt")   ' Makro
End Sub 
```

### 获取文件后缀格式（Get extension name）

```
Sub GetExtensionName()
    Dim fso as Scripting.FileSystemObject
    Set fso = CreateObject("Scripting.FileSystemObject")
    MsgBox fso.GetExtensionName("c:\Documents and Settings\Makro.txt")  ' txt
End Sub 
```

### 获取盘符名（Get drive name）

```
Sub GetDriveName()
    Dim fso as Scripting.FileSystemObject
    Set fso = CreateObject("Scripting.FileSystemObject")
    MsgBox fso.GetDriveName("c:\Documents and Settings\Makro.txt")  ' c:
End Sub
```

提取多层文件夹内文件名
-----------

```
 Sub AutoAddLink()
    Dim strFldPath As String
    With Application.FileDialog(msoFileDialogFolderPicker)
    '用户选择指定文件夹
        .Title = "请选择指定文件夹。"
        If .Show Then strFldPath = .SelectedItems(1) Else Exit Sub
        '未选择文件夹则退出程序，否则将地址赋予变量strFldPath
    End With
    Application.ScreenUpdating = False
    '关闭屏幕刷新
    Range("a:b").ClearContents
    Range("a1:b1") = Array("文件夹", "文件名")
    Call SearchFileToHyperlinks(strFldPath)
    '调取自定义函数SearchFileToHyperlinks
    Range("a:b").EntireColumn.AutoFit
    '自动列宽
    Application.ScreenUpdating = True
    '重开屏幕刷新
End Sub
Function SearchFileToHyperlinks(ByVal strFldPath As String) As String
    Dim objFld As Object
    Dim objFile As Object
    Dim objSubFld As Object
    Dim strFilePath As String
    Dim lngLastRow As Long
    Dim intNum As Integer
    Set objFld = CreateObject("Scripting.FileSystemObject").GetFolder(strFldPath)
    '创建FileSystemObject对象引用
    For Each objFile In objFld.Files
    '遍历文件夹内的文件
        lngLastRow = Cells(Rows.Count, 1).End(xlUp).Row + 1
        strFilePath = objFile.Path
        intNum = InStrRev(strFilePath, "\")
        '使用instrrev函数获取最后文件夹名截至的位置
        Cells(lngLastRow, 1) = Left(strFilePath, intNum - 1)
        '文件夹地址
        Cells(lngLastRow, 2) = Mid(strFilePath, intNum + 1)
        '文件名
        ActiveSheet.Hyperlinks.Add Anchor:=Cells(lngLastRow, 2), _
                    Address:=strFilePath, ScreenTip:=strFilePath
        '添加超链接
    Next objFile
    For Each objSubFld In objFld.SubFolders
    '遍历文件夹内的子文件夹
        Call SearchFileToHyperlinks(objSubFld.Path)
    Next objSubFld
    Set objFld = Nothing
    Set objFile = Nothing
    Set objSubFld = Nothing
End Function
```

![](https://mmbiz.qpic.cn/mmbiz_png/SbWgux809jUiaRUCP5HkGK1xYibInr5sQwZJYO4AcHicI6v6by597ADCt6hkNsc2YzqfrttR2huFvc1bslbFj28VQ/640?wx_fmt=png&tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)