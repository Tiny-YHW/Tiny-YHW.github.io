---
layout: post
title: Windows 10如何找回自带的照片查看器
categories: Windows
description: 
date: 2023-06-26
permalink: windows-photo
excerpt: Windows 10如何找回自带的照片查看器
---

任意处新建一个文本文档输入以下代码
```
Windows Registry Editor Version 5.00
; Change Extension's File Type
[HKEY_CURRENT_USER\Software\Classes\.jpg]
@="PhotoViewer.FileAssoc.Tiff"
; Change Extension's File Type
[HKEY_CURRENT_USER\Software\Classes\.jpeg]
@="PhotoViewer.FileAssoc.Tiff"
; Change Extension's File Type
[HKEY_CURRENT_USER\Software\Classes\.gif]
@="PhotoViewer.FileAssoc.Tiff"
; Change Extension's File Type
[HKEY_CURRENT_USER\Software\Classes\.png]
@="PhotoViewer.FileAssoc.Tiff"
; Change Extension's File Type
[HKEY_CURRENT_USER\Software\Classes\.bmp]
@="PhotoViewer.FileAssoc.Tiff"
; Change Extension's File Type
[HKEY_CURRENT_USER\Software\Classes\.tiff]
@="PhotoViewer.FileAssoc.Tiff"
; Change Extension's File Type
[HKEY_CURRENT_USER\Software\Classes\.ico]
@="PhotoViewer.FileAssoc.Tiff"
```

文本文档后缀改为`.reg`后双击运行

提醒我们是否把它增添到注册表中，我们点击确定，接着就会提醒你已经成功添加到注册表中了

再打开图片即可