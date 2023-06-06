---
title: '修改Cadence系列文件默认打开方式'
date: Tue, 18 Apr 2023 02:24:30 +0000
draft: false
tags: ['Allegro']
---

switchversion.exe
-----------------

### 位置

该文件一般位于安装目录指定版本/tool/bin路径下

![Snipaste_2023-04-18_09-54-50.png](https://a1024.synology.me:222/images/Snipaste_2023-04-18_09-54-50.png)

### 切换版本

一般情况下如果安装可多个版本的Cadence软件，只要打开最高版本安装目录的switchversion文件，它里面自动包含了已经安装过的所有版本，可用于切换Cadence系列文件默认的打开版本，选择指定版本双击即可完成切换

![Snipaste_2023-04-18_09-57-52.png](https://a1024.synology.me:222/images/Snipaste_2023-04-18_09-57-52.png)

### 手动添加版本

如果缺少某个版本，可以选择Manual按钮添加指定版本

![Snipaste_2023-04-18_10-00-53.png](https://a1024.synology.me:222/images/Snipaste_2023-04-18_10-00-53.png)

### 指定后缀文件打开方式

选择File Association可以编辑指定后缀文件使用的软件，可以编辑新增或删除，如net sch后缀的文件可能我们不需要使用Cadence系列软件打开可以将其删掉，sav后缀文件我们希望使用allegro文件打开也可以对其进行新增

![Snipaste_2023-04-18_10-23-10.png](https://a1024.synology.me:222/images/Snipaste_2023-04-18_10-23-10.png)

![Snipaste_2023-04-18_10-20-53.png](https://a1024.synology.me:222/images/Snipaste_2023-04-18_10-20-53.png)