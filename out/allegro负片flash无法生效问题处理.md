---
title: 'Allegro负片Flash无法生效问题处理'
date: Sun, 28 Jun 2020 03:22:49 +0000
draft: false
tags: ['Allegro']
---

问题症状
----

**Allegro通孔焊盘无法（不能）添加Flash**，选择Flash后仍然会变成矩形全连接

![](http://a1024.synology.me:222/images/blog2022/flashfail.png)

![](http://a1024.synology.me:222/images/blog2022/%E7%97%87%E7%8A%B61.gif)

尝试过各种解决方案均为解决

*   热风焊盘的显示都开了
*   16.6 17.2 17.4版本都试了无解
*   加上flash后再更新显示更新成功的，但实际没成功，会变方形全连接，再次打开这个pad发现flash并没有被加上
*   导出此期间在dra加flash生产psm成功，再放入更新到PCB仍然无解
*   另做焊盘，更新焊盘
*   等

最终在EDA365 [dzkcool](https://www.eda365.com/space-uid-88685.html) 和 网友上海-Kim的指引下得出两种解决方案，使用flash\_convert命令或通过导入setting

![](http://a1024.synology.me:222/images/blog2022/Snipaste_2020-06-28_11-12-49.png)

问题的根本猜测是14.0及以下数据库和15.0及以上数据库中对flash的认知不同造成的，官方文档中也明确了此项，具体理解自行查阅帮助文件，关键字flash\_convert

使用flash\_convert命令
------------------

*   在brd中正确的编辑焊盘并更新
*   编写CMD命令文件
*   执行CMD文件，生成新的brd即更新完成
*   详细操作见动图

![](http://a1024.synology.me:222/images/blog2022/cover.gif)

```
flash_convert.exe flash.brd
pause
```

**TIPS：**

*   brd不能放置到中文路径
*   如果遇到报下述错误，是因为对应的Flash文件未在对应路径中查找到，需对所报焊盘依次进行修改为路径中已有的Flash或其它能够识别到的对象后flash\_convert才能运行成功
*   第一条报错中AXY60为Flash的名称 THB0\_9X1\_9D0\_6X1\_6为焊盘名称，需要编辑焊盘THB0\_9X1\_9D0\_6X1\_6来修正AXY60这个Flash

![](http://a1024.synology.me:222/images/blog2022/Snipaste_2020-07-06_09-10-30.png)

通过导入setting
-----------

注意：setting文件包含多种软件相关设置，所以使用此方式这些设置项会被一同导入，可能会产生非预期的setting设置，有条件的优先用上面的方式

*   找一块正常的brd，然后file-export-parameter勾选setting导出设置文件
*   在这块有问题的板子上使用file import parameter，导入setting文件
*   更新所有或对应pad
*   重新编辑需修改的pad

![](http://a1024.synology.me:222/images/blog2022/seting.gif)