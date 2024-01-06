---
layout: post
title: TY-Skill Display->Key Net Assign Color 为包含指定文本的网络增加颜色功能
categories: TY-Skill
date: 2023-08-22
permalink: ty-skill-display-key-net-assign-color
excerpt: 
---

## 功能说明

为包含指定文本的网络增加颜色功能，可用于为不用电压值的网络赋予不同的颜色，或包含指定文本的网络名赋予颜色

![Snipaste_2023-08-03_14-42-30.png](https://tiny-yhw.github.io//images/TY-skill/Snipaste_2023-08-03_14-42-30.png)

## 功能视频演示

<iframe width="720" height="405" frameborder="0" src="https://www.ixigua.com/iframe/7270064701219078690?autoplay=0" referrerpolicy="unsafe-url" allowfullscreen></iframe>

[抖音视频链接](https://v.douyin.com/iJsq3Dc5/){:target="_blank"}

9.43 Qkp:/ Allegro Skill 为关键网络赋予颜色 # allegro软件 # pcb设计  https://v.douyin.com/iJsq3Dc5/ 复制此链接，打开Dou音搜索，直接观看视频！

## 操作说明使用

Form右下主区域为主要控制区域

* 点击指定关键字前方的颜色块可以更改对应关键字的网络颜色
* 点击指定关键字前方的复选框为勾选将会为指定关键字的网络赋予指定颜色
* 同时左侧列表区域会列出所有包含此关键字的网络名，如果你希望某个网络不被赋予颜色，按住Ctrl键点击可以去掉指定网络
* （tips1：可以通过按住Ctrl或Shift键对列表区域的多个网络进行多选、加选或减选）
* （tips2：由于此功能设计初衷多用于为不同电压值赋予颜色，列表区域罗列的网络名已自动去除了名称中包含“en”字段的网络名）
* 点击指定关键字前方的复选框为不勾选将会为指定关键字的网络去掉赋予的颜色

### All on 按钮

开启所有包含关键字的网络对应的定义颜色

### All off 按钮

去除所有包含关键字的网络对应的定义颜色

### 可选项Disable_Custom_Colors

功能与下图选项相同,用于开启或关闭(切换)用户通过assign color或hilight命令定义的颜色

![Snipaste_2023-08-03_10-12-19.png](https://tiny-yhw.github.io//images/TY-skill/Snipaste_2023-08-03_10-12-19.png)

### 可选项 Zoom

视图将自适应大小到选择的焊盘，当选择的焊盘比较多时此功能将自动失效（软件程序限制）

### 可选项 Shadow

切换为阴影模式，突出显示选择的对象

## 操作说明配置

### 如何更改全局默认配色和关键字

该程序默认使用的是我自定义的几个颜色，另外支持使用自定义合适自己的配色

打开环境变量文件夹"%home%\pcbenv\dts_site\key_net_assign_color\key_net_assign_color.ini"文件

若文件不存在可先使用allegro运行一次这个skill程序即可生成此文件

此文件为全局配置文件，每个设计第一次运行均会读取此配置文件

配置文件可使用记事本打开编辑，从第2到最后一行，每一行为一个关键配置，配置格式参考已有部分样式，禁止使用中文字符

每一行以空格为划分符，分为几个字段

* 第一个字段为标识：即Form中显示的名称
* 第二个字段为配色值：用括号包起来的用逗号隔开的三个值为RGB配色值，如何确定指定颜色的RGB值见下文章节描述
* 第三个字段为关键字：用括号包起来的用逗号隔开的多个字符未关键字，即包含指定关键字的网络名被识别为同一组，使用相同的配色值

通过修改配色值和关键字可更改全局配置

还可以增加或减少行来增加或减少配置项（因Form显示限制，不建议使用太多行）

若由于编辑不当造成配置文件格式错误，可删除配置文件使用allegro运行一次这个skill程序，重新生成此文件

### 如何更改当前设计默认配色和关键字

每个设计第一次运行这个skill程序会默认复制使用全局配置文件，并复制一份到当前设计所在文件夹下生成一个"key_net_assign_color.ini"文件

通过修改当前设计所在文件夹下（下文简称工作目录）的此配置文件，可针对当前设计配置配色和关键字，配置文件格式与全局文件一致

工作目录下的配置文件对工作目录中的所有allegro文件同时生效

如果工作目录存在配置文件则不会读取全局配置文件，所以其是针对工作目录设计的配置

修改工作目录的配置文件不会影响全局配置文件，也不会对其它设计的配置产生影响

### 如何查看指定颜色的RGB值

![Snipaste_2023-08-03_15-41-48.png](https://tiny-yhw.github.io//images/TY-skill/Snipaste_2023-08-03_15-41-48.png)

从Allegro的颜色面板点击Customize按钮从基本颜色或颜色面板选择你需要查询的颜色，右下红绿蓝三个值基本对应颜色的RGB值