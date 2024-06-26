---
layout: post
title: Allegro 软件崩溃sav文件
categories: Allegro
permalink: allegro-sav
date: 2024-01-18
---

日常非预期软件运行时可能崩溃，崩溃时文件不能保存将可能导致一定程度的工作量丢失

* 崩溃时大概率会随附产生一个sav文件，这个文件相当于紧急备份，文件的保存时间为崩溃的时间点
* 如果崩溃时没有产生sav文件，那只能自认倒霉，如果丢失的这部分工作量对你很重要，可以保持PCB文件夹所有文件都不要动尝试联系我还可能有一丝拯救的措施，白嫖党请此刻勿扰

即便生成了sav文件，但此时这个sav文件是紧急备份的可能会存在一些数据库问题，建议按以下推荐方案执行

* 如果brd上次保存的时间很近，直接使用返工不大时，此时建议使用上次保存的brd文件
* 如果上次保存的时间太久（直接用会返工较大），就直接将sav后缀改为brd使用，使用sav文件请一定运行一次DB check对数据库进行问题修复
* 如果sav直接使用而不修复，很可能会频繁崩溃