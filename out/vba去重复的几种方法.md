---
title: 'VBA去重复的几种方法'
date: Thu, 16 Apr 2020 07:08:16 +0000
draft: false
tags: ['Excel+VBA']
---

几种方法，前两种速度较慢，后两种较快，第四种需要03以上版本支持。若有其它方法，请不吝赐教。

```
Sub 矩形1_Click()
    i = Range("A65536").End(xlUp).Row
    For s = 1 To i
    For ss = i To s + 1 Step -1
    If Cells(ss, 1) = Cells(s, 1) Then
    Cells(ss, 1).Delete shift:=xlUp
    End If
    Next ss
    Next s
End Sub
Sub 矩形2_Click()
    i = Range("A65536").End(xlUp).Row
    For s = i To 1 Step -1
    If Application.WorksheetFunction.CountIf(Range(Cells(1, 1), Cells(s, 1)), Cells(s, 1)) > 1 Then
    Cells(s, 1).Delete shift:=xlUp
    End If
    Next
End Sub
Sub 矩形3_Click()
    i = Range("A65536").End(xlUp).Row
    Dim dic As Object, ii&, arr, ra
    Set dic = CreateObject("Scripting.Dictionary")
    arr = Range("a1:a" & i)
    For ii = 1 To UBound(arr)
        ra = dic(arr(ii, 1))
    Next
    Range("a:a").ClearContents
    Range("a1").Resize(dic.Count, 1) = Application.Transpose(dic.Keys)
End Sub
Sub 矩形4_Click()
Columns(1).RemoveDuplicates 1
End Sub
```

[案例下载](blob:https://a1024.synology.me:1024/dcbe6f17-3942-49f1-b033-a7549d468cf5)[下载](blob:https://a1024.synology.me:1024/dcbe6f17-3942-49f1-b033-a7549d468cf5)