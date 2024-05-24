---
layout: post
title: TY-Skill Tool->PDF Link Allegro与PDF格式原理图交互
categories: TY-Skill
date: 2024-05-24
permalink: ty-skill-setup-power
excerpt: 
---

![](https://tiny-yhw.github.io//images/TY-skill/image-48.png)

## 功能说明
本程序仅作辅助查看电源线和非阻抗线（常规建议加粗的），不代表本程序能查找到所有这类信号，也不代表程序给出的信号一定是这类信号，只是大概率事件

在设计开始时可以使用此程序创建电源分组

在设计完成时可以使用此程序依次查看检阅电源信号

## 操作说明

1. 从菜单或命令启动此程序
2. 如果有Physical中有名称包含Power的Net Class则这个Net Class的所有net名称将列在右侧窗口中
3. 如果自动识别的Power Class不是你需要的可以从右上角Netclass Phy后的下拉选项选择你需要使用的作为要作为电源的Net Class，已经在你选择的作为电源的Net Class中的网络不会再在左侧列表中显示
4. 如果设计还没做电源的Net Class也可以从Netclass Phy后的下拉选项选择最后一个Create New，程序会自动新建一个Net Class
5. 从左侧列表或右侧列表选择对应的网络名，设计中的这个网络会跳转并高亮
6. 程序支持将指定网络增加到指定的Net Class或从Net Class中移出，选择指定网络（按住Ctrl或Shift可以多选或连续选择），使用箭头对指定网络进行增加或移出
7. 左上角Only Power勾选后将不识别部分控制类的信号，只分析明确的电源信号，见下文程序逻辑中的描述
8. 左上角Shadow勾选后将突出高亮信号更方便查看
9. 若在上述步骤6中对网络进行了分组或移出分组操作，点击Apply后这些操作将会生效
10. 如果6中你选择的网络已经在某个Net Class了，那么此程序不能直接将这个网络增加到指定的Net Class，程序会弹一个报告告知哪些网络未成功分类

## 程序逻辑

![](https://tiny-yhw.github.io//images/TY-skill/image-49.png)

### 通过识别Pin Name识别

在原理图中引脚定义Pin Name包含以下字段的引脚连接的网络的将被识别分析出来

```clike
VCC VDD VEE VREF REFIN REFOUT LDOIN LDOOUT VBAT VBST BOOT GND POWER VIN VSENCE VSONS VO FB PG PWRGD PERGD VBUS
```

若勾选了Only Power则仅识别

```clike
VCC VDD VEE VREF REFIN REFOUT LDOIN LDOOUT VBAT GND POWER VIN VO VBUS
```

### 通过识别Pin Type识别

引脚Pin Type为Power的引脚所连接的网络将被识别分析出来

### 通过识别器件类型识别

器件位号第一个字符为**F**或**L**则这些器件上的所有网络均作为分析对象

程序逻辑如上描述，确实存在符合以上逻辑但不属于此类的信号，也确实存在确实是此类信号但不含上述特征的情况，所以此功能仅作辅助使用，不作为正确性依据