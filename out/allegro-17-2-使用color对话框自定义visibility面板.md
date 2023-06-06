---
title: 'Allegro 17.2 Color Dialog Enhancements颜色对话框增强功能'
date: Wed, 12 Aug 2020 09:12:57 +0000
draft: false
tags: ['Allegro']
---

下述所述功能需要在17.2及之后的版本应用

Fresh New Look全新界面
------------------

颜色对话框现在使用表格方法，并将主要要素分类到其自己的选项卡式页面中，名为Layers, Nets, Display, Favorites, and Visibility Pane.

![172-algPN-472.gif](https://a1024.synology.me:222/images/172-algPN-472.gif)

Searching Subclass Layers搜索子类图层
-------------------------------

层名称可以从Filter Layers使用通配符进行过滤，方便快速查找到指定的层

![172-algPN-473.gif](https://a1024.synology.me:222/images/172-algPN-473.gif)

Viewing Subclasses in Favorites or Visibility Pane将制定层设置为Favorites or Visibility Pane
-------------------------------------------------------------------------------------

### Favorites

Favorites相关设置跟随软件，一次设置对所有设计生效

在layer下查找对应的层需要花时间在诸多不用的层当中去找想要的层，有点眼花的感觉。用户可以根据各自要求、习惯，将常用的颜色添加到Favorites列表中，方便查看、更改颜色。

操作方法同上，右键时选择Add to Favorites.

![172-algPN-475.gif](https://a1024.synology.me:222/images/172-algPN-475.gif)

即可在Favorites标签页查看到被加入Favorites的层

![](http://a1024.synology.me:222/images/blog2022/visifav.png)

### Visibility

同理可以将指定的层通过右键选择Add to Visibility，则指定层将出现在Visibility面板，更加方便切换

![](http://a1024.synology.me:222/images/blog2022/Visibility.png)

### 使用Color对话框自定义Visibility面板

功能演示

![](https://a1024.synology.me:222/images/blog2022/10.10.gif)

在visibility面板下，可以通过自定义层来实现快速切换。如上图，相比默认视图，多了下面红框中的Class/Subclass（User select）部分。

红框部分，可以快速切换一些单独的图层，如：DXF，outline，soldermask等

### 使用方法

1.  打开Color 192面板
2.  在layer子菜单下，选择需要添加的subclass，右键选择Add to Visibility，再点Apply即可Visibility面板在出现对应的层。
3.  如果想取消，在添加的subclass上，右键选择Remove from Visibility即可。

Visibility Class可以增加class显示，拖拽或者双击都可实现添加或删除需求。 如下图，添加RKO后，在走线时，可以快速打开对应层的keepout区域，省去点选多次才找到一个层的繁琐操作。

![](http://a1024.synology.me:222/images/blog2022/visiuser.gif)

Visibility Pane设置跟随设计，仅对当前设计有效，换一个设计如需要需重新设置

Visibility Pane
---------------

动图如下演示下述功能

*   将指定的层别对应到层号加入Visibility面板方便切换
*   单层切换模式（按住Ctrol可以选择多层）
*   其它自定义调整

![](http://a1024.synology.me:222/images/blog2022/visipane.gif)

### Global Visibility

打开或关闭所有层元素现在可直接在Visibility Pane操作

![172-algPN-479.gif](https://a1024.synology.me:222/images/172-algPN-479.gif)

### Mask Layers

Mask Layers也集成到了Visibility Pane可以像管理Pin的可见性一样，切换可见或不可见

![172-algPN-480.gif](https://a1024.synology.me:222/images/172-algPN-480.gif)

### Layer Select Mode

在Visibility pane底部选择Enable layer select mode选项时，导体图层名称将更改为 HTML 链接。您可以单击单个链接以查看画布上的相应图层，也可以单击 Ctrl + 单击多个图层以查看多个图层。

![](https://a1024.synology.me:222/images/blog2022/10.14.gif)