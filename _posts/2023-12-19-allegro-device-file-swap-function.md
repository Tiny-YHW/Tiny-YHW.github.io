---
layout: post
title: Allegro Device Files 应用 Swap Function调管脚
categories: Allegro
permalink: allegro-device-file-swap-function
date: 2023-12-19
---

公众号聊天发送“allegro-device-file”或“231219”从公众号阅读此文，包含所有图文内容

## 文件介绍

Device files是ASCII文本文件，可提供唯一的components逻辑信息，在设计database创建期间，将Device files链接到相关的package symbols以获得这些独特components的完整描述。

Device files为layout editor提供以下信息：

- Package configuration (for example, DIP and SIP)
- Placement class of the package (for example, IC, discrete)
- Number of pins in the component package
- Electronic description of the component pins (for example, logical use and pin swap information)
- Number of functions in the physical package
- How functions are mapped to package slots
- Pin use (how pins are used)--for example, input pins, output pins, and bidirectional pins
- How the logical function pins correspond to the physical pins of the package
- Which pins are tied to power and ground
- Definition properties, such as alternate symbols that can be used instead of the primary package symbol during placement

机器翻译如下

- 程序包配置（例如，DIP和SIP）
- 封装的放置类别（例如，IC，离散）
- 组件封装中的引脚数
- 组件引脚的电子描述（例如，逻辑使用和引脚交换信息）
- 物理包装中的功能数量
- 功能如何映射到软件包插槽
- 引脚使用（如何使用引脚）-例如，输入引脚，输出引脚和双向引脚
- 逻辑功能引脚与封装的物理引脚如何对应
- 哪些引脚连接到电源和接地
- 定义属性，例如可以在放置期间代替主要包装符号使用的替代符号

## 文件格式

### 文件准则

- 区分大小写
- 括号内文本作为注释内容
- 每行为一个语句
- 除特殊语法有特殊的分隔符外均使用空格作为分隔符
- 文本内容使用单引号括起来

![/](https://tiny-y.asia/images/blog/2022/chap5.8.1.1.png)

![/](https://tiny-y.asia/images/blog/2022/chap5.8.1.2.png)

### PACKAGE

```
PACKAGE <name>
```

可省略，但强烈建议保留，代表物理封装（footprint），如果信息不一致对应的逻辑不会被调用

### CLASS

```
CLASS <type>
```

可省略，但强烈建议保留，代表元器件类别，分别可用IC、IO、DISCRETE

如果Device不包含引脚顺序部分，将使用该类来确定设备中包含多少个功能。如果指定IO类，则每个引脚视为一个函数。如果指定IC类，会将所有引脚（电源和接地引脚除外）视为一种功能。

### PINCOUNT

```
PINCOUNT <number_of_pins>
```

必要的，代表引脚数量

### PINORDER

```
PINORDER <function_type> <list_of_pin_names>
```

定义引脚的PIN_NAME

可选的。PINORDER记录包含有关device中唯一功能类型的信息。您还必须提供PINUSE，PINSWAP和FUNCTION记录才能完全定义功能。

function_type:功能名

list_of_pin_names：与该功能关联的引脚列表。用空格或制表符分隔每个引脚名称。引脚名称可以是字母数字。每个引脚名称对应于该功能的引脚。

### PINUSE

```
PINUSE <function_type> <list_of_pin_use_codes>
```

可选的。 PINUSE记录定义门内每个引脚的逻辑用途。您必须为PINORDER记录中列出的每个引脚指定一个引脚使用代码。

function_type：名称

list_of_pin_use_codes：门中使用的引脚类型的列表包括

- IN: Input
- OUT: Output
- BI: Bidirectional
- TRI: Tristate--sending, receiving, or held at some state
- OCA: Open Emitter
- OCL: Open Collector
- POWER
- GROUND
- NC: Not connected internally
- UNSPEC

### PINSWAP

```
PINSWAP <function_type> <list_of_pin_names>
```

定义哪些PIN_NAME可以一起交换
可选的。PINSWAP记录告诉interactive and automatic swapping routines，门内的哪些gate是可以交换的。

### FUNCTION

```
FUNCTION <slot_name> <function_type> <list_of_pin_numbers>
```

可选的。 FUNCTION记录标识PINORDER记录中描述的功能类型的the slots available in the package

slot_name：门的名称。必须与PINORDER记录中定义的门匹配。.
function_type：physical slot的名称.
list_of_pin_numbers：device的字母数字引脚号列表. 引脚号必须与与此device相对应的package symbol的引脚号匹配，引脚号间使用空格分隔

### 其它

POWER：电源引脚名和引脚号

GROUND：GND引脚名和引脚号

NC：NC脚的引脚名和引脚号

PACKAGEPROP：不懂

END：代表结束标记

## 应用案例

Tips：可以使用Allegro菜单File-Export-Libraries，勾选Device files和Package symbols则可以输出整板所有器件的Device files格式的txt文件和封装.dra、psm、pad文件

### 排阻间成对交换

关键字：排阻调管脚

1、打开排阻.dra文件，选择File-->Create Device生成对应的DeviceType.txt文件

2、对DeviceType.txt进行编辑，按上文规则设置可交换的Function，如下为一个案例，做参考使用

```
(DEVICE FILE: 8p4r_0603)

PACKAGE 8p4r_0603
CLASS IC
PINCOUNT 8

PINORDER 8p4r_0603  G1 G2

PINSWAP 8p4r_0603  G1 G2

FUNCTION F1 8p4r_0603  1 8
FUNCTION F2 8p4r_0603  2 7
FUNCTION F3 8p4r_0603  3 6
FUNCTION F4 8p4r_0603  4 5

END
```


3、使用菜单Logic-->Part Logic后选择对应类别的元器件对其Device属性进行替换并修改完成后（选择上述修改后的文件）进行应用，注意需提前定义Devpath路径（Setup->User Preferences->Paths->library->devpath）才能找到对应路径的对应文件。

![/](https://tiny-y.asia/images/blog/2022/paizuswap.png)

4、使用菜单Place -> Swap -> Swap Functions（建议临时指定一个快捷键进行此操作）对排阻内或排阻间的引脚对进行交换

```
funckey key swap functions
```

选择命令后后依次选择需要交换的两个引脚后点击空白处或执行done命令完成一次交换，再次选择命令进行下一组；或者选择命令后依次选择需要交换的两个引脚，再继续选择下一组需要交换的引脚直到完成所有选择后点击空白处或执行done命令完成所有操作

### 另一个案例

![/](https://tiny-y.asia/images/blog/2022/74swappindevice.png)