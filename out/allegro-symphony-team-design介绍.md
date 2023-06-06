---
title: 'Allegro PCB Symphony Team Design实时协同设计'
date: Wed, 29 Sep 2021 09:33:30 +0000
draft: false
tags: ['Allegro']
---

视频演示
----

这是一个并发设计环境，多个用户可以连接到公共数据库进行协作设计活动。 使用此选项，您无需为需要将其工作合并到主数据库中的每个用户创建单独的数据库或分区。

PCB Team Design
---------------

16.X及以下版本已经包含一个的并行团队设计的功能，它是一种允许多个设计人员在一个设计上工作的方式。但是它需要在设计活动中对设计进行一些切割分区并通过分配完成后再次导入以获得完整的设计。目前该方式已经略显过时，本文不做介绍或者以后有机会单独介绍。

![](http://a1024.synology.me:222/images/blog2022/preface-2.gif)

Symphony Team Design
--------------------

在 17.2 Hotfix 9 （QIR 2）版本中，新的并发设计解决方案Allegro PCB Symphony Team Design Option技术提供一种多用户、并行式在线协作的设计方法。并行工作在同一个设计的多个设计师均可访问同一数据库。设计可以由设计团队的几个成员共同进行编辑。每个设计师进行的工作将实时的更新到设计视图中，这种协同方法可以大幅缩短整体设计周期并加速设计过程。

![](http://a1024.synology.me:222/images/blog2022/preface-3.gif)

Allegro PCB Symphony Team Design Option 是**实时联网**的，其基于TCP-Sockets通信，其网络架构如下图所示：作客户端连接到Symphony应用程序服务器，服务器负责Allegro数据库的操作。 每个客户端从服务器拉取数据库信息，以便开始设计工作，并将任何更改发回服务器。 然后，服务器将主数据库中的更改更新到其他客户端。

![](http://a1024.synology.me:222/images/blog2022/preface-4.gif)

使用方法
----

此功能从17.2 Hotfix 9 （QIR 2）版本开始启用，后续各个版本经常对此功能进行更新，越靠后的版本对共享的可操作项目有更多的支持，所以建议协作者使用相同的设计版本（更新补丁号）

软件设置建议开启OpenGL，以显示团队协作时锁定的元件和布线的颜色样式，以及一些正在进行的状态显示

建议设计路径不要使用中文，否则可能出现一些不必要的错误（基本常识）

从Allegro中启用或连接Smphony均需要在软件启动了 Smphony Team Design功能选项

![](http://a1024.synology.me:222/images/blog2022/symphony4.png)

启用了 Smphony Team Design功能选项后，File菜单才会有如下两个命令，否则没有这两项命令这个功能用不起来

![](http://a1024.synology.me:222/images/blog2022/symphony7.png)

### 服务启动（创建协作）

从网络服务器机器启动服务器应用程序作为共用数据库（muserver.exe 此程序一般位于类似如下路径C:\\Cadence\\SPB\_17.2\\tools\\bin\\ muserver.exe）以便多个客户端可以连接到公共数据库并在并发环境中执行设计活动，所有用户加入网络服务器机器并与之通信。服务器管理器可用于管理网络服务器机器上的服务器应用程序。服务器进程包含一个用户界面，用于打开和保存设计文件、配置一些设置和监视活动。

![](http://a1024.synology.me:222/images/blog2022/symphony1.png)

如果不通过网络服务器也可以一台计算机打开设计软件后从菜单File->Start Symphony Server可达到与上述同样的效果

*   Database为当前操作的主设计文件
*   Owner为服务主机的地址，其他设计可以通过对应的地址搜寻连接加入到此设计
*   Open、Save、Close分别用于对设计文件的操作
*   下方为当前参与用户的活动状态

从Flie菜单也可以 选择Open、Save、Close用于对设计文件的操作 ，另外Write As用于将设计文件另写为一个文件，相当于保存当前设计并把这个设计复制到另外一个地方，当前活动设计仍然不变（此处注意与另存为的区别，另存为保存后活动设计会变为存储后的设计）

选择File – Options菜单可以自定义服务器设置

![](http://a1024.synology.me:222/images/blog2022/symphony2.png)

General（常规）选项卡

*   Server Setting用于设置服务器状态，包括最大连接数，端口与号范围，等
*   Autosave Settings用于设置自动保存的相关项
*   Design Setting暂未知

Security（安全）选项卡

用于允许或拒绝特定用户访问数据库。 密码可以自动生成或手动定义。 它附加到数据库以限制访问。

Tool菜单提供对打开数据库的一些基本数据库检查的快速访问，并在日志选项卡中显示结果并禁用服务器数据库上的在线 DRC。

### 服务连接（加入协作）

加入协作一般可以通过如下两种方式

#### 通过网络IP

![](http://a1024.synology.me:222/images/blog2022/symphony5.png)

当通过上文的方式创建并启动一个服务（创建服务的主机后文简称为服务主机），协作者可以通过打开Allegro通过菜单File-> Symphony Connect打开 Symphony 面板如上图

从Host Name处输入服务主机的IP地址，如果你有多个网卡则应输入计算机所在同一局域网的IP地址点击后方的Quary Host按钮

其下方会显示对应服务主机上已经开启协作的设计文件名，选择对应设计后点击左下的Connect加入此设计的协作

经过一小段时间的下载后设计软件即显示对应的协作的设计，设计协作即可开始进行

#### 通过共享文件

![](http://a1024.synology.me:222/images/blog2022/symphony6.png)

使用此方式应先在服务主机端已经对目标设计文件启动了 Symphony 服务

将brd文件或其所在文件夹设置共享，总之要让协作者能够通过共享访问到此设计文件

协作者通过网络发现、运行服务主机的IP地址或者直接在资源浏览器输入“\\\\对方的IP地址”后访问服务主机共享的设计文件

使用Allegro打开服务主机的目标设计文件，将如上如提示连接到此协作，点击是完成加入协作

#### Symphony面板

![](http://a1024.synology.me:222/images/blog2022/symphony5.png)

如上图Symphony面板 （如果被关闭了可以通过菜单 File-> Symphony Connect 再次打开）可以查看当前协同设计的一些状态

*   Connect为当前协作设计的主机情况以及对应的操作对象
*   Users为当前协作的参与者
*   Locks显示团队协作人员锁定了哪些对象
*   Log为所有协作者的操作日志情况
*   Options为部分选线设置具体含义待补充

### 操作事项

在协作过程中可能进行的操作

#### 进程管理

![](http://a1024.synology.me:222/images/blog2022/symphony8.png)

*   Refresh DB：一般是不常用的，因为设计几乎已经是实时更新的了，可通过此按钮强制更新一次
*   Pause：要在协同过程中对设计进行一些全局更改操作时，需要从客户端使用暂停按钮，使控制端完全控制数据库来完成网表导入、网表回注、cross-section（层设置）、应用skill程序（协作期间所有skill程序都是被禁用的）等全局性编辑内容。
*   Disconnecting：断开所有连接，控制端将更新为当前设计的最新状态返回为独立设计

![](http://a1024.synology.me:222/images/blog2022/symphony10.png)

用户选择暂停后会被要求指定一个确认等待时间（上图左上）用于让其他协作用户同意（上图左下）并及时暂停协作任务（超过等待时间将默认同意）协作者同意后将进入暂停状态（上图右下），如果其他协作者需要更多时间来结束他们当前的的工作，请求暂停的客户端可以在结束持续时间倒计时期间通过单击取消暂停按钮来取消此次暂停任务（上图右上）。

![](http://a1024.synology.me:222/images/blog2022/symphony11.png)

暂停期间协作者可以修改数据库，但更改不会被更新到主数据库（仅作本地数据）。 每个命令完成后都会显示一条提醒消息，可以通过点击不再提示弃用此提示。

![](http://a1024.synology.me:222/images/blog2022/symphony12.png)

暂停后主用户可以获得数据库完整的控制状态，进行一些全局的操作，当完成后通过Resume按钮恢复协作。

![](http://a1024.synology.me:222/images/blog2022/symphony13.png)

恢复协作后所有协作者会立即收到通知（上右图）并获取服务器数据库的最新数据。 如果其他协作在暂停的期间进行了任何更改，他们可以保存本地副本仅供参考（上左图），不会被更新到主数据库。

#### 修改规则管理器(Unsupported Prototype)

每个协作者都可以进入约束编辑模式（CNS编辑模式）来更新设计约束， 一次只允许一个客户端可以进入 CNS编辑模式 更新规则，规则更新完成后，服务器数据库和所有其他客户端都会同步更新。

![](http://a1024.synology.me:222/images/blog2022/symphony14.png)

  
此功能目前仅作为 Unsupported Prototype （不受支持的模型）要激活 CNS编辑模模式，请设置环境变量 MU\_ENABLE\_CNSEDITMODE将Value值进行勾选。此设置需要重启生效。

![](http://a1024.synology.me:222/images/blog2022/symphony15.png)

再次重启生效后如上上图才会出现Enter CNS Edit Mode，使用此按钮进获取 CNS编辑模式 权限才能进行对应操作

![](http://a1024.synology.me:222/images/blog2022/symphony16.png)

获取到 CNS编辑模式 的用户名后会有一个cns editor的标识

此处的规则管理包括Identifies DC Nets、signal model assignment、Constraint Manager、SigXplorer中的全部设置

![](http://a1024.synology.me:222/images/blog2022/symphony17.png)

![](http://a1024.synology.me:222/images/blog2022/symphony18.png)

![](http://a1024.synology.me:222/images/blog2022/symphony19.png)

完成编辑后将和上文暂停后流程类似通过上图按钮Leave CNS Edit Mode退出，其它用户将受到提示并将同步更新设计规则确认等操作，不再赘述

其实 CNS Edit Mode 这个所有操作也可以通过上文的暂停完成，两者最大的区别在于，暂停器件其他协作者进行的设计操作不能同步更新到主设计，而进入 CNS Edit Mode 这种操作，操作器件其它协作者可以同步进行设计操作，且所有设计操作的内容会同步更新到主设计

#### 锁定对象

![](http://a1024.synology.me:222/images/blog2022/symphony20.png)

多用户协同时，允许个人用户对对象进行Lock，这样相应对象将不能被其他协作者进行编辑，锁定者拥有lock对象的编辑权限

从PCB中选择对象后通过右键菜单选择Muti-User Lock即可避免其它协作者对其进行编辑，Symphony窗口Locks便签可以查看所有协作对象已经Lock的对象

![](http://a1024.synology.me:222/images/blog2022/symphony21.png)

被Lock的对象将按照用户名前面的颜色对应的特殊的标识方式标识出来

从Lock标签双击或者右键选择Display可以跳转被Lock的对象

选择被Lock的对象右键选择Muti-User Unlock或者从Locks标签选择（支持多选）对象右键选择Unlock可以取消Lock

lock对象仅对当前本次Lock有效，当用户离开协作时所有Lock对象权限将被开放，所有用户均可编辑

#### 其它

每个协作者的设计情况都是独立的，协作者可以随时加入和离开协同设计，当协作者重新加入会话时，将保留客户端级参数、缩放级别和图层显示等信息。

Save命令是不可用的，Write As允许保存本地副本（前文有介绍）。 连接到 Symphony 数据库时完成的所有设计更改都将即时合并保存在到服务器数据库中。

![](http://a1024.synology.me:222/images/blog2022/symphony9.png)

Symphony窗口可以通过点击叉号关闭，若需要再次打开窗口可以在工具栏右键选取对应的项目再次打开此窗口

### Symphony Team Design Commands

大多数命令和功能基本都能在 Symphony Team Design Commands 模式中应用，下面几项内容是不被允许的，这些工作应该在独立设计中完成

*   Cross Section Editor：板子层叠设置，从菜单Setup->Cross-section进入
*   网表导入与更新
*   元器件导入（放置）到板中
*   部分skill功能的应用

#### Supported Commands

内容较多仅供查询，不做详细描述了

从帮助文件中通过关键字Symphony Team Design Commands查询