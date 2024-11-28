---
layout: post
title: TY-Skill Import->DSN Netin 快捷导入DSN原理图网表
categories: TY-Skill
date: 2024-11-28
permalink: ty-skill-import-dsn-netin
excerpt: 
---

![](https://tiny-yhw.github.io//images/TY-skill/Y_DSN-netin.png)

## 功能说明

用于在Allegro环境中选择DSN文件，快捷导入原理图网表，整个过程可无需打开原理图文件

## 操作说明

1. 从菜单或命令启动此程序进人导入配置对话框
2. 选择Autoload按钮自动加载原理图文件，或点击其前面的“...”按钮从文件浏览器选择指定的DSN文件
3. 从DSN Netout区域可以配置Capture网表导出参数选项，这些设置和原理图导出网表时的设置是一样的，但部分默认值有变化
 - Configuration File:配置文件指定及修改参数，默认值与Capture一致
 - Device/Net/Pin Name Char Limit:Device/Net/Pin名称字符长度限制，Capture中的默认值为31，本处此值的默认值关联联brd设置中allegro_long_name_size，改大此值将同步更改allegro_long_name_size值，allegro_long_name_size可以尽量大使用255,大了没坏处
 - Ignore Electrical constraints:忽略电气规则，Capture中的默认值为不勾选，本处默认值为勾选
4. 从Allegro Netin区域可以配置Allegro网表导入参数选项，这些选项和Allegro自身的netin是一样的，Ignore FIXED property默认值为勾选，其它几项默认值为不勾选
5. 点击DSN Netout按钮将从原理图中导出网表文件
6. 待5执行完毕后点击Allegro Netin按钮即将网表导入Allegro

## 程序说明

### Autoload自动读取原理图文件逻辑

- 程序自动从指定路径搜寻dsn后缀的文件，若指定路径有且仅有一个原理图文件时则加载此文件
- 指定路径第一优先级为“./”即与brd同级路径
- 指定路径第二邮箱即为“../sch/”即brd路径父级（上一级）的sch路径，比如brd在“D:\demo\pcb”对应的第二优先级“D:\demo\sch”
- 如果以上两个路径都没有满足条件“有且仅有一个原理图文件”则不进行加载

### 导出的网表文件在哪

指定原理图路径下的allegro文件夹，与Capture默认值一致

### 几个辅助操作按钮功能

- Open DSN Floder:打开原理图所在文件夹
- Open Dsn:打开指定的原理图文件，如果你放置的DSN文件符合要求，甚至可以一直利用这里的按钮开原理图
- Open Netlist Folder:打开网表文件所在路径
- Open ECO:打开brd路径的“eco.txt”文件
- Viewlog: 打开原理图网表导出和PCB网表导入的log报告