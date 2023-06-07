---
layout: post
title: Cadence Allegro What’s New in 22.1 QIR1&2
categories: Allegro
date: 2023-06-06
---
![Cadence-Alegro-2022.png](https://a1024.synology.me:222/images/blog2023/Cadence-Alegro-2022.png)

# QIR 1 (HotFix 001)（12-16-2022）

## Allegro 3DX增强功能

引入了新的3DX引擎，该引擎与Allegro设计数据库集成，通过解决相关的规模和复杂性问题，提供了更快、更有效的大型设计处理。

该QIR为DRC环境提供了全面的增强，并简化了查看和浏览DRC的方式。该版本还为刚挠结合设计提供了额外的支持。

### 器件间隙DRC

器件到器件的间隙的DRC可用于3D model以及Place Bound 和 DFA Bound。DRC支持为单个器件和各类器件（mechanical, connector, discrete, QFN, SOP, and BGA.）设定不同的水平和垂直间隙值。

DRC标记在三维视图中可见，将光标悬停在标记上可以高亮显示DRC对象及提示信息。

3DX Canvas的搜索窗格中可以浏览DRC。

### 3DX刚挠结合

以交互方式查看和测量刚挠设计的弯曲。您可以随时进行目视器件间距检查，也可以在折弯状态下运行DRCs检查

## GPU加速渲染增强

GPU支持在平移和缩放以及打开或关闭图层时提供更快的响应时间，并提高图形渲染质量。

默认情况下，GPU支持是启用的，并且在Windows和Linux平台上可用。

为了获得最佳性能，可考虑使用RTX A6000级别的GPU。

# QIR 2 (HotFix 003)
