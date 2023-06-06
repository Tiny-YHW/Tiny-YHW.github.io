---
title: 'Library Expert软件使用F&Q'
date: Mon, 01 Jun 2020 03:23:23 +0000
draft: false
tags: ['软件应用']
---

软件相关
----

### Library Expert有免费版本吗？

有，LibraryExpert PRO版本可从[官网](http://www.pcblibraries.com/)下载，有基础的建封装和输出各软件的Footprint功能，需要联网环境

由于软件公司在美国，且国内的GFW有存在因连接不稳定造成软件突然停止的情况，推荐科学上网后使用。

### Library Expert 各版本有什么差别

[https://www.pcblibraries.com/Products/Compare/](https://www.pcblibraries.com/Products/Compare/)

具体Pro版本和ENTERPRISE版本的核心差异如下

*   Pro版本界面UI存在无法关闭的广告，ENTERPRISE没有广告
*   Pro需要连接外网，ENTERPRISE无需外网亦可在局域网或单机使用
*   Pro版本不支持封装管理，封装需要即时创建即时输出使用，不能保存源文件供再次修改使用，ENTERPRISE可进行封装管理，随意的对已保存的封装进行编辑修改输出保存等

![](http://a1024.synology.me:222/images/blog2022/fengzhuangguanli.png)

*   Pro版本不支持自定义默认参数，默认生成的Footprint规则默认值是一致的，如丝印线宽，焊盘的预放规则，一脚标识等；ENTERPRISE版本可以通过用户选项自定义多项规则参数，使最终生成的Footprint符合你的预期。

![](http://a1024.synology.me:222/images/blog2022/yonghushezhi.gif)

### 为什么我安装的Pro版本只有一种输出格式

Pro版本的输出格式需要再Help->Installed Option设置的，如下图，这个在安装后第一次打开软件是有提示的。

![](http://a1024.synology.me:222/images/blog2022/shuchu.png)

### ENTERPRISE版本的价格是多少

价格按你需要的输出接口付费，不同的输出接口价格不同，单个输出结构的价格大概在1W或2W左右，比如Allegro需要2W，Pads是1W，3D+Xpedition是3W+，Altium是1W，详细报价详询官方。

### 该软件有破解版吗

目前网上没有公开的破解版本，如果愿意结果付费破解，可私下联系我

20210906更新 个人不要问了（没有个人愿意为这种软件付费） 公司可以继续咨询 软件使用问题接受答疑

设计相关
----

### 机械引脚

[机械引脚或无引脚号的焊盘应如何放置](https://a1024.synology.me:1024/mechanical-pin-%e6%9c%ba%e6%a2%b0%e5%bc%95%e8%84%9a%e7%9a%84%e5%ae%9a%e4%b9%89/)

### 圆角矩形和槽形

圆角矩形不等于槽形，所有圆角矩形均使用矩形忽略圆角，因为Allegro16.x软件标准的焊盘形状不支持圆角矩形  
圆角矩形：矩形四角分别为90度圆弧  
槽形：极性左右两边为180度圆弧

![](http://a1024.synology.me:222/images/blog2022/%E5%9C%86%E8%A7%92%E7%9F%A9%E5%BD%A2.png)

[加工le输出的altium-designer焊盘图形](https://a1024.synology.me:1024/%e5%8a%a0%e5%b7%a5le%e8%be%93%e5%87%ba%e7%9a%84altium-designer%e7%84%8a%e7%9b%98%e5%9b%be%e5%bd%a2/)