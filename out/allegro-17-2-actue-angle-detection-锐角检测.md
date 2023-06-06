---
title: 'Allegro 17.2 actue angle detection 锐角检测'
date: Fri, 11 Nov 2022 07:07:54 +0000
draft: false
tags: ['Allegro']
---

演示视频

**设计规则DRC也引入了基于四个角度的检查。锐角检查通过newSetup-> Constraints -> Modes command运行，然后选择Design Modes (Acute AngleDetection)进入到AnalysisModes。DRC模式可设置为On-line、Off或Batch模式，角度可在<0: 90>度范围内进行设置。**  
**![](https://community.cadence.com/resized-image/__size/748x304/__key/communityserver-blogs-components-weblogfiles/00-00-00-01-14/4370.2.png)**

在Acute Angle DRC视图，DRC标记包括字符“AA”，则为报错。Acute Angle DRC Checks表现为：

**最小shape边缘到边缘**

铜层轮廓为锐角且角度过小

![](https://community.cadence.com/resized-image/__size/739x442/__key/communityserver-blogs-components-weblogfiles/00-00-00-01-14/6445.3.png)

**最小线到焊盘**

焊盘入口与线段产生锐角

![](https://community.cadence.com/resized-image/__size/748x497/__key/communityserver-blogs-components-weblogfiles/00-00-00-01-14/0160.4.png)

**最小线到角度**

铜层与线段交叉产生锐角

![](https://community.cadence.com/resized-image/__size/947x452/__key/communityserver-blogs-components-weblogfiles/00-00-00-01-14/6507.5.png)

**最小线对角度**

线段交叉产生锐角

![](https://community.cadence.com/resized-image/__size/792x529/__key/communityserver-blogs-components-weblogfiles/00-00-00-01-14/8865.6.png)

直角检测：Real-Time Route Analysis  
菜单栏“View->Vision Manager”  
点击“**Conigure…**“按钮可以对需要进行实时检测的项目进行选择  
**90 Degree Corners** 避免90°走线