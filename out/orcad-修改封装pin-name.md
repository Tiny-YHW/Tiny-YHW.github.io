---
title: 'Orcad 修复Pin Name重复问题'
date: Wed, 29 Jul 2020 07:52:28 +0000
draft: false
tags: ['Allegro', '设计技巧']
---

Duplicate Pin Name "VDD" found on Package

问题描述
----

*   1、Orcad创建网表时报错，错误，描述为Pin Name重复（在Orcad中是不允许非Power的pin type的Pin Name相同的）

![](http://a1024.synology.me:222/images/blog2022/OrcadPinName1.png)

#26 ERROR(ORCAP-36041): Duplicate Pin Name "VDD" found on Package

![](http://a1024.synology.me:222/images/blog2022/OrcadPinName2.png)

![](http://a1024.synology.me:222/images/blog2022/OrcadPinName3.png)

处理方式
----

### 修改Pin Name使其不重复

*   1、选中所有引脚复制

![](http://a1024.synology.me:222/images/blog2022/OrcadPinName4.png)

*   2、粘贴到Excel，查找到Pin Name的重复值，在Capture这个表格里使用选择对应数据使用键盘按键Ctrl+Insert为复制（Ctrl+C不好使的）
*   选择: 数据->高亮重复项，选中Pin Name这一列，重名的对象将被高亮

![](http://a1024.synology.me:222/images/blog2022/OrcadPinName5.png)

*   4、选中新的一列第一个单元格，输入1，鼠标移至右下脚显示+号（向下填充）时双击，定义序号，用于保留当前引脚顺序，因为后面需要重拍顺序，这样之后用此序号排序，可以恢复当前顺序。

![](http://a1024.synology.me:222/images/blog2022/OrcadPinName6.png)

*   5、选择D列按字母，扩展重排序

![](http://a1024.synology.me:222/images/blog2022/OrcadPinName7.png)

*   6、新的一列第一行输入公式
*   ＝IF(COUNTIF($D$1:D2,D1)<=1,D1,D1&COUNTIF($D$1:D1,D1))
*   COUNTIF($D$1:D2,D1)代表此行及之前对应的Pin Name出现次数，用作同名的Pin Name编号
*   最终效果如下图

![](http://a1024.synology.me:222/images/blog2022/OrcadPinName8.png)

*   7、按之前指定的序号重新排序，复制回Orcad，在Capture这个表格里使用选择对应数据使用键盘按键Shift+Insert为粘贴（Ctrl+V不好使的）

![](http://a1024.synology.me:222/images/blog2022/OrcadPinName9.png)

### 将Pin Type修改为Power

如上图E列，将发现重复的Pin Name高亮后进行筛选，修正Pin Type为Power即可，建议仅真Power使用此方式，防止Orcad软件在做逻辑检查时报不必要的警告