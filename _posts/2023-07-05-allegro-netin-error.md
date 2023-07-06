---
layout: post
title: Allegro导入网表报错
categories: PCB设计
date: 2023-07-05
permalink: allegro-netin-error
excerpt: Allegro导入网表报错
---

## Device library (SPMHNI-176)

### ERROR(SPMHNI-189)

ERROR(SPMHNI-189): Problems with the name of device 'OSCILLATOR_CO4-3R2X5R0-S_KC5032A25.0000CMGE00': 'Name is too long.'.

原理图定义的device名称太长，超出限制，Allegro默认Long name size值为31，若原理图中定义的名称超过31个字符则会报此错误

尝试更改原理图缩短指定name字符长度或修改PCB设置中Long name size值，Long name size从Allegro菜单*setup-Design Parameters*第二个标签页Design中左上Size区域中Long name size字段，最大不超过255

