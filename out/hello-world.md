---
title: 'WordPress全局字体修改'
date: Thu, 02 Apr 2020 01:25:37 +0000
draft: false
tags: ['Wordpress']
---

参考：[https://www.ratodo.com/article/wordpress-fonts-change.html](https://www.ratodo.com/article/wordpress-fonts-change.html)

前言
--

有很多时候，Wordpress 的字体不能让我们满意，这个时候我们就可以通过一些方法来修改主题的默认字体，来达到我们想要的效果。

下面介绍的更换字体主要分为两种，第一种是直接调用系统的字体，来替换原来主题的默认字体；第二种则是使用自己的字体文件，来实现字体的替换。

第一种：直接调用
--------

这种方法通过修改 CSS 文件就可以实现，有些主题自带了自定义 CSS 样式的设置，Wordpress 也提供了这一入口（后台管理 -> 外观 -> 自定义 CSS），这时候我们就可以直接在里面填上：

```
`*:not([class*="icon"]):not(i) {
font-family: Segoe UI, "Microsoft Yahei" **!important**;
}`Copy
```

上面的例子就是将字体全局优先替换成 **Segio UI**，其次替换成**微软雅黑**，下面列举几个比较适合阅读的字体，供大家替换，替换代码中的 **Segio UI** 和 **Microsoft YaHei** 即可。

**宋体（SimSun），微软雅黑（”Microsoft Yahei”），华文黑体（STHeiti）**，**冬青黑体（ Hiragino Sans GB ），苹方（PingFang SC）**，**Arial，Times New Roman，Droid Sans**

标题1
===

标题2
---

### 标题3

#### 标题4

##### 标题5

段落

1.  列表
2.  列表
    *   列表
    *   列表

```
sdf1564156
ryrtyrty
3423424
```