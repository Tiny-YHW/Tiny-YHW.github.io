---
title: 'ALLEGRO ENVIRONMENT VARIABLES'
date: Mon, 07 Feb 2022 02:22:09 +0000
draft: false
tags: ['Allegro']
---

![](https://a1024.synology.me:222/images/blog2022/Snipaste_2022-02-07_10-04-32.png)

本文将罗列Allegro所有的可设置项，关于本窗口的介绍和几项常用的设置可查看下面这个链接的内容

[allegro user preferences常见设置及说明](https://a1024.synology.me:1024/?p=561)

display
-------

### cursor

infinite\_cursor\_bug\_nt  
Infinite cursor may leave graphics artifacts onscreen in OpenGL with some GPUs or graphics drivers. Ifset, this variable will likely eliminate the problem.Note; for this option to work, display\_raster\_ops must becleared or set to on.  
在使用某些 GPU 或图形驱动程序的 OpenGL 中，无限光标可能会在屏幕上留下图形伪像。如果设置，这个变量可能会消除这个问题。注意；要使此选项起作用，必须清除 display\_raster\_ops 或将其设置为开启。

pcb\_cursor  
If set, Allegro displays the desired cursor type. Thedefault (cross) is a simple cross-hair. The infinite typeis 2 lines extending to the full display; pcb\_cursor\_anglemay be used to set the angle. The octal is four lines, 45degrees apart; the pcb\_cursor\_angle variable is not used.Default value is 'cross'.  
如果设置，Allegro 将显示所需的光标类型。默认（十字）是一个简单的十字准线。无限型为2条线延伸至全屏； pcb\_cursor\_angle 可用于设置角度。八进制是四行，相距45度；未使用 pcb\_cursor\_angle 变量。默认值为“cross”。

pcb\_cursor\_angle  
Applies only to infinite cursor (see pcb\_cursor variable).By default, infinite cross-hair is shown orthogonal. Thisvariable specifies angle for infinite cursor. Values arebetween 0and 90.  
仅适用于无限光标（参见 pcb\_cursor 变量）。默认情况下，无限十字准线显示为正交。此变量指定无限光标的角度。值介于 0 和 90 之间。

### datatips

custom\_datatip\_remove\_delay  
By default a customizible datatip disappears250 milliseconds after the cursor leaves the object. It isthe time required for the user to move cursor to thedatatip in order to access its advanced functionality.This allows this delay to be adjusted between 0 (forimmediate datatip disappearance) and 2000 milliseconds.  
默认情况下，可自定义的数据提示在光标离开对象后 250 毫秒消失。这是用户将光标移动到数据提示以访问其高级功能所需的时间。这允许在 0（数据提示立即消失）和 2000 毫秒之间调整此延迟。

datatips\_delay  
By default a datatip appears if the cursor remains in thesame position for 250 milliseconds. This allows this delayto be adjusted between 100 and 2000 milliseconds.  
默认情况下，如果光标在同一位置保持 250 毫秒，则会出现数据提示。这允许在 100 到 2000 毫秒之间调整此延迟。

datatips\_fixedpos  
By default, datatips appear next to the cursor. Thisoption causes them to display at the bottom of the optionspanel.  
默认情况下，数据提示出现在光标旁边。此选项使它们显示在选项面板的底部。

disable\_datatips  
Disables context sensitive Data tips when mouse hover overAllegro data elements.  
当鼠标悬停在 Allegro 数据元素上时禁用上下文相关的数据提示。

disable\_hover\_over  
Disables dynamic highlighting and datatips that occurwhen you hover over elements in the display. Dynamichighlighting and datatips will still occur for applicationmode commands because they are needed for preselectionpreview.  
禁用将鼠标悬停在显示中的元素上时出现的动态突出显示和数据提示。应用程序模式命令仍然会出现动态突出显示和数据提示，因为预选预览需要它们。

focus\_followmouse  
Controls interaction of window focus and hover-overhighlighting and datatips. If not set,highlighting/datatips are enabled only when the Allegrocanvas is in focus. If set to "allegro\_derived", they arealso enabled when Allegro sub-windows such as show elementare in focus. When set to "anywhere", they are enabledregardless of focus.  
控制窗口焦点和悬停高亮和数据提示的交互。如果未设置，则仅当 Allegrocanvas 处于焦点时才启用突出显示/数据提示。如果设置为“allegro\_derived”，它们也会在 Allegro 子窗口（例如 show element）处于焦点时启用。当设置为“任何地方”时，无论焦点如何，它们都被启用。

### element

etchlen\_ignore\_pinvia  
By default, the etch length that is computed for showelement and other commands will include via to via offsetdistances when a via or pin are direct connected. Thismakes this calculation agree with our delay calculations.Setting this variable will restore the older version ofthe calculation that excludes these offsets.  
默认情况下，当直接连接过孔或引脚时，为 showelement 和其他命令计算的蚀刻长度将包括过孔到过孔偏移距离。这使得该计算与我们的延迟计算一致。设置此变量将恢复排除这些偏移的旧版本计算。

noshow\_current\_selections  
By default, if an interactive command is running,and there are some elements that currently are selected orhighlighted (with temp highlight), running show elementwill result in a window displaying information for thoseelements. The other command will remain active. Settingthis variable disables that feature. The other commandwill terminate and an interactive show element commandwill start.  
默认情况下，如果交互式命令正在运行，并且当前有一些元素被选中或突出显示（临时突出显示），运行 show element 将导致一个窗口显示这些元素的信息。另一个命令将保持活动状态。设置此变量会禁用该功能。另一个命令将终止，交互式 show element 命令将启动。

show\_max\_manhattan\_pins  
Show element does not display information when netscontain more than 50 pins for performance reasons. Valuecan be any number greater than 0. Not applicable for netswith NO\_RAT property.  
出于性能原因，当网络包含超过 50 个引脚时，显示元素不显示信息。值可以是大于 0 的任何数字。不适用于具有 NO\_RAT 属性的网络。

showelement\_autoavoid  
If set, the show element window is automaticallypositioned to avoid the main window. When unset (default)the previous location of the window is used on next open.  
如果设置，显示元素窗口将自动定位以避开主窗口。取消设置（默认）时，下次打开时将使用窗口的前一个位置。

showelement\_basearea  
For show element, default (or traditional) reportsshape area in Sq In. if design units is English or SqCent. if design is Metric. The artwork option matches filmarea output which reports Microns in Sq Millim. andeverything else the same as traditional. Finally, thedesign option reports units the same as current designunits.  
对于显示元素，默认（或传统）报告 Sq In 中的形状区域。如果设计单位是英制或平方分。如果设计是公制的。艺术品选项匹配以 Sq Millim 为单位报告微米的 filmarea 输出。其他一切都和传统一样。最后，设计选项报告的单位与当前设计单位相同。

showelement\_brief  
If set, certain show element detail is filtered.Currently for shapes it filters boundary and voidsegments.  
如果设置，某些显示元素细节将被过滤。目前对于形状，它过滤边界和空隙段。

showelement\_highspeed  
If set and product is Allegro or APD, show elementfor nets will display in PCB SI format.  
如果 set 和 product 是 Allegro 或 APD，show elementfor nets 将以 PCB SI 格式显示。

showelement\_xhatcharea  
If set, reports that actual area of cross-hatchedshapes. By default, the cross hatch lines are notconsidered when calculating the area. This calculation istime consuming which is why it is not the default.  
如果设置，则报告交叉影线形状的实际面积。默认情况下，计算面积时不考虑交叉影线。此计算非常耗时，这就是它不是默认值的原因。

showmeasure\_altunits  
If set, show measure also displays measurements in thespecified units.  
如果设置，show measure 还会以指定的单位显示测量值。

showmeasure\_layerrestore  
If set, show measure restores the active layer tothe setting that existed at the start of the command. Bydefault, a 'Done', leaves the active layer with itscurrent setting.  
如果设置，show measure 会将活动层恢复到命令开始时存在的设置。默认情况下，“完成”会保留当前设置的活动层。

### general

display\_backingstore  
If set stores a copy of the screen in memory to saverepainting when a form is closed or a window moved.Supported only with X-windows (UNIX) and applies todrawing data, not forms. Can be set on the command line bytyping "backingstore".  
如果 set 在内存中存储屏幕副本以在关闭窗体或移动窗口时保存重新绘制。仅支持 X-windows (UNIX) 并适用于绘图数据，而不适用于窗体。可以通过键入“backingstore”在命令行上进行设置。

display\_no\_auto\_hide\_boundary  
By default, turning the visibility of an etchlayer off through the options panel will automaticallyturn off the corresponding dynamic shape boundary layer.Turn on this variable to disable this feature and have theboundary layer remain visible unless manually toggledthrough the Display -> Color/Visibility form.  
默认情况下，通过选项面板关闭蚀刻层的可见性将自动关闭相应的动态形状边界层。打开此变量可禁用此功能并使边界层保持可见，除非通过显示 -> 颜色/可见性表单手动切换。

display\_norepair  
If set, display repair is disabled for the describedelements. Options are rats or all. If not set, displayrepair mode is enabled for all elements. For slowersystems, setting this to "all" provides better performancebut results in some graphics glitches. Leaving thevariable unset results in the best display.  
如果设置，则对描述的元素禁用显示修复。选项是老鼠或全部。如果未设置，则为所有元素启用显示修复模式。对于较慢的系统，将此设置为“全部”可提供更好的性能，但会导致一些图形故障。保持变量未设置会导致最佳显示。

display\_noskeletal\_draw  
If set, skeletal draw mode is disabled. Skeletaldraw is used when very fast refresh of graphics isrequired such as dynamic zoom out mode.  
如果设置，骨骼绘制模式将被禁用。当需要非常快速的图形刷新时使用 Skeletaldraw，例如动态缩小模式。

display\_raster\_ops  
Controls the use of raster operations to improveappearance of display features. The tradeoff is the use ofadditional system memory. Depending on your graphicshardware performance may be slow. For example, it greatlyimproves the look of the dynamic graphics. If set to"slow", features that require frequent use of thecapability are not allowed to use it. The default is "on".In OpenGL this option may get turned off automatically ifallegro display area is bigger than hardware supportedstorage mechanism. Making Allegro smaller should fix it.  
控制栅格操作的使用以改善显示要素的外观。权衡是使用额外的系统内存。根据您的图形硬件性能可能会很慢。例如，它极大地改善了动态图形的外观。如果设置为“slow”，则不允许使用该功能需要频繁使用的功能。默认为“on”。在 OpenGL 中，如果allegro 显示区域大于硬件支持的存储机制，此选项可能会自动关闭。使 Allegro 变小应该可以解决这个问题。

display\_refdes\_subclass  
If set, refdes text on the specified subclass willbe displayed when a symbol is moved.If not set, or iftext does not exist on the chosen subclass, priority ofdisplay will be assembly\_top, assembly\_embedded,assembly\_bottom, silkscreen\_top, silkscreen\_bottom,display\_top, display\_embedded, display\_bottom.  
如果设置，则移动符号时将显示指定子类上的 refdes 文本。如果未设置，或者如果所选子类上不存在文本，则显示优先级将为 assembly\_top、assembly\_embedded、assembly\_bottom、silkscreen\_top、silkscreen\_bottom、display\_top、display\_embedded、display\_bottom .

### highlight

display\_nohilitefont  
If set, displays all highlighted elements with a solidhighlight color. The default is to display highlightedelements with a combination of the highlight color and theelement's original color (striped). OpenGL may not supportstriped highlighting at all zoom levels.  
如果设置，则以纯高光颜色显示所有突出显示的元素。默认是使用高亮颜色和元素的原始颜色（条纹）的组合来显示高亮元素。 OpenGL 可能不支持所有缩放级别的条纹突出显示。

highlight\_shape\_net  
Highlight the net associated with a shape when shape isselected.  
选择形状时，突出显示与形状关联的网络。

### opengl

OpenGL display Settings

disable\_opengl  
Disable running in OpenGL mode. If set, always runs innative display mode and overrides running in OpenGL modeby default.  
禁用在 OpenGL 模式下运行。如果设置，则始终运行本机显示模式并默认覆盖在 OpenGL 模式下运行。

disable\_opengl\_cache  
If set, disables OpenGL performance boost in roam. Setthis option if there are display artifacts while roaming.Caching makes heavy use of GPU resources. Your GPUcapabilities dictate if caching should be disabled.  
如果设置，则禁用漫游中的 OpenGL 性能提升。如果漫游时出现显示伪影，请设置此选项。缓存会大量使用 GPU 资源。您的 GPUcapabilities 决定是否应禁用缓存。

draw\_etch\_outline  
If set while the enhanced display option for connect lineend-caps is enabled, wide lines display with an outline.  
如果在启用连接 lineend-caps 的增强显示选项时设置，则宽线显示带有轮廓。

new\_grid\_display  
If set, a new method is used to display grids (which mayimprove graphics performance). This method is onlyavailable in OpenGL. Internal environment variable name -new\_grid\_display.  
如果设置，将使用一种新方法来显示网格（这可能会提高图形性能）。此方法仅在 OpenGL 中可用。内部环境变量名称 -new\_grid\_display。

static\_shapes\_fill\_solid  
Disable fill pattern for static shapes. If set,static shapes fill the same as dynamic shapes.  
禁用静态形状的填充图案。如果设置，静态形状填充与动态形状相同。

viewer\_useoglgraphics  
By default, the allegro\_free\_viewer disables OpenGLon Windows. This enables use of OpenGL in this program.Note the free viewer is an unsupported program, if anyOpenGL issues are noted you should discontinue use of thisvariable.  
默认情况下， allegro\_free\_viewer 在 Windows 上禁用 OpenGL。这允许在该程序中使用 OpenGL。注意免费查看器是不受支持的程序，如果发现任何 OpenGL 问题，您应该停止使用该变量。

### roam

Roam Settings

pcb\_autoroam  
Defines time interval, in milliseconds, between roamincrements. If set to 1000, roam increments are 1 persecond. If not set, the default value is 250 milliseconds.  
定义漫游增量之间的时间间隔（以毫秒为单位）。如果设置为 1000，漫游增量为每秒 1。如果未设置，则默认值为 250 毫秒。

roaminc  
Defines roam increments in pixels, when using arrow keysto roam. For best performance it should be set tomultiples of 16. Minimum is 16 and maximum is 256 pixels.The default value is 96 pixels.  
使用箭头键漫游时，以像素为单位定义漫游增量。为获得最佳性能，应将其设置为 16 的倍数。最小值为 16，最大值为 256 像素。默认值为 96 像素。

### Seg\_Over\_Void

Settings for Highlight SOV application

sov\_active\_only  
If checked, the Highlight SOV application will considerthe active layer only.If not checked it will considerall layers.  
如果选中，突出显示 SOV 应用程序将仅考虑活动图层。如果未选中，它将考虑所有图层。

sov\_skip\_plane\_check  
If checked, the SOV application will skip checkviolation of partial/missing plane coverage.If notchecked it will check plane coverage.  
如果选中，SOV 应用程序将跳过部分/缺失平面覆盖的检查违规。如果未选中，它将检查平面覆盖。

sov\_spacing  
Spacing parameter for the Highlight SOV application.Apositive value indicates the minimum allowable spacing toan adjacent plane void.A negative value indicatesallowable segment overlap onto an adjacent plane void.  
突出显示 SOV 应用程序的间距参数。正值表示相邻平面空隙的最小允许间距。负值表示允许段重叠到相邻平面空隙。

### shape\_fill

display\_shapefill  
For solid shapes and rectangles fills with lines spacedthe specified number of pixels apart. If not set, defaultis 4 pixels. This variable has no effect in OpenGL mode.  
对于实心形状和矩形，填充间隔指定像素数的线条。如果未设置，默认为 4 像素。此变量在 OpenGL 模式下无效。

no\_etch\_shape\_display  
Disable display of etch shapes. If set, etch shapesare not drawn.  
禁用蚀刻形状的显示。如果设置，则不会绘制蚀刻形状。

no\_shape\_fill  
Disable filling shapes. If set shapes will drawn inskeletal mode.  
禁用填充形状。如果设置形状将绘制 inskeletal 模式。

no\_shape\_fill\_dyn\_ood  
Disable filling dynamic shapes that are out of date.This variable can eliminate the need to move dynamicshapes off the design when setting their fill mode todisable.  
禁用填充过时的动态形状。此变量可以消除在将填充模式设置为禁用时将动态形状移出设计的需要。

old\_shape\_fill\_style  
Fill shapes using old line fill style. If not set,shapes are by default filled with a fill pattern bitmap.This variable has no effect in OpenGL mode.  
使用旧的线条填充样式填充形状。如果未设置，则默认情况下使用填充图案位图填充形状。此变量在 OpenGL 模式下无效。

### visual

bug\_solaris\_hlt\_lines  
On some solaris 7 systems,long odd angledhighlighted lines (e.g. ratsnests) can cause graphicglitches.Setting this variable causes the line draw touse a line width of 1 rather than 0 to work around theproblem. This may slow down the line draw slightly but isneeded until the platform vendor fixes the problem.  
在某些 solaris 7 系统上，长的奇数角度突出显示的线（例如鼠巢）会导致图形故障。设置此变量会导致线条绘制使用 1 而不是 0 的线宽来解决此问题。这可能会稍微减慢绘制速度，但在平台供应商解决问题之前是必需的。

display\_drcfill  
If set, Allegro displays DRC markers as "filled"butterflies.  
如果设置，Allegro 将 DRC 标记显示为“填充”蝴蝶。

display\_no\_close\_grids  
If set, Allegro suppresses grid display when zoomingout reduces the ability to display grids at the spacinglisted in the define grid form.  
如果设置，Allegro 在缩小时抑制网格显示会降低以定义网格表单中列出的间距显示网格的能力。

display\_nocolor\_dynamics  
When set, the dynamic cursor buffer draws theelements as white. When unset, the elements are drawn withtheir assigned color.  
设置后，动态光标缓冲区将元素绘制为白色。未设置时，元素将以其指定的颜色绘制。

display\_nodynamicarcwidth  
If set, for performance reasons, arcs and circlesare drawn at a 1 pixel width when using interactivecommands such as move or copy. Unset to see correct width.  
如果设置，出于性能原因，当使用诸如移动或复制之类的交互式命令时，圆弧和圆将以 1 像素的宽度绘制。取消设置以查看正确的宽度。

display\_nolinewidth  
If set, all lines are displayed at a 1 pixel width.This variable can increase performance at the expense ofan accurate display. The default is lines at width. Note,dynamics drawing ignores this variable.  
如果设置，则所有行都以 1 像素宽度显示。此变量可以提高性能，但会牺牲准确显示。默认为线宽。注意，动态绘图忽略了这个变量。

display\_pinpair\_connection  
If set, Allegro marks differential pairs bydrawing a line between associated pin pairs. This line isa visual indicator only. Note that this feature requiresenabling Enhanced display mode "Diffpair drivers pins" inSetup Design Parameters form.  
如果设置，Allegro 通过在相关引脚对之间绘制一条线来标记差分对。这条线只是一个视觉指示器。请注意，此功能需要在设置设计参数表单中启用增强型显示模式“Diffpair drivers pins”。

display\_readonly\_intensity  
Sets display color intensity for disabled(readonly) database objects. If not set, disabled objectsare drawn at 40% intensity by default. Note that Shadowmode in Allegro does not effect disabled objects.  
设置禁用（只读）数据库对象的显示颜色强度。如果未设置，默认情况下以 40% 的强度绘制禁用的对象。请注意，Allegro 中的阴影模式不会影响禁用的对象。

display\_thintext  
Text is always drawn at one pixel width (ignores photoplotwidth). This restores 13.5 Allegro behavior.  
文本总是以一个像素宽度绘制（忽略 photoplotwidth）。这将恢复 13.5 Allegro 行为。

old\_style\_flash\_symbols  
When set, new boards created in Allegro uses oldstyle flashes for thermals rather than the new WYSIWYGthermal flash symbols.  
设置后，在 Allegro 中创建的新板使用旧式闪光灯进行散热，而不是新的 WYSIWYG 热闪光灯符号。

ratt\_off\_if\_connected  
Controls the visibility of Rat Ts that are fullyconnected (all of its Ratsnests are connected).Bydefault,a Rat T will remain visible when its Ratnestsare all connected.A value of "on" causes a fullyconnected Rat T to be invisible.A value of"unhighlighted" causes a fully connected Rat T to beinvisible unless it is highlighted.  
控制完全连接的 Rat T 的可见性（其所有 Ratsnests 都已连接）。默认情况下，当其 Ratnests 全部连接时，Rat T 将保持可见。“on”值会导致完全连接的 Rat T 不可见。值为“unhighlighted”会导致完全连接的 Rat T 不可见，除非它被突出显示。

drawing
-------

Controls design access behavior typically at the global level.

allegro\_long\_name\_size  
Defines the maximum name length in the design.Examples of long name types are (but not limited to);nets, padstacks, symbols, and function pins. The minimumvalue is 32 and the maximum is 255. IMPORTANT  
定义设计中的最大名称长度。长名称类型的示例是（但不限于）；网络、焊盘堆栈、符号和功能引脚。最小值为 32，最大值为 255。 重要

db\_save\_full\_dbcheck  
How frequently a full dbdoctor is run on save. Forexample, a 2 means that a full dbdoctor will be run onevery other save. By default, a quick design check is runon every save. Caution, this lengthens the time to save adesign.  
保存时运行完整 dbdoctor 的频率。例如，2 表示将在每隔一次保存时运行一个完整的 dbdoctor。默认情况下，每次保存时都会运行快速设计检查。注意，这会延长保存设计的时间。

db\_tier\_nomsg  
If you frequently use different product tiers duringdesign, you may wish to enable this option to inhibit theconfirmer in open drawing that warns about opening thedesign in a different product. Even with this variableset, you will still see a warning in the command area.  
如果您在设计过程中经常使用不同的产品层级，您可能希望启用此选项以禁止打开图纸中的确认程序，警告有关在不同产品中打开设计的警告。即使使用此变量集，您仍会在命令区域中看到警告。

drawing\_4mils  
If set, allows a database in MILS to be set to an accuracyof 3 or 4 decimal places. When unset (default), maximumaccuracy in MILS is 2. Using more then 2 decimal places ofaccuracy causes rounding issues when fabbing drawing.  
如果设置，则允许将 MILS 中的数据库设置为小数点后 3 或 4 位的精度。未设置时（默认），MILS 中的最大精度为 2。使用超过 2 个小数位的精度会在制造图纸时导致舍入问题。

drawing\_no\_4mils\_msg  
If set, does not display a warning message in thedrawing parameter form if accuracy is set to greater then2 while using MILS.  
如果设置，则在使用 MILS 时，如果精度设置为大于 2，则不会在绘图参数表中显示警告消息。

filename\_allow\_brackets  
By default, Allegro does not support squarebrackets ( \[\] ) in filenames. This variable allows Allegroto open brd, mcm, sip files that contain brackets.Internet Explorer may add brackets to filenames if itdetects that a download will overwrite an existing file.Setting this variable is not recommended. After opening adesign containing a square bracket, you should immediatelysave it to a legal name.  
默认情况下，Allegro 不支持文件名中的方括号 ( \[\] )。此变量允许 Allegroto 打开包含括号的 brd、mcm、sip 文件。如果 Internet Explorer 检测到下载将覆盖现有文件，它可能会在文件名中添加括号。不建议设置此变量。打开包含方括号的设计后，应立即将其保存为合法名称。

legacy\_character\_set  
By default, Allegro does not allow a backslash () innet names. This variable sets pre-16.6 behavior whichallows this character in net names.  
默认情况下，Allegro 不允许使用反斜杠 () innet 名称。此变量设置 16.6 之前的行为，允许在网络名称中使用此字符。

multiboard\_always  
By default, Allegro will not automatically open a systemdesign link when a board is open while PCB SI will. Thiscauses Allegro to automatically open a design link if oneis currently associated with the design.  
默认情况下，当 PCB SI 打开时，Allegro 不会自动打开系统设计链接。如果当前与设计相关联，这会导致 Allegro 自动打开设计链接。

no\_symbol\_onsave  
By default, on saving a dra file, the symbol file willalso by created. With this variable set, the old behaviorwhere the user would need to use File->Create Symbol(create symbol) is restored.  
默认情况下，保存 dra 文件时，也会创建符号文件。设置此变量后，用户需要使用 File->Create Symbol(create symbol) 的旧行为将被恢复。

noconfirm\_savedb  
If set, does not display warning message if save willoverwrite an existing database. The database will beoverwritten.  
如果设置，则在保存将覆盖现有数据库时不显示警告消息。数据库将被覆盖。

noconfirm\_uprev  
If set, does not display an uprev warning message on opendrawing. Default is to display warning dialog if opening adrawing will require an uprev.  
如果设置，则不会在 opendrawing 上显示 uprev 警告消息。如果打开绘图需要 uprev，默认是显示警告对话框。

### new\_design

Support base new drawing characteristics. The units and accuracy variables are used if a template design is not utilized as a starting point (see WIZARD\_TEMPLATE\_PATH variable). Cadence recommends the use of template designs. Store these template designs via CDS\_SITE (see documentation) so all your users have access.

allegro\_new\_accuracy  
Specifies accuracy for new board if design specificvariable (e.g. new\_accuracy) is not specified.  
如果未指定设计特定变量（例如 new\_accuracy），则指定新板的精度。

allegro\_new\_units  
Specifies units for new board if design specific variable(e.g. new\_units) is not specified.  
如果未指定设计特定变量（例如 new\_units），则指定新板的单位。

apd\_new\_accuracy  
Specifies accuracy for new mcm if design specific variable(e.g. new\_accuracy) is not specified.  
如果未指定设计特定变量（例如 new\_accuracy），则指定新 mcm 的精度。

apd\_new\_units  
Specifies units for new mcm if design specific variable(e.g. new\_units) is not specified.  
如果未指定设计特定变量（例如 new\_units），则指定新 mcm 的单位。

cdnsip\_new\_accuracy  
Specifies accuracy for new SIP if design specificvariable (e.g. new\_accuracy) is not specified.  
如果未指定设计特定变量（例如 new\_accuracy），则指定新 SIP 的精度。

cdnsip\_new\_units  
Specifies units for new SIP if design specific variable(e.g. new\_units) is not specified.  
如果未指定设计特定变量（例如 new\_units），则指定新 SIP 的单位。

new\_accuracy  
Specifies accuracy for new design if design specificvariable (e.g. allegro\_new\_accuracy) is not specified.  
如果未指定设计特定变量（例如 allegro\_new\_accuracy），则指定新设计的精度。

new\_template\_with\_last\_design  
This restores pre-16.6 behavioral for newdesigns. Before 16.6, new designs took their basecharacteristics (units, accuracy, etc.) from the previousdesign. If this variable is set, then only the firstdesign opened when starting the tool utilize variables onthis page or a new template design.  
这为新设计恢复了 16.6 之前的行为。在 16.6 之前，新设计采用了先前设计的基本特征（单位、精度等）。如果设置了此变量，则只有在启动工具时打开的第一个设计才会使用此页面上的变量或新模板设计。

new\_units  
Specifies units for new design if design specific variable(e.g. allegro\_new\_units) is not specified.  
如果未指定设计特定变量（例如 allegro\_new\_units），则指定新设计的单位。

pad\_designer\_new\_accuracy  
Specifies accuracy for a new padstack if designspecific variable (e.g. new\_accuracy) is not specified.  
如果未指定设计特定变量（例如 new\_accuracy），则指定新焊盘堆栈的精度。

pad\_designer\_new\_units  
Specifies units for a new padstack if designspecific variable (e.g. new\_units) is not specified.  
如果未指定设计特定变量（例如 new\_units），则为新焊盘指定单位。

drc
---

### delay

include\_comp\_delay  
This variable causes the delay of components in a pathto be included in a path delay when the path delay iscomputed to check propagation delay and relativepropagation delay constraints. The delay of the componentis determined from a transmission line (TL) statement inthe ESpice model assigned to the component. If there is noassigned model or the assigned model contains no TLstatement, no delay is included for the component.  
当计算路径延迟以检查传播延迟和相对传播延迟约束时，该变量导致路径中组件的延迟包含在路径延迟中。组件的延迟由分配给组件的 ESpice 模型中的传输线 (TL) 语句确定。如果没有指定的模型或指定的模型不包含 TLstatement，则组件不包含延迟。

include\_terminators  
Setting this variable controls the delay rule checker.If delay is to be checked across the entire net, thisvariable also includes the terminator length in thecalculation. The standard check for delay across entirenet does not include terminators.  
设置此变量控制延迟规则检查器。如果要在整个网络中检查延迟，此变量还包括计算中的终止符长度。整个网络延迟的标准检查不包括终止符。

pre\_12.0\_delay\_rule  
The delay rule checker has changed in 12.0 and beyond.When delay is added across a net in 12.0, the checker ischecking the min delay value against the shortest pinpair, and the max delay value against the longest pinpair. In many cases, designers use the delay rule valuesas a length checker and want the min and max delays to beatolerance across the entire net as it did in rev 11.x.  
延迟规则检查器在 12.0 及更高版本中发生了变化。当在 12.0 中跨网络添加延迟时，检查器会根据最短的引脚对检查最小延迟值，并根据最长的引脚对检查最大延迟值。在许多情况下，设计人员使用延迟规则值作为长度检查器，并希望最小和最大延迟能够像 rev 11.x 中那样在整个网络中实现节拍。

use\_accurate\_delay\_calculation  
If set this variable causes a more accuratemodeling to be done of the power and ground shapes whencomputing impedance and delay. Instead of modeling theplanes as perfect shields with no holes or cutouts, theactual outline of the shapes with all holes and cutoutsare considered. The performance of the impedance,propagation delay and relative propagation delayconstraint checks can possibly be slowed when this moreaccurate calculator is used. Also, the Shield flag must beturned off on every plane layer.  
如果设置此变量，则会在计算阻抗和延迟时对电源和接地形状进行更准确的建模。不是将平面建模为没有孔或切口的完美屏蔽，而是考虑具有所有孔和切口的形状的实际轮廓。当使用这个更精确的计算器时，阻抗、传播延迟和相对传播延迟约束检查的性能可能会减慢。此外，必须在每个平面层上关闭 Shield 标志。

### general

cns\_single\_thread  
Restrict drcupdate and dbdoctor to a single thread ofexecution on a multiple cpu system.This variable has noeffect on a single cpu system.  
将 drcupdate 和 dbdoctor 限制在多 cpu 系统上的单线程执行。该变量对单 cpu 系统没有影响。

cns\_via\_match\_count\_all  
If set, enables matched via count constraint checkon partially connected nets.  
如果设置，则通过对部分连接网络的计数约束检查启用匹配。

dyn\_phase\_canvas\_display  
This displays dynamic phase control delays asgraphic text. Suggestion is to leave this option offexcept when debugging nets with difficult dynamic phaseerrors. Alternatively, you can set it as a teaching aid.When enabled, the display can become very busy with alarge number of phase text errors from adjacent nets.  
这将显示动态相位控制延迟作为图形文本。建议关闭此选项，除非在调试具有困难动态相位误差的网络时。或者，您可以将其设置为教学辅助工具。启用后，显示会因来自相邻网络的大量相位文本错误而变得非常繁忙。

same\_net\_traps  
This variable causes DRC checking for small segment jogs.This new spacing check is not intended for any angle data.It checks for this geometry at angles divisible by 45degrees.  
此变量会导致 DRC 检查小段转折。此新间距检查不适用于任何角度数据。它检查可被 45 度整除的角度的几何形状。

same\_net\_vias\_shape\_connect  
If set, enables filtering of same-net viassharing mutual shape connections.  
如果设置，则启用对共享相互形状连接的同网通孔的过滤。

wire\_finger\_same\_profile  
If set, restricts the wire-to-finger spacingconstraint to fingers with wires of the same profile.  
如果设置，将线到手指间距约束限制为具有相同轮廓的线的手指。

file\_management
----------------

### autosave

Autosave Settings

autosave  
Enables autosaving. It must be set/unset before startingAllegro.  
启用自动保存。必须在启动 Allegro 之前设置/取消设置。

autosave\_dbcheck  
Enables quick database check before an autosave. Indefault mode, this is turned off because this increasesthe time for a save.  
在自动保存之前启用快速数据库检查。在默认模式下，这是关闭的，因为这会增加保存时间。

autosave\_name  
Sets base name used for the autosave file. The defaultname is AUTOSAVE. Do NOT provide a file extension. Allegrowill use the appropriate extension for the type ofdatabase under edit.  
设置用于自动保存文件的基本名称。默认名称是 AUTOSAVE。不要提供文件扩展名。 Allegro 将为正在编辑的数据库类型使用适当的扩展名。

autosave\_time  
Controls autosave intervals. The default is 30 minutes.The minimum is 10 minutes and the maximum is 300 minutes.  
控制自动保存间隔。默认为 30 分钟。最短为 10 分钟，最长为 300 分钟。

### journals

journal\_nobuffer  
By default, the journal file has buffered output toimprove performance when writing the file over a network.This option changes the output to unbuffered. Theadvantage of unbuffered output is sometimes with programcrashes more lines are written to the journal file.  
默认情况下，日志文件具有缓冲输出以提高通过网络写入文件时的性能。此选项将输出更改为无缓冲。无缓冲输出的优点是有时程序崩溃时会向日志文件写入更多行。

journal\_prefix  
Prefix appended to the program's journal file name. Threespecial prefix keys are available; "user" substitutesuser's login, "host" which substitutes system name and"unique" which creates a unique filename based upon host,user and process id. Prefix must be a legal file name (no/ or :). Example journal\_prefix = user for login "me"would create an allegro journal file of me\_allegro.jrl  
附加到程序日志文件名的前缀。三个特殊的前缀键可用； “user”代替用户的登录名，“host”代替系统名称，“unique”根据主机、用户和进程ID创建唯一的文件名。前缀必须是合法的文件名（no/ 或 :）。示例 journal\_prefix = 登录“me”的用户将创建 me\_allegro.jrl 的快板日志文件

### miscellaneous

allegro\_nolocking  
By default, Allegro programs create a lockfile when adesign is opened.This allows other Allegro programs tosense that the design is in use. This option disablesadvisory file locking (pre-16.5 behavior). Users settingthis option will not create file locks but still benotified of locks set by other users.  
默认情况下，Allegro 程序会在打开设计时创建一个锁定文件。这允许其他 Allegro 程序感知该设计正在使用中。此选项禁用建议文件锁定（16.5 之前的行为）。设置此选项的用户不会创建文件锁，但仍会收到其他用户设置的锁的通知。

directory\_cache  
Ignores fully qualified directories in Allegro PATHvariables that do not exist. These directories whenlocated remotely can have slow access. The Allegrocommand, bad\_directories, lists these directories butrequires you to use Allegro with features that use thePATH variables.  
忽略 Allegro PATHvariables 中不存在的完全限定目录。这些位于远程的目录访问速度可能很慢。 Allegro 命令 bad\_directories 列出了这些目录，但要求您将 Allegro 与使用 PATH 变量的功能一起使用。

temp  
Set to Use the specified directory for temporary storageof data files. Most often, artwork requires more temporaryspace than the /tmp directory contains. By default,Allegro uses the OS environment variable TEMP with afallback to TMP.  
设置为<具有大量可用磁盘空间的目录路径> 使用指定的目录来临时存储数据文件。大多数情况下，艺术品需要比 /tmp 目录包含的更多临时空间。默认情况下，Allegro 使用操作系统环境变量 TEMP 并回退到 TMP。

### output\_dir

ads\_sdart  
The subdirectory to which artwork (gerber) and drill filesare written. Default is the same directory as the design.  
图稿 (gerber) 和钻孔文件写入的子目录。默认为与设计相同的目录。

ads\_sdlog  
The subdirectory to which log files should be written.  
应写入日志文件的子目录。

ads\_sdplot  
The subdirectory to which plot files should be written.  
应写入绘图文件的子目录。

ads\_sdreport  
The subdirectory to which report files should be written.  
应写入报告文件的子目录。

dump\_library\_directory  
Specifies the export directory that Export Libraries(dlib UI command) uses as its directory. Default is thecurrent directory. Location may be a relative or absolutepath. Command attempts to create the rightmost directorycomponent if it is not present.  
指定导出库（dlib UI 命令）用作其目录的导出目录。默认为当前目录。位置可以是相对或绝对路径。如果它不存在，命令将尝试创建最右边的目录组件。

### versioning

File Revision Control Settings

ads\_autosaverevs  
Enables file versioning for AUTOSAVE database files. Value = number of versions you want maintained.Default is no versioning.  
为 AUTOSAVE 数据库文件启用文件版本控制。值 = 要维护的版本数。默认为无版本控制。

ads\_boardrevs  
Enables file versioning for allegro layouts (.brd) andsymbol (._sm) files. Value = number of versions youwant maintained. Default is 1 version. 为快板布局 (.brd) 和符号 (._sm) 文件启用文件版本控制。值 = 您要维护的版本数。默认为 1 个版本。

ads\_logrevs  
Enables file versioning for Allegro log files. Value =number of versions you want maintained.  
为 Allegro 日志文件启用文件版本控制。值 = 要维护的版本数。

ads\_textrevs  
Enables file versioning of allegro files which are not.brd ._sm or .logValue = number of versions you wantmaintained. 启用不是 .brd ._sm 或 .logValue = 您想要维护的版本数的快板文件的文件版本控制。

ext\_artwork  
File extension used for artwork (film) files. Default is.art. Recommendation is to set this at the CDS\_SITE level.Use caution before changing the extension to ensure allyour post-processing tools can handle the new extension.  
用于艺术作品（电影）文件的文件扩展名。默认是艺术。建议在 CDS\_SITE 级别设置此项。更改扩展名之前要小心，以确保我们的后处理工具可以处理新扩展名。

ext\_drill  
File extension used for ncdrill files. Default is .drl.Recommendation is to set this at the CDS\_SITE level. Usecaution before changing the extension to ensure all yourpost-processing tools can handle the new extension.  
用于 ncdrill 文件的文件扩展名。默认为 .drl。建议在 CDS\_SITE 级别进行设置。更改扩展名之前要小心，以确保您的所有后处理工具都可以处理新扩展名。

ic\_packaging
-------------

### die\_symbols

icp\_disable\_auto\_symbol\_lock  
By default, the Cadence IC Packaging toolswill maintain the locked property on all die symbols inthe design, to prevent a user from inadvertently modifyingthem in an undesirable way. Set this variable to disablethis automatic locking mechanism.  
默认情况下，Cadence IC Packaging 工具将保持设计中所有芯片符号的锁定属性，以防止用户以不希望的方式无意中修改它们。设置此变量以禁用此自动锁定机制。

icpkg\_unplace\_comps\_on\_delete  
In versions of the Cadence IC Packaging toolsprior to 15.5, deleting the symbol instance of a die orpackage from the design would leave the associated logicalcomponent unplaced in the design. In 15.5, thisfunctionality was modified to delete the logical componentas well as the physical symbol. Setting this variable willrestore the original behavior.  
在 15.5 之前的 Cadence IC 封装工具版本中，从设计中删除管芯或封装的符号实例会使相关的逻辑组件未放置在设计中。在 15.5 中，此功能被修改为删除逻辑组件以及物理符号。设置此变量将恢复原始行为。

### Manufacture

dxf\_bond\_finger\_class  
By default, bond finger objects in IC Package and SiPdesigns are exported to DXF as via objects using the "VIACLASS" class. This override should be used if bond fingersshould be controlled and exported using their own class,"BOND FINGER".  
默认情况下，IC 封装和 SiPdesigns 中的键合指对象作为使用“VIACLASS”类的通孔对象导出到 DXF。如果应该使用它们自己的类“BOND FINGER”来控制和导出键合指，则应使用此覆盖。

dxf\_suppress\_wire\_vias  
By default, when a bond wire is exported to DXF fromthe IC Packaging layout tools, a via with the samediameter as the wire is placed at each end to connect thewire to the start and end items. Set this variable tosuppress creation of these connecting via objects.  
默认情况下，当从 IC 封装布局工具将键合线导出到 DXF 时，会在每一端放置一个与导线直径相同的过孔，以将导线连接到开始和结束项目。设置此变量以禁止通过对象创建这些连接。

stream\_bond\_finger\_class  
By default, bond finger objects in IC Package andSiP designs are exported to stream as via objects usingthe "VIA CLASS" class. This override should be used ifbond fingers should be controlled and exported using theirown class, "BOND FINGER".  
默认情况下，IC 封装和 SiP 设计中的键合指对象被导出为使用“VIA CLASS”类的通孔对象。如果应该使用它们自己的类“BOND FINGER”来控制和导出绑定手指，则应该使用此覆盖。

stream\_drill\_class  
By default, via drill information is not written tostream files. Setting this variable will enable a VIA\_CONNclass in the conversion file and its editor in stream out,where you can select layer pairs. Drills between theselayers will be output on indicated stream layer.  
默认情况下，通过钻取信息不会写入流文件。设置此变量将启用转换文件中的 VIA\_CONNclass 及其流输出中的编辑器，您可以在其中选择层对。这些层之间的钻孔将在指定的流层上输出。

stream\_out\_clean\_shapes  
When exporting stream data with the flattengeometry option, complex shapes are broken into multiplepieces. In rare occasions, one or more of these pieceswill have two boundary segments that touch, but do notoverlap. This can introduce errors in some tools readingthe shape, as it can appear that the boundary isself-intersecting. If set, this option will force streamout to examine and attempt to break these shapes intomultiple pieces.  
使用 flattengeometry 选项导出流数据时，复杂的形状会被分成多个部分。在极少数情况下，这些碎片中的一个或多个将具有两个相互接触但不重叠的边界段。这可能会在某些读取形状的工具中引入错误，因为边界看起来是自相交的。如果设置，此选项将强制流输出检查并尝试将这些形状分成多个部分。

stream\_out\_multi\_drill\_shape  
While multi-drill arrays only support circledrills natively in the packaging tools, depending on yourexact manufacturing process, the actual shape of the holemay be different. Set this variable to override thecircular drill with the actual drill shape during streamoutput.  
虽然多钻孔阵列仅支持封装工具中的圆形钻孔，但根据您的具体制造工艺，孔的实际形状可能会有所不同。设置此变量以在流输出期间使用实际钻孔形状覆盖圆形钻孔。

stream\_out\_prevectorize\_pads  
When exporting stream, all arcs (includingcircle and oblong pads) will get vectorized to the numberof segments indicated on the stream out form. This cancause the air gap between a pad and a surrounding shapevoid to be slightly less than the specified DRC value. Setthis option to vectorize the pads and force a dynamicshape revoiding prior to generating stream data to ensurenecessary clearances are maintained.  
导出流时，所有弧（包括圆形和长方形焊盘）都将矢量化为流输出表单上指示的段数。这会导致焊盘和周围形状空隙之间的气隙略小于指定的 DRC 值。设置此选项以矢量化焊盘并在生成流数据之前强制消除动态形状以确保保持必要的间隙。

stream\_out\_save\_options  
Set this variable in order to have the stream outform remember your output options (Excluding the outputfile name and conversion file name) with the database.This will prevent you from having to set the options onfuture invocations, and will also allow the system toaccess your GDSII configuration for commands designed tosimulate manufactured output like PVS DRC checks and MetalDensity Scan.  
设置此变量以使流输出记住您的输出选项（不包括输出文件名和转换文件名）与数据库。这将防止您必须在未来调用时设置选项，并且还将允许系统访问您的 GDSII用于模拟制造输出的命令的配置，如 PVS DRC 检查和金属密度扫描。

stream\_out\_shape\_bound\_check  
When exporting stream, shapes with voids arebroken into multiple pieces such that no voids arepresent. In uncommon cases, a circular void (such asaround a via) may be tangent to one of these pieces,resulting in a self-intersecting shape outline. This cancause problems for tools importing the resulting streamfile. If set, this option will force stream out to performa detailed scan and ensure all boundaries are legal.  
导出流时，有空隙的形状会被分成多个部分，这样就不会出现空隙。在不常见的情况下，圆形空隙（例如通孔周围）可能与这些部分之一相切，从而形成自相交的形状轮廓。这可能会导致导入生成的流文件的工具出现问题。如果设置，此选项将强制流输出执行详细扫描并确保所有边界都是合法的。

interactive
-----------

addline\_nomerge  
By default, Add line merges lines on same layer if theirend-points touch. This variable disables merging in addline.  
默认情况下，如果端点接触，添加线会合并同一层上的线。此变量禁止在 addline 中合并。

copy\_no\_autosnap  
By default, the copy command will auto-snap clines andvias to aid connections. This option restores the 14.2model where picks were only snapped to the grid.  
默认情况下，复制命令将自动捕捉斜线和通孔以帮助连接。此选项恢复 14.2 模型，其中拾取仅捕捉到网格。

ripup\_delete\_first\_segment  
By default, when a symbol is deleted and etchripup is ON, all etch connected to the symbol's pins isdeleted until the first non-cline/via etch object isencountered. With this preference set, only the first etchsegment is deleted or segments are deleted until theremaining etch is outside a pin's pad extents.  
默认情况下，当一个符号被删除并且 etchripup 为 ON 时，所有连接到符号引脚的蚀刻都会被删除，直到遇到第一个非斜线/通孔蚀刻对象。设置此首选项后，仅删除第一个蚀刻段或删除段，直到剩余蚀刻超出引脚的焊盘范围。

ripup\_retain\_bondwire  
By default, when a symbol is deleted and etch ripupis ON, all etch connected to the symbol's pins is deleteduntil the first non-cline/via etch object is encountered.For wirebonded components, setting this preference allowswirebonds and bondfingers to be retained while subsequentetch is deleted. Combining this preference withDELETE\_FIRST\_SEGMENT will retain bondwires while deletingthe first segment beyond the bondfinger according to thatpreference's rules.  
默认情况下，当删除符号并打开 etch ripup 时，所有连接到符号引脚的蚀刻都会被删除，直到遇到第一个非斜切/通孔蚀刻对象。删除。将此首选项与 DELETE\_FIRST\_SEGMENT 组合将保留键合线，同时根据该首选项的规则删除键合指之外的第一段。

single\_via\_replace\_default  
Select single via replace mode by default whenrunning replace padstack.  
运行replace padstack时默认选择single via replace模式。

stacked\_via\_multi\_split  
By default, splitting a stack of vias during amove, copy, delete, or slide will split a single selectedvia out from the stack, leaving all other vias in place.When set, this will provide additional buttons to allowsplitting off all vias either above or below an identifiedlayer pair.  
默认情况下，在移动、复制、删除或滑动过程中拆分一堆过孔将从堆栈中拆分出一个选定的过孔，而将所有其他过孔留在原位。设置后，这将提供额外的按钮以允许拆分上方或下方的所有过孔在一个识别层对下面。

stacked\_via\_off  
By default, move, spin, copy, delete and slideautomatically select all vias in a stack rather than anindividual via. When set, this variable will disable theautomatic selection of multiple vias.  
默认情况下，移动、旋转、复制、删除和滑动自动选择堆栈中的所有过孔而不是单个过孔。设置后，此变量将禁用多个过孔的自动选择。

### clipboard

clip\_altconnect  
When set, Export Sub-Drawing creates a clipboard file thatinstructs Import Sub-drawing to lower the priority ofshapes for connectivity purposes. Basically pins, vias andclines have priority over shapes for connectivityassignment. This only applies if "Preserve nets of vias"is not checked. Clipboard files using this option are notcompatible with releases older than 16.6. Should be usedif utilizing sub-drawing to copy and paste via structures.  
设置后，Export Sub-Drawing 会创建一个剪贴板文件，该文件指示 Import Sub-drawing 为连接目的降低形状的优先级。基本上，引脚、过孔和斜线优先于连接分配的形状。这仅适用于未选中“保留通孔网络”的情况。使用此选项的剪贴板文件与 16.6 之前的版本不兼容。如果使用子图复制和粘贴通孔结构，则应使用。

clip\_filebrowser  
If set, the clpcopy command uses the file browser insteadof the library path browser. This restores 13.6 behavior.  
如果设置，clpcopy 命令将使用文件浏览器而不是库路径浏览器。这将恢复 13.6 行为。

Interfaces
----------

### DXF

dxf\_incremental  
Specifies to use incremental addition mode for dxf in.Default has dxf import replace the current design.  
指定对 dxf 输入使用增量添加模式。默认有 dxf 导入替换当前设计。

dxf\_version  
Specifies DXF output version for command dxf out. Valuescan be 12 or 14.  
指定命令 dxf out 的 DXF 输出版本。值可以是 12 或 14。

### IDF

IDF (Mechanical Interface) Options

idf\_del\_mcadowned\_symbols\_import  
If set, all the MCAD-owned symbol withoutrefdes will be deleted before the new IDF file isimported.  
如果设置，则在导入新的 IDF 文件之前，将删除所有 MCAD 拥有的没有引用的符号。

idf\_ignore\_comp\_height  
If set, idf\_out will ignore the component definitionHEIGHT property and instead export the symbol definitionheight value.  
如果设置，idf\_out 将忽略组件定义高度属性，而是导出符号定义高度值。

idf\_ignore\_part\_number  
If set, idf\_out will ignore the component definitionPART\_NUMBERproperty and instead export the componentdefinition device type.  
如果设置，idf\_out 将忽略组件定义PART\_NUMBER 属性，而是导出组件定义设备类型。

idf\_layer\_delineate  
By default, idf export uses the slash character todelineate between our class and subclass names. Thisvariable allows you to substitute a new character if theslash character is illegal in your MCAD system.  
默认情况下，idf export 使用斜杠字符来分隔我们的类名和子类名。如果斜线字符在您的 MCAD 系统中是非法的，此变量允许您替换一个新字符。

idf\_mech\_refdes  
If set, idf\_out outputs refdes and part number formechanical parts. This appears to violate the IDF standardin that mechanical parts should output NOREFDES.  
如果设置，idf\_out 输出 refdes 和零件编号 formechanical 零件。这似乎违反了 IDF 标准，即机械部件应输出 NOREFDES。

idf\_nodelete  
If set, idf\_in will only import the .PLACEMENT and .NOTESsections of the IDF file.All other sections of the IDFfile will be ignored.  
如果设置，idf\_in 将仅导入 IDF 文件的 .PLACEMENT 和 .NOTES 部分。IDF 文件的所有其他部分将被忽略。

idf\_place\_bounds\_bottom  
A subclass of the Package Geometry class that isused to calculate the component outline for the IDFLibrary file.User should also specifyIDF\_PLACE\_BOUNDS\_TOP.  
Package Geometry 类的子类，用于计算 IDFLibrary 文件的组件轮廓。用户还应指定 IDF\_PLACE\_BOUNDS\_TOP。

idf\_place\_bounds\_top  
A subclass of the Package Geometry class that is usedto calculate the component outline for the IDF Libraryfile.User should also specify IDF\_PLACE\_BOUNDS\_BOTTOM.  
Package Geometry 类的子类，用于计算 IDF 库文件的组件轮廓。用户还应指定 IDF\_PLACE\_BOUNDS\_BOTTOM。

idf\_units\_naming  
By default, IDF creates padstacks and symbols using thehole diameter with 1 decimal place converted to MILS asthe naming scheme (). Example fora 1.10 mm hole a npin433.pad is created. This option,leaves it in IDF units, uses 2 decimal places of accuracyand uses a unit string ().Units can be MM or MIL. Example for a 1.10 mm hole anpin110mm.pad is created.  
默认情况下，IDF 使用将小数点后 1 位转换为 MILS 的孔直径作为命名方案 () 创建焊盘堆栈和符号。创建一个 1.10 毫米孔的示例 npin433.pad。此选项保留 IDF 单位，使用 2 个小数位精度并使用单位字符串 ()。单位可以是 MM 或 MIL。创建 1.10 毫米孔 anpin110mm.pad 的示例。

### IDX

IDX (Mechanical Interface) Options

auto\_set\_object\_ownership  
If set, the electrical ownership is added to theobject that does not already have ownership, and does notalready have an IDX\_ID on the first, and successiveexports of Allegro data to IDX.  
如果设置，电气所有权将添加到尚未拥有所有权的对象，并且在第一次将 Allegro 数据连续导出到 IDX 时还没有 IDX\_ID。

idx\_ignore\_comp\_height  
If set, idx\_out will ignore the component definitionHEIGHT property and instead export the symbol definitionheight value.  
如果设置，idx\_out 将忽略组件定义高度属性，而是导出符号定义高度值。

idx\_ignore\_part\_number  
If set, idx\_out will ignore the component definitionPART\_NUMBERproperty and instead export the componentdefinition device type.  
如果设置，idx\_out 将忽略组件定义PART\_NUMBER 属性，而是导出组件定义设备类型。

idx\_place\_bounds\_bottom  
A subclass of the Package Geometry class that isused to calculate the component outline.User should alsospecify IDX\_PLACE\_BOUNDS\_TOP.  
用于计算组件轮廓的 Package Geometry 类的子类。用户还应指定 IDX\_PLACE\_BOUNDS\_TOP。

idx\_place\_bounds\_top  
A subclass of the Package Geometry class that is usedto calculate the component outline.User should alsospecify IDX\_PLACE\_BOUNDS\_BOTTOM.  
用于计算组件轮廓的 Package Geometry 类的子类。用户还应指定 IDX\_PLACE\_BOUNDS\_BOTTOM。

idx\_set\_default\_version\_1.2  
By default, IDX version is v2.0. This variableallows you to create an IDX file in old format v1.2.  
默认情况下，IDX 版本为 v2.0。此变量允许您以旧格式 v1.2 创建 IDX 文件。

### IPC2581

IPC2581 Export Options

ipc2581\_filter\_part\_number  
If set, ipc2581\_out will not output part numberfrom BOM items.  
如果设置，ipc2581\_out 将不会从 BOM 项目输出零件编号。

ipc2581\_ignore\_surface\_layer  
If set, ipc2581\_out will not export surfacelayer in the stackup section.  
如果设置，ipc2581\_out 将不会在叠层部分导出表面层。

ipc\_add\_no\_place\_bound\_symbols  
If set, ipc2581\_out will export the symbolswithout PLACE\_BOUND outline.  
如果设置，ipc2581\_out 将导出没有 PLACE\_BOUND 轮廓的符号。

ipc\_ignore\_pads\_smaller\_than\_drill  
If set, ipc2581\_out will ignore the padequal to or smaller than the drill.  
如果设置，ipc2581\_out 将忽略等于或小于钻头的焊盘。

ipc\_ignore\_some\_layer\_specs  
If set, ipc2581\_out will not export theConductivity for the dielectric layers, and the DielectricConstant and Loss Tangent for the conductor layers.  
如果设置，ipc2581\_out 将不会导出电介质层的电导率，以及导体层的 DielectricConstant 和 Loss Tangent。

### PDF

PDF Export Options

pdf\_apply\_film\_undefined\_line\_width  
If set, the value of the film parameter"undefined line width" will apply to all the objects withzero width.  
如果设置，则胶片参数“未定义线宽”的值将应用于所有宽度为零的对象。

pdf\_bookmark\_view\_dest\_no\_fit  
by default, the destination view isautomatically zoom out to fit the page when a new page isselected using the bookmark tabs. If set, the user needsto adjust to get a proper page view when a new page isopen.  
默认情况下，当使用书签选项卡选择新页面时，目标视图会自动缩小以适合页面。如果设置，用户需要调整以在新页面打开时获得正确的页面视图。

pdf\_filled\_shape\_transparency  
This variable allows you to change thedefault transparency value for the filled shape.  
此变量允许您更改填充形状的默认透明度值。

pdf\_minimum\_print\_line\_width\_scale  
If set, the base minimum printed linewidth of 1.0 mil or 0.0254 mm will be scaled, and thenapply the resultant line width to all the objects withsmaller line width.  
如果设置，将缩放 1.0 mil 或 0.0254 mm 的基本最小印刷线宽，然后将所得线宽应用于所有具有较小线宽的对象。

pdf\_netname\_height\_on\_cline  
By default, the height of net name is 80% ofthe cline's width. This variable allows you to change thispercentage value (0.0 - 1.0).  
默认情况下，网名的高度是线宽的 80%。此变量允许您更改此百分比值 (0.0 - 1.0)。

pdf\_netname\_height\_on\_pin  
By default, the height of net name is 20% of thepin's small size. This variable allows you to change thispercentage value (0.0 - 1.0).  
默认情况下，网名的高度为图钉小尺寸的 20%。此变量允许您更改此百分比值 (0.0 - 1.0)。

pdf\_netname\_on\_cline  
By default, the net names are not displayed on clines.This variable allows you to turn it on.  
默认情况下，网络名称不显示在 clines 上。此变量允许您将其打开。

pdf\_netname\_on\_pin  
By default, the net names are not displayed on pins.This variable allows you to turn it on.  
默认情况下，网络名称不显示在引脚上。此变量允许您将其打开。

pdf\_no\_total\_etch\_length\_on\_net  
By default, the total etch length will bedisplayed under Net Tree. This variable allows you to turnit off.  
默认情况下，总蚀刻长度将显示在 Net Tree 下。此变量允许您将其关闭。

pdf\_no\_white\_to\_black\_change  
By default, the white color geometries will bechanged to black to be seen in the PDF viewer. Thisvariable allows you to turn this change off.  
默认情况下，白色几何图形将更改为黑色以在 PDF 查看器中查看。此变量允许您关闭此更改。

### plctxt

place\_text\_filename  
Override default plctxt filename, default name isplace\_txt.txt. TIP  
覆盖默认 plctxt 文件名，默认名称是place\_txt.txt。提示

place\_text\_version2  
Uses version 2 plctxt file format by default. Version 2was introduced to support embedded component design in16.5. By default, designs with embedded components useversion 2 while all other designs use version 1 of theplctxt file format. Setting this variable causes alldesign types to use version 2.  
默认使用版本 2 plctxt 文件格式。 16.5 中引入了版本 2 以支持嵌入式组件设计。默认情况下，带有嵌入式组件的设计使用版本 2，而所有其他设计使用 plctxt 文件格式的版本 1。设置此变量会导致所有设计类型使用版本 2。

### STEP

STEP Package Mapping

copper\_no\_z\_offset  
By default, the external copper will be exported aboveboard level for display. If set, the external copper willbe exported at the board level.  
默认情况下，外部铜将导出到板面上方进行显示。如果设置，外部铜将在板级输出。

step\_board\_level\_package\_height  
By default, the package definiton isexported only once and then referenced by the componentswhich results in smaller and more efficient STEP file. Ifset, the design level package outlines and heights areexported for all the components, the STEP file will bemuch larger.  
默认情况下，包定义只导出一次，然后由组件引用，从而生成更小、更高效的 STEP 文件。如果设置，导出所有组件的设计级别包轮廓和高度，STEP 文件会更大。

step\_display\_resistors\_capacitors  
By default, the capacitors and resistorswill be ignored for performance improvement during mappingmechanical assembly (enclosure, cage, bracket … etc).This variable allows you to turn them on if needed.  
默认情况下，在映射机械装配（外壳、笼子、支架等）期间，电容器和电阻器将被忽略以提高性能。此变量允许您在需要时打开它们。

step\_export\_comp\_part\_number  
If set, the component part number will beexported as part of STEP object ID.  
如果设置，组件零件编号将作为 STEP 对象 ID 的一部分导出。

step\_ignore\_all\_electrical\_packages  
If set, all electrical packages will beignored for performance improvement during mappingmechanical assembly (enclosure, cage, bracket … etc).  
如果设置，则在映射机械装配（外壳、笼子、支架等）期间将忽略所有电气封装以提高性能。

step\_place\_bounds\_bottom  
A subclass of the Package Geometry class that isused to calculate the component outline.User should alsospecify STEP\_PLACE\_BOUNDS\_TOP.  
用于计算组件轮廓的 Package Geometry 类的子类。用户还应指定 STEP\_PLACE\_BOUNDS\_TOP。

step\_place\_bounds\_top  
A subclass of the Package Geometry class that is usedto calculate the component outline.User should alsospecify STEP\_PLACE\_BOUNDS\_BOTTOM.  
用于计算组件轮廓的 Package Geometry 类的子类。用户还应指定 STEP\_PLACE\_BOUNDS\_BOTTOM。

logic
-----

Settings to control logic import/export and editing

dcnets\_delete\_norat  
When set, the identify DC net command, deletes NO\_RATproperty from those nets getting the Power and GroundSchedule. Meant to be a migration aid for legacy boardsconverting from NO\_RAT to this type of scheduling.  
设置后，identify DC net 命令会从那些获得 Power 和 GroundSchedule 的网络中删除 NO\_RATproperty。旨在成为从 NO\_RAT 转换为此类调度的旧板的迁移辅助工具。

edit\_parts\_expand\_lists  
When set, the edit parts command will displayreference designator lists in an expanded format. Itemsare grouped together by default. For example, U1, U2, andU3 will be listed as U1-3. This format does not supportdashes in designator names. If your design uses dashes,enable this variable to have full capabilities in the editparts command.  
设置后，编辑零件命令将以扩展格式显示参考指示符列表。默认情况下，项目分组在一起。例如，U1、U2 和 U3 将列为 U1-3。此格式不支持指示符名称中的破折号。如果您的设计使用破折号，请在 editparts 命令中启用此变量以具有全部功能。

logic\_edit\_enabled  
When set, enables the "net logic" command. By default,this feature is disabled to prevent inadvertent changes tothe logic.  
设置后，启用“网络逻辑”命令。默认情况下，此功能被禁用以防止无意中更改逻辑。

netrev\_forbid\_precision change  
If true, netrev will NOT override board'sprecision during F2B flow.  
如果为 true，netrev 将不会在 F2B 流程中覆盖板的精度。

netrev\_missing\_footprints  
Normally netrev reports missing footprints as awarning and updates the design. By setting this variable,any footprint warnings are reported as an error and logicimport will fail. Also can by driven via the '-e' commandline switch to netrev batch.  
通常，netrev 将丢失的封装报告为警告并更新设计。通过设置此变量，任何封装警告都会报告为错误，并且 logicimport 将失败。也可以通过'-e'命令行开关驱动到netrev批处理。

netrev\_no\_footprint\_warnings  
Normally netrev reports missing footprints aswarnings. This suppresses these warnings. This variableoverrides the netrev\_missing\_footprints environmentvariable.  
通常，netrev 会将丢失的脚印报告为警告。这会抑制这些警告。此变量覆盖 netrev\_missing\_footprints 环境变量。

netrev\_renamenetswshapes  
This is an "Unsupported Prototypes" option, itwill be the default in 17.0. If set, netrev deduces when anet is being renamed or merged into a another net andreassigns any shapes on that net to the merged/rename net.Most traces or vias connected to those shapes are alsoassigned to the new net. Since both APD and CDNSIP allowzero pin nets, this option is ignored when updating theseAllegro design types.  
这是一个“不支持的原型”选项，它将是 17.0 中的默认值。如果设置，netrev 会推断何时将 anet 重命名或合并到另一个网络中，并将该网络上的任何形状重新分配给合并/重命名网络。大多数连接到这些形状的走线或过孔也分配给新网络。由于 APD 和 CDNSIP 都允许使用零引脚网络，因此在更新这些 Allegro 设计类型时会忽略此选项。

pcb\_baf\_pin\_number  
When set, backannotation uses the pin number- not thepin name - for the "was" part of the PIN statement forpreassigned and not yet assigned functions.  
设置后，反注释使用引脚编号 - 而不是引脚名称 - 用于预分配和尚未分配功能的 PIN 语句的“was”部分。

schematic\_editor  
Use this variable to preset brand of a new drawing.Possible values are:"capture" for capture designs and"hdl-concept" for Design Entry HDL (Concept) baseddesigns.  
使用此变量来预设新图纸的品牌。可能的值是：“capture”用于捕获设计，“hdl-concept”用于基于 HDL（概念）的设计。

manufacture
-----------

### artwork

Allegro artwork and artwork user interface options

arc\_oldvectorize  
If set uses the old artwork vectorizing algorithm. Alsoenables access to 'art\_circvects' environment variable.New arc to vector algorithm automatically accommodates thewide range of units and accuracy now present in moderndesigns. Old vectorizing algorithm will be removed in afuture release.  
如果设置使用旧的艺术品矢量化算法。还可以访问“art\_circvects”环境变量。新的弧转矢量算法自动适应现代设计中现在存在的各种单位和精度。旧的矢量化算法将在未来版本中删除。

art\_arc\_centercheck  
By default, GERBER 6X plots an arc even if its arccenter is outside the photoplot outline. Certain CAMstations may have trouble with this model. This variablechanges this condition to an error.  
默认情况下，GERBER 6X 会绘制一个圆弧，即使其圆弧中心在照片绘图轮廓之外。某些 CAMstations 可能会遇到此模型的问题。此变量将此条件更改为错误。

art\_circvects  
Its value represents number of segments to vectorize acircle. If set, it overrides default artwork arcvectorization.By default, vectorization is based upon acombination of design units, accuracy and arc radius. IfVector artwork (Gerber 6x or 4x) this is used for allarcs. Raster artwork vectorization only applies toshape/void edges. If set, user supplied value is used ifit would result in more vectorization then the calculatedvalue. Starting in 15.7, this setting is not used unlessarc\_oldvectorize is also set.  
它的值表示要对圆进行矢量化的段数。如果设置，它将覆盖默认图稿弧向量化。默认情况下，矢量化基于设计单位、精度和弧半径的组合。 IfVector 图稿（Gerber 6x 或 4x）这用于 allarcs。光栅图稿矢量化仅适用于形状/空隙边缘。如果设置，则使用用户提供的值，如果它会导致比计算值更多的矢量化。从 15.7 开始，除非还设置了arc\_oldvectorize，否则不会使用此设置。

art\_stripdirectoryname  
Normally artwork in the comment section of the filmfile includes both the filename and directory name. Thisoption strips the directory name leaving just the designname.  
通常，电影文件注释部分中的插图包括文件名和目录名。此选项去除目录名称，仅保留设计名称。

artwork\_arc\_round\_error  
Treats artwork arc to convert to line accuracywarnings as errors. By default, these are warnings.  
将要转换为线精度警告的图稿弧视为错误。默认情况下，这些是警告。

artwork\_no\_unit\_warn  
Disable popup warnings about artwork output roundingin the artwork user interface. Warnings are still issuedto photoplot.log.  
在图稿用户界面中禁用有关图稿输出舍入的弹出警告。警告仍然发布到 photoplot.log。

artwork\_nophotoplot\_warning  
In artwork, a warning message is issued if thephotoplot window exceeds film size. This option turns thiswarning into an information message and it will not becounted as a warning in the artwork summary.  
在艺术作品中，如果照片绘图窗口超过胶片尺寸，则会发出警告消息。此选项将此警告转换为信息消息，并且不会在图稿摘要中算作警告。

artwork\_undef\_line\_width  
In artwork dialog, uses the value to seed the"Undefined line width" parameter. The default is 0. Thenumber can be unitless which maps to the design's units.If the value contains units will translate it to currentdesign units (example 5 mils).  
在图稿对话框中，使用该值作为“未定义线宽”参数的种子。默认值为 0。数字可以是无单位的，映射到设计的单位。如果值包含单位，则将其转换为当前设计单位（例如 5 密耳）。

artwork\_undefined\_width\_error  
In artwork, makes 0 line widths when theundefined line width setting is also 0 an error. This canbe corrected by setting the "Undefined line width" to avalue for each film in the artwork dialog. By default,these are warnings.  
在图稿中，当未定义的线宽设置也为 0 时，将 0 线宽设为错误。这可以通过将“未定义的线宽”设置为图稿对话框中每个胶片的值来纠正。默认情况下，这些是警告。

film\_nosort  
Sets film param artwork display back to pre-14.2 unsortedorder. Default, is to sort them alphabetically. When thisvariable is set, order may appear in stackup order if youcreate the stackup before opening the film param dialog.  
将电影参数艺术品显示设置回 14.2 之前的未排序顺序。默认是按字母顺序对它们进行排序。设置此变量后，如果您在打开胶片参数对话框之前创建堆叠，则顺序可能会按堆叠顺序出现。

loadgerber\_flash\_size  
Size of flash triangle to be used when loading Gerber4x or 6x and the target option is selected. Default valueis C-point size (80 mils). Value can be a number; unitdefaults to current design units. Value can also include astandard length unit (e.g. MIL, MICRON, etc.).  
加载 Gerber4x 或 6x 并选择目标选项时要使用的 flash 三角形的大小。默认值为 C 点大小（80 密耳）。值可以是一个数字；单位默认为当前设计单位。值还可以包括标准长度单位（例如 MIL、MICRON 等）。

### draft

draft\_retain\_class\_subclass  
Instructs the drafting commands to maintaincurrent active layer.Default behavior is to switch toBoard Geometry/Dimension layer when starting thesecommands.  
指示绘图命令保持当前活动层。默认行为是在启动这些命令时切换到板几何/尺寸层。

### drilling

nclegend\_file  
Override the default filename convention for NC DrillLegend. By default, NC Drill Legend uses a name ofdefault- where units is the current board units.The override name should contain only the filename not aPATH component.  
覆盖 NC DrillLegend 的默认文件名约定。默认情况下，NC Drill Legend 使用的名称为 default-，其中单位是当前板的单位。覆盖名称应仅包含文件名而不是路径组件。

nclegend\_legacy\_row\_height  
If set, NC legend table will keep the legacy rowheights.  
如果设置，NC 图例表将保留旧行高。

nctape\_cam350  
CAM350 software has a bug where it does not correctlyprocess the ";DESIGN" comment line in Allegro drill files.Setting this variable suppresses this line in Allegro's.drl files.  
CAM350 软件有一个错误，它不能正确处理 Allegro 钻孔文件中的“;DESIGN”注释行。设置此变量会抑制 Allegro 的.drl 文件中的该行。

### IPC\_netlist

ipc356\_027record\_netname  
By default, ipc356 (rev A) continuation records(027) do not require the netname since the previous recordhas the name. We have found that some manufacturers expectthe netname. This option enables the netname with the 027record.  
默认情况下，ipc356 (rev A) continuation records(027) 不需要网络名，因为前一个记录具有名称。我们发现一些制造商期望网络名称。此选项启用具有 027 记录的网络名。

ipc356\_nomechpin\_warnings  
By default, ipc356\_out generates warnings ifmechanical pins are defined without drill holes. Thissuppresses that warning.  
默认情况下，如果机械销定义为没有钻孔，ipc356\_out 会生成警告。这会抑制该警告。

ipc356\_truncate\_large  
By default, ipc356\_out generates errors if numbersexceed the magnitude required by the specification. Thisoption truncates these numbers and issues a warning. THISOPTION SHOULD NOT BE USED FOR PRODUCTION OUTPUT. It isintended for debug use of problematic coordinates andsizes.  
默认情况下，如果数字超过规范要求的大小，ipc356\_out 会产生错误。此选项会截断这些数字并发出警告。此选项不应用于生产输出。它旨在调试有问题的坐标和大小的使用。

ipc356\_unique\_netname  
By default, ipc356\_out uses net name "N/C" for dummynet pins with no connections. With variable set, a uniquenet name will be generated for each dummy net pin usingthe same methodology as dummy net pins with connections.  
默认情况下，ipc356\_out 对没有连接的虚拟网络引脚使用网络名称“N/C”。设置变量后，将使用与带连接的虚拟网络引脚相同的方法为每个虚拟网络引脚生成唯一的网络名称。

### plot

Print and plot settings

lp\_abs\_origin  
By default, load plot uses the lower left corner of theIPF file's bounding box as its placement origin. Thisoption causes IPF import to use's the origin containedwithin the IPF file. This mode help alignment if you areusing the design origin for placement.  
默认情况下，载荷图使用 IPF 文件边界框的左下角作为其放置原点。此选项会导致 IPF 导入使用包含在 IPF 文件中的源。如果您使用设计原点进行放置，则此模式有助于对齐。

noplotmargins  
If set, disables plot margins on the printer. By default,printers provide a margin around a plot (typically 1inch). This effects plotting on Windows only.  
如果设置，则禁用打印机上的图边距。默认情况下，打印机在绘图周围提供边距（通常为 1 英寸）。这仅影响在 Windows 上绘图。

plot\_shape\_bw\_outline  
If set, shapes are unfilled when plotting in blackand white mode in order to make items behind the shapesvisible.  
如果设置，在黑白模式下绘图时形状将不填充，以使形状后面的项目可见。

plot\_shape\_spacing  
If set, the lines created for shape fill in a plot arespaced at the value described with this variable. A highvalue draws shape fill with gaps on the paper, but improveplotter speed.  
如果设置，则为绘图中的形状填充创建的线的间距与此变量描述的值相同。高值绘制形状填充纸张上的间隙，但提高绘图仪速度。

plot\_vectext\_width  
If set, in conjunction with plot\_vectorize\_text, itspecifies the default 'width' to appear with 'Vectorizetext' under 'IPF setup' on the Plot Setup form. The widthof the vectorized text is drawn at the value specified.Note that this will be overridden by a remembered .inifile plot\_setup setting.  
如果设置，与 plot\_vectorize\_text 一起，它指定默认的“宽度”与“Vectorizetext”一起出现在“绘图设置”表单的“IPF 设置”下。矢量化文本的宽度以指定的值绘制。请注意，这将被记住的 .inifile plot\_setup 设置覆盖。

plot\_vectorize\_text  
If set, 'Vectorize text' under 'IPF setup' on the PlotSetup form is enabled by default. When enabled, the .pltfiles generated by Allegro vectorizes text data into linesegments. Note that this will be overridden by aremembered .ini file plot\_setup setting.  
如果设置，则默认启用 PlotSetup 表单上“IPF 设置”下的“矢量化文本”。启用后，Allegro 生成的 .pltfiles 会将文本数据矢量化为线段。请注意，这将被 aremembered .ini 文件 plot\_setup 设置覆盖。

### print

print\_nt\_extension  
Windows only  
仅限 Windows

### reports

Allegro report options

extract\_fullaccuracy\_arc  
This causes the extracta program to output fullaccuracy for an arc's center and radius. The default is toround to the design's accuracy. This may improve the arc'sresolution if you use arcs with a diameter approaching thedesign's width or height. This variable must be placed inthe Allegro environment file. Full accuracy arcs are thedefault in extracta starting in release 17.2.  
这会导致提取程序输出圆弧中心和半径的完全精度。默认值是围绕设计的准确性。如果您使用直径接近设计宽度或高度的圆弧，这可能会提高圆弧的分辨率。此变量必须放置在 Allegro 环境文件中。从 17.2 版开始，全精度弧是 extracta 中的默认值。

report\_antennavia  
Controls the vias that are suppressed in the danglingreport under the sub-section Antenna vias. If voltage isset then vias on nets with the VOLTAGE property aresuppressed. If testvia is set then testvias aresuppressed. If thru is set then through hole vias aresuppressed.  
控制在天线过孔子部分下的 danglingreport 中被抑制的过孔。如果设置了电压，则具有 VOLTAGE 属性的网络上的过孔将被抑制。如果设置了 testvia，则禁止 testvia。如果设置了 thru，则通孔过孔将被抑制。

report\_noantennavia  
Suppresses the antenna via section of Dangling Report.  
通过 Dangling Report 部分抑制天线。

report\_nopath  
Strips the directory portion of the design name in certainreports. Default is to output the design name plusdirectory name.  
去除某些报告中设计名称的目录部分。默认是输出设计名加目录名。

testprep\_rpt\_netnames  
In testprep report print net names on each line.Default is to print net on first line and suppresssubsequent lines where net name is the same.  
在 testprep 报告中，每行打印网络名称。默认是在第一行打印网络并抑制网络名称相同的后续行。

### silkscreen

autosilk\_disregard\_solder\_mask  
Autosilk does not clear vias when thesoldermask is not defined. Setting this variable causesautosilk to clear vias which have no soldermask padsdefined.  
当未定义阻焊层时，Autosilk 不会清除过孔。设置此变量会导致 autosilk 清除未定义阻焊垫的通孔。

fst\_ref\_des  
If requiring autorenameto start at a specific ref des number. Example  
如果需要自动重命名以从特定的 ref des number 开始。例子

misc
----

allegro\_sort\_separators  
When using the jedec or natural string sortingstyles, set this option to have the tool compare stringsbetween separator characters against each other. Forexample, comparing ABC-DEF to AB-CDEF would compare ABC toAB, then DEF to CDEF with this option enabled.  
使用 jedec 或自然字符串排序样式时，设置此选项可使工具将分隔符之间的字符串相互比较。例如，在启用此选项的情况下，将 ABC-DEF 与 AB-CDEF 进行比较将先将 ABC 与 AB 进行比较，然后再将 DEF 与 CDEF 进行比较。

allegro\_sort\_style  
Controls how strings are sorted in report outputs and invarious other areas of the tool. Default will sort using afast but simple routine. Natural will sort strings to putthe number 2 before 10. Jedec goes one step beyond innatural, and sorts shorter strings before longer, like Bbefore AA. Restart the tool for this option to take fulleffect.  
控制字符串在报告输出和工具的各种其他区域中的排序方式。默认将使用快速但简单的例程进行排序。 Natural 会将字符串排序为将数字 2 放在 10 之前。Jedec 比 innatural 更进一步，将较短的字符串排序在较长的字符串之前，例如 Bbefore AA。重新启动此选项的工具以使其完全生效。

obsolete
--------

allegro\_old\_report  
By default, we use html based reports.When set, thisuses pre-15.2, text based report files. This variable onlyapplies to the batch report interface. If you wish toaccess to old report user interface form then use the"old\_reports" command. Old reports will be removed in afuture release.  
默认情况下，我们使用基于 html 的报告。设置后，这将使用 15.2 之前的基于文本的报告文件。该变量只适用于批量报表界面。如果您希望访问旧报告用户界面表单，请使用“old\_reports”命令。旧报告将在未来版本中删除。

cns\_noviasort  
Restores 13.6 no sorting behavior for the current via listin constraint dialog Physical Rule Set Values.  
为当前通过列表约束对话框物理规则集值恢复 13.6 无排序行为。

control\_auto\_raise  
Sets the default tab in control panel. If a command hadchanged the tab, upon termination of a command, systemreverts control panel to the default tab. If not set, tabis not changed at end of command.  
设置控制面板中的默认选项卡。如果命令更改了选项卡，则在命令终止时，系统会将控制面板恢复到默认选项卡。如果未设置，则tabis 在命令结束时不会更改。

drc\_diff\_pair\_overide  
Used only for diffpair 15.0 upreving for legacydesigns. In pre-15.0 releases, a 0 value suppresses lineto line drc's between 2 diff pair nets if the line to linespacing for the etch layer is greater than the diff pairprimary spacing. In cases where the diff pair lines arerouted diagonally, the actual spacing is fractionallyhigher or lower than the required spacing. Legal non-zerovalues are 100 (1 unit of accuracy) or 200 (2 units) fortolerancing.  
仅用于遗留设计的 diffpair 15.0 upreving。在 15.0 之前的版本中，如果蚀刻层的线对线间距大于 diff 对主要间距，则 0 值会抑制 2 个 diff 对网络之间的线对线 drc。在差分对线对角布线的情况下，实际间距比所需间距略高或略低。合法的非零值是 100（1 个精度单位）或 200（2 个单位）公差。

drc\_diff\_pair\_primary\_separation\_tolerance  
Used only for diffpair 15.0upreving for legacy designs. In pre-14.2 releases, setdrc\_diff\_pair\_primary\_separation\_tolerance = :.Both and are primary separation values withoptional units ("10 MIL:20 MIL"). The max value is addedto the diff pair primary separation value when checking anodd angle line. The min value is subtracted from theprimary separation value when doing a line to line spacingcheck between diff pair lines.  
仅用于传统设计的 diffpair 15.0upreving。在 14.2 之前的版本中，setdrc\_diff\_pair\_primary\_separation\_tolerance = :。 和 都是带有可选单位的主要分离值（“10 MIL:20 MIL”）。当检查正角线时，最大值被添加到差异对主分离值中。在差异对线之间进行线到线间距检查时，从主要分离值中减去最小值。

drc\_fillet\_samenet  
Enables more conservative same net checking with respectto Fillets. With this variable set more DRCs may bereported. The default is to not consider a fillet touchinga pad to be a DRC even if an adjacent same net cline isbelow the line to line spacing value. This variable onlyapplies to the pre-16.2 cline based fillets.  
启用关于圆角的更保守的相同网络检查。使用此变量设置可以报告更多的 DRC。默认情况下，即使相邻的同一网线低于线间距值，也不会将接触焊盘的圆角视为 DRC。此变量仅适用于 16.2 之前的基于斜面的圆角。

xsection\_modern  
In pre-16.0 Allegro PCB, uses the SI cross-sectiondialog.You should be cautioned that it can be slow onlarge layer count boards and it disables the old xsectionicon. It is only supported in Expert and Performance. In16.0 this is the default, the old dialog is no longersupported.  
在 16.0 之前的 Allegro PCB 中，使用 SI 横截面对话框。您应该注意它在大层数板上可能会很慢，并且会禁用旧的横截面图标。它仅在 Expert 和 Performance 中受支持。在 16.0 中这是默认设置，不再支持旧对话框。

os
--

Provides overrides and options to Allegro core facilities typically where there is Operating System differences.

cdn\_mail\_unix  
For UNIX, specifies an alternative interface to use foremail. See/share/pcb/examples/configure/cdn\_mail\_unixdirectory for instructions on how to integrate analternative email program to Allegro mail. This shouldonly be used if you cannot use the default UNIX mailprogram. This override is not supported on Windows.  
对于 UNIX，指定使用前邮件的替代接口。请参阅/share/pcb/examples/configure/cdn\_mail\_unixdirectory 以获取有关如何将替代电子邮件程序集成到 Allegro 邮件的说明。仅当您不能使用默认的 UNIX 邮件程序时才应使用此选项。 Windows 不支持此覆盖。

ntpserver  
Specifies the Network Time Protocol (NTP) server. Thedefault server is 0.pool.ntp.org. NTP is currently anoption used for design locking. To use a NTP server youmust be connected to the Internet and any firewall must beconfigured to allow port 123 to pass.  
指定网络时间协议 (NTP) 服务器。默认服务器是 0.pool.ntp.org。 NTP 目前是用于设计锁定的一个选项。要使用 NTP 服务器，您必须连接到 Internet，并且必须配置任何防火墙以允许端口 123 通过。

paths
-----

### config

Configuration Search Paths Settings

aptpath  
Search path for aperture flash files (.bsm) when negativeplanes are present. This is obsolete if new style flashdesigns are used.  
当存在负平面时，搜索光圈闪存文件 (.bsm) 的路径。如果使用新样式的 flashdesigns，这已经过时了。

artpath  
Search path for artwork aperture files (.txt).  
图稿光圈文件 (.txt) 的搜索路径。

clippath  
Search path for sub-drawing files (.clp).  
子图文件 (.clp) 的搜索路径。

dclpath  
Search path for decoupling capacitor list files (.dcf).  
去耦电容器列表文件 (.dcf) 的搜索路径。

dfaauditpath  
Search path for DFA Audit (.arl .rle).  
DFA 审计 (.arl .rle) 的搜索路径。

dfacnspath  
Search path for dfa constraints spreadsheet files (dfa).  
dfa 约束电子表格文件 (dfa) 的搜索路径。

idxpath  
Search path for IDX files(.idx).  
IDX 文件 (.idx) 的搜索路径。

ipc2581attrpath  
Search path for IPC2581 property configuration file(.atr).  
IPC2581 属性配置文件 (.atr) 的搜索路径。

ldfpath  
Search path for Library definition file (.ldf).  
库定义文件 (.ldf) 的搜索路径。

lstpath  
Search path to locate list files (.lst).  
查找列表文件 (.lst) 的搜索路径。

materialpath  
Search path to locate materials.dat (Allegro) ormcmmat.dat (APD) (.dat).  
用于定位 materials.dat (Allegro) 或 mcmmat.dat (APD) (.dat) 的搜索路径。

ncdpath  
Search path for NC Drill files (.txt).  
NC 钻孔文件 (.txt) 的搜索路径。

pcell\_lib\_path  
Search path for pcell component implementation (.il .ile).  
pcell 组件实现的搜索路径 (.il .ile)。

prfeditpath  
Search paths for user preferences files.  
用户首选项文件的搜索路径。

scriptpath  
Search path for scripts.  
脚本的搜索路径。

textpath  
Search path for extracta command files (.txt).  
提取命令文件 (.txt) 的搜索路径。

tilepath  
Search path for reusable die pin tiles (.til).  
可重复使用的芯片销块 (.til) 的搜索路径。

viewpath  
Search path for visibility schema files (.color).  
可见性架构文件 (.color) 的搜索路径。

wizard\_template\_path  
Search path for Allegro template databases. Used bythe Template button in New dialogs. In addition, iftemplate files are named new\_default. (ex.new\_default.brd) uses this design as the starting templateif the user did not explicitly specify a templatedatabase.  
Allegro 模板数据库的搜索路径。由新建对话框中的模板按钮使用。此外，如果模板文件被命名为 new\_default. (ex.new\_default.brd)，如果用户没有明确指定模板数据库，则使用此设计作为起始模板。

xtalk\_table\_path  
Search path for Cross talk tables (.xtb).  
串扰表 (.xtb) 的搜索路径。

### editor

UI Search Paths Settings

formpath  
Search paths for forms.  
表单的搜索路径。

menupath  
Search paths for menus.  
菜单的搜索路径。

### library

Library Search Path Settings (CPM enabled)

devpath  
Search path for library devices (.txt).  
库设备的搜索路径 (.txt)。

interfacepath  
Search path for Interface files (.idf).  
接口文件 (.idf) 的搜索路径。

miscpath  
Search path for miscellaneous file types. Supported typesare dxf/idx conversion (.cnv).  
各种文件类型的搜索路径。支持的类型是 dxf/idx 转换 (.cnv)。

modulepath  
Search path for design reuse modules (.mdd).  
设计重用模块 (.mdd) 的搜索路径。

padpath  
Search path for library padstacks (.pad).  
库padstacks (.pad) 的搜索路径。

parampath  
Search path for parameter files (.prm). These allow reuseof physical design data option settings like text,visibility and grid settings.  
参数文件 (.prm) 的搜索路径。这些允许重复使用物理设计数据选项设置，如文本、可见性和网格设置。

psmpath  
Search path for library symbols (.psm .osm .bsm .ssm.fsm).  
库符号的搜索路径（.psm .osm .bsm .ssm.fsm）。

steppath  
Search path for STEP files(.stp .step).  
STEP 文件的搜索路径（.stp .step）。

techpath  
Search path for technology files (.tech).  
技术文件 (.tech) 的搜索路径。

topology\_template\_path  
Search path for topology template files (.top).  
拓扑模板文件 (.top) 的搜索路径。

### signoise

signal\_install\_dir  
Path of directory that contains standard signoise modellibraries.  
包含标准 signoise 模型库的目录路径。

signal\_optlib\_dir  
Paths of directories that contain optional signoise modellibraries.  
包含可选 signoise 模型库的目录路径。

signoisepath  
Miscellaneous Signoise file locations (.dat .wave .mod.ctl).  
其他 Signoise 文件位置 (.dat .wave .mod.ctl)。

sigrity\_eda\_dir  
Path of directory that points to the Sigrity installation.  
指向 Sigrity 安装的目录路径。

placement
---------

### design\_partition

Design Partition Settings

allegro\_email\_address  
Design Partitioning will assign this value to theMaster Designer user field or Active Partition user field. This variable should be used at sites where the user'slogin name is not the same as the user's email address. This variable should only be assigned in the user's envfile, not in a site-wide env file.  
Design Partitioning 会将此值分配给 Master Designer 用户字段或 Active Partition 用户字段。此变量应用于用户登录名与用户电子邮件地址不同的站点。这个变量应该只在用户的 envfile 中分配，而不是在站点范围的 env 文件中。

partition\_suppress\_email  
When enabled, suppresses automatic email messagesassociated with Design Partition actions.The user maytemporarily re-enable email on the Workflow Manager.  
启用后，禁止与设计分区操作关联的自动电子邮件消息。用户可以在工作流管理器上临时重新启用电子邮件。

### DFA

DRC Options

dfa\_pause\_level  
Sets the pause level in manual placement command. If DFADRC check is enabled, when a component reaches its minimalDFA spacing of another component, it pauses briefly so itcan be placed as close as possible to the other componentwithout dfa drc violation. Setting level to 0 disablesthis feature. A 3 gives the longest pause. Default levelis 1.  
在手动放置命令中设置暂停级别。如果启用了 DFADRC 检查，当一个组件达到另一个组件的最小 DFA 间距时，它会短暂暂停，以便尽可能靠近另一个组件放置，而不会违反 dfa drc。将级别设置为 0 将禁用此功能。 3 给出最长的停顿。默认级别为 1。

display\_nodfa\_drc\_marks  
If set, DRC markers for DFA violations do notdisplay dynamically during interactive placement. Onlydynamic spacing circles are displayed. Default is todisplay both DRC markers and spacing circles.  
如果设置，则 DFA 违规的 DRC 标记不会在交互式放置期间动态显示。仅显示动态间距圆。默认是同时显示 DRC 标记和间隔圆。

### general

display\_norefdes  
By default, when a symbol is being moved we will show therefdes. This restores pre-15.2 behavior where the refdeswas never shown for symbols while in dynamic mode.  
默认情况下，当一个符号被移动时，我们将显示 refdes。这恢复了 15.2 之前的行为，其中在动态模式下从未为符号显示 refdes。

display\_refdes\_rats  
Display a rat line from refdes origin to component'spin 1 in order to show component to refdes relationship.  
显示从 refdes 原点到组件的自旋 1 的老鼠线，以显示组件与 refdes 的关系。

modules\_no\_5x\_support  
By default, when Allegro is started with a projectfile (.cpm), modules (.mdd) are located on disk first bysearching the sub-project physical design views under theactive project hierarchy and then by the MODULEPATHvariable. This variable tells the system to search formodule files just by the MODULEPATH (pre-16.5functionality).  
默认情况下，当 Allegro 使用项目文件 (.cpm) 启动时，模块 (.mdd) 首先通过搜索活动项目层次结构下的子项目物理设计视图，然后通过 MODULEPATH 变量在磁盘上定位。此变量告诉系统仅通过 MODULEPATH（16.5 之前的功能）搜索模块文件。

noswapripup  
This controls the swap function. During pin and functionswaps, etch is not ripped up. This does not apply tocomponent swaps. The default is rip up etch.  
这控制交换功能。在引脚和功能交换期间，蚀刻不会被撕掉。这不适用于组件交换。默认是撕裂蚀刻。

plc\_rep\_copy\_attr  
When set, the place replicate commands will propagate pinattributes from the seed circuit.  
设置后，放置复制命令将从种子电路传播 pin 属性。

preserve\_symbol\_textblocks  
Allegro 12.0 and beyond tries to match thesymbol text block size to a board text block size whenplacing components. If a match is not found a newtextblock is created until all text blocks are used. Ifpreserving the symbol block number is desired, use thisvariable when placing components.  
Allegro 12.0 及更高版本尝试在放置元件时将符号文本块大小与电路板文本块大小相匹配。如果未找到匹配项，则会创建一个新文本块，直到使用完所有文本块。如果需要保留符号块编号，请在放置组件时使用此变量。

swapcomp\_acrossmodules  
By default swap components will display aconfirmation message when you swap across modules. Settingthis variable will always allow inter-module swapping (pre15.0).  
默认情况下，当您跨模块交换时，交换组件将显示确认消息。设置此变量将始终允许模块间交换（pre15.0）。

route
-----

### connect

Etch Settings

acon\_dest\_sched\_pinonly  
By default, add connect picks up source anddestination points as per nearest endpoints which may notbe the ones specified in the user schedule. Setting thisvariable causes add connect to always choose the pin asthe destination for user scheduled rats.  
默认情况下，add connect 根据最近的端点（可能不是用户计划中指定的端点）选取源点和目标点。设置这个变量会导致 add connect 总是选择 pin 作为用户预定的老鼠的目的地。

acon\_diag  
By default, while in line lock 45 mode, add connect has apreference for first routing in an orthogonal directionbefore bending towards the cursor. If acon\_diag is set,and you are routing from the dangling end of anon-orthogonal segment, add connect will start in the samedirection as the existing segment before making the bend.  
默认情况下，在 line lock 45 模式下，add connect 优先选择在向光标弯曲之前在正交方向上的第一次布线。如果设置了 acon\_diag，并且您从非正交线段的悬垂端布线，则添加连接将在与现有线段相同的方向上开始，然后再进行弯曲。

acon\_diffpair\_pad\_connect:This option changes the behavior for thediffpair gathering that happens at target terminals whenthe cursor is near the target terminal of the controltrace. "center" is when the cursor is on the near-side ofthe terminal and midpoint gathering is performed. "old" iswhen the cursor is on the far-side of the terminal, thecontrol trace is connected using line lock segments andthe mate connects with automatic "Finish". "cursor ordefault" force midpoint gathering at the target terminalsregardless of cursor position.

acon\_disable\_nullnet\_route  
By default, "add connect" allows routing tostart in open space as well as on legal objects (e.g.pins, vias, clines, shapes, rats, or rat tees). If thisvariable is turned on, open space and pins not connectedto a net are excluded as start points.  
默认情况下，“添加连接”允许在开放空间以及合法对象（例如引脚、过孔、clines、形状、老鼠或老鼠三通）上开始布线。如果打开此变量，则将开放空间和未连接到网络的引脚作为起点排除在外。

acon\_no\_impedance\_width  
If this option is on, impedance rules will have noeffect on the trace width in add connect. The defaultbehavior is for add connect to use a trace width thatsatisfies the impedance requirement unless that width isless than the minimum allowable trace width.  
如果启用此选项，阻抗规则将不会影响添加连接中的走线宽度。默认行为是添加连接以使用满足阻抗要求的走线宽度，除非该宽度小于允许的最小走线宽度。

acon\_no\_width\_override\_retain  
The option controls retaining user specifiedwidth in command for next command execution. By defaultwhen variable is off and user has specified width value inoptions, the value is retained for next command execution.If variable is set the user defined width is not retainedfor next command execution and constraint width value isused instead.  
该选项控制在命令中保留用户指定的宽度以供下一个命令执行。默认情况下，当变量关闭并且用户在选项中指定了宽度值时，该值将保留以供下一个命令执行。如果设置了变量，则用户定义的宽度将不保留用于下一个命令执行，而是使用约束宽度值。

acon\_offnet\_snap  
By default, unless bubble is set to "Shove preferred", addconnect will snap the endpoint of the new cline to theminimum drc distance from another net's cline if thecursor is near the other cline and that cline is on theactive subclass. If the previous pick was also at the drcdistance from the other cline, the new cline will hug tothe other cline. You can totally disable this behavior bysetting acon\_offnet\_snap to "off". You can turn off thehug part and only snap the endpoint by setting thevariable to "endpoint".  
默认情况下，除非bubble设置为“Shove preferred”，如果光标靠近另一个cline并且该cline在活动子类上，addconnect会将新cline的端点捕捉到与另一个网络cline的最小drc距离。如果前一个选择也与另一个 cline 保持距离，则新 cline 将拥抱另一个 cline。您可以通过将 acon\_offnet\_snap 设置为“关闭”来完全禁用此行为。您可以通过将变量设置为“端点”来关闭拥抱部分并仅捕捉端点。

acon\_oldhlt  
If this option is set to "fromto", add connect willhighlight the source and destination elements instead ofthe entire net. This restores the behavior that existedbefore 14.2. Setting the value to "all" causes the entirenet to highlight for all types of nets (14.2 behavior). Bydefault, the entire net is highlighted unless the net isNO\_RAT or POWER\_AND\_GROUND.  
如果此选项设置为“fromto”，添加连接将突出显示源和目标元素而不是整个网络。这将恢复 14.2 之前存在的行为。将值设置为“all”会导致整个网络突出显示所有类型的网络（14.2 行为）。默认情况下，除非网络是 NO\_RAT 或 POWER\_AND\_GROUND，否则整个网络都会突出显示。

acon\_restore\_space\_mode  
By default, add connect sets the group route spacemode to "Current Space" at the start of the command. Ifthis option is set, add connect will restore the spacemode to the value that was active the last time that thecommand was run.  
默认情况下，add connect 在命令开始时将组路由空间模式设置为“当前空间”。如果设置了此选项，add connect 会将空间模式恢复为上次运行该命令时处于活动状态的值。

acon\_route\_on\_active\_subclass  
Set this to limit add connect so that italways begins a route on the active subclass.Otherwise, it may change the subclass to match an element that isfindable at the starting pick.  
设置此项以限制添加连接，以便它始终在活动子类上开始路由。否则，它可能会更改子类以匹配可在起始选择处找到的元素。

allegro\_dynam\_timing  
If unset or if set to "on", the dynamic timingfeedback is enabled. If set to "off",the feedback isdisabled.You can alias a function key to toggle thetiming display enable using the settoggle command asfollows  
如果未设置或设置为“on”，则启用动态时序反馈。如果设置为“off”，则反馈被禁用。您可以使用 settoggle 命令别名功能键来切换定时显示启用，如下所示

allegro\_dynam\_timing\_fixedpos  
If set,the dynamic timing feedback displaydoes not move with the cursor.Instead,it remains at afixed location.You will not be able to move the display.With this option, you also get multiple timing meters, onefor each type of timing constraint that applies for thecurrent edit.  
如果设置，动态时序反馈显示不随光标移动。相反，它保持在固定位置。您将无法移动显示。使用此选项，您还可以获得多个时序表，一个用于每种类型的时序约束适用于当前编辑。

allegro\_etch\_length\_on  
Add connect can display the pin to pin etch lengthinformation and the net length information whileinteractively routing. This is done by typing "etchlength" on the command line while in add connect. To havethis feature active at all times allegro expert, set theallegro\_etch\_length\_on variable. If desired, an alias canbe set up using a function key to activate add connect andetch length as follows  
添加连接可以在交互式布线时显示引脚到引脚蚀刻长度信息和网络长度信息。这是通过在添加连接时在命令行上键入“etchlength”来完成的。要让此功能始终处于活动状态，请设置 allegro\_etch\_length\_on 变量。如果需要，可以使用功能键设置别名以激活添加连接和蚀刻长度，如下所示

bubble\_no\_display\_invisible  
Set this option to prevent elements onnonvisible subclasses from appearing in the etch editingdynamics when they are bubbled.The default behavior isfor any bubbled etch to be displayed in the dynamics evenif the element would not normally displayed.  
设置此选项可防止不可见子类上的元素在冒泡时出现在蚀刻编辑动态中。默认行为是任何冒泡的蚀刻都会显示在动态中，即使元素不会正常显示。

bubble\_shove\_bondpads  
Set this option to allow bondpad vias to be bubbledwhen via shoving is enabled.The default behavior is forbondpads to not be shoved.  
设置此选项以允许在启用 via shoving 时使 bondpad vias 冒泡。默认行为是不推动bondpads。

etchedit\_ignore\_dynamic\_shapes  
This ignores dynamic shapes while doing etchediting tasks like add connect and slide. env\_var -etchedit\_ignore\_dynamic\_shapes  
这在执行诸如添加连接和滑动等蚀刻编辑任务时会忽略动态形状。 env\_var -etchedit\_ignore\_dynamic\_shapes

no\_show\_dynam\_elec\_errors  
Controls etch editing commands that dynamicallyupdate the screen while the cursor moves. When set thiswill DISABLE the following feature. Length errors in thedynamic clines are indicated by drawing a "centerline" onthe etch in the DRC "Through All" color. All dynamicclines that are part of the edit or have been involved inbubbling will have their errors indicated.  
控制在光标移动时动态更新屏幕的蚀刻编辑命令。设置后将禁用以下功能。动态斜面上的长度误差通过在 DRC“Through All”颜色的蚀刻上绘制“中心线”来表示。作为编辑的一部分或涉及冒泡的所有动态线都将显示其错误。

options\_no\_enhanced\_padentry  
For new designs set the default pad entry tooff. By default, enhanced pad entry is enabled in newdesigns for the etch editing commands.  
对于新设计，将默认焊盘条目设置为 tooff。默认情况下，在新设计中为蚀刻编辑命令启用增强的焊盘输入。

padentry\_factor  
Used to control gathering for traces exiting a round pinor via while concurrently routing more than one net (e.g.differential pair). The purpose is to allow the traces togather sooner.The value is used as a percentage toreduce the minimum clearance that the gathering coderequires between the pin/via and the second segment of thecline exiting the pad. By default, it requires 100 percentof the applicable minimum segment to pin/via spacingconstraint. A value of 75 causes the minimum space to be75 percent of the constraint set value.  
用于控制退出圆形 pinor via 的迹线的收集，同时路由多个网络（例如差分对）。目的是让走线更快地聚集在一起。该值用作百分比以减少聚集代码在引脚/通孔和离开焊盘的第二段斜线之间所需的最小间隙。默认情况下，它需要 100% 的适用最小段到引脚/通孔间距约束。值为 75 会导致最小空间为约束集值的 75%。

rats\_factor  
Controls the preference to select straight pin to pinhorizontal and vertical ratsnest connections. The legalvalue is a range between 0.0 and 1.0. The default is .5. Avalue close to 0.0 = no preference to straightness, shortmanhattan length is the sole determining factor. A valueclose to 1.0 causes ratsnesting preference for straightconnections, regardless of distance between the pins.  
控制首选项以选择直销到水平和垂直鼠巢连接。合法值介于 0.0 和 1.0 之间。默认值为 0.5。接近 0.0 的值 = 不偏爱直线度，shortmanhattan 长度是唯一的决定因素。接近 1.0 的值会导致对直线连接的嵌套偏好，无论引脚之间的距离如何。

slide\_no\_snap  
If left unchecked (default), slide will snap to adjacentsegments in order to make it easier to line up a trackwith the neighboring tracks. If checked, the snap featurewill be disabled.  
如果未选中（默认），幻灯片将捕捉到相邻的段，以便更容易地将轨道与相邻轨道对齐。如果选中，捕捉功能将被禁用。

### gloss

Gloss Settings

cbd\_check  
Allegro performs a DRC check on the connections that havebeen changed during glossing processing.  
Allegro 对在上光处理期间已更改的连接执行 DRC 检查。

gloss\_fatten\_single\_seg  
When performing line fattening, By default if onesegment of the cline cannot be fattened because new DRCswill result, no segments of that cline will be modified.Enable this variable to process each segment individuallyfrom other segments on the same cline.  
执行线增肥时，默认情况下，如果由于新的 DRC 导致无法增肥该 cline 的某个片段，则不会修改该 cline 的任何片段。启用此变量可以从同一 cline 上的其他片段单独处理每个片段。

gloss\_pad\_shape  
Allegro considers the outline of a pad as a square orrectangle and enhances line entry into pads.  
Allegro 将焊盘的轮廓视为方形或矩形，并增强了线进入焊盘的能力。

shapes
------

### general

shape\_add\_filltype  
Determines the initial shape type used for adding shapeson ETCH. By default, this type is dynamic. Across use ofadding shapes, we remember that type used for the last addshape.  
确定用于添加 shapeson ETCH 的初始形状类型。默认情况下，此类型是动态的。在使用添加形状的过程中，我们记住了用于最后添加形状的类型。

shape\_arcmode\_nonsticky  
Controls the arc behavior of edit shape/voidboundary commands. By default, if an arc has been added,the segment type will remain at arc until the usermanually changes the value.When this option is set, thesegment type will automatically be changed back to lineafter an arc has been added.  
控制编辑形状/空白边界命令的弧行为。默认情况下，如果添加了圆弧，则线段类型将保持为圆弧，直到用户手动更改该值。设置此选项后，添加圆弧后，这些线段类型将自动更改回直线。

shape\_drag\_move  
Enable moving a shape using left mouse drag when in shapeedit command.  
在 shapeedit 命令中启用使用鼠标左键拖动移动形状。

shape\_local\_temp  
In certain cases, if your design is located on a networkfile server setting this variable may improve shapevoiding performance. When this variable is set, thestandard OS TEMP or TMP variable is used as the locationfor these files. The local temp directory should haveenough space for 8 Megabyte of storage. Default is to savethis file to the current directory.  
在某些情况下，如果您的设计位于网络文件服务器上，则设置此变量可能会提高 shapevoiding 性能。设置此变量后，标准 OS TEMP 或 TMP 变量将用作这些文件的位置。本地临时目录应该有足够的空间用于 8 兆字节的存储。默认是将此文件保存到当前目录。

shape\_merge\_props  
If set, for the shape merge command, also mergesproperties when merging two shapes. If the two shapes haveduplicated properties then the property value on the firstselected shape will be maintained. The default behaviorwhen shape merging is to maintain the properties of thefirst selected shape.  
如果设置，对于形状合并命令，在合并两个形状时也会合并属性。如果两个形状具有重复的属性，则将保留第一个选定形状的属性值。形状合并时的默认行为是保持第一个选定形状的属性。

shape\_no\_ripupthermal  
This changes the default response for the staticshape thermal rip-up question from Yes to No. This meansthat hitting the Enter key will not rip-up the thermals.  
这会将 staticshape 热裂变问题的默认响应从是更改为否。这意味着按 Enter 键不会裂变热流。

shape\_noclip\_rki  
By default, when adding an etch shape that crosses theroute keepin, it is clipped to the route keepin. Shapesadded outside of the keepin are not clipped and generateDRCs. This variable restores pre-15.5 functionality whereno clipping was done.  
默认情况下，当添加与路线保持区交叉的蚀刻形状时，它会被剪切到路线保持区。在 keepin 之外添加的形状不会被剪裁并生成 DRC。此变量恢复 15.5 之前的功能，其中没有进行剪辑。

shape\_rki\_autoclip  
If set, for dynamic shapes, Allegro will preserve theoriginal dynamic shape boundary and re-clip it to theroute keepin during any dynamic shape update. This allowsautomatic update of dynamic shapes to the route keepin. Bydefault, dynamic shape boundaries, when added, are clippedto the route keepin. CAUTION  
如果设置，对于动态形状，Allegro 将保留原始动态形状边界，并在任何动态形状更新期间将其重新剪裁到路由保留中。这允许将动态形状自动更新到路线保持。默认情况下，动态形状边界在添加时会被剪裁到路线保持中。警告

### voiding

Dynamic and Static Shape Settings

av\_endcapstyle  
Applies to static shape voiding. This changes the geometryof voids created around cline end points. Use to changevoid results when via/pin pad sizes are less than or equalto the line thickness. The default, a blank field, uses anoctagon endcap. Setting this variable is not recommended  
适用于静态形状空洞。这会改变在斜线端点周围创建的空隙的几何形状。用于在通孔/引脚焊盘尺寸小于或等于线路厚度时更改空洞结果。默认值是一个空白字段，使用 anoctagon endcap。不建议设置此变量

av\_inline  
Only applies to static shapes. Controls the distancebetween pins during autovoid processing to determine ifpins are voided as a group. The value is a numbergreater than zero. The default is 100. Works only forhorizontally & vertically aligned pins of same size. Totake advantage of this, set shape parameter to "inlinevoiding".  
仅适用于静态形状。在自动取消处理期间控制管脚之间的距离，以确定管脚是否作为一组无效。值 是一个大于零的数字。默认值为 100。仅适用于相同尺寸的水平和垂直对齐的引脚。为了利用这一点，将形状参数设置为“inlinevoiding”。

av\_thermal\_extend  
Only applies to static shapes. Controls the thermalrelief clines generated during autovoid processing. Bydefault, thermals connects from a pin to 5 mils inside theshape. Use this to specify how far into the shape thermalsshould extend. In cases where shape area between pins isless than 5 mils, lowering the value to 2 or 3, createsmore thermal connections.  
仅适用于静态形状。控制自动空隙处理期间生成的热释放曲线。默认情况下，热量从引脚连接到形状内部 5 密耳。使用它来指定热量应该延伸到形状的深度。在引脚之间的形状面积小于 5 密耳的情况下，将该值降低到 2 或 3，会产生更多的热连接。

dv\_endcapstyle  
Applies to dynamic shape voiding. This changes thegeometry of voids created around cline end points. Innormal situations this variable should NOT be used. In mayallow shape voiding where the default mode (circle) mayshow problems. This variable is not recommended, youshould first try oversizing the voids by a small value toaddress voiding issues.  
适用于动态形状空洞。这会改变在斜线端点周围创建的空隙的几何形状。在正常情况下，不应使用此变量。在默认模式（圆形）可能出现问题的 mayallow 形状空洞中。不推荐使用此变量，您应该首先尝试将空隙放大一个较小的值以解决空隙问题。

dv\_fixfullcontact  
Applies to dynamic shape voiding. This attempts to repairdrcs generated by full contact pins or vias which fail tobe covered by the voided shape. In normal situations thisvariable should NOT be used, since covering is notguaranteed and a void created against an outline or voidedge could trap adjacent voids.  
适用于动态形状空洞。这试图修复由无法被空洞形状覆盖的完整接触引脚或通孔产生的故障。在正常情况下，不应使用此变量，因为不能保证覆盖，并且在轮廓或空隙边缘上产生的空隙可能会捕获相邻的空隙。

legacypadsuppress  
Applies to dynamic and static shape voiding. If set,copper shapes will retain the pad to shape void size, eventhough the pad may be suppressed, to enable legacy boards,that used gerber style pad suppression, to maintain thepad to shape voiding when updated to dynamic padsuppression.  
适用于动态和静态形状空洞。如果设置，铜形状将保留焊盘形状空隙大小，即使焊盘可能被抑制，以启用使用 gerber 样式焊盘抑制的旧板，以在更新为动态焊盘抑制时保持焊盘形状空隙。

pad\_drcplus  
Only applies to static shapes. Set this variable whenautovoid generates DRC's for pin to shape spacingproblems. It can cause autovoid to increase the void sizearound pads. The number represents an addition to the drcspace set in shape parameters.  
仅适用于静态形状。当autovoid 为引脚形状间距问题生成DRC 时设置此变量。它会导致 autovoid 增加焊盘周围的空隙大小。该数字表示对形状参数中设置的 drcspace 的添加。

shape\_diffpair\_voiding  
Enables creating a single oblong void for DiffPairvias. By default, DiffPair vias will be voided separatelyand will only be combined if the spacing is less then theaperture setting. This group voiding is the default in17.2.  
允许为 DiffPairvias 创建单个长方形空隙。默认情况下，DiffPair 过孔将单独作废，并且只有在间距小于孔径设置时才会合并。此组无效是 17.2 中的默认设置。

signal\_analysis
----------------

Signal Analysis Settings

anl\_min\_void\_area  
Specifies, in mils, the smallest void that should beconsidered in plane shapes, when non-ideal plane modelingis desired (i.e. the "Shield" buttons are turned off inthe stack-up description). The default value is "99",signifying that voids with an area less than 99x99 squaremils will be ignored.  
以密耳为单位指定在需要非理想平面建模时在平面形状中应考虑的最小空隙（即“屏蔽”按钮在堆叠描述中关闭）。默认值为“99”，表示面积小于 99x99 平方密耳的空隙将被忽略。

anl\_show\_coupled\_trace  
If set, the Display>Parasitic command will find thecrosstalk neighbors (within the geometry window) and showthe multi-trace model name, such that the user can get thecoupled RLGC matrices from the interconn library usingthis model name.  
如果设置，Display>Parasitic 命令将查找串扰邻居（在几何窗口内）并显示多轨迹模型名称，以便用户可以使用该模型名称从 interconn 库中获取耦合的 RLGC 矩阵。

avoid\_matched\_delay\_calculations  
If set, no delay will be computed for pinpairs with relative prop delay constraints if theconstraint is defined as length rather than delay. Sincethe field solver is used to compute delay values, thiswill prevent the field solver from being run when theconstraint is in length. For these cases the Delay columnin the Constraint Manager Relative Propagation Delayworksheet will contain zeros.  
如果设置，如果约束被定义为长度而不是延迟，则不会为具有相对道具延迟约束的引脚对计算延迟。由于场求解器用于计算延迟值，这将阻止场求解器在约束长度较长时运行。对于这些情况，约束管理器相对传播延迟工作表中的延迟列将包含零。

directconvolutionwithapproximation  
If set, enables an accelerated Sparameter simulation algorithm, which will improve thetime domain simulation performance of circuits containingS parameters.  
如果设置，则启用加速 S 参数仿真算法，这将提高包含 S 参数的电路的时域仿真性能。

enforce\_welement\_simulation  
By default, cline segments shorter than thesimulation timestep are modeled as lumped elements. Whenset, this variable forces all cline segments to be modeledas distributed elements.  
默认情况下，短于模拟时间步长的斜线段被建模为集总元素。设置后，此变量会强制将所有斜线段建模为分布式元素。

fix\_all\_t\_points  
If set, no T-Points will get moved during topologyassignment.  
如果设置，则在拓扑分配期间不会移动 T 点。

frequency\_at\_max\_loss\_tangent\_in\_ghz  
This variable allows the user tocontrol the non-linear dependency of the loss tangent tothe signal frequency. The value of this variable specifiesthe frequency (in GHz) where the dielectric losses aremaximum. The field solver uses this value to calculate theasymptotic behavior of the frequency-dependent Gparameter. The default value is 1 GHz.  
该变量允许用户控制损耗正切与信号频率的非线性相关性。此变量的值指定介电损耗最大的频率（以 GHz 为单位）。场求解器使用该值来计算频率相关 G 参数的渐近行为。默认值为 1 GHz。

ignore\_mapping\_discrete\_values  
When mapping an Electrical Cset topology toan Xnet, the values of the discrete components in thetopology must match the values of the discretes in theXnet. If this variable is set then discretes must match bytype (i.e., a resistor, capacitor or inductor) but thediscrete values are not required to match.  
将电气 Cset 拓扑映射到 Xnet 时，拓扑中的离散组件的值必须与 Xnet 中的离散组件的值匹配。如果设置了此变量，则离散值必须按类型（即电阻器、电容器或电感器）匹配，但离散值不需要匹配。

max\_mappings\_factor  
When mapping an Electrical Cset topology to an Xnet,there are limits to the number of possible mappings thatwill be tried. For very large topologies that have manypins or T-points this limit can cause a "no mapping found"error. The limit can be increased by using this variable.The value of the variable is an integer multiplier. Forexample, a value of 10 means that the limit is increasedby 10X.  
将电气 Cset 拓扑映射到 Xnet 时，将尝试的可能映射数量存在限制。对于具有许多引脚或 T 点的非常大的拓扑，此限制会导致“未找到映射”错误。使用这个变量可以增加限制。变量的值是一个整数乘数。例如，值为 10 表示限制增加了 10 倍。

no\_duplicate\_model\_checks  
If set, no checks will be make for Iml or Dmlmodels with duplicate names.  
如果设置，则不会对具有重复名称的 Iml 或 Dmlmodel 进行检查。

no\_pullup\_diff\_pairs  
If set, a diff pair will not be created if one side ofthe diff pair only consists of a pin connected to a pullupor pulldown resistor.  
如果设置，如果差分对的一侧仅由连接到上拉或下拉电阻的引脚组成，则不会创建差分对。

num\_new\_iml\_models\_before\_save  
This integer value defines the number of newIML models that must be added to the IML working librarybefore this library is saved to disk. For simulations thatgenerate a large number of IML models, the frequentwriting of this library to disk can create a performanceproblem. By default, this value is set to 50 but thispreference allows a user to change this value. The valuemust be an integer that is greater than zero or it will beignored.  
此整数值定义了在将此库保存到磁盘之前必须添加到 IML 工作库中的新 IML 模型的数量。对于生成大量 IML 模型的模拟，将此库频繁写入磁盘可能会产生性能问题。默认情况下，此值设置为 50，但此首选项允许用户更改此值。该值必须是大于零的整数，否则将被忽略。

sig\_mapfile\_orgpath  
Normally, the "Include ORIGINAL Model Path in Map File"option on the Signal Model Assignment form is notselected. If this variable is set to "1", this option willbe set by default.  
通常，不会选择信号模型分配表单上的“在映射文件中包含原始模型路径”选项。如果此变量设置为“1”，则默认设置此选项。

sig\_pinuse\_frozen  
Normally, when a packaged device model is assigned to acomponent, the pin use codes of the pins of the componentare updated to match the type of buffer model that isassigned to each pin. If this variable is set, thecomponent pin use codes are not updated.  
通常，当封装器件模型分配给组件时，组件引脚的引脚使用代码会更新以匹配分配给每个引脚的缓冲器模型的类型。如果设置了此变量，则不会更新组件引脚使用代码。

sigxp\_allowoldrevs  
Normally, a topology that was created by a newer releaseof sigxp cannot be imported into an older release ofConstraint Manager. If this variable is set importing anewer topology into an older version of Constraint Managerwill be allowed. Any part of the topology that isn't legalin the older release will be ignored.  
通常，由较新版本的 sigxp 创建的拓扑无法导入到较旧版本的约束管理器中。如果设置了此变量，则将允许将新拓扑导入旧版本的约束管理器。在旧版本中不合法的拓扑的任何部分都将被忽略。

sigxp\_length\_mode  
By default, when a topology is extracted, T-line delaysare shown in time. If this variable is set, then thedefault display of T-line delay will be in length.  
默认情况下，提取拓扑时，会及时显示 T 线延迟。如果设置了这个变量，那么 T 线延迟的默认显示将是长度。

sigxp\_tier  
This variable controls which license is checked out when SigXplorer is invoked from Allegro PCB. For example, ifthis variable is set to PA5630, (the Allegro PCB SI 630product) while running Allegro PCB Design 610, andSigXplorer is invoked, it will check out a PA5630 licenseand run SigXplorer 630 tier.  
此变量控制从 Allegro PCB 调用 SigXplorer 时检出哪个许可证。例如，如果在运行 Allegro PCB Design 610 时将此变量设置为 PA5630（Allegro PCB SI 630 产品），并且调用了 SigXplorer，它将检出 PA5630 许可证并运行 SigXplorer 630 层。

simsavefiles  
When set, the tlsim circuit files that get created when asimulation is run will be saved. If not set, these filesare deleted after the simulation is complete.  
设置后，将保存运行模拟时创建的 tlsim 电路文件。如果未设置，则在模拟完成后将删除这些文件。

sn\_maxwidthlimit  
Specifies that wider traces are to be modeled as tracesrather than as shapes. The value is the maximum width of atrace (in meters) that is to be modeled as a trace. Alltraces wider than this value will be modeled as shapes.The default value is 0.001016 meters (40 mils).  
指定将更宽的轨迹建模为轨迹而不是形状。该值是要建模为轨迹的轨迹的最大宽度（以米为单位）。比此值更宽的所有迹线将建模为形状。默认值为 0.001016 米（40 密耳）。

sq\_enable\_udiff\_extraction  
Normally, a topology extraction of a net that'spart of a user defined diff pair will only extract asingle net. If this variable is set, both nets in the diffpair will be extracted.  
通常，作为用户定义的差异对的一部分的网络的拓扑提取只会提取单个网络。如果设置了这个变量，diffpair 中的两个网络都将被提取。

translate\_entire\_design  
If set, SPDIF translates the entire design withoutdisplaying the XNet selection dialog.  
如果设置，SPDIF 将转换整个设计而不显示 XNet 选择对话框。

use\_sigwave  
If set,in Allegro Sigrity SI use Sigwave as the defaultwaveform viewer.  
如果设置，在 Allegro Sigrity SI 中使用 Sigwave 作为默认波形查看器。

variant\_property\_name  
This variable defines the name of the property thatwhen attached to a component defines that the component isa member of a variant. The value of the property is thename of the variant. The default name for this property is"VARIANT".  
此变量定义属性的名称，当附加到组件时，该属性定义组件是变体的成员。属性的值是变体的名称。此属性的默认名称是“VARIANT”。

variant\_to\_ignore  
This variable defines the name of the variant whose pinsare to be ignored when extracting a topology. The defaultvalue of this variable is "DNI".  
此变量定义了在提取拓扑时要忽略其引脚的变体的名称。该变量的默认值为“DNI”。

skill
-----

Skill options

skill\_height  
MS Windows only, controls the height of the telskill inputwindow. Value can be any number between 10 and 50. Defaultis 24.  
仅限 MS Windows，控制 telskill 输入窗口的高度。值可以是 10 到 50 之间的任何数字。默认值为 24。

skill\_linebuffer  
MS Windows, controls the scrollbuffer of the telskillinput window. Value can be any number between 40 and 2500.Default is 250 lines.  
MS Windows，控制 telskillinput 窗口的滚动缓冲区。值可以是 40 到 2500 之间的任何数字。默认值为 250 行。

skill\_width  
MS Windows only, controls the width of the telskill inputwindow. Value can be any number between 40 and 140.Default is 80.  
仅限 MS Windows，控制 telskill 输入窗口的宽度。值可以是 40 到 140 之间的任何数字。默认值为 80。

telskill  
When developing Skill programs allows Skill information tobe entered in the xterm used to open Allegro (UNIX) or inan additional command window (MS Windows). Do not runAllegro with background with this variable set (UNIX).  
开发 Skill 程序时，允许在用于打开 Allegro (UNIX) 的 xterm 或附加命令窗口 (MS Windows) 中输入技能信息。不要在设置此变量的背景下运行 Allegro (UNIX)。

telskill\_nomsg  
Normally if a TelSkill window is present, Allegro directsall program output to the TelSkill window. This optioncauses the TelSkill window to only have Skill output;other messages are shown in their intended message areas. This option does not apply if Skill out (on UNIX) isdirected to the tty window.  
通常，如果存在 TelSkill 窗口，Allegro 会将所有程序输出定向到 TelSkill 窗口。此选项使 TelSkill 窗口仅具有技能输出；其他消息显示在其预期的消息区域中。如果将 Skill out（在 UNIX 上）定向到 tty 窗口，则此选项不适用。

telskill\_notty  
UNIX/Linux only, if the telskill environment variable isset, creates a separate TelSkill window instead of usingthe xterm window used to start Allegro. Note if Allegrocannot detect a tty (xterm) it automatically runs in thismode.  
仅限 UNIX/Linux，如果设置了 telskill 环境变量，则会创建一个单独的 TelSkill 窗口，而不是使用用于启动 Allegro 的 xterm 窗口。请注意，如果 Allegro 无法检测到 tty (xterm)，它会在此模式下自动运行。

ui
--

### app\_modes

appmode  
Controls initial tool application mode. Default is to useapplication mode that was in use on previous invocation oftool. The none mode disables pre-selection.  
控制初始工具应用模式。默认是使用先前调用工具时使用的应用程序模式。 none 模式禁用预选。

### browse

Browser Settings

browser\_nodircheck  
This causes all browsers to have the change directorycheckbox initially unset. By default, the main filebrowsers (e.g. File->Open) have the checkbox initially setwhile secondary file browsers (e.g. scripts) have itinitially unset.  
这会导致所有浏览器最初都未设置更改目录复选框。默认情况下，主文件浏览器（例如文件->打开）最初设置了复选框，而辅助文件浏览器（例如脚本）最初未设置。

browser\_nosticky  
When set, file browser always opens to the current workingdirectory. If not set, file browser is opened to thedirectory that was selected the last time it was invokedand a file was opened.  
设置后，文件浏览器始终打开到当前工作目录。如果未设置，文件浏览器将打开到上次调用和打开文件时选择的目录。

browser\_type  
Replaces browser\_win31 variable. Controls file anddirectory browser appearance. Default (win2000) is abrowser with the place bar. Nt eliminates the place bar(15.x browser compatibility). The win31 setting uses anold 2 pane Windows 3.1 browser. Unix currently does notsupport the place bar browser.  
替换 browser\_win31 变量。控制文件和目录浏览器的外观。默认 (win2000) 是带有位置栏的浏览器。 Nt 消除了位置栏（15.x 浏览器兼容性）。 win31 设置使用旧的 2 窗格 Windows 3.1 浏览器。 Unix 目前不支持地点栏浏览器。

browser\_win31  
Applies to pre-16.0 Allegro. When Set the windows 3.1 filebrowser is used. The new browser lists all directories andfiles in one section and supports preview for certain filetypes. When set, 2 sections exist; 1 containingdirectories to filter, and the other containing the filedata. Use browser\_type variable for post 15.x Allegro.  
适用于 16.0 之前的 Allegro。设置时使用 windows 3.1 文件浏览器。新浏览器将所有目录和文件列在一个部分，并支持某些文件类型的预览。设置时，存在 2 个部分； 1 个包含要过滤的目录，另一个包含文件数据。将 browser\_type 变量用于 15.x Allegro 后。

filemgr\_unix  
Applies to UNIX platforms for the filemgr command. Defaultis GNOME's nautilus. You can substitute a 3rd party filemanager replacement or use arguments to change defaultfile manager appearance. Alternatively use the CDE filemanager, dtfile. For example to use the CDE browser set:dtfile %s where the %s allows the substitution of thedirectory name.  
适用于 UNIX 平台的 filemgr 命令。默认是 GNOME 的 nautilus。您可以替换第 3 方文件管理器替换或使用参数来更改默认文件管理器外观。或者，使用 CDE 文件管理器 dtfile。例如，使用 CDE 浏览器 set:dtfile %s 其中 %s 允许替换目录名称。

filemgr\_windows  
Applies only to Windows for the filemgr command. Defaultis explorer.You can substitute a 3rd party explorerreplacement or use arguments to change the defaultexplorer appearance. For example to enable an alternativetwo pane explorer set  
仅适用于 Windows 的 filemgr 命令。默认是资源管理器。您可以替换第 3 方资源管理器替换或使用参数来更改默认资源管理器外观。例如启用一个替代双窗格资源管理器集

nolast\_directory  
If set, Allegro base products do not use the lastdirectory stored in the ~/pcbenv/allegro.ini. This meansallegro, with no command line arguments, opens in thecurrent working directory. This (with variablenolast\_file) restores old 12.0 behavior.  
如果设置，Allegro 基础产品不使用存储在 ~/pcbenv/allegro.ini 中的最后一个目录。这意味着 alllegro，没有命令行参数，在当前工作目录中打开。这（使用 variablenolast\_file）恢复旧的 12.0 行为。

nolast\_file  
If set, Allegro based products when started with nocommand line arguments do not use the master.tag in thecurrent working directory to determine the initial boardto open. If starts with unnamed.brd. This (with variablenolast\_directory) restores old 12.0 behavior.  
如果设置，则基于 Allegro 的产品在以无命令行参数启动时不会使用当前工作目录中的 master.tag 来确定要打开的初始板。如果以 unnamed.brd 开头。这（使用 variablenolast\_directory）恢复旧的 12.0 行为。

old\_scriptbrowser  
When set, uses a file browser for replaying scripts. Ifnot set, uses an Allegro data browser, which supportsSCRIPTPATH. This restores 13.6 behavior.  
设置后，使用文件浏览器重放脚本。如果未设置，则使用支持 SCRIPTPATH 的 Allegro 数据浏览器。这将恢复 13.6 行为。

padlib\_filebrowser  
If set, the padeditlib command (Tools->Padstack->ModifyLibrary Padstack) uses the file browser instead of alibrary path browser.  
如果设置，padeditlib 命令（工具->Padstack->ModifyLibrary Padstack）使用文件浏览器而不是库路径浏览器。

### color

Settings for color form.

color\_dlg\_auto\_apply  
If set, Allegro color form hides the 'Apply' buttonand applies changes instantly. This option can be modifiedtemporarily in color form via 'Enable Auto Apply' checkbox. Internal environment variable name -color\_dlg\_auto\_apply.  
如果设置，Allegro 颜色表单会隐藏“应用”按钮并立即应用更改。可以通过“启用自动应用”复选框以颜色形式临时修改此选项。内部环境变量名称 -color\_dlg\_auto\_apply。

hidecolorpalette  
If set, Allegro color form hides the palette at startup orwhen a new design is opened. Internal environment variablename - hidecolorpalette.  
如果设置，Allegro 颜色表单会在启动时或打开新设计时隐藏调色板。内部环境变量名称 - hidecolorpalette。

### control\_panel

Settings effecting control panel operations. This includes find filter, options, visibility and worldview.

addpin\_default\_space  
Provides a seed value for spacing fields used by theadd pin command in the options panel. Value can be anumber; units will default to current symbol units. Valuecan also include a length unit (e.g. MIL, MICRON, etc.)where the value will be converted to the current symbolunits.  
为选项面板中的 add pin 命令使用的间距字段提供种子值。值可以是一个数字；单位将默认为当前符号单位。值还可以包括长度单位（例如 MIL、MICRON 等），其中值将被转换为当前符号单位。

color\_lastgroup  
By default, the Color and Visibility dialog uses thecurrent active class in the options panel to determine theinitial display panel. This option causes it to use retainthe last displayed in the dialog.  
默认情况下，“颜色和可见性”对话框使用选项面板中的当前活动类来确定初始显示面板。此选项使其使用保留对话框中最后显示的内容。

color\_nofilmrecord  
By default view scheme control in the visibility tabcontains both artwork films and external user defined viewscheme files. This option disables the display of artworkfilms in this control.  
默认情况下，可见性选项卡中的视图方案控件包含艺术品电影和外部用户定义的视图方案文件。此选项禁用此控件中艺术作品的显示。

color\_nosort  
By default, the Color and Visibility dialog sortssubclasses for most classes in the tree control. Thisoption disables the sorting.  
默认情况下，颜色和可见性对话框对树控件中的大多数类的子类进行排序。此选项禁用排序。

find\_nongui\_reject  
When you reject after a pick and there are more than twoelements in the reject buffer, a form is shown with anlist of elements. Use this variable to change thethreshold where this reject list appears. An integer valuecauses the reject list to not appear if the number ofelements is less than or equal to the value. A value of"Always" disables the reject list form. When the Rejectpopup does not show the form, it automatically selects thenext item in the reject buffer.  
当您在挑选后拒绝并且拒绝缓冲区中有两个以上的元素时，将显示一个包含元素列表的表单。使用此变量可更改此拒绝列表出现的阈值。如果元素数小于或等于该值，则整数值会导致拒绝列表不出现。 “始终”值禁用拒绝列表表单。当 Rejectpopup 不显示表单时，它会自动选择拒绝缓冲区中的下一项。

find\_reject\_graphics  
When the reject list is active, the element that isselected in the list can have its graphics altered to helpidentify it. The find\_reject\_graphics option allows you tochange the behavior so the element is either blinked (offthen on), highlighted or unchanged. The default is blink.Note that there could be performance issues withhighlighting of some elements.  
当拒绝列表处于活动状态时，在列表中选择的元素可以更改其图形以帮助识别它。 find\_reject\_graphics 选项允许您更改行为，以便元素闪烁（关闭然后打开）、突出显示或保持不变。默认值为闪烁。请注意，突出显示某些元素可能会出现性能问题。

vis\_activelayer  
By default the Visibility Panel will not change the activelayer. With this option, checking the 'All' cell of a rowin the Visibility Panel will set that row's Etch/Conductorto be the active layer.  
默认情况下，可见性面板不会更改活动层。使用此选项，在可见性面板中选中行的“全部”单元格将将该行的蚀刻/导体设置为活动层。

wv\_voltage\_nets  
If set, displays all highlighted VOLTAGE net elements inthe world view (pre-14.0 mode). By default, only displayspins of nets with the NO\_RAT or VOLTAGE property. Defaultmode may improve interactive performance on boards withlarge number clines on highlighted voltage nets.  
如果设置，则在世界视图中显示所有突出显示的 VOLTAGE 网络元素（14.0 之前的模式）。默认情况下，仅显示具有 NO\_RAT 或 VOLTAGE 属性的网络的自旋。 Defaultmode 可以提高在高亮电压网络上具有大量线路的板上的交互性能。

### fonts

fontface  
Font name used in forms. Default is "MS Sans Serif".  
表单中使用的字体名称。默认为“MS Sans Serif”。

fontfixedface  
Fixed font name used in forms using fixed fonts. Defaultis "courier".  
使用固定字体的表单中使用的固定字体名称。默认是“快递”。

fontsize  
Font size used in forms. Default is -12 for Unix and -9for Windows NT.  
表单中使用的字体大小。 Unix 的默认值为 -12，Windows NT 的默认值为 -9。

fontweight  
Font weight used in forms. Default is 400.  
表单中使用的字体粗细。默认值为 400。

### general

User Interface Settings

allegro\_abortmsg  
Provides an override for the message seen if Allegroaborts. Default message suggests to download the latestISR and contact customer support which may not beappropriate for large installations. Large sites will wantto set this override message in the CDS\_SITE env file.  
为 Allegroabort 时看到的消息提供覆盖。默认消息建议下载最新的 ISR 并联系客户支持，这可能不适合大型安装。大型站点将希望在 CDS\_SITE env 文件中设置此覆盖消息。

allegro\_history  
Controls command history length for both Allegro commandline and the telskill development window. Default is 200.A value of 0 disables history.  
控制 Allegro 命令行和 telskill 开发窗口的命令历史长度。默认值为 200。值为 0 将禁用历史记录。

allegro\_noabort\_confirm  
Variable will suppress Allegro's abort confirmer.The recommended use model is to include this variable inyour script if that script is used to run Allegro in anunattended mode.  
变量将抑制 Allegro 的中止确认器。如果该脚本用于在无人参与模式下运行 Allegro，则推荐的使用模型是将此变量包含在您的脚本中。

allegro\_noghosting  
If you experience problems on Vista or Windows 7 withAllegro showing a "Not Responding" message when runningscripts or Skill programs then set this variable. On otherOperating Systems this option is ignored.  
如果您在 Vista 或 Windows 7 上遇到问题，并且在运行脚本或技能程序时 Allegro 显示“无响应”消息，请设置此变量。在其他操作系统上，此选项将被忽略。

allegro\_savehist  
Controls if history buffers should be saved to/pcbenv on exit. The value asks Allegro to store theuser's last N commands in a file which is read into thehistory buffer next time the program is run. Default isoff.  
控制是否应在退出时将历史缓冲区保存到 /pcbenv。该值要求 Allegro 将用户的最后 N 个命令存储在一个文件中，该文件将在下次运行程序时读入历史缓冲区。默认关闭。

cdsdoc\_shownav  
Requests Cadence Help show its Document Browser along withthe content. Default is to not show the Document Browser.  
请求 Cadence 帮助显示其文档浏览器和内容。默认是不显示文档浏览器。

display\_main\_nosaved\_geometry  
If set, controls the feature that remembersuser sizing and positioning of the program's main window.If set to position, only sizing saved. If set to size,only window locations is saved. If set to both, no windowinformation is saved. Use display\_nosaved\_geometryvariable for secondary windows.  
如果设置，则控制记住用户大小和程序主窗口位置的功能。如果设置为位置，则只保存大小。如果设置为 size，则仅保存窗口位置。如果设置为 both，则不保存窗口信息。将 display\_nosaved\_geometryvariable 用于辅助窗口。

display\_nosaved\_geometry  
If set, controls the feature that remembers usersizing and positioning of windows. If set to position,only sizing saved. If set to size, only window locationsis saved. If set to both, no window information is saved.This does not apply to the tool's main window.  
如果设置，则控制记住窗口的用户大小和定位的功能。如果设置为位置，则只保存尺寸。如果设置为 size，则仅保存窗口位置。如果设置为 both，则不保存窗口信息。这不适用于工具的主窗口。

helpcmd\_execute  
By default, the Allegro helpcmd dialog shows help on acommand. This changes its default behavior to execute thecommand.  
默认情况下，Allegro helpcmd 对话框显示命令的帮助。这将更改其默认行为以执行命令。

noabout  
Suppresses splash screen on startup.  
禁止启动时的闪屏。

orcad\_use\_legacy\_menu  
Use the OrCAD Legacy Menu when set.  
设置后使用 OrCAD Legacy Menu。

readme\_never  
If set, the Allegro README is suppressed on Allegrostart-up. As of 15.0 this is obsolete.  
如果设置，则在 Allegro 启动时禁止显示 Allegro README。从 15.0 开始，这已过时。

recentfilelist  
Controls maximum number of files available in the File,Recently Used Design list. Default is 10.  
控制文件，最近使用的设计列表中可用的最大文件数。默认值为 10。

report\_height  
Height of text window used in report command. Legal valuesare 20 to 70 lines.  
报告命令中使用的文本窗口的高度。合法值为 20 到 70 行。

resizable\_status\_bar  
Enable resizable status bar panes.  
启用可调整大小的状态栏窗格。

text\_nocompact  
Hides the compact button in the define text dialog. Thisvariable should be set at the CDS\_SITE level if you do notwant your users compacting the text blocks.  
在定义文本对话框中隐藏压缩按钮。如果您不希望您的用户压缩文本块，则应在 CDS\_SITE 级别设置此变量。

### html

allegro\_html  
The default uses a html viewing for text windows.Unsetting this variable restores the older non-htmlviewing window.  
默认情况下，文本窗口使用 html 查看。取消设置此变量将恢复旧的非 htmlviewing 窗口。

browser\_text\_size  
Controls the default font size used in the html textbrowser windows. Default is medium.  
控制在 html 文本浏览器窗口中使用的默认字体大小。默认为中等。

http\_netscape  
For UNIX, alternative name of a html viewer. By default,we use the program netscape. Alternative browser mustsupport the netscape -remote and -openURL command linearguments and netscape-remote X protocol. Allegro has beenverified with Netscape 7 and Mozilla 1.4.  
对于 UNIX，html 查看器的替代名称。默认情况下，我们使用程序 netscape。替代浏览器必须支持 netscape -remote 和 -openURL 命令线性参数和 netscape-remote X 协议。 Allegro 已通过 Netscape 7 和 Mozilla 1.4 的验证。

http\_newwindow  
For UNIX, opens a new html window in the current virtualdesktop By default, we will reuse an existing netscapewindow even if it is in a different virtual desktop thenthe Allegro program.  
对于 UNIX，在当前虚拟桌面中打开一个新的 html 窗口 默认情况下，我们将重用现有的 netscape 窗口，即使它位于与 Allegro 程序不同的虚拟桌面中。

### input

Changes keyboard and mouse behavior

canvascommandmode  
Changes Allegro behavior back to 15.0 mode, where theEnter key is required when typing in commands. In newmode, when cursor is in the graphics canvas and an aliasis recognized, it is immediately executed without the needof the Enter key. To have type-in command mode the cursormust be clicked in the console (TITO) area.  
将 Allegro 行为改回 15.0 模式，在该模式下键入命令时需要 Enter 键。在新模式下，当光标在图形画布中并且识别出别名时，它会立即执行，无需 Enter 键。要输入命令模式，必须在控制台 (TITO) 区域中单击光标。

cmd\_linebuffer  
Provides history length in the canvas/message area (TITOwindow). Default is 200 lines and may be set anywhere from50 to 1000 lines. The environment variable,skill\_linebuffer, provides the same control for the Skilltype-in window.  
在画布/消息区域 (TITOwindow) 中提供历史长度。默认值为 200 行，可以设置为 50 到 1000 行。环境变量skill\_linebuffer 为Skilltype-in 窗口提供相同的控制。

designhdl\_pan  
DesignHDL like roam/pan. With this option, Allegro panningbehaves like many other applications. If set, mouselocation is no longer fixed and roam is in the samedirection as the mouse movement.  
DesignHDL 喜欢漫游/平移。使用此选项，Allegro 平移就像许多其他应用程序一样。如果设置，则鼠标位置不再固定并且漫游与鼠标移动的方向相同。

form\_oldreturn  
When a carriage return is used after adding a value in anAllegro form, forms follows standard conventions andpushes the default button. Set this variable to cause acarriage return to "tab" to the next field.  
当在 Allegro 表单中添加值后使用回车时，表单遵循标准约定并按下默认按钮。设置此变量会导致回车返回到“制表符”到下一个字段。

no\_dragpopup  
By default, to use strokes you must hold down the Ctrl keywhen pressing the right mouse button.Setting this optionallows strokes to be used by just dragging with the rightmouse button depressed. With this option, you lose theability to select popup menu items by doing right mousebutton drag. Instead, you have to click twice with theright mouse button  
默认情况下，要使用笔画，您必须在按下鼠标右键时按住 Ctrl 键。设置此可选功能可以通过按住鼠标右键拖动来使用笔画。使用此选项，您将无法通过鼠标右键拖动来选择弹出菜单项。相反，您必须用鼠标右键单击两次

no\_shiftpopup  
By default, the mouse Shift-RMB is directed topre-selection popup. This variable restores roamcapability to the Shift-RMB. Useful for 2-button mice suchas notebooks. Normal pre-selection without the Shiftmodifier will still function with this option.  
默认情况下，鼠标 Shift-RMB 指向预选弹出窗口。此变量恢复 Shift-RMB 的漫游能力。适用于笔记本等 2 键鼠标。没有 Shift 修饰符的正常预选仍然可以使用此选项。

unix\_numlock  
On certain Linux and AIX XServer implementations, we maynot be able to correctly detect the 'Numlock' setting onstartup. If you see multiple characters echoed to theAllegro commend area when you press the keypad, you willwant to set this variable. This variable does not apply toWindows.  
在某些 Linux 和 AIX XServer 实现上，我们可能无法在启动时正确检测“Numlock”设置。如果您在按下键盘时看到多个字符回显到 Allegro 推荐区域，您将需要设置此变量。此变量不适用于 Windows。

### license

all\_license\_choices  
When set will show all products supported by a programin its Product Choices dialog. By default, only thelicenses you have in your license file are shown. Whenset, this can improve tool startup performance but you maysee many more products in the choice dialog. Tip, you canalso improve performance by using the "-product "option when starting the program (use "-product help" tosee a complete list of choices).  
设置后将在其产品选择对话框中显示程序支持的所有产品。默认情况下，仅显示您在许可文件中拥有的许可。设置后，这可以提高工具启动性能，但您可能会在选择对话框中看到更多产品。提示，您还可以在启动程序时使用“-product ”选项来提高性能（使用“-product help”查看完整的选项列表）。

allegro\_license\_caching  
Enables license caching which improves tool startupperformance. If you frequently change license servers, donot use this option. The license cache can be reset on thetoolswap dialog by checking the "Reset license cache"option. Default is license cache is on.  
启用许可证缓存，从而提高工具启动性能。如果您经常更改许可证服务器，请不要使用此选项。通过选中“重置许可证缓存”选项，可以在工具交换对话框中重置许可证缓存。默认为启用许可证缓存。

cds\_ng\_licenses  
When enabled allows the software to check for NG licenses.This allows access to some Cadence evaluationfunctionality (most customers do not possess theselicenses). When enabled, it may cause tool startupslowness if you have multiple Cadence license servers inyour CDS\_LIC\_FILE and one or more of these servers have aslow 'ping' response or high network packet drops.  
启用后允许软件检查 NG 许可证。这允许访问某些 Cadence 评估功能（大多数客户不拥有这些许可证）。启用后，如果您的 CDS\_LIC\_FILE 中有多个 Cadence 许可证服务器，并且其中一个或多个服务器的“ping”响应慢或网络丢包率高，则可能会导致工具启动缓慢。

license\_nolegacy  
When enabled filters any legacy product from the ChangeEditor dialog. This intended for CAD administrators to seton a site wide basis. Default is to show all productsavailable from the license server. This does not apply topre-16.5 installations.  
启用后，可从 ChangeEditor 对话框中过滤任何旧产品。这旨在让 CAD 管理员在站点范围内进行设置。默认是显示许可证服务器中可用的所有产品。这不适用于 16.5 之前的安装。

### pad\_designer

padstack\_allow\_null  
By default, Allegro does not allow padstacks to bedefined with no etch (conductor) layers. This variableallows padstacks to be defined that contain only masklayers (pre-16.01 behavior).  
默认情况下，Allegro 不允许在没有蚀刻（导体）层的情况下定义焊盘堆栈。此变量允许定义仅包含掩膜层的焊盘堆栈（16.01 之前的行为）。

padstack\_hole\_outside  
Makes it an error for multi-drill padstacks to havetheir drill array overlap the pad boundaries. By default,this is a warning. As an error, you will not be able tosave the padstack.  
使多钻孔焊盘堆叠的钻孔阵列与焊盘边界重叠是错误的。默认情况下，这是一个警告。作为一个错误，您将无法保存焊盘。

padstack\_nowarning\_display  
By default, the pad\_designer displays a warningbefore file save.This allows the disabling of the display.This variable is provided for automation of padstackcreation. You should not set this variable on permanentbasis.  
默认情况下，pad\_designer 在文件保存之前显示警告。这允许禁用显示。此变量用于自动创建 padstack。您不应永久设置此变量。

padstack\_nowarning\_drill  
In pad\_designer suppresses warning when the drillhole is equal or larger then the smallest pad size.  
在 pad\_designer 中，当钻孔等于或大于最小焊盘尺寸时会抑制警告。

### remote

Tuning options for thin clients, VNC, Remote Desktop, remote X-windows and graphics poor environments. Also see OpenGL group for more options.

allegro\_no\_ownerdraw  
Can improve drop-down menu performance by disablingbitmaps shown in the menus. If you notice a noticeabledelay in the menus invoking (e.g. like the File menu), setthis variable and re-start the tool.  
可以通过禁用菜单中显示的位图来提高下拉菜单的性能。如果您注意到调用菜单中的明显延迟（例如文件菜单），请设置此变量并重新启动该工具。

roam\_slowconnect  
Improves roam control when using the middle mouse buttonto roam over high latency connections like VNC, RemoteDesktop or remote X WAN connection. Side effect of settingthis variable is the cursor is not kept at its startinglocation. This option should not be used for running thesoftware locally.  
改进了使用鼠标中键漫游高延迟连接（如 VNC、RemoteDesktop 或远程 X WAN 连接）时的漫游控制。设置这个变量的副作用是光标没有保持在它的起始位置。此选项不应用于在本地运行软件。

### script

noconfirm  
If set Allegro does not prompt you to confirm certainactions. This variable should be used only with scripts.  
如果设置 Allegro 不会提示您确认某些操作。此变量应仅用于脚本。

noconfirm\_startup  
Suppresses confirmer windows on startup. These typicallyinform the user of warnings or errors in the Allegrostartup files. Messages suppressed with this option arenot journaled.  
在启动时禁止确认窗口。这些通常会通知用户 Allegrostartup 文件中的警告或错误。使用此选项抑制的消息不会被记录。

noformscriptbutton  
When set, print to script for a form containingadd/reset buttons can include add and reset as commands.Replay of the script updates values and then performRESET. With the variable set, script record does notrecord the form buttons.  
设置后，打印到包含添加/重置按钮的表单的脚本可以包括添加和重置作为命令。脚本的重播更新值然后执行RESET。设置变量后，脚本记录不会记录表单按钮。

script\_keepformopen  
When set, will keep script dialog open across scriptreplay. Default is to close form during replay.  
设置后，将在脚本重放期间保持脚本对话框打开。默认是在重播期间关闭表单。

script\_startup  
Script name used on startup. We will prepend the programname to the name provided (_), and lookupthe filename using Script_ name used on startup. We will prepend the programname to the name provided (<program>\_<name>), and lookupthe filename using SCRIPTPATH. No warning is issued ifscript cannot be found. More flexibility can obtained byusing the "-s <script>" option when starting the program

启动时使用的脚本名称。我们将在提供的名称前添加程序名并使用 SCRIPTPATH 查找文件名。如果找不到脚本，则不会发出警告。启动程序时使用“-s <script>”选项可以获得更大的灵活性。

### title

Title bar option variables. Title variable strings are truncated to a maximum of 20 characters. Title bar space is at a premium when long project paths are present, recommend strings shorter then 20 be used.

title\_allegro  
Adds user defined text to the title bar for the Allegroprogram.  
将用户定义的文本添加到 Allegro 程序的标题栏。

title\_allegro\_viewer\_plus  
Adds user defined text to the title bar for theallegro\_viewer\_plus program.  
将用户定义的文本添加到 allegro\_viewer\_plus 程序的标题栏。

title\_apd  
Adds user defined text to the title bar for the APDprogram.  
将用户定义的文本添加到 APD 程序的标题栏。

title\_cdnsip  
Adds user defined text to the title bar for the cdnsipprogram.  
将用户定义的文本添加到 cdnsip 程序的标题栏。

title\_sigxp  
Adds user defined text to the title bar for the sigxpprogram.  
将用户定义的文本添加到 sigxp 程序的标题栏。

### undo

Settings for undo/redo command history.

max\_undo\_memory  
Sets maximum memory (in MB) for storing undo history.Default is 8 MegaBytes. Range is 0 to 100.  
设置用于存储撤消历史的最大内存（以 MB 为单位）。默认值为 8 兆字节。范围是 0 到 100。

undo\_depth  
Sets maximum depth for Undo history. More undo historytakes more memory. Default is 10 commands. Range is 0 to100 commands. The actual number of commands in the undobuffer is dynamically determined based upon this value andthe undo memory consumed to undo each command, the totalof which must not exceed max\_undo\_memory.  
设置撤消历史的最大深度。更多的撤消历史需要更多的内存。默认值为 10 个命令。范围是 0 到 100 个命令。 undobuffer中的实际命令数是根据这个值和每条命令所消耗的undo内存动态确定的，其总和不能超过max\_undo\_memory。

### xprobe

Manage internal and external cross-probing.

allegro\_no\_xprobe  
Controls Allegro cross-probing with external tools. Bydefault, inter-tool cross-probing is enabled. If set toyes both input and output communication is disabled. Ifset to exceptProjectManager, cross-probing is enabled ifAllegro is started from project manager. When Allegro isrun stand-alone cross-probing is disabled.  
使用外部工具控制 Allegro 交叉探测。默认情况下，工具间交叉探测处于启用状态。如果设置为yes，则输入和输出通信都将被禁用。如果设置为 exceptProjectManager，则在从项目经理启动 Allegro 时启用交叉探测。当 Allegro 运行时，独立交叉探测被禁用。

ignore\_external\_highlight  
If this is set, then highlight (cross-probe)messages fromsimultaneously running, external instancesof this program are ignored.  
如果设置了此项，则同时运行的突出显示（交叉探测）消息，该程序的外部实例将被忽略。

longmsg\_noxprobe  
Disables xy center functionality from text view windowssuch as show element, reports, etc. By default, clickingon a text coordinate causes the main Allegro canvas tocenter on that coordinate.  
从文本视图窗口（例如显示元素、报告等）禁用 xy 中心功能。默认情况下，单击文本坐标会导致主 Allegro 画布在该坐标上居中。

### zoom

buttonfactor  
Provides mouse wheel zooming adjustment. By default, usesa value of 1 which zooms by a factor of 2 for every clickof the mouse wheel. If less sensitivity is desired thentry 0.5 or 0.25 which will zoom by a factor of 1.5 and1.25 respectively. Range is 0.1 to 5.  
提供鼠标滚轮缩放调整。默认情况下，使用值 1，每次单击鼠标滚轮时都会缩放 2 倍。如果需要较低的灵敏度，则尝试 0.5 或 0.25，这将分别放大 1.5 和 1.25 倍。范围是 0.1 到 5。

no\_dynamic\_zoom  
Middle mouse click now performs dynamic zoom whichprovides zoom in, zoom out, window fit and zoon centeroperations. If disabled, middle mouse key will behave theold way, providing zoom in and zoom out only.  
鼠标中键现在执行动态缩放，提供放大、缩小、窗口适合和缩放中心操作。如果禁用，鼠标中键将按照旧方式运行，仅提供放大和缩小功能。

no\_zoom\_to\_object  
In find by name, an automatic zoom in operation isperformed to enhance display of highlighted objects. Ifset, the zoom operation is disabled.  
在按名称查找中，执行自动放大操作以增强突出显示对象的显示。如果设置，则禁用缩放操作。

wheel\_zoom\_center  
If set, mouse wheel zooming is performed based on centerof screen instead of current mouse location which is thedefault behavior.  
如果设置，鼠标滚轮缩放将基于屏幕中心而不是当前鼠标位置执行，这是默认行为。

unsupported
-----------

These variables control access functionality that is of Beta quality. These features are present for customer feedback but they are NOT supported or documented. Once we are satisfied with the feature's quality and functionality, they will be promoted to a core feature. We welcome your comments and suggestions.

aipt\_enable\_nets  
If set, the selection of Nets and xNets is enabled in theObject Find Filter for Auto-interactive Phase Tune.Thiscapability is of Beta quality and CCRs do not followstandard Cadence CCR policy. It will be enabled by defaultin release 17.0. Internal environment variable name -aipt\_enable\_nets.  
如果设置，则在用于自动交互相位调谐的对象查找过滤器中启用网络和 xNet 的选择。此功能为 Beta 质量，CCR 不遵循标准 Cadence CCR 策略。它将在 17.0 版中默认启用。内部环境变量名称 -aipt\_enable\_nets。

cns\_ck\_diffx  
If set, enables a new Dynamic Phase DRC algorithm. Whenset, DRC checks phase starting at the driver pin insteadof first coupling event. pin escapes or layer changes.This capability is of Beta quality and CCRs do not followstandard Cadence CCR policy. It will be the defaultcalculation in release 17.0. Internal environment variablename - cns\_ck\_diffx.  
如果设置，则启用新的动态相位 DRC 算法。设置后，DRC 检查从驱动器引脚开始的相位，而不是第一个耦合事件。引脚转义或层更改。此功能为 Beta 质量，CCR 不遵循标准 Cadence CCR 策略。这将是 17.0 版中的默认计算。内部环境变量名 - cns\_ck\_diffx。

dbdoc\_fixed\_private  
If set, Dbdoctor will remove FIXED\_PRIVATE propertiesleft behind by partitioning application. Use only ifunable to MOVE symbols or modules after importingpartitions.  
如果设置，Dbdoctor 将删除分区应用程序留下的 FIXED\_PRIVATE 属性。仅在导入分区后无法移动符号或模块时使用。

disable\_unsupported\_menus  
This will hide "Unsupported Prototypes" Submenuin All Menus. Commands available through these submenusare of Beta quality and CCRs filed against them do notfollow standard Cadence CCR policy. Internal environmentvariable name - disable\_unsupported\_menus.  
这将隐藏所有菜单中的“不支持的原型”子菜单。通过这些 Beta 质量的子菜单可用的命令和针对它们提交的 CCR 不遵循标准的 Cadence CCR 政策。内部环境变量名称 - disable\_unsupported\_menus。

unsupported\_strip\_design  
Enables Strip IP design capability in the FileExport menu. This capability is of Beta quality and CCRsdo not follow standard Cadence CCR policy. It will anadvertised feature in a future version of 16.6 release.Internal environment variable name -unsupported\_strip\_design.  
在 FileExport 菜单中启用 Strip IP 设计功能。此功能具有 Beta 质量，CCR 不遵循标准 Cadence CCR 政策。它将在 16.6 版本的未来版本中进行广告功能。内部环境变量名称 -unsupported\_strip\_design。