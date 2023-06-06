---
title: 'Altium PCB Rules And Violations 查看规则和冲突演示'
date: Wed, 18 May 2022 15:19:01 +0000
draft: false
tags: ['Altium']
---

视频演示从[抖音](https://v.douyin.com/Fx6CP55/)或[公众号](https://mp.weixin.qq.com/s?__biz=MzI2NDQxMjg4NA==&mid=2247484379&idx=1&sn=2efd84d2d1c972ff89f556386fac6432&chksm=eaac4860dddbc176d49a9d4d60bf0d9825114bb75c24beced6471260b54eef5536738bbaf386&token=1966602140&lang=zh_CN#rd)查看

![](https://a1024.synology.me:222/images/blog2022/fdd5fc0197764558b5bc212dd5b256ad_tplv-pk90l89vgd-crop-center_0_0.jpeg)

当完成PCB设计后，进行DRC检查是必要的

DRC检查是介于设计与生产之间的一项重要保障

特别是开路、短路、合适的线宽、线间距等

所以一定要运行DRC检查

可以从状态面板中打开规则和冲突面板

规则面板中罗列了规则管理器设置的所有项目

你可以一次性进行所有项目的规则检查

或者选中某个指定的项目进行检查

我们选择宽度约束，对其进行单项检查

如果存在不符合项，则对应的项目将被罗列出来

这里我们创建了一个错误

接下来演示如何查看这个错误详情

将鼠标悬停在有冲突标识的对象上

点击鼠标右键选择Violations

可以从此面板中查看错误详情

如果这个错误是可以接受的，可以选择Wave

则这个错误将不再被突出显示

这里还是建议大家正确的配置规则，匹配所需内容

同样我们可以从规则和冲突面板中查看这项错误

将错误对象进行修正则可以消除此项错误