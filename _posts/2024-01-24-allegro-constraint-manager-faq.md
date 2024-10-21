---
layout: post
title: Allegro Constraint Manager 规则管理器常见报错
categories: Allegro
permalink: allegro-constraint-manager-faq
date: 2024-01-24
---

## 设定规则值超限

修改规则值时值不能修改成功并弹出"XXX not be larger(smaller) than XXX"，这种错误一般是由于设定值逻辑错误产生

* 设定的最小值大于最大值
* 设定的最大值小于最小值
* 设定的优选值不介于最小值和最大值之间

出现此类错误需要按正确的逻辑配置值正确即可，可参考下述案例理解

* eg1:Min Line Spacing may not be larger than Primary or Neck Gapess (-) Tolerance.
* ![/](https://tiny-y.asia/images/blog/2024/allegro-constraint-manager-faq1.png)

* eg2:Max value should not be smaller than the Min value.
* ![/](https://tiny-y.asia/images/blog/2024/allegro-constraint-manager-faq2.png)