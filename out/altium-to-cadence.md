---
title: 'Altium to Cadence'
date: Sat, 16 May 2020 06:45:15 +0000
draft: false
tags: ['Allegro', 'Altium', '设计技巧', '设计软件']
---

**SCH（DE HDL）**
---------------

[altium2hdl](https://a1024.synology.me:1024/wp-content/uploads/2020/05/altium2hdl.pdf)[下载](https://a1024.synology.me:1024/wp-content/uploads/2020/05/altium2hdl.pdf)

****SCH（Orcad）****
------------------

### ASCII格式转换

使用Altium Designer软件打开需要进行转换的原理图文件

![](https://www.u-c.com.cn/uploads/editor/2019/12/10163748291.png)

选择原理图文件，在保存文件的类型里面选择Advanced Schematic ascii的格式，将原理图另存为ASCII的格式。

Orcad 16.6版本注意此时应保证Altium原理图文件夹内应有后缀为PrjPCBStructure的文件，如果没有使用右键工程后选择Compile the project生成

Orcad 17.2及以上版本无需此文件

![](https://www.u-c.com.cn/uploads/editor/2019/12/10163807329.png)

注意事项。若需要转换的文件里面有中文的名称，或者中文的路径，或者有其他非法字符，为了能够保证转换的正确性，请在转换前将这些问题都修改掉，以便于提高转换的正确性。 

打开OrCAD Capture 选择File-Import-Altium Schematic Translator命令，将会弹出转换设置对话框。

![](https://www.u-c.com.cn/uploads/editor/2019/12/10163935428.png)

选择需要转换工程文件，设置转换输出的路径。注意路径里面不能有中文，不能有非法字符。

![](https://www.u-c.com.cn/uploads/editor/2019/12/10163957301.png)

点击Translate按钮，即可执行转换命令，在命令消息窗口中可以观察文件转换的过程和执行的命令。等到转换完成以后在设置的路径下，可以看到转换后的格式文件。比如，ORCAD\_LIBRARY.OLB是转换后的原理图符号库文件，PCB\_PROJECT.DSN是转换后的原理图文件。

![](https://www.u-c.com.cn/uploads/editor/2019/12/10164019497.png)

8、打开对比文件。打开原理图DSN对比和AD工程文件的差异（Altium工程文件）

![](https://www.u-c.com.cn/uploads/editor/2019/12/10164058207.png)

总结

通过上面的学习让我们看到了Cadence OrCAD Capture 17.2提供的 Altium原理图文件和符号库的完整迁移转换方法。可以利用这个接口方法将Altium的原理图文件迁移转换进入OrCAD Capture 17.2，让工程师以随时输入、修改、管理、复用于自己的原理图设计。该接口方法相对于其他方法来说，操作简单，转换后DSN文件准确和完整都高，可以说这是一种高效率文件转换的方法。对于提升设计效率以及设计的准确性都有很大的帮助，阅读完这篇文章的小伙伴可以自己去试一试这个新功能，为己所用提高工作效率。

[OrCAD\_Migration\_Guide\_Altium](https://a1024.synology.me:1024/wp-content/uploads/2020/05/OrCAD_Migration_Guide_Altium.pdf)[下载](https://a1024.synology.me:1024/wp-content/uploads/2020/05/OrCAD_Migration_Guide_Altium.pdf)

**[如何将AD原理图直接转为Orcad的原理图（17.2新转法）](https://mp.weixin.qq.com/s/UCom7xSZNelZE3z1EZ0egw)**

https://v.qq.com/x/page/e3149brbosu.html

### 直接另存为dsn

打开Altium的原理图，选择工程 选择菜单File/Export/Orcad

****PCB（Allegro）****
--------------------

需要软件 ：Allegro 16.6加补丁版本及以上、Altium任意版本

1.  Altium软件打开Altium PCB另存为PCB ASCII File格式
2.  打开Allegro选择OrCAD PCB Designer ...产品，启动Allegro
3.  选择菜单Import/Translators/Altium PCB
4.  指定1中的PCB ASCII File，点击Translate即可
5.  进行derive connectivity lines
6.  进行Database Check

**Create Individual Symbol Definitions选项**  
当此选项被勾选时  
将转换PCB将为每一个位号的元器件使用Symbol+后缀生成一个独立的Symbol，如0805\_1、0805\_2、0805\_3等  
这样即使设计时在Altium PCB中对元器件焊盘图形的更改仍能成功转换  
若有在Altium PCB中对元器件的焊盘图形更改请勾选此选项  
当此选项不被勾选时  
转换PCB将仅为给定同名的的Altium 焊盘图形创建一个Symbol  
如没有在Altium中编辑Footprint，抓换时请不要勾选此选项，这会使转换更慢，并且生成更多的多余的焊盘图形。

**derive connectivity lines**  
转换完成后，有需要可使用此命令将位于Etch层连接断开的短线和有连接到logical net data的Line变为Cline，  
可以直接键入此命令，或从菜单Tool/derive connectivity打开对话框，勾选Convert Lines to Connect Lines后点击ON执行

**[AD完美转Allegro（新版）并成功解决问题](https://mp.weixin.qq.com/s/BD6ij4OfJubNJLm-VcpAMA)**

[altium2pcb16.6](https://a1024.synology.me:1024/wp-content/uploads/2020/05/altium2pcb16.6.pdf)[下载](https://a1024.synology.me:1024/wp-content/uploads/2020/05/altium2pcb16.6.pdf)

[altium2pcb17.2](https://a1024.synology.me:1024/wp-content/uploads/2020/05/altium2pcb17.2.pdf)[下载](https://a1024.synology.me:1024/wp-content/uploads/2020/05/altium2pcb17.2.pdf)

**测试结果****（****总结****）：****测试版本Allegro16.6S112，带删除线的字非常规用法**  
**焊盘图形转换测试结果，含生成的lib文件和PCB中****Component对象的所有元素**

*   机械一层转换到PG/ASSEMBLY层
*   Keepout层的对象转换存在问题
*   Arc/Track使用Keepout属性时转换错误
*   Pin盘
    *   不支持长宽不一致的8角焊盘会转换为腰形
    *   Mask不支持Tending，负值转换为Null
*   Pin孔
    *   非金属化转换为金属化孔
    *   不支持方孔
*   其它情况一切正常

**PCB对象转换测试结果（总结）：PCB中非****Component对象的所有元素**

*   Free Pad对象转换容易转换错误
*   Poly Cutout属性转换逻辑有问题，需要检查
*   Plane层的Fill或Region会错误的转换为Etch
*   Keepout层只允许存在Arc/Track/Fill/Region别放其它的对象
*   Multilayer层只允许存在Via、Pad、BoardCutout
*   网格或None属性 Poly均转换为实心Shape
*   不带网络的Via不会被转换
*   BarCode字体将不被转换，中文字会造成转换停止
*   Rooms/Dimension/Coordinate均不被转换
*   其它情况一切正常

**貌似17.2的转换修复了Keepout转换的错误，更新了一个高级的****derive connectivity lines功能****，检查测试了一下，在修复部分问题的同时又带来了更多问题，而且17.2我用的还不熟也不是特别普遍17.2的测试放到日后再说**