---
layout: post
title: 杂项记录
categories: Allegro Skill
date: 2023-07-05
permalink: allegro-skill-other
excerpt: 杂项记录
---


allegro在每个不同版本中，都新加了一些AXL函数。
可通过以下文件大概了解。
首先进入到目录：
%CDSROOT%\share\pcb\examples\skill\DOC
里面列出了每个版本下的AXL函数，及各个版本所更新的AXL函数。


type 查询数据类型

### 列出目前有哪些function

```lisp
_lfn("axl")
listFunctions("axl")
```

### 获取登陆名和计算机名

```lisp
axlGetVariable("username");登陆名
nthelem(2 getSystemName());计算机名
```

## arglist 用来查函数的参数


arglist函数用来查函数的参数，比如
Skill > arglist('help)
(sym 0 1 "S")

Skill > arglist 'sort
(l_list g_general "lg")



## [AXL函数] AXL函数使用

### axlDesignType


axlDesignType 可获取当前Design的类型。

如果为LAYOUT，则包含以下类型：
"BOARD", "MCM", "MDD"(module), "TIL" (tile).

如果为SYMBOL,则包含以下类型：
"PACKAGE", "MECHANICAL","FORMAT", "SHAPE",  "FLASH".

基本格式：
axlDesignType(
g_detailed
)

g_detailed 如果为nil，则返回最上级类型，即LAYOUT还是SYMBOL。如果为t，则返回当前Design类型，即LAYOUT SYMBOL的下级属性。

比如，当前打开一个brd文件，分别在命令栏输入以下内容：
skill axlDesignType(t)
复制代码
=>"BOARD"
skill axlDesignType(nil)
复制代码
=>"LAYOUT"

### axlExportXmlDBRecords


axlExportXmlDBRecords(
t_fileName
lt_parmGroups/nil
) -> t/nil
axlExportXmlDBRecords(
nil
) -> lt_parmGroups
描述
该函数用于导出当前allegro的各项参数设置。等效于从菜单文件(File - Export - Parameter)导出. 导出时会额外创建一个param_write.log LOG文件.

参数
t_fileName 导出的参数文件名。默认文件后缀为".prm"。如果未指定路径，那么导出到环境变量"PARAMPATH"指           定的路径. 如果该参数为 nil ，则直接输出当前可导出的参数列表。

lt_parmGroups 需要导出的参数，可通过list传递。如果为nil，则导出所有的参数。



返回值

t 执行成功
nil 执行失败


相关函数

axlImportXmlDBRecords


例子
1. 导出当前brd所有参数，并导入到一个新的brd中

axlExportXmlDBRecords("myparam" nil)
axlOpenDesign(?design "newDesign")
axlImportXmlDBRecords("myparam")

2. 输出当前可导出参数列表

axlExportXmlDBRecords(nil)

=>("Color Generic Group" "Color Profile" "Color Component" "Color Palette" "Color Net"
    "Application or Command Parameters" "Text Size" "Color Layer" "Artwork" "Design Setting"
)

### axlDBTextBlockCreate


axlDBTextBlockCreate(
x_blockTemplate
?width f_width
?height f_height
?lineSpace f_lineSpace
?charSpace f_charSpace
?photoWidth f_photoWidth
) => x_textBlock/nil

描述

用于从模板创建一个新的字号。需要通过以下函数获取字号模板:

lst = axlGetParam("paramTextBlock")

参数

x_blockTemplate
f_XXX

返回值
x_textBlock - 新的字号
nil - 创建失败返回nil. 一般由于字号超过了allegro可提供的数量或者某个参数传递错误。

相关函数

axlGetParam, axlSetParam, axlDBTextBlockCompact

例子：

基于1号字体来创建一个新的字号。比如目前共32个字体，那么新创建的字号为33.未修改的参数默认使用1号字体的。

blockNum = axlDBTextBlockCreate(1 ?width 15.0 ?height 16.0)

### axlSetParam

axlSetParam (
od_paramDbid
)
=> rd_paramDbid/nil

描述

该函数用于修改Allegro某些参数。 该函数主要结合axlGetParam使用。

参数
od_paramDbid 通过axlGetParam函数获取到参数的Dbid，当修改过某些参数的属性后，使用axlSetParam 函数进行数据更新.

返回值
rd_paramDbid 设置成功则返回该参数的Dbid。
nil 数据未被更新.

相关函数
axlGetParam

例子 :

1. 改变显示(注，一般使用axlVisibleSet 更方便快捷。)
(setq etch_top (axlGetParam "paramLayerGroup:ETCH/paramLayer:TOP"))
=>param:123456
; is layer visible ?
etch->visible
t
; blank it
etch_top->visible = nil
t
(axlSetParam etch_top)
=>param:123456
; layer is now invisible
etch_top->visible
nil

2. 改变精度
p = axlGetParam("paramDesign")
p->accuracy = 3
axlSetParam(p)

### axlColorGet


axlColorGet(
x_number/`background
) -> lx_rgb/nil

axlColorGet(
'count)
-> x_count

axlColorGet(
'all)
-> llx_rgb

axlColorGet(
'pattern
) -> x_count


描述

获取调色板. 支持以下模式:

模式一： 通过颜色索引编号获取该颜色的RGB值，RGB值从0到255（8位）。例如RGB(255 255 255 )为白色 。 'background  返回allegro的背景色RGB值。

模式二： 'count 获取当前allegro版本所支持的颜色数。allegro 16X为192色，15X及以下为24色。  

模式三： 获取所有颜色编号的RGB值，除了背景色外。allegro 16x获取192种颜色的RGB.

模式四： 返回当前调色板所支持显示的颜色数量。参考模式二。

注：allegro中所有层的颜色都是通过颜色索引来设置的，而非直接通过RGB来设置，所以设置颜色前，需要将颜色的RGB值赋予某个颜色编号，再通过编号来传递值 (参考 axlVisibleGet).


参数

x_number 颜色编号.

'background 获取背景色.

`count 获取调色板所支持的颜色数量。.

`all 获取整个调色板RGB值(除背景色).


返回值

x_count 调色板支持颜色数量大小.

nil 错误.

lx_rgb 单个颜色编号RGB值.

llx_rgb 整个调色板RGB值



相关函数

axlColorSet, axlVisibleGet


例子

获取color2的RGB:

clr = axlColorGet(2)

=>(14 210 255)

获取背景色:

bground = axlColorGet(`background)

=>(0 0 0)

获取颜色数量:

cnt = axlColorGet(`count)

=>192

获取所有颜色的RGB值:

all = axlColorGet(`all)


获取支持显示的颜色数量

cnt = axlColorGet(`pattern)

=>16

### getCurrentTime获取当前时间函数


getCurrentTime的一般格式为：
getCurrentTime()
=> t_timeString

返回值：
t_timeString 为一字符串，字符串的形式为：month day hour:minute:second year
注:一般我们会通过 parseString 函数将字符串变为一个list，便于操作。

例子:
getCurrentTime()
复制代码
=>"May 10 22:39:39 2013"

### axlDBGridSet


axlDBGridSet(
og_grid)
==> t/nil

描述

该函数用于修改格点参数.关于格点的参数，可参考axlDBGridGet函数。

除了直接设置格点layer层外，还可以通过以下两个参数设置：

'all - 设置所有格点

'etch - 设置所有ETCH层格点


xGrids 和 yGrids 可以为浮点数。xMajor的值为xGrids的总和；yMajor的值为yGrids 的总和


注意:

Non-etch层的格点不能分层设置，所有Non-etch层只能设置同一个值。 格点设置后是不能进行Undo操作，设置时需要注意；
Etch层格点的layer名与Etch下的SUBCLASS名一样。设置的偏移位置不能超出板子界面大小。
如果格点窗口打开的话，使用该函数不能更新格点参数。

参数

og_grid 需要设置的格点layer名，可通过list传递。具体可参考函数axlDBGridGet


返回值

t    格点设置成功

nil  格点设置失败


相关函数

axlDBGridGet, axlDBDisplayControl


例子：

1.设置表层格点

grid = axlDBGridGet("TOP")
grid->xGrids = 10
grid->yGrids = 10
axlDBGridSet(grid)

2.修改所有层的格点(xGrids、yGrids可以不通过list传递值)


grid = axlDBGridGet("TOP")

grid->name = 'all

grid->xGrids = 5.0

grid->yGrids = 5.0

axlDBGridSet(grid)

3. 修改所有 etch 层格点


grid = axlDBGridGet("TOP")

grid->name = 'etch

grid->xGrids = '(5.0 7.0)

grid->yGrids = '(5.0 6.0)

axlDBGridSet(grid)


### axlColorSave


axlColorSave(
t_file/nil
) -> t/nil


描述

将当前brd的颜色保存为一个col文件。即将allegro颜色窗口中的颜色参数导出。如下图：


参数

t_file 文件名（包括路径）。如果参数设置为  nil ; 默认将保存到<HOME>/pcbenv/lallegro.col；如果未指定扩展名，默认为.col


返回值

t 保存成功.

nil 保存失败.


相关函数

axlColorSave,axlColorSet


例子

将当前颜色导出到mycolor文件

axlColorSave("mycolor")

### axlDMFileParts文件路径分离


axlDMFileParts(t_filespec)
返回值：(路径 文件名 文件名及后缀 后缀)
t_filespec为文件名或完整的文件路径


fileparts = axlDMFileParts("/usr1/xxx/stuff.txt"))    --> ("/usr1/xxx/" "stuff" "stuff.txt" "txt")
fileparts = axlDMFileParts("stuff.txt"))    --> ("/usr1/xxx/" "stuff" "stuff.txt" "txt")

### axlPadSuppressGet


axlPadSuppressGet(
nil
)
=> ll_LayerPadSuppress

axlPadSuppressGet(
t_layer/x_layerNumber
)
=> l_LayerPadSuppress

描述

用于获取 某个层面的 pad suppress 参数. Pad suppression 在 symbol editor模式下无效.


参数

nil 返回所有层的pad suppress

t_layer 返回指定t_layer e层的pad suppress参数

x_layerNumber 返回指定序号的 layer层pad suppress参数 (第一个层为 0)


返回值

ll_LayerPadSuppress -所有层的l_LayerPadSuppress 列表. 从top 到 bottom.

l_LayerPadSuppress - 指定层的suppress特性.  

(<t_layer> [<s_pin>] [<s_via>])


相关函数

axlPadSuppressSet, axlPadSuppressOkLayer, axlDBControl, axlSubclassRoute, axlPadOnLayer


例子

获取所有层的suppress状态
suppress = axlPadSuppressGet(nil)
foreach(item suppress
printf("Layer=%s what= %L\n", car(item) cdr(item)))

获取 "GND"层的suppress状态
suppress = axlPadSuppressGet("GND")

获取序号为1层的suppress状态
suppress = axlPadSuppressGet(1)

### axlPadSuppressOkLayer


axlPadSuppressOkLayer(
t_layer/x_layerNumber
)
=> t/nil

描述

用于判断某层是否可以设置pad suppression，一般只有内层走线层可以设置，表底层及负片都不能设置。


参数

t_layer layer名 (例如 "TOP")
x_layerNumber layer序号(以 0开始排列);


返回值

t   layer 可以进行pad suppress设置;
nil 其他情况


相关函数

axlPadSuppressGet，axlPadSuppressSet


例子:

axlPadSuppressOkLayer("TOP") =>nil
axlPadSuppressOkLayer(0)

### axlGetParam


axlGetParam(
t_parm_name
)  
=> o_paramDbid/nil  

描述

获取指定t_parm_name参数的dbid。 下面列出了所支持的参数名：

参数

t_parm_name 需要获取的参数名。下面是所支持的参数类型：

paramTextBlock:<#>  # 为字体号数 (例如: paramTextBlock:1，可获取1号字体大小)
paramDesign
paramDisplay
paramLayerGroup:<name> name为allegro的层名称paramLayerGroup:<name>/paramLayer:<name>
artwork 光绘名列表
artwork:<filmName> 获取指定 filmName的光绘层信息
testprep 具体可参考函数 axlParamTestPrepDoc

返回值
o_paramDbid 所获取参数的dbid.
nil 所获取参数未找到.


相关函数
axlSetParam

例子:

1) 获取所有etch的subclass 信息
Skill> etch_parm = axlGetParam("paramLayerGroup:ETCH")
param:123456
Skill> etch_parm->??
(objType "paramLayerGroup" name "ETCH" visible
-1 nChildren 4 groupmembers
("TOP" "GND" "VCC" "BOTTOM")
color -1
)
Skill> etch_parm->color
-1
Skill> etch_parm->groupMembers
("TOP" "GND" "VCC" "BOTTOM")

2) 获取所有光绘artwork记录:

A) 获取所有光绘信息列表.
Skill> p = axlGetParam("artwork")
Skill> p->??
(objType "artwork" nChildren 4 groupMembers
("TOP" "GND" "VCC" "BOTTOM")

B) 获取单个"VCC"光绘层信息.
r = axlGetParam("artwork:VCC")
Skill> r->??
(objType "artwork" groupMembers
("ETCH/VCC" "PIN/VCC" "VIA CLASS/VCC") vectorBasedPad
t suppressShapeFill t useApertureRotation nil
drawMissingPadApertures nil suppressUnconnectPads t fullContact
nil mirrored nil shapeBoundingBox 100.0
offset (0.0 0.0) rotation 0 undefineLineWidth
0.0 negative t name "VCC"
)

C) 删除TOP层光绘参数信息.
axlDeleteObject("artwork:TOP")
3) Design (paramDesign) 修改.
axlDBChangeDesignOrigin: 修改原点
axlDBChangeDesignExtents: 修改视野大小
axlDBChangeDesignUnits: 修改单位或者精度

### axlImportXmlDBRecords

axlImportXmlDBRecords(
t_fileName
) -> t/nil


描述

该函数用于导入当前allegro的各项参数设置。等效于从菜单文件(File - Import - Parameter)导出.导出时会额外创建一个 param_read.log   LOG文件。关于该函数的具体使用方法，可以参考axlExportXmlDBRecords函数


参数

t_fileName 导入的参数文件名。默认文件后缀为".prm"。如果未指定路径，那么从环境变量"PARAMPATH"指定的路径查找t_fileName .


返回值

t  执行成功
nil  执行失败


相关函数

axlExportXmlDBRecords


例子

可直接参考axlExportXmlDBRecords

### axlDBAddProp

说明：
axlDBAddProp主要用于为某个目标添加一个属性，如果该目标不具备该属性，那么将导致添加失败，不如SYMBOL具有高度属性，而NET不具有，当为NET添加高度属性时，会添加失败。其他同理。假如该目标已经有了这个属性及值，那么会用当前的属性值替换掉旧的值。
函数结构：
axlDBAddProp
axlDBAddProp(
lo_attach
ll_name_value
)
T l_result/nil

参数说明：
lo_attach，为需要添加的目标的DBID，为一个list。
ll_name_value，为需要添加的属性及值，同样为一个list,第一个参数为属性名，第二个参数为属性值，例如：axlDBAddProp(Comps list("HIGH" 15))

返回值
l_result为返回值，car(l_result)将返回添加成功的DBID，cadr(l_result)始终为nil

注意，在使用axlDBAddProp之前，确保添加的目标具有该属性，若没有，请通过axlDBCreatePropDictEntry函数为该目标定义一个属性。

### axlColorLoad


axlColorLoad(
t_file/nil
) -> t/nil   

描述

用于加载Allegro PCB Editor 颜色文件 (后缀为.col ). 颜色文件保存在路径： <cdsroot>/share/pcb/text/lallegro.col.注cdsroot为安装路径。

颜色文件格式 :

# Comment if in first column.

#N     Next line with a number is number of colors (currently only 24 is supported). This should appear first in the file.

Number format

#Number

24

#B - next line with a number is background color. This should appear after color number. Format of color line must be:

(name is currently ignored):

0 <red> <green> <blue> [<name>]

EXAMPLE of background format setting it to black

#Background Color

0 0 0 0

#I - next set of lines sets the colors. These should always appear last in the file. We will read until the first color number that exceeds the color number (currently hardcoded as 24) or the end of file is

reached. The order the colors appear in the file determines the initial color [priority (highest (first) to lowest (last)].

Format is:

<color number> <pen number> <red> <green> <blue> [<name>]

EXAMPLE:

1 1 255 255 255 White

2 2 14 210 255 LtBlue

<color number>: entry in color table. This is the color number referenced by the allegro subclass (axlLayerGet)

<pen number>: Used by Allegro plot (UNIX) to control what pen to use during plotting. Not applicable on Windows.

<red> intensity of red to blend into color 0 to 255

<green> intensity of green to blend into color 0 to 255

<blue> intensity of blue to blend into color 0 to 255

<name> (optional) name of color, currently not used by Allegro but sigxp takes advantage of the name to auto-assign colors.

当更新颜色文件并加载后，需要调用 axlVisibleUpdate 函数更新显示，否则可能会导致颜色还保留在之前的设置。

当新建一个allegro brd文件时，allegro会自动加载颜色文件（16X默认加载allegro_192.col）,当新建brd成功并保存后，就不再使用该col文件了，所有的颜色数据保存在brd文件数据库中，所以后续更新颜色就需要在allegro brd文件

中更新。修改allegro_192.col可修改新建brd默认的颜色。一般不建议这样操作。


参数

s_file 需要加载的颜色文件路径

nil 使用默认的 lallegro.col. 文件。如果未指定路径，则allegro默认查找环境变量LOCALPATH所指定路径下的颜色文件


返回值

t 颜色文件加载成功

nil 颜色文件未找到或者颜色文件格式错误。


参考函数

axlColorSave,axlColorSet


例子

加载allegro默认颜色文件，并更新allegro显示:
axlColorLoad(nil)
axlVisibleUpdate(t)



### axlMKSConvert 单位转换函数


axlMKSConvert可将任何允许的单位转换为另外一个单位类型。

有两种使用方式：

axlMKSConvert(
n_input
t_inUnits
[t_outUnits]
)
&#8658; f_output/nil
将输入的 n_input 数字从t_inUnits 转换到 t_outUnits，并将转换后的结果通过f_output返回

各个参数说明如下：
n_input 需要转换的数字
t_inUnits 输入转换数字的单位
t_outUnits 输出转换数字的单位，如果为nil，则为当前layout使用的单位

f_output 转换输出的结果


例子：
(axlMKSConvert .5 "MILS" "INCHES) -> 0.0005
复制代码
axlMKSConvert还可以通过以下方式使用：

axlMKSConvert(
t_input
[t_outUnits]
)
&#8658; f_output/nil

与上面不同的是，将n_input、t_inUnits合并到t_input参数里面了。

例子：
(axlMKSConvert ".5 MILS" "INCHES) -> 0.0005