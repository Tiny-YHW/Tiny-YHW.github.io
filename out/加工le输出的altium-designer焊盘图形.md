---
title: '加工LE输出的Altium Designer焊盘图形'
date: Sat, 13 Jun 2020 02:41:43 +0000
draft: false
tags: ['元器件管理']
---

**内容**
------

     针对Library Expert输出的Altium Designer焊盘图形，封装类型为BGA类和SOP(SOP、SON、QFP、QFN)类的封装的加工。

**流程**
------

1.  安装脚本程序，[传送门](https://a1024.synology.me:1024/altium%e5%ae%89%e8%a3%85%e5%92%8c%e5%90%af%e5%8a%a8%e8%87%aa%e5%ae%9a%e4%b9%89%e8%84%9a%e6%9c%ac%ef%bc%88scripting%ef%bc%89/)，脚本程序自行索取
2.  打开焊盘图形，判断是否需要加工，见加工要求
3.  如需加工，启动脚本程序

![](http://a1024.synology.me:222/images/blog2022/%E5%8A%A0%E5%B7%A5LE%E8%BE%93%E5%87%BA%E7%9A%84Altium%20Designer%E7%84%8A%E7%9B%98%E5%9B%BE%E5%BD%A21.png)

**加工要求**
--------

1.  BGA类和SOP类单边引脚数边大于等于6脚需要添加引脚标识
2.  添加的引脚标识应放置在元器件安装后靠近元器件对应引脚位置
3.  引脚标识应清晰易读

### **SOP类**

1.  选中需要添加标识一排引脚
2.  在脚本程序中选择添加标识的Position（上、下、左、右）
3.  点击Add Mask按钮

![](http://a1024.synology.me:222/images/blog2022/%E5%8A%A0%E5%B7%A5LE%E8%BE%93%E5%87%BA%E7%9A%84Altium%20Designer%E7%84%8A%E7%9B%98%E5%9B%BE%E5%BD%A22.gif "点击查看原图")

### **BGA类**

1.  选中需要添加标识一排引脚
2.  在脚本程序中选择添加标识的Position（上、下、左、右）
3.  在脚本程序中选择添加标识按焊盘的Alphabet/Number
4.  点击Add Text按钮
5.  调整Text的位置

![](http://a1024.synology.me:222/images/blog2022/%E5%8A%A0%E5%B7%A5LE%E8%BE%93%E5%87%BA%E7%9A%84Altium%20Designer%E7%84%8A%E7%9B%98%E5%9B%BE%E5%BD%A23.gif "点击查看原图")

### **注意项&使用技巧**

1.  Library Expert输出的焊盘图形A1脚均有0.5mm实心圆点，加工前应将其删除，因为与引脚标识（数字和字母）功能重复。
2.  文本位置和选项一般情况均为左&数字、上&字母
3.  如果文本选项选择Line（直线）时引脚标识交错覆盖，可尝试选择Stagger（交错）使文本错开清晰易读

批量处理
----

如果需批量按次序打开pcblib

### **思路**

使用批处理的“cd”“call”函数，依次打开所有pcblib文件。

### **流程**

1.  新建一个批处理文件，获取所有pcblib文件位置。bat内容dir \*.PcbLib /B/S >>prjscr.txtcd" C:\\Users\\Administrator\\Desktop\\AltiumDesigner"$@#call"BGA6CP40\_2X3\_95X134X60B26N.PcbLib"
2.  将获取到的所有路径复制到Excel表格中，并进行分列，组合，添加call、cd函数。cd"C:\\Users\\Administrator\\Desktop\\AltiumDesigner"$@#call"BGA6CP40\_2X3\_95X134X60B26N.PcbLib"
3.  新建一个批处理文件，将Excel中内容复制进去，使用UltraEdit-32打开，将所有$@#替换为空格。（使用word进行此操作也可）
4.  运行批处理文件，即可依次打开pcblib文件。