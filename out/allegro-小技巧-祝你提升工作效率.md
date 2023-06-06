---
title: 'Allegro 小技巧 祝你提升工作效率(Tips and Tricks)'
date: Fri, 29 May 2020 09:28:56 +0000
draft: false
tags: ['Allegro']
---

ENV
---

您可以定义键盘 "快捷键 "来运行PCB Editor中的命令。要定义这些快捷键，请在您的pcbenv目录中找到一个名为env的文件，（如果您不知道它的位置，请在Windows资源管理器的地址栏中键入%HOME%，然后回车进入pcbenv文件夹）。这里有env文件。在文本编辑器中打开env文件，并在下面部分的上方添加以下内容（如果需要，请更改快捷键），因为在这部分下方的任何编辑都不会被保留。

```
### User Preferences section
### This section is computer generated.
### Please do not modify to the end of the file.
### Place your hand edits above this section.
```

要了解PCB编辑器使用的“实际”命令，请在PCB编辑器的命令行中键入scriptmode + e。 此后调用的任何命令都将在命令行中列出。参见Command处显示输入命令章节  
注意在env文件中的任何地方定义＃之后的任何项目均为注释。

[站长自用env](https://a1024.synology.me:1024/env-%e8%87%aa%e7%94%a8%e9%83%a8%e5%88%86/)

### Reopen命令

重新打开设计文件（上一次保存的，上次保存之后的改动均不会被保存）。多数人不知道这个方便的命令是做什么的。  
在命令窗口中输入reopen以重新打开相同的文件

当你想放弃从上次打开到现在你对设计进行的操作并重新打开时使用，比如你在一个设计版本上做各种尝试，直到你满意为止时，在你做的各种尝试时它会很有效率，常规情况下你需要关闭设计并重新打开来进行各种尝试，现在只需要输入reopen即可,他的命令如下，是系统env默认存在的，一般不需要单独设置

```
alias reopen 'open -q $module'
```

### 为铜皮赋予网络

先按Shift+左点选Shape，然后按Shift+右选择一个需要给予网络的对象

```
#Shape全命令
#添加铜皮
alias SUp shape add
#编辑铜皮
alias SDown shape edit boundary
#选择铜皮
alias SLeft shape select
#为铜皮加网络
alias SRight pop net list
#优化铜皮倒角
alias CSDown fse_shape_chamfer 
```

### 使用快捷键吸附对象

```
funckey ss “prepopup; pop dyn_option_select ‘Snap pick to@:@Segment Vertex'”
funckey se “prepopup; pop dyn_option_select ‘Snap pick to@:@Segment Midpoint'”
funckey sd “prepopup; pop dyn_option_select ‘Snap pick to@:@Pin'”
funckey sa “prepopup; pop dyn_option_select ‘Snap pick to@:@Arc/Circle Center'”
funckey sv “prepopup; pop dyn_option_select ‘Snap pick to@:@Via'”
```

### 将光标处调整到视图中心

```
funckey z "zoom center; pick -cursor"
```

### 使用空格键增加via

```
funckey " " "pop bbdrill -cursor"
```

### 一键多用

#### 设置按键为多个命令切换

**Add Connect时使用F2切换多种拐角模式**

```
alias a1 'FORM mini lock_mode Arc;FORM mini lock_direction 45' 
alias a2 'FORM mini lock_mode Arc;FORM mini lock_direction 90' 
alias a3 'FORM mini lock_mode Line;FORM mini lock_direction 45' 
alias a4 'FORM mini lock_mode Line;FORM mini lock_direction 90' 
alias F2 'settoggle CMD a1 a2 a3 a4;$CMD'
```

#### 指定按键，在不同的模式（命令）时实现不同功能

虽然这种方法在一定程度上是违法的，但合理使用的话还是挺方便的

实现原理为对一个输入指令，设定多个命令，则这多个命令会依次执行，但由于命令状态，只有一个命令能被执行，其它命令都是错误命令，举个例子

训练时，如果指挥官发出"向上"的指令后，要求士兵"跳一次"（地面时）然后"向上飞"（驾驶飞机时）

这时候当士兵在陆地行进时，听到"向上"的指定时便会"跳一次"而无法向上飞（错误指令）

当士兵在驾驶飞机时，听到"向上"的指定时便会"向上飞"而无法跳一下（错误指令）

语法为 funckey "向上" "跳一次;向上飞"

要求"跳一次"和"向上飞"命令相互独立，不能同时发生

**使用空格旋转元器件和改变差分扇孔方向**

```
funckey ' ' "angle 90;pop viapattern next"
```

**add line、add connect、Shape Add时线型模式切换，CF11切换直线和圆弧**

```
alias changeline "options dyns_lock_mode Line;FORM mini lock_mode Line"
alias changearc "options dyns_lock_mode Arc;FORM mini lock_mode Arc"
alias CF11 'settoggle CMD changeline changearc;$CMD'
```

**add line、add connect、Shape Add时线型模式切换，CF12切换角度**

```
alias changge45 "FORM mini lock_direction 45;FORM mini dyns_lock_mode Line 45"
alias changge90 "FORM mini lock_direction 90;FORM mini dyns_lock_mode Line Orthogonal"
alias changgeoff "FORM mini lock_direction Off;FORM mini dyns_lock_mode Line"
alias CF12 'settoggle CMD changge45 changge90 changgeoff;$CMD'
```

#### 布线时通过按键改线宽为固定值

```
funckey F10 form mini acon_line_width 25
```

#### 差分走线切换单线和双线模式，add connect时直接使用

```
funckey sx "prepopup;pop singletrace"
```

#### 查找元器件或网络对象

```
funckey jc "prepopup ; pop dyn_option_select 'Selection set@:@Clear all selections';set prompt;prompt 'Find Ref Des';refdes $prompt;zoom selection"
funckey jn "prepopup ; pop dyn_option_select 'Selection set@:@Clear all selections';set prompt;prompt 'Find Net Name';net $prompt;zoom selection"
```

#### 切换app mode

```
funckey a "settoggle CMD 'generaledit' 'placementedit' 'etchedit';$CMD"
```

#### 活动层切换

```
funckey + subclass -+
funckey - subclass --
```

#### 删除鼠标处对象

```
funckey d "prepopup; pop dyn_option_select @:@Delete"
```

#### 给鼠标滚轮加命令

```
button Swheel_up subclass -+ 
button Swheel_down subclass --
button Cwheel_up "roam y -$roamInc" 
button Cwheel_down "roam y $roamInc" 
button SCwheel_up "roam x -$roamInc" 
button SCwheel_down "roam x $roamInc"
```

#### 特殊语法

```
#点击鼠标所在格点处
pick_to_grid -cursor
#右键鼠标
prepopup
#命令中的;代表在一行上依次执行多个命令 
```

#### 按格点复制对象

结合格点设置skill和相对跳转一个格点指令实现不同间距复制对象

```
#相对跳转一个格点
alias CSUp        "ipick_to_gridunit 0 +1"
alias CSDown      "ipick_to_gridunit 0 -1"
alias CSLeft      "ipick_to_gridunit -1"
alias CSRight     "ipick_to_gridunit +1"
```

![](http://a1024.synology.me:222/images/blog2022/copy%20by%20grid.gif)

属性
--

### 禁布区域允许某些对象

给禁布区域增加允许的属性即可

Via\_Allowed、Shapes\_Allowed、Routes\_Allowed

### 同网络动态铜皮避让

给对象增加void\_same\_net属性，如下图Cline增加了void\_same\_net属性

![](http://a1024.synology.me:222/images/blog2022/Allegro_Tips_Tricks3.jpg)

操作
--

### 善用全局按键Alt

这是一个应用于所有Windows系统的功能，他是一个全局的功能，无需进行配置，应该像Ctrl+C或Ctrl+V一样常用

Windows软件的菜单栏菜单的单词一般都有某个字母下方有一个下划线，按住键盘Alt键+这个字母，此一级菜单则会被打开，再次查看二级菜单的下划线字母，可继续执行对应命令

对应我们常用Allegro的按键分三类，非常常用的如Add Connect、Slide、Copy等适合直接设置一个按键，对于不常用的鼠标点点菜单就好了，但对于那些常用但不是非常常用的功能，如果指定一个按键这样会非常占用键盘资源没推荐使用Alt组合键解决这个问题，如下是我已经形成肌肉记忆的按键可做参考，你也可以形成自己的习惯来解放键盘占用

*   ez：Zcopy
*   es：旋转对象
*   ev：编辑对象端点
*   et：编辑文本
*   at：增加文本 
*   dt：状态面板Status
*   dc：Color 192 层开关和颜色
*   de：查看对象属性
*   dd：去除高亮
*   ll：Net Logic
*   tu：更新DRC

### 解锁全部

选择Unfix命令，右键选择Unfix All

### 扩展或收缩shape or void

“General Edit” Application Mode时指向对象右键选择Expand/Contract

![](http://a1024.synology.me:222/images/blog2022/Allegro_Tips_Tricks.2jpg.jpg)

### [刷新重置选中的Symbol](https://a1024.synology.me:1024/refresh-syminst-%e5%88%b7%e6%96%b0%e9%87%8d%e7%bd%ae%e9%80%89%e4%b8%ad%e7%9a%84symbol/)

### 使用Ctrl+P打印一个Form

部分Form可早Form激活时使用Ctrl+P输出Form到Txt或Scr，打印出的内容包含所有当前From的设置项，其中Scr可直接用于脚本程序

### 打开当前设计所在文件夹

菜单 Tools - Utilities - File Manager

### Uprev Symbols 焊盘图形升级到当前版本

uprev\_overwrite 可以用于将之前版本的Footprint升级到当前版本在DOS中执行的语法为  
Syntax: uprev\_overwrite n where n = \*.dra; \*.psm; \*.ssm  
更多功能在Dos中输入uprev -help查看  
Note: 升级之前建议做好备份.

设置
--

### 在Add Connect时隐藏其它飞线（16.6 QIR6）

![](http://a1024.synology.me:222/images/blog2022/Allegro_Tips_Tricks1.jpg)

### Datatip Options

> [自定义数据提示datatip（更加直观的对象参数显示）](https://a1024.synology.me:1024/?p=1513)

### Command处显示输入命令

默认情况下Command只显示结果或提示性内容，输入指令是不显示的

若我们需要查看所有输入指令可在Command输入：scriptmode +e后在进行命令输入，则所有输入命令均以CMD>……的形式显示出来，方便查看交互命令，

输入scriptmode -e取消上述设置

### 只读变量

在env中增加 readonly "变量名"

![](http://a1024.synology.me:222/images/blog2022/Allegro_Tips_Tricks.4jpg.jpg)

设置只读变量

![](http://a1024.synology.me:222/images/blog2022/Allegro_Tips_Tricks.5jpg.jpg)

在命令行输入readonly查看只读变量

![](http://a1024.synology.me:222/images/blog2022/Allegro_Tips_Tricks6.jpg)

只读变量不被允许被修改

### 差分汇集点

User Preferences Editor中可设置padentry\_factor值调整汇聚点

![](http://a1024.synology.me:222/images/blog2022/huijudian.png)

Cline/Line
----------

### Auto Interactive Convert Corner (AiCC)

自动交互转换倒角：将板中已完成布线的Clines/Cline segs/Nets倒角为圆弧或固定角度，因行业内的设计习惯，倒圆角功能比较实用，其它功能不做介绍

需要Allegro16.6及以上版本

命令：aicc

菜单：Route->Unsurpported Prototypes->Auto-interactive Convert Corner

操作方法：选择命令->设置选项->设置过滤项->选择对象（可进行多次选择），选项简单不做介绍

![](http://a1024.synology.me:222/images/blog2022/Aicc.gif)

Shape
-----

### 优化铜皮倒角

将Shape倒角均转换为圆角或斜角，再也不用担心铜皮的直角问题和不美观问题，需要16.6及以上Analog/RF产品选项

命令：fse\_shape\_chamfer

菜单：_RF-PCB - Flexible Shape Editor - Shape Corner Chamfer_

操作方法：选择命令->设置选项->设置过滤项->选择对象（可进行多次选择），选项比较简单不做介绍。

![](http://a1024.synology.me:222/images/blog2022/fse_shape_chamfer%20.gif)

[如何在PCB编辑器中自定义菜单](https://a1024.synology.me:1024/?p=1016)
---------------------------------------------------------

脚本SCR
-----

在脚本中加入一个延时：pause 3；在命令行输入=暂停三秒

[Allegro 16.6增效功能](https://a1024.synology.me:1024/allegro-16-6%e5%a2%9e%e6%95%88%e5%8a%9f%e8%83%bd/)
----------------------------------------------------------------------------------------------------