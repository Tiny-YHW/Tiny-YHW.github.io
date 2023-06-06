---
title: '解决ORCAD部分元器件与原理图不交互方法其一'
date: Mon, 01 Mar 2021 06:27:22 +0000
draft: false
tags: ['Allegro', '设计软件']
---

 有时候会遇到一些设计，总有那么几个元器件没办法让原理图与PCB之间交互选择，像下图一样（动图看不清，右击图片选择在新标签页中打开图片方可看清、或者将图另存到本地查看）

![](http://a1024.synology.me:222/images/blog2022/%E4%B8%8D%E4%BA%A4%E4%BA%92%E7%97%87%E7%8A%B6.gif)

       这种情况首先排除了网表关联问题、软件设置问题。而后经过各种控制变量法，最终将问题锁定到原理Symbol上，最后果不其然，假装编辑一下原理Symbol，然后全部更新此原理Symbol，问题得以解决。

![](http://a1024.synology.me:222/images/blog2022/lingcun%E4%B8%8D%E4%BA%A4%E4%BA%92%E7%97%87%E7%8A%B6.gif)

       但出现此问题的根本原因我尚未找到，只找到了这种临时性解决方案  
        当然此方案及适用于此种情况，如果你也遇到这种情况通过此方不能解决，可留下你的案例，再寻找其它可能的问题。

原理图与PCB交互必备因素

*   网表一致：即PCB为对应原理图的网表
*   交互使能开启：原理图中菜单选项Option>Preferences选择Miscellaneous标签，右侧中部偏下Intertool Communication的Enable Intertool Communication处于勾选状态