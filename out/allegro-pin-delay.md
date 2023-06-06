---
title: 'Allegro Pin Delay'
date: Mon, 20 Apr 2020 01:22:37 +0000
draft: false
tags: ['Allegro', '设计技巧']
---

Pin Delay：IC器件包装内部长度转换值  
在高速设计中，常常需要将器件的Pin Delay信息导入PCB设计，包含Pin Delay信息的长度更能真实反应信号传输时间，一般IC器件Pin Delay数据由供应方提供或官网下载（元器件手册），一般为EXCEL格式如下

![](http://a1024.synology.me:222/images/blog2022/Allegro%20Pin%20Delay1.jpg)

常用时间单位换算
--------

*   1ps (皮秒) =0.0000000000001s=10^-12s（秒）
*   1ns (纳秒) =0.0000000001s=10^-9s (秒)
*   1ns=1000ps

时间与长度单位换算
---------

电信号在PCB上的传播速度为Vp=Vc/sqrt（Er）  
Vc为光速m/s  sqrt是开根号的意思  Er为介电常数

以下数据为方便计算取约数描述，如果你需要更精确的转换可使用更精确的值计算

我们以常规FR4材料为例Er=4左右  可得出Vp=150000000 m/s  
若取Er=4 则Vp=1.5\*10^8  
1m=39.37\*10^3mil    1S=10^12ps  
单位换算得出电信号在FR4中传输速度约为6mil/ps

得出Pin Delay
-----------

这里有效信息如上图Pin Number、Min Trace Delay (ps)、Max Trace Delay (ps)，不过此处Delay一般为时间单位ps或ns，我们需要转化为长度单位mil公式如下  
取Trace的平均值 所以我们可以算出Pin Delay的长度为（在右边插入一列输入）

![](http://a1024.synology.me:222/images/blog2022/Allegro%20Pin%20Delay2.jpg)

向下填充得出所有

匹配数据格式
------

Allegro 的数据格式如图[CSV](https://baike.baidu.com/item/CSV/10739?fr=aladdin)格式，常规可以按下图自己做,对应好字符和DEVICE，此处提供一个[模版数据](https://layouto.lanzouf.com/it6N50w837lc)，使用的话将A3、A4、A6及以下数据替换为你的Pindelay数据可以用

![](http://a1024.synology.me:222/images/blog2022/Allegro%20Pin%20Delay3.jpg)

或者按下述方法重新生成一个

*   在规则管理器里随意给上述U14器件的pin-pair加一个Pin Delay数值
*   选择File—Export—Pin Delay命令后选择U14器件（选择的器件应该包含至少一个Pin Delay值，否则无法导出，所以第一步才随意添加了一个值）
*   PCB所在目录将生成一个后缀为csv格式的文件
*   用Excel打开csv文件编辑即可得到上表前五行
*   在此基础上做修改对Pin Delay数据值进行更改更新
*   用第一张图的B列Pin Nunber替换A6及下方数据，用第二个图G列Pin Delay粘贴到B6完成格式匹配保存

导入Pin Delay
-----------

选择 File—import—Pin Delay

![](http://a1024.synology.me:222/images/blog2022/Allegro%20Pin%20Delay4.jpg)

选择路径，Import

从规则管理器抽样核对导入的Pin Delay值是否添加成功，值是否正确

20160818更新
----------

上面介绍的是在excel加入ref name及package name导入的方法，还可以不加这两项，在导入时通过选择器件的方式导入，自己可以试试

引申阅读：我们常见的是上述导入方式，导入后单位为mil，下面再介绍一种方式，可以直接导入时间单位，软件自己实现单位转换  
导入时间以时间为单位的文件，然后  
打开规则管理器，选择Analyze——Analysis Modes 勾选Pin Delay一栏

![](http://a1024.synology.me:222/images/blog2022/Allegro%20Pin%20Delay5.jpg)

关键是下面Propagation Velocity Factor的值 这个地方代表电信号在介质中的传输速度，如上图值代表1.542\*10的8次方m/s, 此时虽然规则管理器中显示的值为ps，但已经做了相应单位转换  
举个例子：如果上述值我设置为1.5e+08m/s 那在pin delay出填6mil和填1ps是一样的结果  
视频演示：https://v.qq.com/x/page/l3149honh0q.html