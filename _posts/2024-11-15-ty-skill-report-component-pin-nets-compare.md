---
layout: post
title: TY-Skill Report->Component Pin Nets Compare 报告BRD文件间器件网络差异情况
categories: TY-Skill
date: 2024-11-15
permalink: ty-skill-report-component-pin-nets-compare
excerpt: 
---

![](https://tiny-yhw.github.io//images/TY-skill/report-component-pin-nets-compare1.png)

## 功能说明

比对当前BRD设计中指定器件和被比较BRD的指定器件的所有PIN网络分配差异
推荐用于调管脚后比对两个设计的管脚差异输入报告发给原理设计放调整管脚网络分配

## 操作说明

1. 从菜单或命令启动此程序
2. 从Original brd输入要比较（原始的）的设计软件
3. 从Now Symbol按钮从板中选择一个要比较的器件或者手动输入其位号
4. 默认Original位号与Now位号一致，当不一致时在Original输入框输入其位号
5. 勾选Include more information选项会同时输出ORIGINAL_NET原来的引脚分配情况（H-K列）及部分提
示检查内容(L列）
6. 点击Start按钮程序运行，生成报告文件在BRD同级目录并打开它供查看确认，报告文件名为“器件位号-comp_pin_net_compare.csv”
7. 如果需要多个器件比对，重复3-6步骤生成多个csv文件即可

![](https://tiny-yhw.github.io//images/TY-skill/report-component-pin-nets-compare2.png)