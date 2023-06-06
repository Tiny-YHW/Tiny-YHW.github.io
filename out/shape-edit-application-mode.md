---
title: 'Allegro Shape Edit Application Mode'
date: Fri, 21 Apr 2023 01:11:24 +0000
draft: false
tags: ['Allegro']
---

Allegro 17.2版本 新增一种Shape Edit Application模式，主要用于提高编辑shape的效率

![172-algPN-455.gif](https://a1024.synology.me:222/images/172-algPN-455.gif)

鼠标悬停在Shape segment (edge)右键，可选对Shape进行的操作项目

![172-algPN-457.gif](https://a1024.synology.me:222/images/172-algPN-457.gif)

若鼠标悬停区域有多个元素，可使用Tab键进行循环切换

![172-algPN-458.gif](https://a1024.synology.me:222/images/172-algPN-458.gif)

在此模式下Option菜单可以定义对于对应鼠标动作将对Shape进行调整方式，下图是默认的调整方式，可以根据个人习惯进行更改，以下内容按默认方式进行介绍

![172-algPN-459.gif](https://a1024.synology.me:222/images/172-algPN-459.gif)

点击Shape同一边上的两个点，Shape上将出现两个描点，可以向内侧或外侧移动形成内凹或外凸

![172-algPN-460.gif](https://a1024.synology.me:222/images/172-algPN-460.gif)

鼠标悬停到Shape的一条边上，按住鼠标拖动，则选中的Shape边将随鼠标移动

![172-algPN-461.gif](https://a1024.synology.me:222/images/172-algPN-461.gif)

鼠标悬停到Shape的一条角上，按住鼠标拖动，则角对应的两个Shape边将随鼠标移动

![172-algPN-462.gif](https://a1024.synology.me:222/images/172-algPN-462.gif)

鼠标悬停到Shape的一条角上，单击，即将对应的叫导斜角或圆角，斜角的值在Option中Coners中进行调整

![172-algPN-463.gif](https://a1024.synology.me:222/images/172-algPN-463.gif)

若要一次导多个角，请将鼠标悬停在Shape边沿上，然后单击鼠标右键以访问“Trim corners”命令。

![172-algPN-464.gif](https://a1024.synology.me:222/images/172-algPN-464.gif)

若要将斜角转换回正交角，请将“Click”设置更改为“Remove/Extend”，然后选择倒角段。

![172-algPN-465.gif](https://a1024.synology.me:222/images/172-algPN-465.gif)

或者，可以将鼠标悬停在斜边上，然后使用右键单击菜单访问“Remove/Extend Segment（s）”命令。

![172-algPN-466.gif](https://a1024.synology.me:222/images/172-algPN-466.gif)

若要圆角，请将“Corners”设置更改为“Round”，然后选择顶点位置。

![172-algPN-467.gif](https://a1024.synology.me:222/images/172-algPN-467.gif)

选中Extend Selection复选框，则在拖动Shape边时其关联的两个边（即三条边）一起移动（不够选是按住Shift按键可以实现同样的效果）slide命令也有同样的使用方式

![172-algPN-469.gif](https://a1024.synology.me:222/images/172-algPN-469.gif)

选中Auto-Join复选框，则在拖动Shape边时设计多个边重合时，边会合并为一条边

![172-algPN-470.gif](https://a1024.synology.me:222/images/172-algPN-470.gif)

若要移动并保持形状多边侧的完整性，请按 Ctrl 键，然后选择三个垂直线段。将鼠标悬停在任何一个突出显示的区段上，然后使用“Move Segments”命令。

![172-algPN-471.gif](https://a1024.synology.me:222/images/172-algPN-471.gif)