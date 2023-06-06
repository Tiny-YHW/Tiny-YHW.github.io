---
title: 'SigXplorer 设置方法'
date: Mon, 27 Apr 2020 08:07:07 +0000
draft: false
tags: ['Allegro']
---

使用场景
----

如图SDRAM的连线U2到U5、U6和U7的地址线均需要设置等长，常规我们对每个网络设置pin pair，会比较繁琐，设过的人都知道。

![](http://a1024.synology.me:222/images/blog2022/1.jpg)

创建Cset
------

开始设置，打开规则管理器，在电气规则里面选择任意一个net，右击新建一个Electrical CSet（这里理解为新建了一个模型 下文简称CSet），起一个你认识的名字（很多人会忽略这一步，那样的话软件会用当前网络名自动命名CSet）

![](http://a1024.synology.me:222/images/blog2022/2.jpg)

![](http://a1024.synology.me:222/images/blog2022/3.jpg)

调用Cset
------

同组相同连接方式，需要一起等长的net均套用CSet

![](http://a1024.synology.me:222/images/blog2022/4.jpg)

编辑模型
----

指向任意一个CSet右键选择Sigxplorer，对模型进行设置

![](http://a1024.synology.me:222/images/blog2022/5.jpg)

下图是模型界面，为了方便看可以调整一起符号位置

![](http://a1024.synology.me:222/images/blog2022/6.jpg)

![](http://a1024.synology.me:222/images/blog2022/7.jpg)

等长参数
----

选择菜单Set-Constraints（快捷键Alt+S然后C），选到Rel Prop Delay（相对等长，常用的等长方式用的相对误差，通过Prop Delay也可以设等长，用的最大最小值）

*   Existing Rules：已经做好的规则 及包含信息 点new会自动分配一个name
*   Pins/Tees：pin脚名，或选择内建逻辑
*   Rule Editing：新建规则，或对已建的规则进行修改更新
*   Rule Name：规则名，是Existing Rules里面的name,未来是matchgroup的组名
*   From&to：开始端及结束端，从Pins/Tees选取或单击左侧符号引用
*   Scope：Controls how the members of the Group are validated. Select one of the following from the drop-down list（不懂求指教，一般都选Global ）
*   Delta Type&Delta：增量形式及增量，感觉像是在线长的基础上加长，一般都选None
*   Tol Type：公差形式，可选延时，长度，或者百分比
*   Tolerance：上行形式对应值

设置好上面这些选择Add即将此规则加到模型，点击modify或Delete相应可对Existing Rules进行修改或删除，然后点击ok或apply规则生效

![](http://a1024.synology.me:222/images/blog2022/8.jpg)

更新模型
----

选择菜单Flie-Update，讲此模型及规则更新脚规则管理器，等长组即更新好

![](http://a1024.synology.me:222/images/blog2022/9.jpg)

模型验证
----

从下图看有一些网络模型套用是红色的，没错这些网络的连接方式（拓扑结构）与模型不一致，模型会调用失败

![](http://a1024.synology.me:222/images/blog2022/10.jpg)

模型管理
----

好了完毕，顺便带一句，这里是总的模型的管理。

![](http://a1024.synology.me:222/images/blog2022/11.jpg)