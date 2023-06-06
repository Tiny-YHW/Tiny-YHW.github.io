---
title: 'ALTIUM Swap pin'
date: Sat, 28 Nov 2020 01:39:51 +0000
draft: false
tags: ['Altium', '设计技巧']
---

（待再次编辑整理，先放到这里）

[原文链接](https://www.altium.com/documentation/altium-designer/pin-pair-and-part-swapping-ad)

https://v.qq.com/x/page/t32078z0fzr.html

引脚，差分对和零件交换系统与Altium Designer的交互式布线和BGA转义布线功能协同工作。该功能提供了传统引脚交换系统的所有优点，但是利用了Altium Designer对设计中网络分配的深入了解。在引脚交换操作期间，Altium Designer会分析分配给所选引脚的网络，并在引脚和任何连接的铜缆上动态重新分配网络。

这种功能水平意味着可以交换来自复杂BGA设备的部分路由的网络和预先路由的多层逃生设备。利用FPGA上有关差分引脚对的知识，也可以交换差分对。

![](https://www.altium.com/documentation/sites/default/files/wiki_attachments/299992/Results_From_Optimization_19.png)

![](https://www.altium.com/documentation/sites/default/files/wiki_attachments/299992/Pin_Net_Swapping_19.png)

在PCB级别，系统包括功能强大的自动优化器，该优化器使用此信息来动态地重新分配网络以提高可路由性。例如，系统可以在多个设备上进行转义的多个设备上执行重新连接。它将基于匹配的逃生路线层，最短的曼哈顿路线距离以及每层上的最小交叉点数来分配这些。

加上部分路由网络交换以及自动优化器，使您能够采用分层和迭代路由策略，先避开路由设备，然后路由到给定区域的边缘，最后将这些部分连接在一起。根据部分路由网络提供的更新信息，可以随时重新运行自动交换器以进行重新优化。

交换分为三类：

*   引脚交换
*   差分对交换
*   子部分交换。

配置交换组
-----

对于交换的每种类别，_交换组_规定了组件中可以交换的内容和不能交换的内容。在插针交换的情况下，共享一个公共_插针组_的组件中的_插针_可以相互交换。同样，对于线对交换和零件交换，线_对组_和_零件组_值确定可以分别交换差分对或子零件。组件的交换组在“[配置引脚交换”](https://www.altium.com/documentation/altium-designer/pinswapper-dlg-configurecomponentpinswapconfigure-pin-swapping-for-component-ad)对话框中[配置](https://www.altium.com/documentation/altium-designer/pinswapper-dlg-configurecomponentpinswapconfigure-pin-swapping-for-component-ad)，如下图所示。可通过以下方式访问它：

*   在PCB文档中，右键单击组件，然后选择**Component Actions»Configure Pin / Part Swapping**。
*   在Sch文档中，右键单击该组件，然后选择“**零件动作”»“配置引脚交换”**。
*   单击“在**组件**中[配置交换信息”](https://www.altium.com/documentation/altium-designer/pinswapper-dlg-configureallpinswapconfigure-swapping-information-in-components-ad)对话框底部的“[配置组件”](https://www.altium.com/documentation/altium-designer/pinswapper-dlg-configureallpinswapconfigure-swapping-information-in-components-ad)按钮（“**工具”»“配置引脚交换”**）。
*   在“在组件中_交换信息”_对话框中双击任何_组件_。

[![](https://www.altium.com/documentation/sites/default/files/resize/wiki_attachments/299992/configure_pin_swapping_19-700x395.png)](https://www.altium.com/documentation/sites/default/files/wiki_attachments/299992/configure_pin_swapping_19.png)

### 销组

当一个组件引脚属于同一_引脚组_（具有相同的_引脚组_值）时，可以与该组件中的另一个引脚互换。所述_销组_是各销的组件中的属性和它的值可以是任何字母数字字符串。整个组件的_引脚组_在“_配置引脚交换”_对话框中设置。

[](https://www.altium.com/documentation/sites/default/files/wiki_attachments/299992/pin_swap_sch.png)包含双路5输入正或非门元件的原理图。每个子部件的每个输入引脚在逻辑上都是等效的，为引脚交换提供了一种理想的情况。

考虑上图所示的示意图，其中包含SNJ54S260组件的两个5输入或非门。由于NOR门的特性，INA0至INA4的每个网络都可以互换。同样，每个网络INB0到INB4都可以交换，但是INAx网络不能与INBx网络交换。

NOR门的交换约束在_配置引脚交换_对话框中定义。为网络INAx提供交换组1，为网络INx提供交换组2，以确保交换仅由系统以与组件逻辑一致的方式执行。将引脚的引脚组值保留为空表示该引脚不可用于交换。

### 零件组和序列ID

组件通常由多个功能上等效的子部分组成。零件交换允许交换此类等效子零件的网络。再次考虑上图所示的组件。两个NOR门均提供相同的功能，并且网络（INA0，INA1，INA2，INA3，INA4，OUTA）可以与网络（INB0，INB1，INB2，INB3，INB4，OUTB）交换。

使用_零件组_和_序列ID_属性配置零件的零件交换。这些都是文本属性，可在“_配置引脚交换”_对话框的“**零件交换”**选项卡中访问，如下所示。下图还显示了与上图中显示的组件相对应的_零件组_和_序列ID_设置。的_部分组_指示哪个子部分能够与彼此交换。两个子部件可以互换，因此，在下图中，它们的_部件组_的值相同。

的_序列ID_属性确定交换的子部分之间的引脚的等价性。在“或非”门示例中，重要的是，在发生零件更换时，输入引脚不要与输出引脚互换。下图显示了_序列ID_的设置，以便OUTA与OUTB交换，INA0与INB0交换，INA1与INB1交换，依此类推。

[](https://www.altium.com/documentation/sites/default/files/wiki_attachments/299992/Part_Swap_19.png)在双5输入或非门组件的“配置引脚交换”对话框中设置零件交换组。

请注意，“零件交换”仅适用于设计为子零件的组件，因为它基于在两个子零件之间交换所有网络。

### 配对组

差分对的交换受差分对的_对组_的值控制。在_对组_属性在被访问的**差分对交换来实现**所述的标签_配置管脚交换_对话。通过访问左下角的下拉框，可以设置“**差分对交换”**选项卡中的三种模式。

*   _显示指令对_\-系统将使用原理图上的[差分对指令](https://www.altium.com/documentation/altium-designer/sch-obj-parametersetparameter-set-ad)填充表中的差分对。
*   _显示来自FPGA_的配对-系统将使用从组件可用的FPGA信息中获得的差分对数据来配对引脚。注意，当组件是FPGA时，此模式可用。
*   _显示所有引脚_\-系统将显示所有组件引脚。

[](https://www.altium.com/documentation/sites/default/files/wiki_attachments/299992/differential_pair_swapping_19.png)在“配置引脚交换”对话框中设置“配对交换”组。

### 控制如何在原理图上执行掉期

在PCB编辑器引脚中，通过交换元件焊盘和相应铜线上的网来执行对和零件的交换。将更改合并到原理图中后，可以通过两种方式来处理引脚交换：通过交换组件符号上的引脚，或交换连接到引脚的电线上的网络标签。每种方法都有其优点和缺点。

交换引脚将始终适用于原理图，但是这可能意味着该元件符号的实例不再与库中定义的实例相同。在这种情况下，这意味着无法从库中更新符号，也意味着该设计中同一组件的其他实例将具有不同的引脚排列。因此，这种方法对于简单的组件（例如电阻器阵列）非常理想。

仅当通过网络标签建立连接且引脚未硬接线在一起时，才能通过交换网络标签来执行原理图上的交换。这种方法的优点是组件符号不会更改，以后可以从库中进行更新。这种方法是FPGA等复杂组件的最佳选择，在该组件上物理移动符号上的两个引脚可能会导致基于I / O bank的符号显示不正确。

您可以通过在“[项目选项-选项”](https://www.altium.com/documentation/altium-designer/workspacemanager-dlg-projectpropertiesdialog-pagecontrol-main-optionsproject-options-options-ad)对话框的“**使用这些方法进行引脚交换”**部分中选择“**添加/删除网络标签**或**更改原理图引脚”**选项来确定执行**交换的方式**，如下所示。[](https://www.altium.com/documentation/altium-designer/workspacemanager-dlg-projectpropertiesdialog-pagecontrol-main-optionsproject-options-options-ad)

![](https://www.altium.com/documentation/sites/default/files/wiki_attachments/299992/Project_Options_Options_19.png)这些项目选项控制原理图文档中引脚交换的更新方式。

### 在PCB上启用引脚，配对和零件交换

设置组件中的引脚，配对和零件交换所需的_交换组_属性存储在原理图组件中。但是，此信息是在PCB编辑器中使用的。每个PCB组件都有一个选项，允许进行引脚交换。

可以在“[属性”面板中](https://www.altium.com/documentation/altium-designer/pcb-prop-componentcomponent-properties-ad)配置PCB组件的交换选项，该[面板](https://www.altium.com/documentation/altium-designer/pcb-prop-componentcomponent-properties-ad)显示在设计空间中选择该组件时的属性。这些选项可以在“**常规”**选项卡的“**交换选项”**区域中找到。

![](https://www.altium.com/documentation/sites/default/files/wiki_attachments/299992/Swapping_Options_19.png)

“_在组件中配置交换信息”_对话框中列出了设计中使用的所有组件（包括SCHlib / PCBlib）及其当前交换设置。从PCB编辑器中访问时，“_在组件中配置交换信息”_对话框包含一个用于启用/禁用交换板上板上每个组件的附加列，称为“**在PCB中启用”**。将_在组件配置交换实现信息_对话框从访问**工具»** **配置管脚交换**命令。

[](https://www.altium.com/documentation/sites/default/files/wiki_attachments/299992/Enable_Pin_Swapping_19.png)该_配置交换实现信息在组件_对话框。

“_在组件中配置交换信息”_对话框包含一个功能强大的右键菜单，使您可以轻松地将设置从一个组件快速复制到另一个组件，或者单击即可启用/禁用多个组件。

在“组件中的_交换信息配置”_对话框中双击某个组件将打开该_组件_的“_配置引脚交换”_对话框，您可以在其中定义引脚，差分对和子部件的交换组设置。

执行销，对和零件交换
----------

### 交互式引脚，配对和零件交换

交互式交换允许在PCB编辑器中一次交换引脚，差分对或子零件。交互式交换命令可在“**工具”»“销/零件交换”**子菜单中找到。从菜单中选择命令后，将突出显示可用于交换的引脚。状态行显示执行交换所需的步骤：

1.  第一步是选择突出显示的引脚之一，这些引脚将成为引脚交换的来源。在成对或部分交换的情况下，引脚所属的差分对或子部分将随后被交换。
2.  第二步是为交换选择目标引脚。对于成对或部分交换，此引脚将代表差分对或子部分。

下图两个图像显示了交互式部分交换双5输入或非门组件的阶段。可以交换两个子部分，这意味着可以选择其五个引脚中的每个引脚，如上图所示。选择对应于子部件U2B的引脚8。然后，系统突出显示可以交换的子部件U2A的引脚。

[](https://www.altium.com/documentation/sites/default/files/wiki_attachments/299992/OR_before.png)  [](https://www.altium.com/documentation/sites/default/files/wiki_attachments/299992/OR_after.png)左图，步骤1-选择要交换的引脚，可用引脚将突出显示。右图，第2步-选择目标引脚。

### 自动Pin / Net优化器

自动Pin / Net优化器是一个两阶段工具。从PCB编辑器菜单中选择**工具»引脚/零件交换»自动引脚/网络优化**器以执行自动优化。

自动Pin / Net优化器首先运行一个快速的单遍优化器，该优化器试图最小化交叉和连接长度，但实际上可能会增加交叉和连接长度。完成后，将询问您是否要运行迭代优化器。迭代优化器将执行多次传递，以尝试减少交叉次数和连接长度。

![](https://www.altium.com/documentation/sites/default/files/wiki_attachments/299992/Results_From_Optimization_19.png)

将更改传递回原理图
---------

在“_配置引脚交换”_对话框中配置_交换组_时，无论启动命令时哪个编辑器处于活动状态，您所做的编辑都会立即应用于原理图组件。但是，由于您在PCB编辑器中执行了引脚，差分对或子零件交换而导致的设计更改会使用标准的“**设计更新”**过程传播回原理图。

### 将更改从PCB推送到原理图

销，对和零件交换以与传递其他设计更改相同的方式传递回原理图-通过从菜单中选择“**设计»更新**”。根据“_项目选项-选项”对话框中_“[允许换针”](https://www.altium.com/documentation/altium-designer/pin-pair-and-part-swapping-ad#allow_options)选项的配置方式，将按以下方式执行换针：

*   更改引脚名称-此更改将移动符号上的引脚。引脚实际上并没有在符号上移动，但是从视觉上看，这两个引脚已经移动或交换了位置。
*   将引脚移动到不同的网络-此更改将交换所连接电线上的网络标签。
*   更改子零件ID-执行零件交换时，此更改将更改子零件索引。

[![](https://www.altium.com/documentation/sites/default/files/resize/wiki_attachments/299992/pin_swapping_move_pins_on_sch_highlighted-400x375.png)](https://www.altium.com/documentation/sites/default/files/wiki_attachments/299992/pin_swapping_move_pins_on_sch_highlighted.png)

[![](https://www.altium.com/documentation/sites/default/files/resize/wiki_attachments/299992/pin_swapping_move_net_labels_on_sch_highlighted-400x370.png)](https://www.altium.com/documentation/sites/default/files/wiki_attachments/299992/pin_swapping_move_net_labels_on_sch_highlighted.png)

左图显示了通过交换引脚在原理图中解决的引脚交换。右图显示了通过移动网络标签解决的交换。

如果原理图未更新以显示交换的引脚或零件，请按**结束**键以刷新显示。

### 利用FPGA设计充分利用新型引脚/部件交换系统

除了智能引脚，配对和部件交换所提供的明显优势之外，交换部分路由子网的能力还为交换带来了新的维度，这是与大容量FPGA配合使用的理想之选。动态网络重新分配使您可以使用逐步完善的引脚/网络分配的多阶段设计过程

#### 初始I / O分配

在此阶段，以原理图级别上最简单的方式，对FPGA和其他设备引脚进行网络分配设置。通常，这意味着仅按数字总线顺序将网络标签添加到FPGA的引脚上。示意图编辑器中的“[智能粘贴”](https://www.altium.com/documentation/altium-designer/sch-dlg-smartpasteformsmart-paste-ad)功能非常适合执行此操作。

#### 初始连接优化

该设计可以转移到PCB布局，由于原理图级别的随机分配，会有很多连接交叉。运行“[自动Net / Pin优化器”命令](https://www.altium.com/documentation/altium-designer/pinswapper-cmd-runautopinswapperrunautopinswapper-ad)将迅速大大减少交叉次数。结果并不需要是理想的，因为它主要用于使连接在PCB层面上在视觉上更易于管理。

#### 逃生路线

现在可以在PCB上的大型设备上执行扇出和转义路由（右键单击组件以有选择地执行扇出/转义路由）。这可能会使先前优化的分配情况恶化，但是在这一点上并不重要。

#### 转义连接优化

再次运行自动优化器。这次，它将利用扇出/转义路由的预路由部分。

#### 手动路由

现在，您可以将逃生路线的末端视为要驶向的“目标”。由于您可以从网络的另一端路由到PCB上最近的转义I / O路由（在空间上和逐层），而不是同一网络上的路由，因此忽略了实际的连接线。连接不会排队。取而代之的是，在FPGA I / O引脚的转义路由与来自PCB其他部分的路由之间将出现一系列小间隙。下图显示了一个简单的示例。

[![](https://www.altium.com/documentation/sites/default/files/resize/wiki_attachments/299992/auto_optimizer_before-400x508.png)](https://www.altium.com/documentation/sites/default/files/wiki_attachments/299992/auto_optimizer_before.png)

[![](https://www.altium.com/documentation/sites/default/files/resize/wiki_attachments/299992/auto_optimizer_after-401x508.png)](https://www.altium.com/documentation/sites/default/files/wiki_attachments/299992/auto_optimizer_after.png)

#### 最终优化

再次运行自动优化器，它将把路由子网分配给最近的可能的转义I / O引脚。这将使您的连接非常短。在这种情况下，自动优化器具有特殊的例程以产生良好的结果。这些现在可以交互方式或自动路由。

#### 手动销

使用交互式交换器可以执行所需的任何特定的引脚交换更改。

#### 将更改传播回原理图

准备好将这些引脚分配传播回原理图时，最好禁用原理图符号上的引脚更改。这是因为FPGA通常以多部分组件的形式出现，每排引脚都是独立的原理图部分。将引脚从一个零件移动到另一零件将导致这些符号在逻辑上变得不正确，因为存储体符号将包括不属于该存储体的引脚。在这种情况下，通过更改网络标签执行引脚交换是正确的方法。

#### 根据需要重复

该过程可以根据需要运行多次，也可以在设计过程中随时运行。