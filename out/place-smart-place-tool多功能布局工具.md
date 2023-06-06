---
title: 'Place->Smart Place Tool多功能布局工具'
date: Thu, 12 Jan 2023 09:36:00 +0000
draft: false
tags: ['TY-Skill']
---

功能说明
----

此工具支持多种布局功能详见下文

*   按页放置器件
*   高亮指定类别器件
*   按飞线布局
*   按原理图器件位置布局

操作说明
----

此功能的大多数功能需要从Capture中输出Cross reference（.xrf）文件支持，建议将xrf文件放置到brd同级目录方便调用

![](https://a1024.synology.me:222/images/blog2023/xrf.png)

第一次启动此功能，会自动跳转调用Cross reference（.xrf）的对话框，选择对应文件即可

如果xrf有变化或者需要重新加载，在对话框最后一个标签Option Input后面的load按钮重新选择新的xrf文件，（此处可能支持更多原理图工具待测试）

### 按页放置器件

对话框第一个标签页Place用于分页放置器件，可以指定某个原理图页的一个或多个一起放置，从工具中选择器件后从PCB中框选一个区域，对应器件将排布到指定区域内

### 高亮器件

对话框第一个标签页Highlight主要用于分页查看器件分布

左下角HI color可以指定高亮颜色，DHL all按钮可取消板中已经高亮的器件

**按页查看器件**

从列表区域选择某个原理图页的一个或多个器件对应的器件将在PCB中被高亮显示

从Page后方的输入框输入指定页码，则对应页码的所有器件将被高亮显示“1-3，5”代表1 2 3 5四个页，其它依次类推

点击Hl like page按钮后在PCB选择一个器件，则与该器件位于同页的器件将被一起高亮显示

点击列表右下方Query Page按钮后在PCB选择一个器件，Command将报告该器件的位号及所在原理图页

![](https://a1024.synology.me:222/images/blog2023/Bypage2.png)

**按位号、Room或封装查看器件**

从Refdes后方的输入框输入位号，可高亮指定位号的器件，位号支持通配符（这个功能暂时有些问题，待处理）

点击Room按钮，可查看包含Room属性的同类器件（须在原理图中定义Room属性）

点击下图Like按钮后在PCB选择一个器件，则与与该器件封装名相同的器件将被一起高亮显示

点击下图Like按钮后的...，可以从列表选择指定封装名的器件高亮查看

![](https://a1024.synology.me:222/images/blog2023/Bypage3.png)

### 按飞线布局

*   从Re-place标签页选择Re-place by rats nest order
*   从Replace Option设置好元器件放置角度、放置面和排列方向
*   框选需要排列的元器件（接触选择）
*   框选对应的飞线（接触选择）
*   选择元器件将按飞线的连接进行重排，间距控制为元器件放置在当前格点上，且为不产生DRC的最小距离

![](https://a1024.synology.me:222/images/blog2023/ratsnetsorder.jpg)

### 按原理图元器件位置布局

1.  从Re-place标签页选择Re-place by schematic page xy
2.  框选需要重排列的元器件（如果选择器件再多页，会让你再次选择需要先放哪一页）
3.  框选需要重排的区域，框选区域越大元器件相对间距越大，自行控制框选区域大小
4.  选择元器件将按在原理图中的相对位置重置

![](https://a1024.synology.me:222/images/blog2023/compxydal.png)