---
layout: post
title: TY-Skill Report->Placebound Area Percentage 评估器件布局密度
categories: TY-Skill
date: 2024-11-15
permalink: ty-skill-report-placebound-area-percentage
excerpt: 
---

## 功能说明

布局时大概评估布局密度，评估板子疏密程度

## 操作说明

从菜单或命令启动此程序直接输出报告

## 程序说明

1. 程序的基本逻辑为计算板中所有PLACE_BOUND图形的面积除以2倍Route Keepin-ALL面积的百分比,所以使用此程序需要板中存在Route Keepin-ALL层图形
2. 为了评估结果更加准备,存在以下几种情况的事可以先进行一些调整再输出报告
  - BGA器件其对面侧有效布局面积受限,可增加（或复制）绘制一个大致的PLACE_BOUND图形
  - 板中有布局禁布区域时,在禁布区域绘制PLACE_BOUND图形
  - 板中安装子板或对应器件下方能布一些器件时适当减小或删除子板或对应器件的PLACE_BOUND图形
3. 密度值大概评估如下
  - 0.4 以下 很宽松
  - 0.4 比较宽松
  - 0.5 面积够用，中规中矩的设计
  - 0.6 比较密，需充分利用板空间才能做好布局
  - 0.6以上 很密，必须充分里面板空间才能做好布局，适当考虑使用盘中孔或埋盲孔工艺以更充分利用板面积
  - 1以上 放不下必须调整板框或电路