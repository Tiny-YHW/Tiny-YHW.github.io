---
title: 'Cadence 疑难杂症 报错 问题解决记录'
date: Mon, 29 Mar 2021 02:53:12 +0000
draft: false
tags: ['技术讨论', '设计经验']
---

软件安装 破解 启动问题
------------

### Orcad 软件启动报错

关键字: This application has quit unexpectedly

问题尚未解决，官网有相关讨论，并没有确切的解决方案，确定不是软件破解问题，不是软件盗版问题，目前好像只能通过重装系统解决（重装软件已尝试，无法解决上述问题）

以下是我收集的解决方案 虽然都没解决我的这个问题，但值得尝试一下（有别人的成功案例）参考链接[1](https://community.cadence.com/cadence_technology_forums/f/pcb-design/30493/orcad-capture-crashes-on-start-up) [2](https://www.eda365.com/thread-41964-1-1.html)

#### CAPTURE.INI

Cadence\\SPB\_XX.X\\tools\\capture里的CAPTURE.INI文件出错了尝试删除它，让软件重新生成或者文件开头在

\[Part Management\]  
Configuration File=d:\\Cadence\\SPB\_16.3\\tools\\Capture\\Samples\\BENCHACC.DBC  
DemoConfiguration File=d:\\Cadence\\SPB\_16.3\\tools\\Capture\\Samples\\DemoBENCHACC.DBC  
下面加上库的路径  
\[Part Library Directories\]  
Dir1=D:\\Cadence\\SPB\_16.3\\tools\\capture\\library\\  
\[Allegro Footprints\]  
Dir0=D:\\Cadence\\SPB\_16.3\\share\\pcb\\pcb\_lib\\symbols

#### 系统变量

将系统的环境变量PATH的值中最前方增加

%CDSROOT%\\tools\\bin;%CDSROOT%\\tools\\libutil\\bin;%CDSROOT%\\tools\\fet\\bin;%CDSROOT%\\tools\\pcb\\bin;%CDSROOT%\\tools\\specctra\\bin;%CDSROOT%\\tools\\PSpice;%CDSROOT%\\tools\\PSpice\\Library;%CDSROOT%\\tools\\Capture;%CDSROOT%\\OpenAc cess\\bin\\win32\\opt;

或者尝试将原来PATH中的%CDSROOT%相关值剪切到前面

#### 注册表

找到注册表HKEY\_CURRENT\_USER\\Software\\OrCAD\\CaptureWorkSpace展开删除对应版本的注册表

Capture导出或allegro导入网表报错
-----------------------

### 非法字符

关键字：Illegal character(s)

所有从Orcad或HDL原理图中导出网表或者导入Allegro是报错包含上述关键字时都是由于在原理图中使用了软件不支持编译的字符如 Ω、. 空格 回车等，尝试查找并改变此类字符，重新导网表，肯定支持的字符包含 大小写字母、数字、下划线，其它任何字符都可能是非法字符

非法字符包括（不是所有）：. / 空格 中文字符 中文标点 回车换行字符

ERROR(ORCAP-36052): Value for property PCB Footprint contains carriage return for R74  
错误解释：R74的footprint属性的值包含回车  
解决办法：重新填写正确的footprint值，或去掉回车，不太好找，一般在末尾按一下del就行

ERROR(SPMHNI-190):Device problem '20K5% XXX'.Package property error:'PART\_NAME'='20KΩ±5% XXX'. Illegal character(s) present in the name or value  
错误解释： PART\_NAME字段存在非法字符 Ω 处理掉非法字符

ERROR(OPCAP-36112):Illegro character "white space" found in Refdes "U16 DIN" in……  
错误解释：位号U16 DIN存在非法字符空格，需要将空格处理掉

### Footprint未指定名称

ERROR(ORCAP-36002): Property "PCB Footprint" missing from instance C9: SCHEMATIC1, PAGE1 (175.26, 93.98)  
错误解释：原理图中没有指定Footprint C9  
解决方法：在原理图中找到 C9，然后双击或通过右键选中edit properties，在PCB Footprint 对应的框中填入封装名

![](http://a1024.synology.me:222/images/blog2022/yinanzazheng1.jpg)

### 属性缺失

ERROR(ORCAP-36022): Pin number missing from Pin "1" of Package C/C , C9: SCHEMATIC1, PAGE1 (175.26, 93.98). All pins should be numbered.8  
错误解释：这类问题是在制作symbol时，没有给package 的pin 编号。C9  
解决方法：修改原理库，然后在在原理图中design cache中进行更新；或找到器件选择右击edit part，双击pin脚（或单击选择可按住Ctrl多选，然后Ctrl+E 批量修改），打开如下视图，在Number下方的框中输入pin number，处理完后，关闭时选择update all。

![](http://a1024.synology.me:222/images/blog2022/yinanzazheng2.jpg)

### 管脚类型逻辑错误

OrCAD Capture Pin Type[定义和连接 注意事项](https://a1024.synology.me:1024/orcad-capture-pin-type%e5%ae%9a%e4%b9%89%e5%92%8c%e8%bf%9e%e6%8e%a5-%e6%b3%a8%e6%84%8f%e4%ba%8b%e9%a1%b9/)

ERROR(ORCAP-36041): Duplicate Pin Name "VDD3V" found on Package F85226AD , U159 Pin Number 120: BRASWELL, P16 F85226AD (2.60, 2.40). Please renumber one of these.  
错误解释：U159器件 120脚 Pin Name "VDD3V"重复  
解决方法：找到U159，选择右击edit part，双击pin脚（或单击选择可按住Ctrl多选，然后Ctrl+E 批量修改），根据实际情况将重复的pin name type属性均改为power，或分别将Pin Name 进行区别。出错原因：我只知道type为passive的pin name不能相同，type为power则可以相同，其它的自己引申我也不懂  
相关操作：打开原理库 原理图中右击part 选择 Edit part  鼠标只框选pin按ctrl+e 可批量修改

![](http://a1024.synology.me:222/images/blog2022/yinanzazheng3.jpg)

### 管脚号不能为0

ERROR(ORCAP-36021):Pin number “0” found on pin "PIN Name" of Package …… Pin number shuould be greater than "0" 要求Pin number不能为0改为其它数值或字母即可，修改注意保证原理图库和PCB库引脚号一致问题

原理与PCB交互
--------

[解决ORCAD部分元器件与原理图不交互方法其一](https://a1024.synology.me:1024/%e8%a7%a3%e5%86%b3orcad%e9%83%a8%e5%88%86%e5%85%83%e5%99%a8%e4%bb%b6%e4%b8%8e%e5%8e%9f%e7%90%86%e5%9b%be%e4%b8%8d%e4%ba%a4%e4%ba%92%e6%96%b9%e6%b3%95%e5%85%b6%e4%b8%80/)

PCB设计报错
-------

### [Allegro 17.2 不能创建XNET](https://a1024.synology.me:1024/allegro-17-2-%e4%b8%8d%e8%83%bd%e5%88%9b%e5%bb%baxnet/)

### 导入dxf时部分圆弧线不能被导入

该圆弧线属性可能为样条曲线，Allegro软件不支持此类线性，需转换样条曲线为多段线后再导出，样条曲线的处理方式见[这里](https://a1024.synology.me:1024/autocad-%e7%ac%94%e8%ae%b0/)

出光绘数据Artwork
------------

### [Undefined aperture symbol](https://a1024.synology.me:1024/?p=1828)

封装库器件导入
-------

W- (SPMHA1-126): Illegal size identifier  
E- Cannot load symbol 'XXX'

出现上述错误有可能是Datebase出问题了，进行一下DB Doctor可能就可以了，菜单Tool->Datebase Check