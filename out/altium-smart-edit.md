---
title: 'Altium Smart Edit'
date: Fri, 28 May 2021 03:00:56 +0000
draft: false
tags: ['Altium']
---

本功能提供了两种不同的方法来执行功能强大且复杂的字符串修改可以应用于PCBLIB、PCB、SCH、SCHLIB的关于文本的快捷修改，让你从设计中修改文本像从Excel中通过查找替换或公式函数来修改一样简单，以下以PCB中使用的方法为例，在原理图中的应用方法类似不再赘述,其实应该是原理图中的修改更为常用。

如何访问
----

### List面板

从PCB List or PCBLIB List 面板，选择你要修改的数据范围（文本类型）要求对象为文本类型，且list面板是编辑状态（也可以从右键切换，同时建议仅操作被选择的对象），然后右键选择**Smart Edit**

![](http://a1024.synology.me:222/images/blog2022/Smart%20Edit1.png)

### 属性面板

从设计中选择对象，按F11调出属性面板，选择文本类型字段，右侧将出现一个...，单击他进入

![](http://a1024.synology.me:222/images/blog2022/Smart%20Edit2.png)

功能选项
----

### Batch Replace 批量替换

本标签页用于文本的查找替换，From列填你要替换的文本，To列填你要替换为谁，编写多行代表需要分别替换多种情况，比如需要把某个设计封装的引脚号AA1-AA100替换为A1-A100；BA1-BA100替换为B1-B100，可以选择这些pad后打开本功能按如下设置来实现，

![](http://a1024.synology.me:222/images/blog2022/Smart%20Edit3.png)

### Formula 公式

相对上面的查找替换，这个标签提供更高级的修改方式，支持通过表达式来达成某种修改，适用于字符串的任何内置算术运算符和函数（在[Pascal](https://baike.baidu.com/item/pascal%E5%87%BD%E6%95%B0)中找到）。如果要将属性的当前值用作表达式的一部分，则需要通过使用属性的全名或使用感叹号替代本值来引用此原始值。使用属性名称时，如果文本包含空格，须将其替换为下划线字符。例如，在公式中使用“Component Comment”字段应输入为`Component_Comment`。

比如某设计要在所有TOP面的器件位号前加“T”，Bottom面器件位号前+“B”，可以分别选择所有Top面器件使用表达式输入‘T’ + ！或 ‘T’ + Name。（本案例中T代表所加前缀文本使用单引号括起来；+代表组合；！代表当前操作的对象值；Name代表器件位号）同理Bottom层也按此方式进行修改

Copy用于提取文本中的字段，与Excel中的Mid语法一致，以下是一个将某个封装中AA1-AA1000前缀去掉的方法，此处我们理解为取值为从第三位开始取到结束

Copy(!,3,4) ，这里的3代表从第三位开始取，4代表向后取4位，这里最大值为1000所以4位够用了

关于本功能的更多应用我还用的很少，灵活使用可以实现很多神奇的功能，等我以后再用到我在补充更多案例

PCB Inspecor
------------

本文引申一个关于属性面板修改的一些灵活应用，直接用案例来说，关于其中的底层逻辑自己去琢磨理解，其它的应用场景也自己举一反三

### 支持公式

![](http://a1024.synology.me:222/images/blog2022/PCBinsp1.png)

![](http://a1024.synology.me:222/images/blog2022/PCBinsp2.png)

### 支持变量代数

![](http://a1024.synology.me:222/images/blog2022/PCBinsp3.png)