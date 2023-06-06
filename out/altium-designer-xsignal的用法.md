---
title: 'Altium Designer xSignal的用法'
date: Fri, 18 Dec 2020 01:04:37 +0000
draft: false
tags: ['Altium', '设计技巧']
---

整理资料By My Dream

      在用AD进行高速布线时，有时候需要进行过电阻（电容）的等长，或者DDR之间的拓扑等长，AD 15之前的版本进行此类布线时一般采用From toEditor来进行规则设置，但是比较麻烦，也有其他的一些方法，过电阻（电容）等长时，网上看到有些人先将电阻（电容）短路，绕弯等长后再改回来，再修改布线网络等等，总之给我们布线带来了较大的麻烦，好在在AD15及以后的版本增加了xSignals这个功能，不过目前来看，虽然版本已经更新到了AD19，但网上关于AD xSignals的介绍还是少之又少，这就导致了知道这个功能但是又不会用的尴尬局面。本人由于工作需要需要用到这一功能，经过几天摸索之后，差不多搞明白了，先将教程公布一下。Ps：电路在公司内网上画的，就不具体演示了，软件版本AD 19.0.12  
     xSignals可以用于DDR的拓扑结构走线，过电阻（电容）等长走线，我们以过电阻（电容）等长走线为例。

创建xSignals
----------

