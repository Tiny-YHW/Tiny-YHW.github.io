---
title: '网页表格提取 Table Capture'
date: Fri, 08 May 2020 05:27:23 +0000
draft: false
tags: ['未分类']
---

需求：网页中有表格形式的文本，需要提取，直接复制难以成功或没有表格格式  
案例网址1：[https://www.micron.com/products/dram/ddr4-sdram/part-catalog](https://www.micron.com/products/dram/ddr4-sdram/part-catalog)  
案例网址2：[https://www.intel.com/content/www/us/en/programmable/support/literature/lit-index/lit-pkg/package.html?family=Cyclone\_10](https://www.intel.com/content/www/us/en/programmable/support/literature/lit-index/lit-pkg/package.html?family=Cyclone_10)

需要工具：[谷歌浏览器](https://a1024.synology.me:1024/read.php?tid=338&fid=21)、Excel、[Tab Capture谷歌插件](https://www.lanzous.com/i50wx5a)

谷歌插件安装

*   下载[Tab Capture谷歌插件](https://www.lanzous.com/i50wx5a)，解压缩
*   打开谷歌浏览器，复制文本 chrome://extensions/ 到地址栏打开
*   右上角打开开发者模式
*   左上角加载已解压的扩展程序，选择1、解压的文件夹，选择文件夹

![](http://a1024.synology.me:222/images/blog2022/Snipaste_2019-07-17_11-32-15.png)

安装完谷歌插件在网页右击会显示如下图有Tab Capture选项，如果你的没有可能是点击的位置不对（指向空白而非链接出），或者插件没装好。选择箭头处菜单进入表格管理，已案例网址1为例

![](http://a1024.synology.me:222/images/blog2022/%E6%8A%80%E6%9C%AF%E8%AE%A8%E8%AE%BA%E5%8C%BA/Tab%20Capture%E6%8F%92%E4%BB%B61Snipaste_2019-07-15_10-07-53.png)

从左侧调整父级元素或子级元素（一般情况直接可用如案例2，案例1需要单击三次父级元素），只至预览区域的内容符合预期（网页上会有红框，框选内容为目标区域，预览区域显示似乎不太友好，凑合用，）

![](http://a1024.synology.me:222/images/blog2022/%E6%8A%80%E6%9C%AF%E8%B0%88%E8%AE%BA%E5%8C%BA/Tab%20Capture%E6%8F%92%E4%BB%B62Snipaste_2019-07-15_10-16-42.png)

确认好目标区域，选择下方复制，然后打开你的Excel粘贴就可以了，右边是谷歌的Excel使用需科学上网，请自行测试。

![](http://a1024.synology.me:222/images/blog2022/%E6%8A%80%E6%9C%AF%E8%B0%88%E8%AE%BA%E5%8E%BB/Tab%20Capture%E6%8F%92%E4%BB%B6table%20capture.gif)