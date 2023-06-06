---
title: 'Allegro 16.6增效功能'
date: Tue, 02 Jun 2020 02:10:46 +0000
draft: false
tags: ['Allegro', '设计技巧']
---

基础功能
----

https://v.qq.com/x/page/w0975lb6c1m.html

### 元器件对齐

说明：将选中的元器件按水平或垂直方向对齐或等距分布

使用方法：在Placement Eidt模式下选择元器件，右键选择Align Componment，调整Option

### 放置带倒角（圆角）的铜皮

说明：放置预编辑好尺寸或倒角的Shape

使用方法：选择放置矩形shape命令，调整Option

### 缩放Shape

说明：按一定步进值外扩或内缩Shape边框

使用方法：选择Shape，右键选择Expand/Contract，调整Option

### 显示网络名

说明：在Shape、Traces、Pins上显示该对象的网络名称

使用方法：在OpenGl开启的状态下，选择菜单Setup-Design Parameters，调整Display net names下的复选框

### 异形选择工具

说明：按任意形状的选择方式选择对象

使用方法：再无指令状态下，右键选择Selection set，选择各种选择工具

*   Select by Polygon
*   Select by Lasso
*   Select on Path

![](http://a1024.synology.me:222/images/blog2022/lasso.png)

### 显示双单位

说明：使用测量工具是同时给出2种单位的数值

使用方法：在用户设置框中设置Display–>Element  showmeasure\_altunits，可以设置成millimeters此时进行测量时，会显示双单位

![](http://a1024.synology.me:222/images/blog2022/show_measure.png)

### Contour Routing 按轮廓布线

说明：软硬结合设计软区经常使用圆角，若布线路径预软区圆角路径一致可以获得更优质的布线空间

使用方法：在Add connect命令时右键选择Contour，调整依附轮廓和间距参数，顺着轮廓描摹即可

![](http://a1024.synology.me:222/images/blog2022/highspped5.png)

### Auto Connect 自动布线

待补充

### Scribble Mode Routing 涂鸦模式布线

个人感觉有点鸡肋，没什么用途，在Add connect命令时通过右键菜单选择Scribble Mode激活此布线模式

![](http://a1024.synology.me:222/images/blog2022/scribble_mode_routing.png)

### Split Views分割视图

将当前显示界面分割为两个部分，分别对焦不同的设计区域，当进行较长的布线时，可以直观清晰的看到连接两端的状态，通过菜单View-Split View访问

![](http://a1024.synology.me:222/images/blog2022/split_view16.66.png)

### Find by Query高级的查询过滤选项

可以设置更多的查找条件，查找需要的对象，从Find面板下端的Find by Query访问，如图分别为查找所有使用padstack PAD19的引脚，和查找/突出显示U100上所有GND引脚的示例

![](http://a1024.synology.me:222/images/blog2022/find_by_query.png)

![](http://a1024.synology.me:222/images/blog2022/find_by_query_2.png)

### Ref-Des Layer Visibility Control

移动symbol时默认显示装配层的位号，现在可通过定义_display\_refdes\_subclass_值设置，显示某个层的位号

![](http://a1024.synology.me:222/images/blog2022/display_refdes_subclass.png)

### DRC marker - Link to Constraint Manager DRC定位到规则管理器

再_General Edit_ App模式下选择DRC符号右键选择_Display DRC_，程序将打开规则管理器定位到冲突规则详情

### Auto Interactive Convert Corner (AiCC)

自动交互转换倒角：将板中已完成布线的Clines/Cline segs/Nets倒角为圆弧或固定角度，因行业内的设计习惯，倒圆角功能比较实用，其它功能不做介绍

命令：aicc

菜单：Route->Unsurpported Prototypes->Auto-interactive Convert Corner

操作方法：选择命令->设置选项->设置过滤项->选择对象（可进行多次选择），选项简单不做介绍

![](http://a1024.synology.me:222/images/blog2022/Aicc.gif)

### Symbol Instance Refresh

[refresh syminst 刷新重置选中的symbol](https://a1024.synology.me:1024/refresh-syminst-%e5%88%b7%e6%96%b0%e9%87%8d%e7%bd%ae%e9%80%89%e4%b8%ad%e7%9a%84symbol/)

### 杂七杂八

*   Add Connect选择其中一个飞线时可选让其它飞线隐藏
*   Snap Pick选项增加焊盘边缘，对象中心、偏移值等可选项
*   可对字号定义名称，更方便识别，而不是只叫1234
*   3D可视化效果增强
*   非常多的RF选项功能（本人很少用）
*   输出Step（3D）格式的PCB文件
*   IPC2581支持
*   Artwork设置中可定义序号作为光绘文件输出的页码顺序
*   记忆线宽选项（并不好用）
*   测量时显示测量支持两个对象之间的角度
*   款选多个Shape 右键_Assign Net_ option中选择网络
*   Logo Import (Symbol Editor only)导入logo（并不好用）
*   背钻功能增强
*   尺寸标注关联到对象实时更新
*   Find过滤器新增可过滤对象
*   新增重新编号符号引脚功能
*   Shape Edit App模式中的多项铜皮编辑功能（本人很少用）

ToolBox
-------

使用下述功能需启用Allegro Productivity Toolbox产品选项，可在软件启动时选择或File-Change Editor选择。

https://v.qq.com/x/page/p0975ttcv0e.html

### 高级镜像

说明：将多个对象按同面进行图形镜像或按镜像面镜像

使用方法：选择菜单Eidt - Advanced Mirror，调整Option，选择对象

[https://www.u-c.com.cn/w/news/technical/63.html](https://www.u-c.com.cn/w/news/technical/63.html)

### 批量修改线宽

说明：修改指定区域内某值线宽的Clines改变线宽

使用方法：选择菜单Eidt - Change Width，调整Option，选择目标层（可以是多个），选择区域

### 跨类复制

说明：将一个Class的对象复制或移动到另一个Class（Change命令不能跨Class Change）

使用方法：选择菜单Eidt - Cross Copy，调整调整Option，选择对象

### Class颜色

说明：对用户定义过额Net Class标记一种颜色显示

使用方法：选择菜单DisPlay - Class Color，调整对话框并应用。

### [位号调整 Label Tune](https://a1024.synology.me:1024/label-tune-%e4%bd%8d%e5%8f%b7%e8%87%aa%e9%80%82%e5%ba%94%e5%a4%a7%e5%b0%8f%e5%b9%b6%e5%b1%85%e4%b8%ad/)

### [查看板中的过孔Via类型或焊盘Padstack类型](https://a1024.synology.me:1024/allegro-%e5%a6%82%e4%bd%95%e6%9d%bf%e4%b8%ad%e7%9a%84%e8%bf%87%e5%ad%94%e7%b1%bb%e5%9e%8b/)

Planning Option
---------------

### [Auto Interactive Break Out Technology](https://a1024.synology.me:1024/allegro-aibtauto-interactive-break-out-technology%e8%87%aa%e5%8a%a8%e4%ba%a4%e4%ba%92%e5%b8%83%e7%ba%bf%e6%8a%80%e6%9c%af/)

### [Flow Planning](https://a1024.synology.me:1024/allegro-flow-planning/)

高速互连增强
------

[Allegro 16.6高速互连增强](https://a1024.synology.me:1024/allegro-16-6%e9%ab%98%e9%80%9f%e4%ba%92%e8%bf%9e%e5%a2%9e%e5%bc%ba/)

Relational Rules Checker 关系规则检查器
--------------------------------

新的绘图能力
------

[Allegro 新的绘图能力](https://a1024.synology.me:1024/allegro-%e6%96%b0%e7%9a%84%e7%bb%98%e5%9b%be%e8%83%bd%e5%8a%9b/)

相关附件
----

[allegro\_v166\_new](https://layouto.lanzous.com/imXWIew52ha)

[allegro\_v166\_new\_QIR8](https://layouto.lanzous.com/itU51ew528b)