---
title: 'AXL-SKILL 函数简介'
date: Thu, 07 May 2020 06:22:38 +0000
draft: false
tags: ['Allegro Skill']
---

简介
==

AXL-SKILL
---------

专用于allegro的skill被称为AXL-SKILL，只有使用这些专用的函数才可以直接访问allegro的database。结合skill语法和这些专用函数可以编写出实现各种功能的命令。专用于allegro的skill都是以axl开头，比如axlClearSelSet()。

运行AXL-SKILL
-----------

在allegro中输入skill就得到了AXL-SKILL的运行环境，在这样的环境中可以直接调用AXL-SKILL命令/函数，另外输入set telskill可以得到一个尺寸大小可调的skill开发窗口。（如果没有弹出窗口，尝试在allegro菜单里面，选择setup->user prference->skill->telskill----OK）

AXL-SKILL Database
------------------

allegro中的每个对象object(比如IC元件，net)都有一个对应的dbid(database identifiers)，AXL-SKILL操作allegro的也正是这些dbid。

dbid对象：在不同的级别上的dbid是不一样的，比如在Design以及包含的database对象有

Property Dictionary， Lines， Text， Polygons， Shapes， Property Definitions， DRCs， Vias that are Padstack object types， Symbols that are Symdef object types， Components， Nets；

而在Symbol级别上则是

Pins that are Padstack object types， Vias that are Padstack object types， Lines， Arcs， Text， Polygons， Shapes。

