---
title: 'Altium Designer巧用元素转换铺设异型铜皮'
date: Thu, 17 Sep 2020 08:41:19 +0000
draft: false
tags: ['Altium']
---

要求：如下图，要求在如下图形圆环内区域铺设与图形一致的铜皮及开窗，空网络

![](http://a1024.synology.me:222/images/blog2022/Altium%20Designer%E5%B7%A7%E7%94%A8%E5%85%83%E7%B4%A0%E8%BD%AC%E6%8D%A2%E9%93%BA%E8%AE%BE%E5%BC%82%E5%9E%8B%E9%93%9C%E7%9A%AE1.jpg)

首先说明一点这种圆环型图形（由两条没有连接的线组成的图形）需要分割，成首尾分离的图形（变为分别由一条线连接成的图形）说出来有点绕自己理解吧  
建议先将图形做到辅助机械层，做好图形再复制到相应层  
对图形做如下处理增加两条线（建议选择两条直边，分别选取两端连接）

![](http://a1024.synology.me:222/images/blog2022/Altium%20Designer%E5%B7%A7%E7%94%A8%E5%85%83%E7%B4%A0%E8%BD%AC%E6%8D%A2%E9%93%BA%E8%AE%BE%E5%BC%82%E5%9E%8B%E9%93%9C%E7%9A%AE2.jpg)

全选图形减选相应的两条线，剩余部分组成一个单线闭合图形（去掉刚选择的两条直边）

![](http://a1024.synology.me:222/images/blog2022/Altium%20Designer%E5%B7%A7%E7%94%A8%E5%85%83%E7%B4%A0%E8%BD%AC%E6%8D%A2%E9%93%BA%E8%AE%BE%E5%BC%82%E5%9E%8B%E9%93%9C%E7%9A%AE3.jpg)

选择菜单tool—convert—create polygon/region from Selected Primitives(快捷键tvr/tvg),

![](http://a1024.synology.me:222/images/blog2022/Altium%20Designer%E5%B7%A7%E7%94%A8%E5%85%83%E7%B4%A0%E8%BD%AC%E6%8D%A2%E9%93%BA%E8%AE%BE%E5%BC%82%E5%9E%8B%E9%93%9C%E7%9A%AE4.jpg)

tip：选择从选择的元素创建polygon，polygon默认属性Fill Mode属性为None所以看不到图形，双击修改即可

![](http://a1024.synology.me:222/images/blog2022/Altium%20Designer%E5%B7%A7%E7%94%A8%E5%85%83%E7%B4%A0%E8%BD%AC%E6%8D%A2%E9%93%BA%E8%AE%BE%E5%BC%82%E5%9E%8B%E9%93%9C%E7%9A%AE5.jpg)

图形创建完毕，选择剩余部分先用相同方式转变图形  
图形做好 复制到对应层  
Tip：Alt+Insert 可直接粘贴对象到当前活动层（空网络）