![](http://a1024.synology.me:222/images/blog2022/xSignal1.jpg)

可以用向导创建也可以直接创建（差不多），或者选中源焊盘和目标焊盘，右键创建xSignals，本教程选择创建xSignals

对象过滤和选择
-------

左上元器件，右上目标器件，比如现在一个A器件上四组差分对，1、2接在B器件上，3和4接在C器件上，这4对差分对8根线之间都串联一个电阻，这样一个走线为例，那么下图左上的元器件是A，目标器件可以同时选中B和C；

![](http://a1024.synology.me:222/images/blog2022/xSignal2.jpg)

网络分析
----

选中后点击下面的分析，软件就会自动分析他们之间的走线，到这里xSignals就创建好了，PCB中已经将xsingal网络进行高亮。

建立类
---

在 设计-类中，找到xSignals，把需要网络的建立一个类。

![](http://a1024.synology.me:222/images/blog2022/xSignal3.jpg)

设置等长
----

设置等长规则，设计-规则-High speed-Matched Length进行长度约束设置，可以右键 执行new rule创建等长约束规则，在net class里面就可以看到我之前创建的类。然后进行约束就可以了。

![](http://a1024.synology.me:222/images/blog2022/xSignal4.jpg)

官网教程链接：[使用xSignals定义高速信号路径](https://www.altium.com/documentation/15.1/display/ADES/((Defining+High+Speed+Signal+Paths+with+xSignals))_AD#)   [在元器件之间创建xSignals](https://www.altium.com/documentation/15.1/display/ADES/PCB_Dlg-Form_CreateCompPinPairs((Create+xSignals+Between+Components))_AD)  [xSignals Multi-Chip Wizard](https://www.altium.com/documentation/15.1/display/ADES/PCB_Dlg-FormWizardView((xSignals+Multi-Chip+Wizard))_AD)  
官网资料PDF版本（带翻译）：链接: [https://pan.baidu.com/s/1BM7G7sYDFtir-RlZWf293A](https://pan.baidu.com/s/1BM7G7sYDFtir-RlZWf293A) 提取码: v8ry

另一篇文章，以下内容由网友ivanll提供
=====================

来源 Altium.cn  
在Altium Designer中发布的[xSignals Wizard](http://techdocs.altium.com/cn/display/ADOH/xSignal+Wizard) 将在多个元件之间创建多重xSignal的过程简化为一种单一的过程。

xSignal Wizard在单一源元件和多个目标元件之间创建xSignal。Wizard使用一种面向元件的方法识别潜在的xSignal——您可选择一种单一源元件、相关网络和目标元件——然后这种方法将分析从该元件到指定元件之间的所有潜在路径，包括经过一系列被动元件和支线。作为工程师，您可以选择需要生成的xSignal，也可以针对这些xSignal创建匹配长度设计规则。

原有的xSignals Wizard支持为多个元件创建定制xSignal。本次发布的Wizard扩展了该功能，可针对大量不同的公共接口和存储电路自动创建xSignal和xSignal组。

本次发布版本为xSignals Wizard增加了USB3模式。USB 3.0 xSignal Wizard用于为所有USB 3.0通道创建xSignals、xSignal组和匹配长度规则。

**运行XSIGNAL WIZARD**
--------------------

xSignal Wizard可通过以下路径打开：

*   **Design » xSignals » Run xSignals Wizard**
*   **元件right-click » xSignals » Run xSignals Wizard**

![](http://techdocs.altium.com/sites/default/files/wiki_attachments/264081/xSignals_Wizard.png)

Wizard可处理用户指定的控制器-连接器对之间的所有USB 3.0通道。Wizard自动评估与控制器相连的差分对网络，检测跨距与连接器相连的网络。该跨距中可能包括被动元件和多个网络。Wizard用一种xSignal组标识这些对，同时用控制器-连接器xSignal标识这些对的各条支线。

一旦您选用了**USB 3.0**, 页面上将显示**差分对内匹配长度公差设置**，请输入适当值。该值将用于Wizard创建的设计规则中，并能通过PCB规则和约束编辑器随时变更。这类用户定义的设置将会保留，以供将来使用。

对于USB 3.0，所有USB用户端口均被称为_通道_。如图所示，各通道包含3个差分对：即传输对、接收对和数据对。

对于USB 3.0，关键布线设计需求应匹配所有对的线路长度，对之间的长度匹配则不那么严格。考虑到这一需求，并且匹配长度设计规则需要差分对能检查一对网络内的长度，Wizard将检查差分对的定义，或者自动创建合适的差分对（如果没有合适的差分对）。随后将配置Wizard创建的匹配长度设计规则，使其用于检查与差分对内长度（**Within Differential Pair Length**）匹配的长度。注意：该规则配置为对比整个xSignal对的支线长度，而非对比各差分对的支线长度。

![](http://techdocs.altium.com/sites/default/files/wiki_attachments/264081/xSignals_USB3_1.png)  
选择USB 3.0，使用Wizard为重要的USB 3.0网络自动创建xSignal和差分对。

**选择源元件和目标元件**
--------------

在下一页面上，Wizard根据标号前缀和引脚数量标识了所有潜在的源元件和目标元件。

1.  为**Controller**标号和**Connector**标号设置过滤器前缀，并按要求设置**Min Pin Count**的值，然后
2.  选择单一源元件，然后
3.  选择目标元件。

![](http://techdocs.altium.com/sites/default/files/wiki_attachments/264081/xSignals_USB3_2.png)  
选择源控制器元件和目标USB连接器。

如选择了多个目标元件，您最好通过Wizard下一页面上的下拉列表框检查这些元件的xSignal和网络命名语法。

**标识通道和创建xSignal**
------------------

在本页面上，您可以定义命名语法，以便Wizard标识xSignal中包含的相关发射器、接收器和数据对网络。所有xSignal对将分别群集为一个xSignal组，并且这些组可用于界定匹配长度设计规则的范围。  
![](http://techdocs.altium.com/sites/default/files/wiki_attachments/264081/xSignals_USB3_3-highlight.png)  
检查，并在必要时为xSignal和网络定义合适的命名规则，然后点击创建xSignal。  
本页面功能如下：

1.  控制器的标号显示在**Components**标签旁。与之并列的下拉列表框包括了在Wizard上一页中选定的所有**Connector**。

*   如下所示的命名语法选项适用于下拉列表框中显示的所有连接器，依次选定各选项，并检查选定的命名语法是否完整和适宜。
*   如前文所述，对于USB 3.0，所有USB用户端口均被称为通道。您可设置通道数量（**Channels Total**）为1-32。通常每个连接器均有一条对应通道。

1.  所有USB 3.0通道内分别有3条差分对路径，即传输对、接收对和数据对。这些路径连接控制器和连接器。Wizard将为所有正向网络分别创建一个xSignal，并为各反向网络创建另一个xSignal，这些xSignal可能根据需要跨多个元件。然后用xSignal组表示控制器-连接器对。使用**Define xSignal Class Syntax**组指定这些xSignal组的名称。如果没有已定义的差分对，Wizard还会创建合适的差分对。

*   **Define xSignal Class Name Syntax** ——创建后按指定方式命名的xSignal组，各通道指定用数字值代替\[#\]。请根据需要输入最佳字符串。

1.  **Channel <N>**——这些字段定义了用于标识相关发射器/接收器/数据对网络名称的掩码。

*   Wizard拥有用于检查的大型预定义命名方案模板，一般而言，它会自动填入这些字段。如果没有填入，则应从下拉列表框中选择正确的名称，或键入合适的网络名称语法。

1.  配置了命名字段后，点击**Analyze Nets & Create xSignal Classes**按钮。

*   Wizard将为所有通道创建xSignal、xSignal组和匹配长度规则。注意：您每次重新运行Wizard时均需重新创建上述内容，如您打算再次运行Wizard时，删除这些内容。

1.  所创建的xSignal组名及该组中的xSignal成员详情见网格。
2.  点击**Create Spreadsheet**按钮，为Wizard创建的所有xSignal生成XLS格式的电子表格。
3.  点击**Finish**选项，关闭Wizard。

**创建XSIGNAL和XSIGNAL组**
----------------------

如前所述，Wizard自动创建：

*   **xSignals**——针对控制器-连接器之间的3个对（传输对、接收对和数据信号路径）分别创建，由**Net Names Syntax**掩码标识。
*   **xSignal Classes** - 为xSignal对分别创建xSignal组，并根据**Define xSignal Class Name Syntax**控件指定的命名方式命名。
*   **Differential Pairs** - 界定匹配长度设计规则的范围，使这些规则在规定的网络对和差分对内检查。Wizard检查是否有合适的对，并在未能检测到合适对时自动加以创建。将PCB面板设置为差分对编辑器模式，从而检查各对，并确保其正确性。

**创建设计规则**
----------

之后，Wizard为所有xSignal组创建了一条匹配长度设计规则。因为这条规则已界定用于测试所有xSignal对，并对比各对内的支线长度，所以只需这一条规则即可。该规则采用Wizard第二页输入的Tolerance约束条件。如有必要，可调整公差。  
![](http://techdocs.altium.com/sites/default/files/wiki_attachments/264081/Rule_MatchedLength_DiffPairScope.png)  
因为只需测试各对内的支线长度，所以只需创建一条匹配长度规则即可检查所有xSignal组。