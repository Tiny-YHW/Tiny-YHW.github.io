---
title: 'Excel 2016 打开后空白的解决方法'
date: Sat, 11 Apr 2020 08:28:05 +0000
draft: false
tags: ['Excel+VBA']
---

**修改注册表：**

使用快捷键**Windows + R**进入**运行，**输入**regedit**，然后**确定**或**回车**进入到**注册表编辑器**

找要修改的位置(可复制粘贴)：**HKEY\_CLASSES\_ROOT\\Excel.Sheet.12\\shell\\Open\\command **

将默认数值数据中最后的 /dde 修改为 "%1" 后确定，即将"E:\\SoftwareInstallation\\Microsoft Office 2016\\Microsoft Office\\Root\\Office16\\EXCEL.EXE" /dde 修改为"E:\\SoftwareInstallation\\Microsoft Office 2016\\Microsoft Office\\Root\\Office16\\EXCEL.EXE" "%1"

（注意"%1"和前面之间有空格，双引号是英文状态的）：

如果xls格式一起修改，按下面操作

在**注册表编辑器**中找到路径**HKEY\_CLASSES\_ROOT\\.xls**，修改其中的**默认**项，将**默认**项的值**Excel.Sheet.8**修改为**Excel.Sheet.12**即可：