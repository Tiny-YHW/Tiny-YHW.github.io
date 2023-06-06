---
title: 'Allegro手动编辑元器件Part Logic和器件网络Net Logic'
date: Mon, 31 Aug 2020 06:02:02 +0000
draft: false
tags: ['Allegro', '设计技巧']
---

Allegro设计较为严谨，尤其是关于Pad、Package、和网络表的管理，软件逻辑不同于Altium，想在PCB中直接编辑修改Pad、Package或网络表，总是不容易的，软件设置了层层障碍，避免设计者修改此类内容，而是鼓励用户在源文件处或原理图中管理PCB使用的库文件和网表文件

但由于某些原因，设计库文件、原理图、PCB的可能不是同一个人，或者某些地方的强制要求，PCB设计者不得不直接在PCB中修改对应的内容，本文介绍直接在PCB中修改网表的方法（能在原理图中修改还是建议在原理图中修改）主要涉及在PCB中增加元器件使用Part Logic功能或对已有的元器件（Package Symbol）的引脚网络进行编辑使用Net Logic功能

网表编辑使能项
-------

关于在PCB中修改网表的操作均需在用户设置中启用Setup -> User Preferences Editor->Logic->Logic\_edit\_enabled功能，否则命令不能被有效运行

![](https://www.u-c.com.cn/uploads/editor/2019/11/25135028527.png)

Part Logic
----------

本功能适用于在不修改原理图的情况下在PCB中增加元器件使用，增加的元器件一般用于强连或特殊作用，增加的元器件的网络可使用Net Logic功能进行添加

### 库路径设置

打开Setup -> User Preferences Editor中的Paths -> Library文件夹下的devpath，padpath，psmpath指向需要增加元器件的Package路径。

将你需要在设计中添加的器件和上述路径对应，否则后面流程从库中选择器件添加时是找不到需要添加的器件的

### 启用命令功能

从菜单选择Logic-Part Logic进入编辑窗口

![](http://a1024.synology.me:222/images/blog2022/Partlogic.png)

### 选择需要添加的器件

从左下边或上边选择要添加的器件对象

**上边选择板中已有器件添加**：直接选择板中已有的器件

**左下从库中选择器件添加**：

*   Physical Devices（第三方格式）：读取设置的devpath路径的txt后缀文件的元器件对象
*   Physical Packages（第一方格式）：读取设置的psmpath路径的psm后缀的文件的对象

### 编辑新增器件信息

*   Refdes：新增器件位号，名称不要与已有器件名称重复，如果新增多个同样的器件可以使用减号连接，如XINZENG1-10代表增减XINZENG1、XINZENG2、……XINZENG9、XINZENG10共11个器件
*   Devices：新增器件的Devices值
*   Package：新增器件使用的Footprint（Package）

其它信息非必填，按需填写，点击Add按钮，即修改网表成功，元器件被新增；选择已有或新增的元器件点击Modify按钮可对已有器件信息进行修改；点击Delete按钮钮可对已有器件信息进行删除

### 放置新增器件

选择菜单命令Place-Manually或选择Quick place把器件放置到PCB上

### 添加网络

使用Net Logic功能为新增器件添加网络

### 注意

通过Part Logic功能添加的器件，与原理图网表冲突，若重新导入网表文件，器件将被删除

Net Logic
---------

本功能适用于在不修改原理图的情况下在PCB中增加修改或移除某个网络名称也可对板中任何有位号的元器件引脚网络进行编辑

### 编辑网络

从菜单选择Logic-Net Logic从Option处选择功能

![](http://a1024.synology.me:222/images/blog2022/netlogic.png)

当勾选unassigned nets only复选框后表示只显示尚未分配的网络表，列表中将会根据过滤器显示网络表信息。

Create 按钮用于手工创建新的网络表，

Rename 按钮用于对选中的网络重新命名

Remove按钮用于对选中的网络删除

### 编辑元器件管脚网络

从菜单选择Logic-Net Logic从Option处选择功能

当勾选Assign时为给元器件管脚赋予网络，从网络清单选取或PCB中拾取一个网络名称，再点击需要增加为这个网络名称的元器件引脚，完成对此元器件引脚赋予此网络

当勾选Unassign时，为移除元器件管脚网络，使元器件管教网络为Null Net。勾选选框后从PCB上点击需要移除网络的元器件管脚，再次点击确认移除网络；连续点击多个引脚，则多个引脚的玩过将被移除