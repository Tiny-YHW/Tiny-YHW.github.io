---
title: 'Allegro Skill加载'
date: Mon, 20 Apr 2020 09:30:47 +0000
draft: false
tags: ['Allegro', 'Allegro Skill']
---

如何加载skill
---------

按照Allegro的启动逻辑，软件启动时会自动加载allegro.ilinit文件，所以常规通过此文件加载skill文件（当然你也可以直接在打开的Allegro软件中直接加载，仅对此次加载生效）

1.  获取Skill文件，放到指定目录（见下方skill文件内容）
2.  打开**allegro.ilinit**文件，加载上方的skill文件（见allegro.ilinit文件内容）
3.  这样每次启动Allegro软件时，skill文件都会被加载

如何调用skill功能
-----------

### CIW

直接在Skill环境下，调用函数，如getSkillPath()是一个定义好的skill功能，在Command窗口直接输入skill getSkillPath()则可以直接执行这个程序。skill环境内容参考后面的资料**PCB Editor搭载SKILL 环境**

### Bindkeys

见后续章节axlCmdRegister

axlCmdRegister( "20" 'BOTTOM)

一般设计者会将skill程序，使用axlCmdRegister注册一个快捷命令，一同写在il文件中（但其实写在任何skill环境的文件中并被加载，都能生效），这样通过定义的快捷命令即可调用此skill功能

更多见[Cadence SKILL 第二节 语言一览](https://a1024.synology.me:1024/%e7%ac%ac%e4%ba%8c%e8%8a%82-cadence-skill%e8%af%ad%e8%a8%80%e4%b8%80%e8%a7%88/)，SKILL函数调用章节内容

Allegro PCB启动
-------------

1.  读取allegro PCB 编辑器的env 文件
2.  然后运行allegro.ilinit 文件
3.  最后自动加载菜单配置文件allegro.men

**allegro.ilinit文件**
--------------------

用户在程序启动时加载的skill代码。顺序在在加载数据库或菜单之前，如果需要在数据库打开时执行操作，请通过axlTriggerSet API 注册回调触发器

Allegro默认识别两个路径 X:\\Cadence\\SPB\_XX.X\\share\\pcb\\etc；%home%\\pcbenv。%home%为你的环境目录，直接输入到资源管理器可定位到位置，更多知识见下文

加载函数案例load( "testfns.il")，load函数介绍见下文

skill文件
-------

包含某些功能的文件，可加载到Cadence软件调用相关功能。

常见的后缀格式有il、ile、cxt、ils,不过后缀不重要，文件格式才是根本，自己引申学习。

在Allegro的Command命令处输入skill getSkillPath()可以获得软件当然识别的skill文件路径，如果加载此处的skill文件直接写文件名即可，如果是其它地方需还需增加对应的文件路径。

**PCB Editor搭载SKILL 环境**
------------------------

直接输入set  telskill，这个界面就是用来运行SKILL 函数和命令的解释器。 （使能选项setup-> user prference->skill->telskill----勾选）

![](http://a1024.synology.me:222/images/blog2022/skill11.jpg)

command环境使用skiil的方式

直接输入skill空格语句

输入skill回车将command环境切换为skill环境，使用完毕用exit退出

![](http://a1024.synology.me:222/images/blog2022/skill12.jpg)

**关于路径**
--------

### 绝对路径

目录下的绝对位置，直接指向目标位置 Eg：C:\\Cadence\\LicenseManager

### 相对路径

文件所在的路径与其它文件（或文件夹）路径的相对关系

*   如果路径以(~/)开始，那么搜索路径为环境变量home指定的路径)
*   如果路径以(./)开始，那么搜索路径为你当前工作目录路径
*   如果路径以(../）开始，那么搜索路径为当前目录的父目录。

### Cadence路径

*   echo $cdsroot：安装路径
*   echo $home：环境路径一级
*   echo $localenv：环境路径二级
*   echo $menupath：菜单配置文件路径
*   skill getSkillPath()：Skill文件路径

![](https://a1024.synology.me:1024/wp-content/uploads/2020/04/19_178_c576e175b3db8e2.png)

### **环境路径修改**

也叫环境变量一般在软件安装时会有涉及，我们只谈后期设置，Win10为例其它系统类似，右键 我的电脑 选择 属性或者 控制面板\\系统和安全系统

![](http://a1024.synology.me:222/images/blog2022/skill13.jpg)

然后在环境变量里面新建或编辑要求变量名为home值为路径

![](http://a1024.synology.me:222/images/blog2022/skill14.jpg)

### **软件自带skill案例路径**

*   C:\\Cadence\\SPB\_XX.X\\share\\pcb\\examples\\skill
*   C:\\Cadence\\SPB\_XX.X\\share\\pcb\\toolbox\\skill\\barcode(加密格式)

### Skill帮助文件相关

#### 用户手册SKILL Language User Guide

路径 "C:\\Cadence\\SPB\_16.6\\doc\\sklanguser\\sklanguser.pdf"

SKILL Language User Guide 主要讲 SKILL 编程语言的语法，包括Skill编程语言的基本构成、语法，怎样进行函数调用，数据结构，算数及逻辑表达式，逻辑判断及循环，IO及文件处理，宏定义等等，其实Skill编程语言跟C语言非常相似，如果是熟悉C语言编程的会比较容易入手。

#### 参考文档Cadence SKILL Language Reference

"C:\\Cadence\\SPB\_16.6\\doc\\sklangref\\sklangref.pdf"

SKILL Language Reference 主要讲 Skill 编程语言自身实现的各种api功能及其调用实例

#### 接口函数文档Allegro® User Guide: SKILL Reference

路径 "C:\\Cadence\\SPB\_16.6\\doc\\algroskill\\algroskill.pdf"

AXL函数介绍

#### XXX

Allegro PCB and Package User Guide: SKILL Reference Cadence Allegro 相关操作的API，这个是特定针对Allegro操作的API，以实现Skill对Allegro进行功能扩展

#### 实例文档

C:\\Cadence\\SPB\_16.6\\share\\pcb\\examples\\skill\\DOC

常用函数
----

### setSkillPath

setSkillPath(buildString(append1(getSkillPath() "D:/skill")))

getSkillPath() ;函数，作用是获取ALLEGRO的SKILL PATH列表，此列表所包含路径中的SKILL文件可直接使用相对路径调用。

append1 ;函数，在列表中添加内容，append1(getSkillPath() "D:/skill"))) 的作用就是将D:/SKILL这个目录添加进SKILL 路径里，这样只要123.il文件放在D:/skill目录下就可以直接使用load("123.il")来调用。

buildString ;将LIST类型组成字符串，此函数可以省略

setSkillPath ;函数，根据重新组成的路径设置SKILL PATH.

### load

```
load(
t_fileName
[ t_password ]
)
=> t
``````
load( "testfns.il")             ; Load file testfns.il
fn.autoload = "myfunc.il"       ; Declares an autoload property.
fn(1)
fn is undefined at this point, so this call triggers an autoload of myfunc.il, which contains the definition of fn. The function call fn(1) is then successfully performed.

fn(2)      ; fn is now defined and executes normally.
You might have an application partitioned into two files. Assume that UtilsA.il contains classic SKILL code and UtilsB.ils contains SKILL/SKILL++ code. The following example loads both files appropriately.

procedure( trLoadSystem()
    load( "UtilsA.il" )    ;;; SKILL code
    load( "UtilsB.ils" )   ;;; SKILL++ code
    )                     ; procedure
```

载入函数,如果SKILL带有密码，写法为load("xxx.il" "password");另外也可以使用loadi函数。load加载文件遇到错误时会停止加载之后的文件。而loadi可直接跳过当前错误文件，继续加载之后的文件。

### axlCmdRegister

注册一个命令，调用某个函数，如下t\_allegroCmd为命令，ts\_callback为调用的函数

```
axlCmdRegister(
t_allegroCmd
ts_callback
?cmdType t_cmdType
?doneCmd ts_doneCmd
?cancelCmd ts_cancelCmd
)

axlCmdRegister( "do it" 'do_print)
;当在Allegro中使用"do it"命令时，执行do_print函数

axlCmdRegister( "my swap gates" 'axlMySwapGates 
?cmdType "interactive" ?doneCmd 'axlMySwapDone
?cancelCmd 'axlMySwapCancel)
;当在Allegro中使用"my swap gates"命令时，执行axlMySwapGates程序，命令类型为interactive，在此命令下右键done参考执行axlMySwapDone程序，在此命令下右键cancel参考执行axlMySwapCancel程序，
```

常用程序
----

### 按文件夹和指定后缀加载skill文件

```
skillpath = "D://SPB_Data//pcbenv//skill"
foreach(file rexMatchList(".*\\.il$" getDirFiles(skillpath))
when(nequal(file, "load.il")
load(file)
)
)

下面是解释
;load.il 加载函数自己名字为load.ilskillpath = "D://SPB_Data//pcbenv//skill";设定要加载的路径
;getDirFiles:读取路径中的文件
;rexMatchList:提取后缀为.il的部分做成list
;foreach:依次加载il文件
foreach(file rexMatchList(".*\\.il$" getDirFiles(skillpath))
; don't load myself -- bad idea
when(nequal(file, "load.il")
load(file)
);end when
);end foreach


加载所有skill路径的il格式skill文件
setSkillPath(buildString(append1(getSkillPath() "D://SPB_Data//pcbenv//skill" )))
  foreach(dir getSkillPath()
    when(isDir(dir)
           foreach(file rexMatchList("\\.il$" getDirFiles(dir))
        when(
           printf("Loading Skill file: %s\n" file)
           load(file)
      )
    )
  )
)
```

### 通过Skill加载菜单

```
; The following demos additional Allegro script capabilities:
; - command chaining via the ";" allows multiple commands on 1 line
; - "scriptmode +i" to make forms invisible; scriptmode value restored at
; end of command chain
; - "toggle" value for checkbox form fields will switch the checkbox state
; - "form_next" for enum fields (or checkboxes) will switch to next enum
; item (form_prev also available). Change "FORM" to form_next and
; remove value
custMenu = '(
(popup "User-Defi&ned")
("&LogoMaker" "logomaker")
("&Height" "upd_fe_height")
("&SMD Pin Count" "smd_count")
(separator)
("&Missing Paste/Solder Pad" "smd pad check")
("Fin&d Component" "find component")
("Find &Net" "find net")
("Change Net of Vias" "change_vianet")
("Assign Dummy Nets" "cns_dummy_net")
)
procedure( menuTrig1()
; add a new menu item before the help menu
res = axlUIMenuRegister(-1 custMenu)
)
; To see axlUIMenuRegister uncomment the following line
menuTrig1()
```

解密ile文件
-------

使用方法：文件load，输入NlDecrypt(加密文件 解密后文件)即可，例如：NlDecrypt(“123.ile”“123.il”)  
注意：该解密只能解密没有使用密码加密的ile文件，有密码的ile文件，即使知道密码，也无法解密。不要使用该脚本到非法用途和商业用途。