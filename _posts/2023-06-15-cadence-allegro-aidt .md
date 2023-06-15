---
layout: post
title: Allegro Auto-Interactive Delay Tune (AIDT) 自动等长
categories: Allegro
description: 
date: 2023-06-15
---

用于自动调整一组设好match group的clines，使clines延时匹配

如下视频02:03-04:45部分为此功能的演示

<iframe frameborder="0" src="https://v.qq.com/txp/iframe/player.html?vid=u05222pbpop" allowfullscreen="true" width="640" height="480"></iframe>

### Aidt Option

![](http://a1024.synology.me:222/images/blog2022/aidt14.jpg)

上图基本能说明这些参数额外解释  
排除智能信号：仅在tvision命令中将时序模式设置为smart timing时此参数才有效

![](http://a1024.synology.me:222/images/blog2022/aidt15.jpg)


### 应用实践

首先连好需要做等长的线，如下图并设好规则

![](http://a1024.synology.me:222/images/blog2022/aidt4.png)

![](http://a1024.synology.me:222/images/blog2022/aidt3.png)

TIPS：关于目标值，碰巧遇一个设规则的图，当然这是截的Relative Delay（相对规则）的图，比较常用，那我顺便多说一些，Delta：Tolerance（Δ：公差），这边我们常用0:100表达，多数人都晓得是±100的误差，但我听到的所有教程都是这样的：设好规则和误差，按length长度排序，找到最长值，看能否变短，直到不能变短，则把它设置为目标值，等等！是不是哪里不对，明明是正负公差，那为什么要拿最大值做目标值呢，所以我来纠正一下这个误区，正确的姿势应该是按照上图截图方式设置目标值max-to=2182-100=2082 选一个比他大离它最近的值做目标值。

找到目标值 我这里高亮了一个红色（其实没什么用，不过建议lock一下它不lock一般也没关系）

![](http://a1024.synology.me:222/images/blog2022/aidt7.png)

然后菜单或自动等长指令aidt，设置好对应参数（见文末）

![](http://a1024.synology.me:222/images/blog2022/aidt5.png)

![](http://a1024.synology.me:222/images/blog2022/aidt6.png)

然后分别选取或直接选取我们要绕等长将自动生成

![](http://a1024.synology.me:222/images/blog2022/aidt8.png)

![](http://a1024.synology.me:222/images/blog2022/aidt9.png)

上图是分别用“长号”和“手风琴”方式的运行结果，可见并不是太理想，因为我们一般绕等长的线对时序有要求的同时会对信号干扰比较在意，所以会要求间距3w，然后以上设置并没有涉及此项，仅仅因为这个问题似乎好多人认为这个功能有点“鸡肋”，但只要我们再多想一层，用区域规则来限制信号间距，那这功能是不是可以直接晋升为神器，接下来我们试试

还是那个设计我们在default的基础上新建一个3w的规则仅修改line to line的规则其实刚刚那个线宽为4我这里设置为10效果会更好一些

![](http://a1024.synology.me:222/images/blog2022/aidt11.png)

![](http://a1024.synology.me:222/images/blog2022/aidt10.png)

然后用规则shape框住理想中这些信号需要绕的区域这样会出现一些drc，我们视情况调整（可能不调整也没关系）此范例我没有调整这些drc

![](http://a1024.synology.me:222/images/blog2022/aidt12.png)

然后用aidt指令，设置参数框选这些线，下面是“长号”和“手风琴”方式的两种结果

![](http://a1024.synology.me:222/images/blog2022/aidt2.png)

![](http://a1024.synology.me:222/images/blog2022/aidt13.png)

Tips：等长绕完之后可能会存在一些没有比较的拐角配合custom smooth使用效果更佳等长处理完毕command窗口会显示类似Clines Selected: 28; Timing constraints: 28; Timing violations: 7; Outside ideal range: 1 的报告注意看一下

