---
title: 'Allegro Shape Operations'
date: Wed, 19 Oct 2022 08:05:40 +0000
draft: false
tags: ['Allegro']
---

Allegro 17.2开始支持对多个Shape进行布尔运算，使编辑Shape更加灵活

从菜单Shape->Shape Operations选择对应的命令后点击铜皮即可

以下所有操作均以选择的第一个Shape作为主元素

*   OR：依次合并选择的多个Shape
*   AND：取选择Shape的重叠部分
*   ANDNOT：从主元素上去掉Shape的重叠部分
*   XOR：合并，并去掉Shape的重叠部分

![](https://a1024.synology.me:222/images/blog2022/%E5%9B%BE%E7%89%871.png)