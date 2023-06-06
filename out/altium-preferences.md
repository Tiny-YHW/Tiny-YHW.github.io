---
title: 'Altium Preferences'
date: Mon, 11 May 2020 09:16:17 +0000
draft: false
tags: ['Altium']
---

关键字：Altium 配置 用户设置 首选项

![](http://a1024.synology.me:222/images/blog2022/Altium%20Preferences.png)

仅介绍常用修改项，标红色的为我常规会修改的选项，其它的均使用默认，有按需的情况可能会对其进行修改，未做介绍的基本不会更改（没有必要或者我还没理解其用意）

System
------

### General

**Startup软件启动设置**

*   重新打开最近一次进行的工程（按需使用，如果电脑配置不高建议关闭，打开工程可能会耗费一些时间，尤其是你不需要开启此工程时）
*   软件开始时打开主页（建议关闭，除非你要及时关注官网动态）
*   显示启动过程界面（选择性启动或关闭）

**Reload Documents Modified Outside of Altium Designer文档修改响应**

当Altium中正在打开的文档被其它应用修改后Altium是否重新加载为被修改后的文档（按需设置）

*   不修改
*   询问
*   修改

Localization本地化（切换中文）（不建议使用中文，影响使用快捷键的感觉）

**Advanced**（高级设置）

**PCB.LayerDrawingOrder.ProperMultilayer**

上述可配置项从AD21开始引入，在以前的版本中，PCB 编辑器始终以多层图层颜色显示多层对象。 在此版本中，多层的行为变得直观且可预测，在单层模式下多层对象（如过孔或通孔pin的盘）将使用单层模式显示（[演示链接](https://www.altium.com/documentation/sites/default/files/wiki_attachments/302670/AccurateMultilayer.mp4)），如果习惯使用早期版本的显示模式可以取消此项配置的勾选

**PCB.ComponentDrag.ConnectionLimit**

拖拽器件是最大允许显示飞线数，当移动器件的pin总数超出此值时其飞线将会被主动关闭，按需设置

**UI.UseActiveBar**

打开或关闭PCB视图页面前端中间靠上位置的快捷图标（对于我这种熟知各种命令键盘按键的玩家这种东西只会遮挡视线，所以我选择关闭）

**BOM**.**ActiveBOMDesignPreview**

上述可配置项从AD22开始引入，默认会自动在工程下生成一个ActiveBOM，如果不需要可以设置这里关掉这个功能

[Altium指定某层作为元器件布局边框](https://a1024.synology.me:1024/altium%e5%88%b6%e5%ae%9a%e6%9f%90%e5%b1%82%e4%bd%9c%e4%b8%ba%e5%85%83%e5%99%a8%e4%bb%b6%e5%b8%83%e5%b1%80%e8%be%b9%e6%a1%86/)

### View界面显示

**Desktop软件布局**：加载保存或重置软件可视化布局

**UI Theme：**切换明暗两种软件主题显示，明亮的为17及版本之前的色调，黑暗的为18及之后默认的色调

### Account Management

Altium Connection：不需要连接到Altium网络时可以关闭，节约资源

### Navigation 导航？不知道怎么翻译

**Objects To Display**：哪些对象显示

**Cross Select Mode**：原理图和PCB交互开关（建议打开），重要设置项，左边设置交互时显示的模式，右边设置哪些对象允许交互（建议关闭Nets）

### Default Locations

按需修改全局默认的几个路径

### **File Type**软件识别文件后缀设置

当后缀被选中时则此类文件默认通过Altium软件打开，即打开方式的设定

### Installation

自动检查更新频次，建议选为Never，因为（我们用的都是pojie版）不需要更新

### Product Improvement

参与产品改进计划，个人用建议关闭

### Network Activity

网络活动使能项，建议除Built-In Browser外全部关闭，因为我们基本也不会使用那些在线功能，如果你需要某项可以单独开启，比如Parts Providers（零件供应商）选项等

Built-In Browser如果关闭后所有html界面将会从浏览器打开而不是Altium内置的浏览器

Data Management
---------------

### Backup

自动备份选项，建议开启，自动备份时间和步数自己按需设置即可。

### Local History

Use global repository：关于历史保存版本的存档位置修改（默认值为pcbdoc所在路径，可修改至某固定位置）

### Flie based Libraries

安装或移除Altium设计的安装库，

PCB Edit PCB编辑器
---------------

### General

#### Eiditing Options

**Online DRC**：在线DRC开关

**Object Snap Options**：吸附对象参考点设置

**Remove Duplicats**：移除重复，默认为开，建议开启，可移除重孔和重线等重复画的图形

**Protect Locked Objects**：保护锁定对象，当对象有锁定属性时，不能通过鼠标单击、拖动、框选动作与对象互动，需要双击可与对象互动

#### **Other**

**Rotation Step**：旋转步进值，默认为90，尤其当元器件需要45度放置时，修改此处为45，当然也可以直接编辑元器件角度属性实现

**Cursor Type**：光标样式，大小十字或X

**Comp Drag:**元器件对齐引导线

**Polygon Rebuild**：**Polygon**被修改后是否立即更新，更新被修改的**Polygon**和更新所有相关的**Polygon**

**File Format Change Report**：打开别的版本保存的设计时，是否显示差异报告

### Board Insight Display

**Available Single Layer Modes**：单层模式设置，当启用单层显示模式时（Shift+S）除当前层外的图层状态，包括隐藏其它层、灰化其它层、其它层变为同一种灰色

### True Type Fonts

**Embed TrueType fonts inside PCB documents**：TrueType字体是安装在计算机上的字体。启用此设置以保存您在PCB文件中使用的TrueType字体。这将允许没有特定字体的其他机器查看您想要的设计时字体保持不变。关闭此项可以让PCB文件不包含字体文件，可以减小PCB文档的存储大小，是一个不错的可选项，但当查看PCB不包含特定字体时会被下面的字体取代，自行选择是否勾选此项设置

**Substitution font **：替换字体将替换您打开的文件中包含的任何TrueType字体，但这些字体不在您的系统中。使用下拉菜单选择所需的字体

### **Defaults**

设计中所有元素被设计时的默认状态，配合设计习惯使用能很大程度上提高设计效率（个人设置项如下仅供参考）

#### Polygon

设置移除死铜选项 和 Pour Over All Same Net Objects，移除面积小于2500 sq.mil的选项按需设置或者去掉勾选，防止铜皮过小时铺不出来

#### via

设置过孔Tented（盖绿油不开窗）

#### Track

指定层对应的线宽，丝印层0.12mm

#### String

默认增加字符，字符的层和大小等

### Report

某些报告输出时的格式以及是否立即打开

### Layer Color

图层颜色设置

Scripting System
----------------

**Global Projects**：为软件安装脚本程序，一次安装永久有效

**Form Designer**：脚本调用窗口时，窗口的格点和大小

DXPPrf（软件配置文件）
--------------

以下几个文件是我常规会导入的选项

### Version Control

包含了history的保存逻辑（我设置了保留到指定位置，而不是当前文件夹）

### System

对应配置中的System，包含高级设置，跨大版本时慎导，

Templates包含定义的快捷键设置

Customizations包含自定义的菜单

### Data Management

### PCB Eidtor

### Scripting System