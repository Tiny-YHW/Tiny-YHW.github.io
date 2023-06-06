---
title: 'allegro user preferences常见设置及说明'
date: Thu, 30 Apr 2020 01:49:14 +0000
draft: false
tags: ['Allegro']
---

用户设置 用户首选项

在这里可以进行工作环境、界面和显示效果的一些设定，对应菜单 Setup>User Preferences ，因为这里涉及的内容比较多，而且很多功 能都很少用到，所以下面只针对一些常用设置作介绍  持续更新...... 

本文将罗列Allegro 常用的设置项，关于所有可设置项可以查看后面这个链接 [ALLEGRO ENVIRONMENT VARIABLES](https://a1024.synology.me:1024/?p=2539)

使用逻辑
----

favorite用法：User Preferences窗体左侧上面是分级菜单，第一个为favorite，默认是空的，这里可以菜单可以配置，看下面的菜单可以发现每个功能后方有一列多选框（白色方框可以打勾），对应最上方列命名为favorite，在对应功能后方勾选此项即代表将其设置为favorite，在第一个菜单下可视，方便查找及修改设置。

search用法：很简单即搜索，支持通配符，比如输入\*save\*可搜出所有与保存有关的设置

effective说明：生效方法分为

*   command：完成当前命令生效，一般为done
*   immediate：立刻生效；
*   restar：重启软件生效。

常规设置
----

###  自动保存

![](http://a1024.synology.me:222/images/blog2022/USER1.png)

 Autosave： 我们在方框中打勾后系统才会帮助我们自动存档.  
 Autosave\_dbcheck： 我们在方框中打勾后系统会帮我们在自动存档前做一下 datebase 的检查. (这会使 autosave 花很多时间，建议不勾选.)  
 Autosave\_name： 我们可以在这输入 autosave 的文件名，如果不输入系统默认的文件名是 Autosave. Autosave\_time： 在这里可以输入我们需要的 autosave 的时间间隔. (默认值是 30minutes，我们可以在 10~300minutes 之间设定所需的时间间隔.)

###  brd中修改网表

Misc -> logic\_edit\_enabled  勾选代表允许用户修改 不勾代表不允许  
对应功能：  
a.增加器件：选择下拉式菜单的指令Logic>Part Logic从part table 中选出零件.  
b.修改连线关系: 选择指令Logic>Net Logic,选择要被指定的net,net name 会出现在control panel 的Option tab 中, 进行增加，删除，修改NET的编辑

### 光标设置

左侧Ui，在右侧Pcb\_cursor 的下拉菜单中选不同的项，则可以实现不同的设定，其中 Cross 是小光标，infinite 是大光标。

### 库路径设置

Path -> library  
padpath：.pad文件路径及焊盘  
psmpath：.psm .bsm .fsm等后缀为".?sm"文件的识别路径  
devpath：.txt文件路径，含第三封库和txt格式库文件  
其他还有  
clppath：.clp文件路径即File—export—sundrawing的东西  
scriptpath：.scr文件即录制脚本文件路径

### 手势触发

ui>input>no\_dragpopup 勾选：右键直接拖动有效；不勾选：按住ctrl才能触发手势功能

### OpenGL

Display-disable\_opengl 不勾选PCB渲染为实心，勾选渲染为透明透明度叠加，在display-color中display项opengl可设置透明度

![](http://a1024.synology.me:222/images/blog2022/USER2.png)

在勾选此项允许PCB渲染3d视图及翻转PCB  
菜单view-3d view 3d显示pcb  
View-flip design 镜像pcb，brd中实际所视与bottom相关的层均为镜像过的视图，此指令可方便查看底层实际视图

### 等长显示框

![](http://a1024.synology.me:222/images/blog2022/USER3.jpg)

Allegro\_dynam\_timing  设置为on为显示 off为不显示

Allegro\_dynam\_timing\_fixdpos 勾选为固定在右下角，不勾选跟随鼠标  
关于手势

### Connect

![](http://a1024.synology.me:222/images/blog2022/aconrouteon.png)

### 输出文件路径

Allegro软件生成或输出文件的路径，File\_ management-->Output \_dir

*   ads\_ sdart：Artwork和钻孔文件输出路径，默认为设计坐在路径
*   ads\_ sdlog：log文件
*   ads\_ sdplot：plot（pdf）文件
*   ads\_ sdreport：report文件
*   dump\_ library directory：library文件

进阶设置
----

### 撤销步数

UI-undo max\_undo\_memory:设置最大可撤销步数，最大多少我不知道

### DRC标记显示为实心

 setup-->user preferences...勾选Display中的display\_drcfill即可

### Display-Shape\_fill

New\_shape\_fill\_nt：勾选shape填充为实心，不勾选，填充为横线与下方old\_shape\_fill\_style对应  
no\_shape\_fill:shape填充方式为空心只显示边框

### IPC机械Pin警告

Manufacturer-IPC\_netlist  ipc356\_nomechpin\_warnings 勾选出ipc时忽略机械pin的报warning，不勾选不忽略，常见于板中增加了机械封装的表贴mark点报warning，勾选可忽略此项

### DC nets 高亮方式

Route-Connect-->Acon\_oldhlt  常用于设置对设置了voltage的网络的高亮规则（logic-identity DC nets对网络设置值，飞线显示方式为方框打叉）  设置为all 拉线时此种网络依然全部高亮，其他值相同网络不高亮，此问题有挺多人问过，建议设置为all

当有时候感觉拉线时相同网络对象不一起高亮时，可能是这个选项没设置到位

### Win7 64位系统16.3 手势不能用，且乱码报错问题

表现为使用手势时command栏出现乱码现象，类似E- Can't open STED stroke file 'Üõ¥'m¾uQm¾u®Ñ??Z'.

打开环境变量下面pcbenv文件夹内allegro.ilinit文件（如果没有可以新建）  
用文本工具打开末尾增加下面三条语句大小写不能错，空格不能缺

```
procedure(stroke_fix_163 (t_open)
axlShell("strokefile allegro")
)
axlTriggerSet('open 'stroke_fix_163)
```

然后重启软件

16.6版本新增
--------

### 字符和器件的连接鼠线

Placement-General中的display\_refdes\_rats项可以设置，是否显示从 refdes 原点到器件1脚的鼠线，以显示器件与 其refdes 的关系。勾选代表显示，不勾选代表不显示

### 记忆线宽

 add connect指令下线宽设置默认为记忆线宽，对应设置项为Route-Connect  acon\_no\_width\_override\_retain

此选项默认为关闭状态，即记忆线宽，add connect时默认线宽均为上次（不区分net、class等）指定的值无视规则设置的值，如果需要按规则值设计需开启此选项

### 双单位显示

Display-->Element  showmeasure\_altunits，可以设置成millimeters此时进行测量时，会显示双单位

### 字符鼠线

Placement-->General  display\_refdes\_rats 勾选为显示 显示连接字符和元器件中心的鼠线

### **右键手势拖影问题**处理

![](http://a1024.synology.me:222/images/blog2022/USER4.jpg)

出现此问题需两种情况同时满足OpenGL处理Open状态且光标显示为大十字或大米字，更改上述两个设置中的任意一个都可解决本问题

若坚持使用上述两种设置，可在ENV中增肌语句set infinite\_cursor\_bug\_nt解决此问题

也可尝试[禁用Aero](http://www.windows7en.com/Win7News/18571.html)功能解决

### 关闭原理图启动界面

从原理图菜单打开命令行View---Toolbar----Command Window，输入命令SetOptionBool EnableStartPage 0

### Ref-Des Layer Visibility Control

移动symbol时默认显示装配层的位号，现在可通过定义_display\_refdes\_subclass_值设置，显示某个层的位号

![](http://a1024.synology.me:222/images/blog2022/display_refdes_subclass.png)

17.2版本新增
--------

### 关闭PCB启动界面

Start Page：Ui --> Startpage --> allegro\_no\_startpage  勾选

### 关闭原理图启动界面

如果不希望软件开启时弹出启动界面或者莫名的报以下错误可以尝试关闭启动界面，关键词当前页面的脚本发生错误，错误：Script error，URL：googletagmanager

![](http://a1024.synology.me:222/images/blog2022/screrror.png)

#### 解决方案（多种自行尝试）

如果有下图选项可以直接勾选这个项不再显示启动界面Startup，如果没有这个选项继续往下读

![](http://a1024.synology.me:222/images/blog2022/startpage%20off.png)

Close Capture and go to a File Explorer window, type %HOME% into the address bar followed by a return. then go to cdssetup\\OrCAD\_Capture\\17.2.0. In here is a file called spinfo.ini, open this with a text editor and at the bottom change EnableStartPage=true to EnableStartPage=false. Then save and restart Capture

[https://www.u-c.com.cn/w/news/technical/cadence.html](https://www.u-c.com.cn/w/news/technical/cadence.html)

疑难杂症记录
------

放置器件吸附到对象上时非常卡顿

检查env中是否有set display\_norepair的相关文本 删除文本所在行重启allegro，这是一个图形显示问题，不做过多解释，照做即可