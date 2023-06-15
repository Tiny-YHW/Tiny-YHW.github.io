---
layout: post
title: Allegro (AIBT)Auto Interactive Break Out Technology自动交互布线技术
categories: Allegro
description: 
date: 2023-06-15
---


[Allegro Flow Planning将设计意图表达在设计中](https://a1024.synology.me:1024/allegro-flow-planning/)

使用此功能前建议学习上面章节内容

菜单Setup > Design Parameter Editor > Route >Auto-I.Breakout、Auto-I. Trunk Route可对两个功能的预设参数进行调整：如是否移除已布的线、是否参照创建的**Bundle**和Flow规则、是否避让动态铜皮等

![](http://a1024.synology.me:222/images/blog2022/aibt.png)

Auto I. Break Out 自动交互扇出引线
--------------------------

### 生成线序

选择已经创好的Bundle，右键选择Flow Edit > Sequence > Generate 程序将按Bundle连接的点在两端生成线序，可使用Flow Edit > Sequence > Eidt选择两个网络交互顺序，直到布线能够畅通，再次使用Flow Edit > Sequence > Generate生成线序

### Break Out不知道怎么翻译就叫扇出吧

选择创建好Bundle并预设好线序的Flow

右键选择Auto-I. BreakOut Both Ends，可将线从连接的两段均扇出到集结点处

右键选择Auto-I. BreakOut Closest Ends，可将线从较近的一端扇出到集结点处

右键选择Auto-I. BreakOut Delete，可删除已经扇出的布线

线序调整和Break Out可以交叉调整，排序不分先后

<iframe frameborder="0" src="https://v.qq.com/txp/iframe/player.html?vid=u0975xgaz3m" allowfullscreen="true" width="640" height="480"></iframe>

Auto-I. Trunk Route 自动交互布线
--------------------------

### 交互布线

选中Bundle后右键选择Auto-I. Trunk Route，程序将按预设参数完成Break Out后对Bundle的布线(Setup > Design Parameter Editor > Route >Auto-I. Trunk Route)

### 设置间距

选中Bundle后右键选择Auto-l. Adjust Spacing (Prototype)，可对交互布线的间距按规则值或指定值进行调整

### Swap Pin

若设置好的了对元器件设置好了Swap Pin属性，可选中Bundle后右键选择Auto-I. Swap Pins Closest End (Prototype)，进行自动根据线序自动Swap Pin使线序平行一致，进行完此项功能需重新生成Break out

### 等长调整

若设置好的了对应Bundle的网络的Machgroup规则，可选中Bundle后右键选择Auto-interactive Delay Tune程序将按预设参数完成自动绕等长(Setup > Design Parameter Editor > Route >Auto-I Delay Tune)

<iframe frameborder="0" src="https://v.qq.com/txp/iframe/player.html?vid=v0975kxch79" allowfullscreen="true" width="640" height="480"></iframe>

Tip：如果Bundle比较长使用View > Split View 可以分割出一个敞口用来查看连接另一端的状态

结合使用
----