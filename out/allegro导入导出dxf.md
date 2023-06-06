---
title: 'Allegro导入导出DXF'
date: Mon, 04 Jan 2021 06:46:00 +0000
draft: false
tags: ['Allegro', '设计技巧']
---

DXF文件通常使用基于机械工具创建。机械工程师将定义PCB板的轮廓，固定孔的位置，高度限制区域，连接器的位置等。所有这些信息都可以使用DXF文件导入到PCB编辑器中。电路板完成后，您还可以导出DXF格式的数据以与机械工具一起使用。

导入
--

待补充

File -> Import -> DXF

导出
--

建议先设置好需要输出的层做好视图，Display –color关闭所有层，然后打开需要输出的层

菜单：File – Export – DXF 或command输入dxf out

详细设置见下图，设计好后选择输出即可

![](http://a1024.synology.me:222/images/blog2022/dxfout1.jpg)

编辑层转换关系

![](http://a1024.synology.me:222/images/blog2022/dxfout2.jpg)

DXF定义层有责输出空白则不输出