[Database Read Functions](https://a1024.synology.me:1024/?p=2942)
-----------------------------------------------------------------

[Form](https://a1024.synology.me:1024/?p=2322)
----------------------------------------------

[Command Control Functions 控制和命令](https://a1024.synology.me:1024/?p=2489)
-------------------------------------------------------------------------

[Selection and Find Functions选择和查找功能](https://a1024.synology.me:1024/?p=2495)
-----------------------------------------------------------------------------

[Logic Access 操作](https://a1024.synology.me:1024/?p=2509)
---------------------------------------------------------

[Design Control Functions 设计控制功能](https://a1024.synology.me:1024/?p=3856)
-------------------------------------------------------------------------

Interface界面
-----------

axlMsgPut

axlUIPopupDefine

### axlHighlightObject、axlDehighlightObject

高亮对象和取消高亮对象

两个函数中的t参数，如果设置代表使用永久高亮颜色，如果不设置则使用临时高亮颜色

```
axlHighlightObject( axlGetSelSet() t)
axlDehighlightObject( axlGetSelSet() t)
``````
(axlDehighlightObject ((axlDBGetDesign)->symbols))
(axlVisibleDesign nil) 
(axlVisibleLayer "ETCH" t) 
(axlClearSelSet)
(axlSetFindFilter ?enabled '("NOALL" "clinesegs") ?onButtons '("NOALL" "clinesegs")) 
(lSeg = (axlGetSelSet (axlAddSelectAll))) 
(axlClearSelSet) 
(axlDehighlightObject lSeg)
```

### axlUIMultipleChoice

显示一个对话框，其中包含一个问题，其中包含一组两个或多个答案的列表。 您必须选择其中一个答案才能继续。 返回选择的答案的序号，0是第一个序号

```
listtype = '("Net Class" "Bus" "Net Group")
ret = axlUIMultipleChoice("Please select a group type to creat pinpairs" listtype "which one")
(case ret
	(0 allclass = axlDBGetDesign()->netclass selecttext = "Net Class")
	(1 allclass = axlDBGetDesign()->bus selecttext = "Bus")
	(2 allclass = axlDBGetDesign()->netGroup selecttext = "Net Group")
)
``````
axlUIMultipleChoice => axlUIMultipleChoice("Pick a layer" '("top" "bottom" ) "View Layer")
```

这里介绍一下其中几个很常用的函数的用法

### axlUIConfirm

在确认窗口中显示字符串 t\_message。

```
axlUIConfirm(t_message [s_level]) ==> t
```

*   t\_message：Message string.
*   s\_level：Option level symbol; default is info level, other levels are warn and error.

```
axlUIConfirm("are you sure to delete all highlight shapes?")
```

### axlUIYesNo

提供显示消息 t\_message 的对话框。 如果您选择 Yes，则返回 t，No 则返回 nil。

```
axlUIYesNo(t_message [t_title] [s_default]) ==> t/nil
```

*   t\_message：Message string to display.
*   t：User responded Yes.
*   nil：User responded No.

```
axlUIYesNo( "Overwrite module?" )
axlUIYesNo( "Overwrite module?" nil 'no )
axlUIYesNo( "Overwrite module?" "My Skill Program" )
axlUIYesNo("are you sure to delete all highlight shapes?" "Delete Shape Command")
```

### axlUIYesNoCancel

基本和axlUIYesNo一样，选项增加到三个，返回值有区别

```
axlUIYesNoCancel(t_message [t_title] [s_default]) ==> x_result
```

*   x\_result: 0 for No, 1 for Yes and 2 for Cancel.

Tips：axlUIConfirm只是个提醒，返回值总是t，另外两个返回值是数字0=>Yes, 1=>No, 2=>Cancel。

### axlUIPrompt

```
axlUIPrompt(t_message [t_default]/'password) ==> t_response/nil
```

axlUIPrompt这个函数提供了用户输入信息的功能，返回值为字符串，如果你想要数字，需要自行转换，atoi/atof之类。

```
axlUIPrompt( "Enter Your Name" "user name" )
axlUIPrompt( "Enter module name" "demo" )
```

axlClearDynamics  
axlAddSimpleRbandDynamics  
axlAddSimpleMoveDynamics  
axlDesignFlip  
axlEnterPoint  
axlEnterString  
axlEnterAngle  
axlCancelEnterFun  
axlFinishEnterFun  
axlGetDynamicsSegs  
axlGetLineLock  
axlEnterBox  
axlEnterPath  
axlMiniStatusLoad  
axlDrawObject  
axlDynamicsObject  
axlEraseObject  
axlControlRaise  
axlEnterEvent  
axlEventSetStartPopup  
axlGetTrapBox  
axlRatsnestBlank  
axlRatsnestDisplay  
axlSetDynamicsMirror  
axlSetDynamicsRotation  
axlShowObjectToFile  
axlUICmdPopupSet  
axlZoomToDbid  
axlMakeDynamicsPath

显示
--

### Database Layer相关操作函数

```
这里给出一些方便操作Layer的函数：      
```

**axlVisibleGet**

该函数的返回值是命令运行当前design的可见性 - 哪些层可见/不可见

```
visList = axlVisibleGet();找个设计查看结果输出
```

**axlVisibleSet**(l\_vislist)

该函数使用**axlVisibleGet**()函数的返回结果，重置design的显示状态。

**axlGetXSection**()，这是获取design的**crosssection**(层叠结构)的函数；

**axlLayerGet**(t\_layer)，这是获得指定层t\_layer的dbid的函数；

**axlIsLayer**(t\_layer)，判断指定的层t\_layer存不存在；

**axlIsVisibleLayer**(t\_layer)，判断指定层t\_layer是不是显示状态(visible)；

**axlVisibleLayer**(t\_layer g\_makeVis)，设置指定层t\_layer的状态是显示还是不显示；

**axlVisibleDesign**(g\_makeVis)，设置design的状态是显示还是不显示；

```
when(axlIsLayer("Board Geometry/Design_Outline")
        axlVisibleLayer("Board Geometry/Design_Outline" t)
        )
```

axlVisibleUpdate

axlUIWUpdate

更多相关函数请参考algroskill.pdf文档

### axlVisibleGet

```
(vis = (axlVisibleGet));将当前显示存为vis
;do sth
(axlVisibleSet vis);恢复存储的vis显示状态
```

### 示例：选择一个Symbol，并将其移动到另一个相对位置

axlTransformObject() 函数的作用是将一个或多个symbol由一个地方移动、翻转、旋转到另一个新的位置。  
axlTransformObject( ; lo\_dbid/o\_dbid ; ?move l\_deltaPoint ; ?mirror t/nil ; ?angle f\_angle ; ?origin l\_rotatePoint ; ?allOrNone t/nil )

```
axlClearSelSet(); 清除之前可能存在的被选择函数选择的元素，避免引入不合适的dbid，这是个好习惯    
axlSetFindFilter(?enabled '("noall" "symbols" ) ?onButtons '("noall" "symbols" )); 设置Find Filter的Symbols选项处于选中状态  
axlSingleSelectPoint();  请通过点击选择的方式，选择一个Symbol对象
dSym = axlGetSelSet(); => (dbid)，将得到被选择的dbid列表，尽管这个列表只有一个元素
axlClearSelSet(); 清理掉你自己做过的选择，避免给别的程序带来错误，同样是个好习惯
dSym = car(dSym); => dbid，的到Symbol的dbid    ;dSym->?? ;=> 将得到这个Symbol的相关属性    ix = 100;    iy = 200;    axlTransformObject(dSym, ?move ix:iy); =>将该Symbol右移100mil，上移200mil    ; 
```

### axlEnterPoint

提示并接收用户选择的点。 将点数据返回给调用函数。默认gridSnap is nil、prompt is "Enter point"

```
point = axlEnterPoint(?prompts "Please pick" ?gridSnap t)
snappedPoint = axlEnterPoint(?gridSnap t ?points '((3162.0 1315.0)))
snappedPoint = axlEnterPoint(?gridSnap t ?points list(3162.3 1315.8))
```

Polygon Operation Functions
---------------------------

Polygon是多边形的意思，其实和Shape一样(根据Polygon生成的Shape，所以当然是一样的)，只是Polygon是不可见的，而 Shape是可见的。Polygon的操作函数之所以不并入Shape我想可能是因为每次对Shape形状的改变allegro都会update整个 design的shape，顺便还要update DRC(Shape和On-Line Drc没有disable的情况下)，这都是些很耗时的操作。Polygon的任何操作都不会影响到design，直到当它最后呈现为Shape时。

### axlPolyFromDB

获得指定对象的Polygon，这是一个非常好用的函数，比如有个形状很怪异的Pad，而你必须根据这个Pad画出个 Shape，这个时候你就可以直接用这个命令直接得到那个Pad的Polygon,然后就可以生产Shape了，

```
padbox = car(pins)->bBox
mypath = axlPathStart( list(car(padbox) caadr(padbox):cadar(padbox) cadr(padbox) caar(padbox):cadadr(padbox) car(padbox)) 0)
(pin_poly = car((axlPolyFromDB mypath ?endCapType "ROUND" ?padType 'REGULAR))) 
```

### axlPolyOperation

Polygon的一些操作，比如多个Polygon以某个规则(AND OR ANDNOT)组合到一起,形成一个/多个新Polygon。

### axlPolyExpand

将Polygon外扩/內缩一定的尺寸

axlPolyMemUse  
axlPolyOffset  
axlIsPolyType  
axlPolyFromHole  
axlPolyErrorGet

实现allegro的merge shape的命令

*   选择需要被merge的Shape
*   使用axlPolyFromDB函数得到每一个Shape的Polygon
*   使用axlPolyOperation函数的"AND"规则，将多个Polygon形成一个
*   删除选中的所有Shape
*   使用下面将要提到的axlDBCreateShape命令生成新的Shape

#### Shape部分函数

Shape是几何图形，所以Create Shape通常需要先提供一个boundry(Shape的边界/区域)，而这通常有2种方式，其一是使用上面讲到的Path函数来Create一个闭合的区域，其二是用Polygon函数来为Shape提供一个Polygon。

Shape相关函数

axlDBCreateOpenShape，这个函数是用来Create一个Open状态的Shape的，Open的意思是可以在Create的Shape上再添加Void。 axlDBCreateCloseShape，这个函数是前一个函数的补充，Open状态的shape使用了这个函数就被Close了，Close意思是Shape不可以再添加Void了。 axlDBCreateShape, 这个函数直接Create一个Close的Shape。

Database操作相关函数
==============

```
这里又有一组比较好用的函数    
```

*   **axlTransformObject**()，早已经在之前的章节介绍了。
*   **axlDBCloak**(g\_func \[g\_mode\])，将一些可能会引起shape update或者drc update之类的比较耗时的函数/命令嵌入在这个命令中运行会比较省时。

### axlDBTransactionStart

标记数据库transaction的开始。 向调用者返回一个标记，该标记被传递回嵌套transaction的提交、标记、oops 或回滚。 只有此函数的最外层调用者（第一个调用者）有权控制提交或回滚整个transaction。

您可以将此函数与其他 axlDBTransaction 函数一起使用。

### axlDBTransactionMark

在数据库中写入一个标记，您可以将其与 axlDBTransactionOops 一起使用以将数据库更改回滚到此标记。

当提交或回滚事务标记时，与该标记关联的所有axlDBTransactionMark都将被丢弃。

Emulating the Allegro "oops" model.

```
 mark = axlDBTransactionStart()
      .. #1 do stuff ..
      axlDBTransactionMark(mark)
      .. #2 do stuff ..
      axlDBTransactionMark(mark)
      .. #3 do stuff ..
 
      ;; do an oops of last two changes
      axlDBTransactionOops( mark )               ; oops out #3
      axlDBTransactionOops( mark )               ; oops out #2
      axlDBTransactionCommit(topList)            ; commit only #1
```

Multiple Start marks

```
 i = axlDBTransactionStart()
         ... do stuff...
 
         j = axlDBTransactionStart()
         ... stuff...
         axlDBTransactionCommit(j)      ;; this is not really commited
                                         ;; til the outer commit
                                 
         j = axlDBTransactionStart()
         ... do more stuff...
         axlDBTransctionRollback(j)  ;; oops out "do more stuff"
 
     axlDBTransactionCommit(i)      ;; commit changes to database
```

### axlDBTransactionRollback

是database Transaction的一次Undo操作，相当于allegro中的Cancel操作。

### axlDBTransactionCommit

确定一次transaction的完成，之后n\_Mark将不再有效，也即不能再执行Oops/Rollback操作了，相当于done

### axlDBTransactionOops

取消最近一次的axlDBTransactionMark以来的操作，使得design返回Mark前的状态。和allegro中的Oops命令是相似的。

另外：举个简单的例子说明为什么这个命令好用。假设你要编写一个实现Symbol横向或者纵向对齐的命令，最简单的想法就是让用户选择需要移动的 Symbol，然后记录下各个Symbol的 coordinate，rotation，mirror，name，type等等参数，对应于Opps或者Cancel操作就是利用之前备份的那一大堆数 据来恢复现场。这里涉及一大堆的数据管理，而且当用户同时选择了n个symbol然后又去掉了部分选择，以及在done掉命令之前有做过几次Opps和几 次transaction，这个数据的管理会很让人伤脑筋。然而通过这里介绍的几个命令，就很简单了，只要在transaction之前Mark一下(记 录现场)，Opps，Cancel之类的操作只是简单的恢复到Mark点就好了，不用管Mark以后用户是怎么个操作的，是不是很简单？

读数据
---

### axlIsLayerNegative

判断设计层是否为负片

```
poetchlayerlist = nil
etchs = axlGetParam("paramLayerGroup:ETCH")->groupMembers
(foreach etch etchs
    etchlayer = strcat("ETCH/" etch)
    when(axlIsLayerNegative(etchlayer) == nil
    	poetchlayerlist = cons(etch poetchlayerlist)
    	)

)
```

environment and command 设置和命令
-----------------------------

### axlSetVariable

设置Allegro的环境变量值

*   变量名称和值可能会因为软件版本不同而不同
*   变量仅适用用当前会话，不会被保存至ENV中

```
The following example sets the new library search path "libpath".
axlSetVariable("libpath" "/mytools/library")
==> t
libraryPath = axlGetVariable("libpath")
==> "/mytools/library"
Using list mode:
axlSetVariable("psmpath" '("." "symbols"))
==> t
axlGetVariableList("psmpath")
==> ("." "symbols")
```

### axlUnsetVariable

类似axlSetVariable，将指定名称的环境变量值变为nil

```
(axlUnsetVariable "libpath");==> "/mytools/library"
libraryPath = (axlGetVariable "libpath");==> nil
```

### axlSetVariableFile,axlUnsetVariableFile

设置Allegro的环境变量值 ,并保存到ENV文件中

### axlGetVariable

获得某个环境变量的值

```
menu = axlGetVariable("menuload")
==> "geometry"
psmpath = axlGetVariable("psmpath")
==> ". symbols"
axlGetVariable("ALLEGRO_BRD2ODB")
axlGetVariable("home")
```

其它
--

### axlAirGap

两个给定对象的间隙距离，可指定层

```
axlAirGap(o_item1 DBIDo_item2 DBID[t_layer]/nil [s_mode])==> l_airGapData/nil/(s_error l_airGapData/l_errorData)
``````
 Basic input
axlAirGap(el1 el2)-> ((1337.5 1100.0) (1362.5 1100.0) 25.0)

Basic input layer
axlAirGap(el1 el2 "TOP")-> ((1337.5 1100.0) (1362.5 1100.0) 25.0)

Full output success
axlAirGap(el1 el2 nil t)-> (t ((1337.5 1100.0) (1362.5 1100.0) 25.0))

Any layer airgap
q = axlAirGap(el1 el2 nil 'anyLayer)

Enhanced output
q = axlAirGap(el1 el2 nil 'enhanced)

Obtain soldermask spacing
axlAirGap(via1 pin2 ""PIN/SOLDERMASK_TOP" )-> (((1337.5 1100.0) (1362.5 1100.0) 40.0))

Full output failure
axlAirGap(el3 el2 nil t)-> (RANGE ("TOP" "GND"))
```

### axlDBCreateRectangle

按坐标创建一个矩形

```
axlDBCreateRectangle(list(100:100 200:200))
axlDBCreateRectangle(list(200:200 400:300) t)
rect = axlDBCreateRectangle( axlEnterBox() t "ETCH/TOP" 45.0 "net_1")
```

### axlDBAddProp

为对象增加属性

```
rect变量来自于上文axlDBCreateRectangle
axlDBAddProp(car(rect),  list("ROUTES_ALLOWED"))
axlDBAddProp(car(rect),  list("VIAS_ALLOWED"))
```

axlFinishEnterFun

### axlVersion

返回 Allegro PCB Editor 或操作系统相关数据。

```
axlVersion('version)  ;当前设计版本
```

allegro skill Database操作相关函数
----------------------------

### axlMKSConvert

根据传递的参数，以多种方式操作。

典型用途，从设计单位转换为另一种类型（设计单位为mil）

```
axlMKSConvert("80 mils" car(axlDBGetDesignUnits()));80mil转换为当前设计的单位值为多少
axlMKSConvert(.5 "design" "INCHES") => 0.0005
axlMKSConvert(".5 millimeters" "mils") => 19.68504;0.5mm转换为mil后值为多少
axlMKSConvert(39.37 "design" "millimeters") => 0.999998 ;当前设计单位39.37对应到mm的值应该是多少
``````
axlDBGetAttachedText(o_dbid) => text dbid
```

得到o\_dbid对象所具有的(被attached的)text的dbid列表。该函数常用于在一个包含很多text的symbol对象上查找特定text的应用中。比如我们通常会把一个design放在适当尺寸的sheet中，对应于design的各个层，sheet也会有对于的页码来表示，比如sheet的第1页是Top层，那么int1层可能就是第2页，如果你想写个程序来实现页码的自动更新，就会用到这个函数来找到需要被修改的字符 (text)，然后用后面将要说到的Database Create相应函数来修改选中的字符。

```
axlDBGetPad(o_dbid t_layer t_type) => pad dbid
```

获得pin，via，padstack相应层的特定pad。

```
axlDBGetPad (dpin “Etch/Top" ”anti“)=>dpin
```

对象在Top层的anti-pad的dbid。通过这个dbid又可以进一步得到pad的一些相关属性。

```
axlDBGetPropDictEntry(t_name) => propdefinition
```

得到user defined properties里面设置的各个属性的信息，比如属性类型，应用的对象。

```
axlDBGetProperties(o_dbid [lt_type]) => l_results
```

得到o\_dbid所具有的properties列表，allegro默认的或者是user defined。

```
axlDBIsFixed(o_dbid) => t/nil
```

判断一个对象是不是被fixed了。通常在用户程序想修改一些design的对象的时候，必须先确定该对象是不是被fixed了，fixed 对象是不可以被修改的。(用户必须先给fixed的对象un-fixed，然后才能进行修改)

```
axlDBGetShapes(t_layer) => shape dbid
```

一种获取指定层所有shape的快捷方式。(通常的获取对象的方式都是先要设置FindFilter，然后addselect，再getselset，3步才可以。)

### Database Create

首先allegro本身不支持的操作使用下面将要给出的AXL-Skill函数也是无法实现的。比如allegro不支持将一个cline画到非Etch 层去，那么用axlDBCreatePath()也无法在非Etch层Create一个cline的。对于非法操作，函数的返回值都是nil。

要想让你create的对象立即显示出来有2种方法，运行axlDisplayFlush()命令来刷新allegro的显示状态，或者运行一个allegro本身的命令，否则的话你create的对象是不会被显示出来的。

#### Path部分的函数

```
Path指的是各种形状的Line。Path总会有个起点有个终点，axlPathStart函数用于确定起点，而终点则是Path里面的最后一点。  
``````
axlPathStart(l_points [f_width]) => r_path,产生一个path对象并确定起点  
axlPathArc(Radius/Angle/Center) => 这里的三个函数都是用来生成曲线的  
axlPathLine() => 向一个path末尾添加一个点  
axlPathGetWidth(r_path) => 得到一个path的宽度，如果一个path中的各个segment的宽度都不一样，可以使用axlPathSegGetWidth()函数。  
axlPathSegGetEndPoint(r_pathSeg) => 得到path的最后一个点，
```

axlPathGetLastPathSeg()用来得到path的最后一个segment。 axlDBCreatePath()和axlDBCreateLine()，将不可见的path或point列表转变成可见的实际存在的 Line，Create在不同的layer，将产生不同的对象，比如在Etch layer将产生Cline对象，在Silkscreen layer就是些简单的Line。

#### 和Path无关的函数

axlDBCreateExternalDRC，create一个用户自定义的DRC，通常是在用户自定义的检查中 axlDBCreatePadStack，Create一个新的Padstack，比如你想要用一种新的Via，但是Library中还没，就可以使用该命令Create一个Padstack,然后用axlDBCreateVia命令生成一个 axlDBCreateText，比如前面提到的自动修改字符的操作，这个命令就可以生成指定的字符。

#### Property函数

axlDBCreatePropDictEntry，在user defined property列表中创建一个新的property类型 axlDBAddProp，将指定的property赋予特定的对象，比如将Fixed Property赋予一个Component，这个和allegro本身的Fixed命令是一样的。

### Database Group

```
Group比较简单，相关的函数也不是很多。    
```

*   axlDBCreateGroup，create一个新的Group对象
*   axlNetClassCreate，create一个NetClass对象
*   axlRegionCreate，create一个Region对象

NetClass和Region是16.0以后新的属性

### Database Attachment

这里说到的Attachment是attach到design的database中的。

**axlCreateAttachment**(t\_attachmentId t\_passwd x\_revision s\_dataFormat t\_data ) Create一个名字/ID是t\_attachmentId的attachment，t\_password设定密码，x\_revision确定版本，s\_dataFormat将决定t\_data的数据类型。

**axlGetAllAttachmentNames**() 得到design Database中所有attachment的dbid列表。

**axlGetAttachment**(t\_attachmentId \[s\_dataFormat\]) 获得指定attachment的value。

### Database Transaction

### Database Miscellaneous

举几个很适用的函数，其它的请自行参考学习了。

**axlAirGap**()，功能如同allegro中的Measure结果中的Airgap。

**axlDBGetLength**()，功能如同allegro的Show Element命令选择一个Cline显示长度一样。

**axlGeoPointInShape**()，这个命令能检验一个Point是不是在特定的Shape里面。

**axlChangeNet**()，改变指定对象的net name，不过因为一些功能方面的限制，其实适用性不强

allegro skill Parameter操作函数正如在allegro skill database对象类型中提到的，一个PCB Editer设计中会有很多的Parameter，比如在design级别就有设计的精度，设计的版面尺寸，单位等等。在AXL-Skill中有一系列相 应的函数可以直接读取以及修改这些Parameter值。 2. 1 获取Parameter值的通用函数

#### 获取Parameter值的函数 axlGetParam

函数定义：axlGetParam ( t\_parm\_name ) => o\_paramDbid/nil 参数t\_parm\_name要求：被查询的parameter的名字。

这个名字必须符合如下规则：

paramTextBlock:<#> where # is 1-16 (Example: axlGetParam("paramTextBlock:1"); 默认的block只到16，对于大于16的block，如果系统里面有设定就可以同样得到，比如说有block 30，就可以这样得到axlGetParam("paramTextBlock:30") )

paramDesign

```
paramDisplay                      
``````
paramLayerGroup:<name> where name is legal Allegro class name               paramLayerGroup:<name>/paramLayer:<name>                    
``````
artworkList of film names        artwork:<filmNameA film given by filmName    testprep            返回值o\_paramDbid：返回值是个param型的dbid，该dbid将可用于axlSetParam函数来修改相应的Parameter。            
``````
**示例：**
```

**axlGetParam**( "paramDesign") => param:107955700(返回一个param类型的dbid, 该dbid包含了design的parameter信息)

**axlGetParam**("paramLayerGroup:ETCH") => param:107955760(返回的dbid包含系统的ETCH相关信息，比如有几个ETCH层)

axlGetParam("paramLayerGroup:ETCH")->?? => (objType "paramLayerGroup" name "ETCH" visible nil nChildren 4 groupMembers ("TOP" "INT1" "INT2" "BOTTOM") color -1)(说明：axlGetParam("paramLayerGroup:ETCH")将得到一个dbid，而->??操作将得到该dbid的所有直接相关属性，objType说明该dbid的对象类型是paramLayerGroup，nChildren=>4表面当前的design有4 个Etch层，groupMembers对应了具体的4个Etch层名字)

axlGetParam("paramLayerGroup:ETCH")->groupMembers => ("TOP" "INT1" "INT2" "BOTTOM")

#### 设置Parameter值的函数 axlSetParam

函数定义：axlSetParam ( o\_paramDbid ) => o\_paramDbid/nil

参数o\_paramDbi要求：axlGetParam函数的返回值

返回值o\_paramDbid：返回值类型和axlGetParam返回的一样

使用方法：Originalparam = axlGetParam( "paramDesign")，

做一些其它的操作可能涉及到多个系统参数的改变，然后通过axlSetParam(Originalparam)命令来使系统所有的参数设置恢复之前保留的值。（参考后面提到的类型相似的axlVisibleGet和axlVisibleSet函数）

### Color操作函数(部分)

#### Allegro中的Color

Allegro支持2种访问Color的方式，预定义的color和allegro database color。

预定义的color有'black，‘'white，'red，'green，'yellow，'blue，'multivalue - use dfor fields where value not the same，'button - current color of button faces (grey)。

database color是以\[1-24\]之间的整数表示的，0被保留为背景颜色。

#### 常用Color相关函数

获取Color调色板

axlColorGet(x\_number/'background/'count/'all), 如axlColorGet('all)=>得到系统的颜色设置结构列表。对应设置Color调色板函数，axlColorSet()；

系统颜色设定的保存与重载函数，axlColorSave(file)与axlColorLoad(file)；

用户定制颜色来设置系统中的元素，axlCustomColorObject(\[lo\_dbid\] \[g\_custom\_color\])，

相应的清除命令为axlClearObjectCustomColor(\[lo\_dbid\])；

其它更多的color相关函数请参考algroskill文档

Constraint Manager操作函数
----------------------

```
所有的Constraint Manager相关的函数都会是以axlCNS开头，如：    
```

axlCnsAddVia(); axlCNSCreate(); axlCNSGetPhysical(); axlCNSGetSpacing();

Math函数
------

### axlDistance

获得两个坐标的距离

```
axlDistance(10:20 5:20) = 5.0
```

axlGeoEqual(); 在当前design精度下，比较2个浮点数是否相等

axlIsPointInsideBox(); 检查点是不是在Box里面

axl\_ol\_ol2(); 检查两个线是否相交

其他
--

allegro skill选择和获取函数对Allegro中的对象进行操作，比如移动、删除，都需要先选择和获取该对象的dbid。选择操作包含一些选择设置比如是只选 择Symbol还是 Symbol和Via都可以选等等，然后通过axlSelect相关函数来选择具体的对象，然后是axlGetSelSet函数来得到那些被选择的 dbid。 AXL-Skill函数支持多种选择的方式，比如单选择一个对象，或者是框选多个对象，又或者说是使用Temp Group的方式来选择多个对象，不过通常对象只有在当前可见(Visible)的情况下才可以被选择上(除非设置了invisible选项)。选择设置 和被选择了对象的有效性会一直持续到用户使用其它的系统命令，比如allegro的Add Cline命令，因为allegro的命令将会改变一些系统的dbid，所以的Skill之前获取的bdid都会变成无效的(removed)。通常的选 择和获取操作如下，

设置Find Filter来控制将要被选则的对象类型； 选择对象的三种模式：单选，多选或通过名字来选择； 从被选择的对象中添加和移除对象

skill交互函数axlUI系列集锦 Interface指和用户交互，allegro给出一些Message提醒用户进行相关的操作，比如说Pick a Point就是让用户用鼠标选择一个点；又比如说allegro弹出一个Confirm对话框，需要用户选择Yes/No的情况。在allegro的 skill窗口输入\_lfn("axlUI")一般会查到如下的函数：

axlUICmdPopupSet

axlUIColorDialog

axlUIControl

axlUIDataBrowse

axlUIEditFile

axlUIGetUserData

axlUIMenuDump

axlUIMenuLoad

axlUIPopupDefine

axlUIViewFileCreate

axlUIViewFileReuse

axlUIViewFileScrollTo

axlUIWBeep

axlUIWBlock

axlUIWClose

axlUIWDisableQuit

axlUIWPerm

axlUIWRedraw

axlUIWSetHelpTag

axlUIWSetParent

axlUIWTimerAdd

axlUIWTimerRemove

  
最后还有一个 axlUIWBeep()，就是一个beep提示音

axlUIWDisableQuit => axlUIWDisableQuit(userDefinedForm) ;屏蔽掉form右上角的那个close叉叉

axlUIWClose => axlUIWClose(userDefinedForm); 关闭掉form

axlUIWPerm => axlUIWPerm(userDefinedForm t); allegro打开新的板子会默认关闭掉当前打开的所以的form窗口，用这个命令可以屏蔽这个功能 axlUIWBlock => axlUIWBlock(userDefinedForm);强制用户操作了当前的form才可以继续其它的工作

axlUIWRedraw axlUIWUpdate => axlUIWUpdate(nil)这个和axlUIWRedraw(nil)更适合刷新主屏幕

axlUIDataBrowse axlUIColorDialog 这2个函数调用allegro系列的form，挺有用的。

参考algroskill.pdf中的例子：

axlUIDataBrowse('NET '(RETRIEVE\_NAME) "hi" t) rgb = axlColorGet(1) rgb = axlUIColorDialog(nil rgb) when( rgb axlColorSet(1 rgb) ) 这里的1可以是其它的数字，16.0以上可以到192。

axlUIMenuDump=>axlUIMenuDump("CurrentMenu") 输出当前allegro的menu信息到当前工作目录的CurrentMenu.men文件 axlUIMenuLoad=>axlUIMenuLoad("menu.men") load menu.men的信息到allegro中建立新的目录很实用的2个功能

axlUIViewFileCreate axlUIViewFileReuse axlUIViewFileScrollTo 只读方式打开文件，没怎么用过，也觉得没有啥用处。还剩下几个除了Time可能有些作用，其它的没有没有什么感觉。

axlUIWTimerAdd

axlUIWTimerRemove

axlUIControl（ do not use ）

axlUIEditFile

axlUIGetUserData

axlUIWSetHelpTag

axlUIWSetParent

allegro skill 交互式编辑函数这里介绍一些基本的编辑命令，比如axlDeleteObject用来删除可被删除的系统对象(各种 dbid)，axlShowObject用来显示被选择对象的信息，和allegro中的Show Element命令显示的结果差不多。常用函数示例：

axlChangeWidth(); => 和Allegro中的Change命令类似，该命令用来改变Cline/Line的宽度

#### axlDBDeleteProp

该命令可以删除选择对象的指定属性，使用该命令相当于Allegro中Edit Property命令。

删除指定属性，属性名称可以从信息面板查看

下述案例可删除设计中所有的锁定属性，即解锁所有元器件。

axlDBDeleteProp(axlDBGetDesign()->symbols "FIXED")

axlDBDeletePropDictEntry(); =>该命令相当于Allegro中的User Defined Property命令 axlLastPick(); => 获得用户鼠标最近一次点击的坐标

axlShapeChangeDynamicType(); =>改变选择Shape的动静态属性 axlTransformObject(); =>移动对象

另外：

axlEnterString() ; 提示用户输入一个字符串

axlCancelEnterFun(); 取消一个提示Enter操作的函数的作用

还有一些比如

axlHighlightObject(); highlight对象

allegro skill Shell操作相关函数这里的函数可以用来读取Allegro PCB Editor的环境参数，比如Alias，FuncKey以及一些

系统的参数(.psmpath)。比如：

axlGetAlias()

axlGetFuncKey()             

axlSetAlias()         

axlSetFunckey()         

另外：axlShell()，这个命令很有用，它支持在skill环境中运行allegro的命令，比如allegro的status命令，在skill状态下是不可以直接运行的，需要通过axlShell("status")来运行。

另：设置和获得windows/UNIX系统下的环境变量 setShellEnvVar() getShellEnvVar()

  
allegro skill ipc ipc是Interprocess Communication的缩写，ipc使得skill对创建其它非skill进程和与之通信成为可能。比如如果一个skill工具要求比较复杂的界 面，而这个界面用skill来完成会很麻烦，这样就可以试着用其它的语言(java)写出要求的界面并生成可执行文件(jar)，用ipc相关的函数来调 用这个可执行文件，并传递相关的参数，用户在该界面上做的任何操作也会有相应的函数读回并执行。 ipc的功能极大的方便了用户做开发。

父进程通过ipc和子进程通信 1. 如何通信父进程通过子进程的stdin将信息传递给子进程，从子进程的stdout和stderr读取返回信息。 e.g. 一个简单的perl程序＃! /usr/bin/perl -w print $ARGV\[0\]; getinfo; sub getinfo {

```
return $ARGV\[1\];
```

} 如果用ipcBeginProcess调用这个简单程序，这个程序运行以后， ipcReadProcess读到的返回值将会是print输出的值。

2\. 同步，异步读取子进程返回信息同步读取会屏蔽当前操作直到读取完成，异步读取会等到数据和父进程中处理函数都准备好的时候发生，不会屏蔽别的程序运行。

3\. 数据缓存一般的标准输入输出通道有4096byte的缓存区，通常子进程在将数据写入输出通道后推荐刷新该端口使得父进程可以顺利读到这些输出。

4\. 子进程的属性子进程通常有如下的只读属性, 和其它的skill对象一样可以通过"->"来读取。 command Name of the command host Name of the host machine running the process processPid Process id of the child process on host exitStatus Exit status of the child process priority Priority given to the child process type Begin, Skill, or Batch process state Active, Dead, or Stopped

5\. 几个主要的ipc函数 5.1 ipcBeginProcess 5.2 ipcSkillProcess 5.3 ipcWaitForProcess 5.4 ipcReadProcess 5.5 ipcWriteProcess 5.6 ipcIsActiveProcess 5.7 ipcIsAliveProcess 5.1 ipcBeginProcess 该函数用来调用别的程序并返回子进程， 函数定义如下： ipcBeginProcess(

```
t\_command      \[ t\_hostName \]      \[ tsu\_dataHandler \]      \[ tsu\_errHandler \]      \[ tsu\_postFunc \]      \[ t\_logFile \]    )
```

\=> o\_childId 参数解释，

```
t\_command=> 要执行的程序/命令，比如linux里面的命令date；      t\_hostName=>被调用的命令执行的环境，null也就是“”表示在本地执行；      tsu\_dataHandler/errHandle/postFunc=>这3个参数用来处理子进程的输出，如果设置了相应的处理函数就是异步读取方式，这种方式会自动读取子进程的返回值，如果没有设置则是同步读取方式，这种方式下就必须显式的用命令 (ipcReadProcess,ipcIsActiveProcess...)来读取子进程的输出值或者状态；    t\_logfile=>用来记录所有的子程序的输出信息。
```

示例：

```
同步读取  cid = ipcBeginProcess("date") => ipc:0  ;子进程0                      
``````
ipcReadProcess(cid) =>"Tue Aug 1 14:23:07 PDT 1995\\n"  ; 显式的读取子进程的输出值
``````
异步读取 handler = (lambda (cid data) printf("\\n Date:%s\\n" data))=>funobj:0x2848e8 ;定义输入数据处理函数        
``````
        cid = ipcBeginProcess("date" "" handler)=>ipc:0  ；handler会自动处理子进程的输出数值                                                                                        Date: Tue Aug 1 14:29:17 PDT 1995
```

5.2 ipcSkillProcess 这个函数类似于ipcBeginProcess, 只是增加了对子进程可以在父进程中执行skill命令的能力，以及设置了2个专门的通道方便子进程输出skill命令到父进程执行并读取执行的结果。函数 定义： ipcSkillProcess(

```
t\_command      \[ t\_hostName \]      \[ tsu\_dataHandler \]      \[ tsu\_errHandler \]      \[ tsu\_postFunc \]      \[ t\_logFile \]      \[ x\_cmdDesc \]      \[ x\_resDesc \]      )
```

\=> o\_childId 参数解释:

```
x\_cmdDesc=> skill命令输出通道，默认为3        x\_resDesc=> skill运行结果接受通道，默认为4
```

示例请参考ipc文档P44.

5.3 ipcWaitForProcess 父进程调用子进程的时候，可能由于系统的延时子进程不能即刻就执行，考虑到这样的一个延时用ipcWaitForProcess就可以挂起父进程直到子进程运行起来。函数定义： ipcWaitForProcess(

```
o\_childId          \[ x\_timeOut \]      )
```

\=> t 参数说明:

```
o\_childId=> 子进程的ID          x\_timeOut=>等待的时间
```

5.4 ipcReadProcess

5.5 ipcWriteProcess 这2个是对子进程的读取和写入函数，具体内容参考ipc手册。

5.6 ipcIsActiveProcess

5.7 ipcIsAliveProcess 检查一个子进程是不是还有效，类似于查看子进程的state属性

dicusss：和VB通信， 2种情况， 一种是调用VB编写成的可执行程序，这种很简单，就是ipc调用该程序加上适当的参数，就好了。另一种是和VB编写的程序交互，这样就需要既输出数据给 VB的程序，也要从VB那边读相应的返回结果。主要涉及ipcBeginProcess和ipcSkillProcess这2个函数