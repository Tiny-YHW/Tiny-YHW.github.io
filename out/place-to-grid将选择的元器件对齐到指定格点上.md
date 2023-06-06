---
title: 'Place->TO Grid将选择的元器件对齐到指定格点上'
date: Wed, 11 Jan 2023 07:37:01 +0000
draft: false
tags: ['TY-Skill']
---

功能说明
----

高亮元器件原点没在格点上的元器件，并可以通过选项将元器件批量移动到指定格点处。

Allegro16.6的某个补丁版本Toolbox已引入此功能可替换本Skill程序，启动命令为tbx push2grid

![](https://a1024.synology.me:222/images/blog2023/dalgrid.png)

操作说明
----

1.  使用菜单或者命令启动后从Option面板配置功能选项。
2.  程序有设置网格功能与前述Change Grid重复此处功能舍弃。
3.  设置All grid或Place grid为指定的格点值，按需求勾选下方选项
    1.  Include mechanical symbols：包含机械器件
    2.  Highlighted only：仅对已高亮的器件起作用
    3.  Ignore fixed property：忽略锁定属性
4.  框选需要对齐到格点的元器件
5.  弹出对话框报告未对齐到格点的器件数量，是否对齐到格点，
    *   选择是程序将将器件对齐到格点
    *   选择否则仅高亮未对齐到格点的元器件。