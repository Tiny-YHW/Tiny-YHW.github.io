---
title: 'Display->Layer Visibility层叠显示快捷切换，自定义层叠的保存及调用'
date: Tue, 27 Dec 2022 08:22:45 +0000
draft: false
tags: ['TY-Skill']
---

功能说明
----

多种层叠的快捷切换方式

快捷切换查看Artwork层叠

用户自定义层叠模版的保存和再调用

操作说明
----

使用菜单或者命令启动弹出功能对话框

### 信号（导体）相关层的快捷切换

![](https://a1024.synology.me:222/images/blog2023/Snipaste_2022-12-27_15-53-03.png)

*   标签页选择到Etch
*   Conductors选框用于打开或隐藏对应层
*   Planes选框用于打开或隐藏对应层
*   Single select下方选择对应层，视图将以单层形式显示对应层
*   Multi select下方选择对应层，视图将显示对应的1个或多个层叠
    *   直接单击为单层选择
    *   按住Shift为连续选择连续的多个层
    *   按住Ctrl为打开或关闭单击的一个层
*   Toggle select下方几个层通过单击打开或关闭层的选择，被选择的层将于单层或多层显示时同步进行切换

Non-Etch标签页与Etch类似不再赘述

### 默认配置层的配置和切换

#### 方式1 global按钮

![](https://a1024.synology.me:222/images/blog2023/Snipaste_2022-12-27_16-01-46.png)

*   从对话框下方选择Global
*   选择Restore相关的层面，视图将切换为指定的层
*   设置好当前的视图后，点击Save view可将自己配置的层保存，方便再次调用

#### 方式2 views便签页

![](https://a1024.synology.me:222/images/blog2023/Snipaste_2022-12-27_16-05-29.png)

*   选择Views标签页
*   选择对应的Directory以及子目录（右侧多选列表）的对应的view名称，视图将切换为指定的层
*   下方Create new view directory按钮用于新建一个Directory（可以视为一个分类）
*   下方Save new wiew用于将当前视图存储到选择的Directory中
*   Delete .view dir按钮用于删除选中的Directory
*   Delete .view file按钮用于删除选中的view文件

#### 打开或关闭所有层

对话框底端All on和All off按钮用于打开或关闭设计中的所有层

Artwork
-------

选择Artwork标签页可进行以下几个功能，不是很常用，不做详细介绍了

按Artwork显示层叠，移除当前Artwork film和按模版创建Artwork film，指定未定义线宽值，叠层报告等功能