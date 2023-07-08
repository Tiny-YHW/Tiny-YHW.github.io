---
layout: post
title: Skill Database User Model数据库（对象）类型属性及关系
categories: Allegro Skill
date: 2023-07-05
permalink: allegro-skill-database-user-model
excerpt: This chapter describes each AXL database object type, listing each type's attributes and relationships to other object types.
---

[Allegro Skill Database Read Functions](https://tiny-yhw.github.io//allegro-skill-database-read-functions){:target="_blank"}

16.6help Allegro PCB Editor-Allegro User Guide-Allegro SKILL Reference-The Allegro PCB Editor Database User Model

## Object Types 对象类型

### Figure图形

Arcs、Branches、Design Files、DRCs、Lines、Paths、Polygons、Pins、Shapes、Symbols、Tees 、Vias、Pads 、Padstacks、Symdefs

### Logical

Components、Functions、Function Pins、Nets

### Property dictionary

### Parameter objects

Design、Display、Layer Group、Layer、Textblock Group、Textblock

## Description描述

虽然一个数据库对象类型可以有几十个属性，但您只需要了解几个属性的语义即可从 Allegro PCB Editor 数据库中获取有用的信息。只要保证被访问的元素的dbid有效，就可以对其进行处理。请求不适用于对象的属性或对象上不存在的属性函数返回nil。

调用 axlShell函数或编辑新的 Allegro PCB Editor 数据库会使所有 dbid 无效。

使用超出范围的 dbid 访问对象的属性会产生不可靠的值。

axlDBRefreshId 函数为任何超出范围的 dbid 返回nil。

修改对象的一个属性的 AXL 函数可能会导致该对象的相关属性过期。  
当您修改其子属性之一时，父属性可能会过期。

## Data Types 属性值类型

AXL 数据库对象可以具有以下数据类型：

* bbox:Boundary box (list of two points, lower left andupper right of a rectangular area that encloses the object)
* integer: Signed integer number
* float:Floating-point number
* string:A string. For attributes with a list of possible stringvalues, the attribute description lists the allowed values.
* t/nil:Either true (t) or false (nil)
* dbid:Allegro PCB Editor object identifier
* l\_dbid:List of dbids
* point:A point--a list of two floats denoting a coordinatepair
* l\_propid:A list of properties accessed byaxlDbGetProperties
* l\_fill:t = solid; nil = polygon; _r\_fill_ = crosshatch type

### Generic Object Attributes 通用对象属性 属性名称

* objType:string Name of the object type
* prop:propid Attached properties
* parentGroups:l\_dbid List of groups to which the object belongs
* readOnly:t/nil t = cannot modify object with AXL function

### Figure类型

Figure在allegro PCB Editer里面一般被成为几何形状，一个Figure类型的元素通常具有如下的属性。

### 共同的Figure属性

```
属性名            类型              描述       
bBox           bbox        Figure’s bounding box        
branch         dbid        For etch, the figure’s branch parent          
layer          t\_layer     Layer of figure, nil **if** object is multi-layer        
parent         dbid        Nonconnective owner            
net            dbid        Net object **if** figure is associated **with** a net
```

注意: 对于所有空(dummy)网络的Figure, 它们的net属性都是"", 而不是nil。

#### Arc Attributes

* objType:"arc"
* isCircle: t/nil t = circle; nil = unclosed arc
* isClockwise:t/nil t = clockwise; nil = counterclockwise
* isEtch:t/nil t = a CLINE; nil = a LINE
* parent:dbid Path, polygon or shape
* radius:float Radius
* startEnd:l\_point Start and end points of arc
* width:float Width of arc
* font:int/nil Line font, etch always has nil while 0indicates a solid font.
* xy:point Location of arc center

#### Branch Attributes

* objType:"branch"
* children:l\_dbid List of _dbids_ of the objects that make up branch: paths, tees, vias, pins and shapes
* parent:dbid Always nil

#### Design Attributes

使用**axlDBGetDesign**获取

详情见[axlDBGetDesign](https://tiny-yhw.github.io//allegro-skill-database-read-functions){:target="_blank"}

##### DRC Attributes

* **actual:**string Actual value (user units)
* **expected:**string Expected value (user units)
* **fixed:**t/nil t = Allegro PCB Editor generated DRC  nil = user defined DRC
* **name:**string Name of constraint that was violated
* **objType:**string Type of object, in this case "drc"
* **parent:**dbid Design dbid
* **source:**string DRC source (property or constraint set name)
* **type:**string Domain of DRC
* **violations:**l\_dbid List of figures causing error (2 max)
* **waived:**t/nil t = waived drc  nil = regular
* **xy:**point Location of DRC marker

##### Group Attributes

groupMembers

l\_dbid

List of members of the group

name

string

Name of the group

objType

string

Type of object, in this case "group"

type

string

Predefined group type.**Note:**This cannot be defined in SKILL. Userdefined groups are considered "GENERIC."

##### Module Attributes

bBox

bBox

Bounding box of all physical members of group

groupMembers

l\_dbid

List of members of the module

name

string

Name of the module

objType

string

Type of object, in this case "group"

type

string

"MODULE"

##### Line Attributes

isEtch

t/nil

t = a CLINE; nil = a LINE

lineType

s\_type

a symbol: horizontal, vertical, odd

objType

string

Type of object, in this case "line"

parent

dbid

Path, polygon, or shape

startEnd

l\_point

Start and end points

thermal

t/nil

Cline is a thermal relief.

width

float

Width of line

font

int/nil

Line font, etch always has nil, while 0indicates a solid font.


##### Path Attributes

branch

dbid/nil

Branch owner

hasArcs

t/nil

t = path has one or more arcs

isSameWidth

t/nil

t = all segments in path have same width

isEtch

t/nil

t = a CLINE; nil = a LINE

nSegs

integer

Number of segments in path

objType

string

Type of object, in this case "path"

parent

dbid

Branch, symbol, shape or nil

segments

l\_dbid

List of arc and line figures in this path

symbolEtch

dbid

Symbol owner if etch.

startEnd

lt\_layer

If bond-wire start and end layers;   
nil if not bondwire.


##### Pin Attributes

* **objType:**"pin"
* **branch:**dbid/nil Branch owner
* **component:**dbid/nil Component owner of pin nil if unassigned symbol pin
* **definition:**dbid/nil Pin对应的Padstack的dbid nil if unplaced component pin
* **fixedByTestPoint:** t/nil OBSOLETE - kept for backwards compatibility. Use axlDBIsFixed(dbid) oraxlDBControl(?testPointFixed) instead.
* **functionPins:** l\_dbid/nil List of function pinsnil if unassigned symbol pin
* **isExploded:** t/nil t = pin is instance edited
* **isMech:** t/nil t = pin is mechanical
* **isMirrored:** t/nil t = pin is mirrored
* **isThrough:** t/nil t = pin is a throughhole
* **mirrorType:**string Type of mirror.
* **name:** string Pin对应的Padstack Name if unplaced component pin
* **number:** string Pin number
* **pads:**l\_dbid Unordered list of pads.1To access a particular pad, use axlDBGetPad.
* **parent:**dbid dbid of symbol owning this pin2nil if pin is standalone (as it is in a symbol drawing)
* **relRotation:**float Pin rotation (relative to symbol)
* **relxy:**point Location (relative to symbol)
* **rotation:**float Pin rotation (absolute)
* **startEnd:**lt\_layer Range of layers spanned by pin2
* **testPoint:**t\_layer/nil _t\_layer_, denotes layer of testpoint nil = pin is not a testpoint
* **use:**string Pin use as shown by show element
* **xy:**point Location of pin in absolute coordinates

##### Padstack Attributes

* **objType:**"padstack"
* **definition:**o\_dbid (see isPadRef) Points to padstack definition if this is padReference otherwise nil
* **drillChar:**string drill characters (max 3)
* **drillDiameter:**float Drill hole diameter
* **drillSizeWidth:**float width of slot, diameter if hole and extents ofmultidrill
* **drillSizeHeight:**float height of slot, diameter if hole and extents ofmultidrill
* **drillOffset:**point offset of drill hole
* **drillFigureName:**string type of drill symbol (circle, square, and so on.
* **drillFigureWidth:**float Width of drill symbol
(for slots same as drillSizeWidth)
* **drillFigureHeight:**float Height of drill symbol
(for slots same as drillSizeHeight)
* **drillNonStandard:**string Type of drill (nil is standard)
(not supported by slots)
* **holeTolerance:**l\_float A list of two numbers reporting the + and - drillhole tolerance.
* **multiDrillData:**l\_values If not multidrill then nil otherwise list of:(rows columns clearanceX clearanceYstaggered)Both clearances are in dbreps and staggered is t/nil
* **holeType:**string Type of hole (circle\_drill, oval\_slot, etc.)
* **keepout:**t/nil Padstack built to accommodate anti-pads asRoute keepouts for mechanical pins. This padstack can also be used for logical connections but this option is ignored.
* **isPadRef:**t/nil t = padstack is a padstack reference.This means that the actual padstack is a template and the start and end layers of the padstack are dynamically mapped, depending upon its use with a pin or a via.
* **isThrough:**t/nil t = through padstack
* **name:**string Padstack name
* **pads:**ll\_dbid List of pads
* **parent:**dbid Design
* **padSuppresion:**t/nil Does padstack have Pad Suppression enabled. This is for the legacy artwork based pad suppression.The dynamic pad suppression ignores this option.
* **plating:**string One of "Plated", "Non-Plated", "Plating-Optional"
* **prop:**nil Always nil, padstacks do not support properties
* **startEnd:**lt\_layer Start and end layer of padstack
* **type:**string Type of padstack; valid values are:through、smd、bbvia、uvia
* **uvia:**t/nil A sub-type of bbvias, to differentiate in constraint system.

##### Pad Attributes

bBox

bBox

Bounding box. Coordinates are always relative.

figure

lr\_path

List of r\_paths defining pad's boundary lr\_path always contains at most one r\_path nil denotes a null pad

figureName

string

Name of pad figure is one of the following:CIRCLE, SQUARE OBLONG, RECTANGLE, SHAPE ornil (if drill only)

flash

string

If of type FLASH, name of flash symbol otherwise an empty string ""(Obsolete; use name attribute)

layer

string

Pad layer

name

string

If type is a SHAPE or FLASH, name of symbol.

objType

string

Type of object, in this case "pad"

offset

l\_point

Offset of pad (relative to pin/via origin)

parent

dbid

Padstack _dbid_

readOnly

t

Cannot be modified.

type

string

Pad type is one of: REGULAR, ANTI, or THERMAL

##### Polygon Attributes

area

float

Area of the polygon in drawing units.

bBox

bBox

Bounding box.

holes

list

List of _o\_polygons_.

isHole

t/nil

t = polygon is a hole

isRect

t/nil

t = polygon is a rectangle

nSegs

integer

Number of segments in polygon

objType

string

Type of object, in this case "polygon"

parent

dbid

Symbol, shape (for voids), or nil

segments

l\_dbid

Path describing boundary of shape. Boundaryconsists of line and arc segments.

symbolEtch

dbid

Symbol owner if etch

vertices

list

Outer boundary available as a list containing apoint, which is the vertex of a polygon, and a floating point number, which is the radius of the edge from the previous to the present vertex.

##### Rat\_T Attributes

name

string

Name of T to T-<n>

net

dbid

Net of Rat-T

objType

string

Type of object, in this case "rat\_t"

parent

dbid

Net

xy

point

Location of T

##### Shape Attributes

bBox

bBox

Bounding box

cavity

t/nil

If a boundary shape is for cavity generation(embedded design). Cavity shapes are generated automatically based on the rki.

branch

dbid/nil

Branch owner

children

l\_dbid

Used when a Boundary Shape points to a list of dynamic shapes

connect

l\_dbid/nil

List of connected figures

fill

g\_fill/t/nil

Fill pattern (see axlDBCreateOpenShape).t = filled; nil = unfilledEach axlFillType has spacing width, origin, and angle.

fillet

t/nil

shape is a fillet (teardrop)

fillOOD

t/nil

Dynamic fill is out of date.t = shape needs fill updating   
(Only dynamic shapes can be t)nil = shape does not refill

holes

list

List of o\_polygons

isHole

t/nil

t = polygon is a holenil = polygon is not a hole

isRect

t/nil

t = shape is a rectangle

nSegs

integer

Number of segments in polygon

objType

string

Type of object, in this case "shape"

parent

dbid

Branch (if etch shape), Symbol, shape (for voids)nil = no parent

priority

integer/nil

If shape is a dynamic shape boundary this is an integer voiding priority. For all other shapes this is nil. The priority is relative to other dynamic shapes on the same layer. If two dynamic shapes are coincident, the shape with the higher priority wins in voiding. This number is re-calculated as needed, so use only for comparison purposes.

region

l\_dbid/nil

Region owner if a region shape.

segments

l\_dbid

Path boundary of shape

shapeAuto

l\_dbid/nil

If dynamic shape list of generated shapes on the matching auto-gen ETCH or CAVITY layer

shapeBoundary

dbid/nil

If this shape is generated from a dynamic shape, this points to that shape.Boundary shapes may either be used for ETCH or CAVITY (see state of cavity attribute)

shapeIsBoundary

t/nil

This shape is a dynamic shape, for example, on BOUNDARY class.

taper

t/nil

shape is used for tapering

dynamicGroup

t/nil

If this a dynamic shape (BOUNDARY class)return its dynamic group object. This is where voiding instance overrides are stored.

symbolEtch

dbid

Symbol owner, if etch

vertices

list

outer boundary available as a list containing apoint (vertex of a polygon) and a floating point number (radius of the edge from the previous to the present vertex).

voids

l\_dbid

List of polygon boundaries defining voids in this shape

##### Symbol Attributes

children

l\_dbid/nil

List of figures other than pins making up symbol

component

dbid

Component owner of symbol

definition

dbid

Symbol definition

isMirrored

t/nil

t = symbol is mirrored

mirrorType

string

Type of mirror.

name

string

Symbol name

objType

string

Type of object, in this case "symbol"

parent

dbid

Design (no other parent possible for symbols)

pins

l\_dbid/nil

List of pins

refdes

string/nil

Reference designator

rotation

float

Symbol rotation

type

string

Symbol type is one of: PACKAGE, MECHANICAL,FORMAT, SHAPE or DRAFTING

xy

point

Symbol location

embedded

t/nil

symbol placed on embedded layer

embeddedLayer

string

layer of placed symbol or nil if external

embeddedMethod

string

method (CHIP\_UP or CHIP\_DOWN)

embeddedAttach

string

attachment method (DIRECT\_ATTACH orINDIRECT\_ATTACH)

##### Symdef (Symbol Definition) Attributes

children

l\_dbid/nil

List of figures other than pins making up shape

instances

l\_dbid

Symbol instances

name

string

Name of symbol definition

objType

string

Type of object, in this case "symdef"

parent

dbid

Design

pins

l\_dbid/nil

List of pins

type

string

Symbol type is one of the following: PACKAGE,MECHANICAL, FORMAT, or SHAPE

##### Tee Attributes

branch

dbid

Branch owner

objType

string

Type of object, in this case "tee"

parent

dbid

Branch

readOnly

t

User cannot directly modify

xy

point

Location

##### Text Attributes

isMirrored

t/nil

t = text mirrored

justify

string

"left", "right" or "center"

mirrorType

string

Type of mirror.

objType

string

Type of object, in this case "text"

parent

dbid

Symbol or nil

rotation

float

Rotation angle

text

string

The text itself

textBlock

string

Text block type

xy

point

Location of text origin

##### Via Attributes

branch

dbid/nil

Branch owner

definition

dbid

Padstack definition

isMirrored

t/nil

t = via mirrored

isThrough

t/nil

t = through via

mirrorType

string

Type of mirror.

name

string

Padstack name

objType

string

Type of object, in this case "via"

pads

l\_dbid

Unordered list of pads.   
To access a specific pad, use axlDBGetPad.

parent

dbid

Symdef or nil

rotation

float

Via rotation

startEnd

lt\_layer

Start and end layer of via

testPoint

t\_layer/nil

Via test point state is one of: ETCH/TOP orETCH/BOTTOM

xy

point

Location of via

#### Logical类型

Logical类型其实就是和电气有关的属性，比如网络连接(net)，电子器件{component)等。 Logical类型通常都具有objType, prop, and readOnly3种属性。 如果你选择了一个component，那么它的objType就是component，如果选择的是pin，则objType属性值就是pin......

在allegro的应用中会根据工作的需要自己定制(创建)属性——用户定义的属性(user defined properties)。Allegro支持用户创建具备如下特性的属性

NETS， COMPONENTS， FUNCTIONS PINS， VIAS， SHAPES， SYMBOLS， CLINES， LINES， DRCS， FIGURES， DESIGNS， COMPDEFS， PINDEFS， FUNCDEFS。

如果你创建了一个只包含SYMBOLS类型的属性，那么你创建的这个属性只能被赋给Allegro中的Symbol对象，而不可以赋给 一个net或其它非Symbol的对象。

##### Bus Attributes

groupMembers

l\_dbid

List of xnets of the bus

name

string

Name of the bus

objType

string

"group"

type

string

"BUS"

lock

t/nil

Is locked for editing (vector buses)

##### Compdef Attributes

class

string

Component classification

components

l\_dbid

List of component instances of this definition.

deviceType

string

Device type of the component

functions

l\_dbid

List of functions.

objType

string

Type of object, in this case "compdef"

pins

l\_dbid

List of pins comprising the component.

##### Component Attributes

class

string

Component classification

compdef

dbid

dbid of component definition (COMPDEF)

deviceType

string

Device type of component (see COMPDEF)

functions

l\_dbid

List of functions

name

string

Reference designator

objType

string

Type of object, in this case "component"

package

string

Package name

pins

l\_dbid

List of pins comprising component

symbol

dbid/nil

_dbid_ of the placed symbol of this component,nil if unplaced

##### Diffpair Attributes

groupMembers

l\_dbid

List of xnets of the differential pair

name

string

Name of the differential pair

objType

string

"group"

type

string

"DIFFPAIR"

userDefined

t/nil

If you create t, can be modified. Nil indicates creation by SigNoise models and cannot be changed.

##### Function Attributes

name

string

Function designator

objType

string

Type of object, in this case "function"

parent

dbid

_dbid_ of component owning this function

pins

l\_dbid

List of function pins composing function

slot

string

Slot name

type

string

Function type

##### Function Pin Attributes

name

string

Function pin name

objType

string

Type of object, in this case "functionPin"

parent

dbid

_dbid_ of function owning this pin

pin

dbid

Pin owner of function pin

swap code

integer

Swap code of function pin

use

string

Pin usage description, one ofUNSPECIFIED, POWER, GROUND, NC,LOADIN, LOADOUT, BI, TRU, OCA, OCL

##### MATCH\_GROUP Attributes

**Note:**For more information, see axlMatchGroupCreate.

groupMembers

l\_dbid

List of xnets, nets and pinpairs making up thisgroup.

name

string

Name of the match group.

objType

string

"group"

pinpair

l\_dbid

List of pinpairs associated with xnet

type

string

"MATCH\_GROUP"

##### Net Attributes

**Note:** 

1) If net is a member of an xnet then all pinpairs will appear on the xnet.

2) For more information on the rpd attribute see axlMatchGroupCreate

branches

l\_dbid

List of branches

name

string

Net name

bus

dbid

Bus dbid if part of a bus

nBranches

integer

Number of branches (when exactly one, net is fullyconnected)**Note:**Island shapes causes the count to be not one, even if all pins are connected.

objType

string

Type of object, in this case "net"

pinpair

l\_dbid

List of pinpairs associated with net (1)**Note:**If a net is a member of an xnet, all pinpairs appear on the xnet.

ratsnest

l\_dbid

List of ratsnest for net.

ratsnest On

t/nil

State of ratsnest display for the net.

ratT

l\_dbid

List of rat\_T's. If none exist, this is NULL.

rpd

l\_rpd

List of lists for each member net of a match group (mg\_dbidt\_relatePropDelay).For more information, see axlMatchGroupCreate

isBundled

t/nil

t = net contains at least one bundled ratsnest.

scheduleLocked

t/nil

t = net schedule cannot be changed

unconnected

integer

Number of remaining connections. This does not includeconnections to unplaced symbols.

unplaced

integer

Number of unplaced pins.

##### **NETCLASS Attributes**

**Note:** 

**a.**A NetClass can be a member of one or more domains but its name must be unique across all domains.

**b.**Constraint overrides can be added to netclass via properties.

**Attribute Name**

**Type**

**Description**

groupMembers

l\_dbid

List of nets, xnets, buses or differential pairs.

name

string

Name of the net class

objType

string

"group"

type

string

"NETCLASS"

electrical

t/nil

If part of the electrical and same net domain

physical

t/nil

If part of the physical and same net domain

spacing

t/nil

If part of the spacing and same net domain

##### REGION Attribute

groupMembers

l\_dbid

List of constraint area shapes.

name

string

Name of the region

objType

string

"group"

type

string

"REGION"

##### **CLASS Table Attribute**

**Note:**These are the class-class, class-class-region and class-region constraint table entries. See axlCnsClassTableCreate.

**Attribute Name**

**Type**

**Description**

name

string

Name of ecset

netclass1

dbid

net class entry

netclass2

dbid

second net class entry (may be nil)

region

dbid

region class for table entry (may be nil)

physical

dbid

physical cset associated with entry or nil

spacing

string

spacing cset associated with entry or nil

sameNet

string

sameNet cset associated with entry or nil

assembly

string

physical assembly cset associated with entry (SIP/APD only)

objType

string

"classTable"

readOnly

t/nil

Cannot be modified

prop

l\_dbid

List of properties on table entry.Typically where constraint overrides on entry exist. Also duplicates the cset names.

##### Pinpair Attributes

**Note:**For nets that are part of an xnet, the pinpair always has the xnet as the pinpair owner. For more information on the rpd attribute, see axlMatchGroupCreate.

ecsetDerived

t/nil

If t, pinpair was created from an ECset. Nil indicates pinpair created due to net override property.

groupMembers

l\_dbid

List of two pins making up pinpair.

name

string

Name of the pinpair (<refdes>. <pin#>: <refdes>.<pin#>)

objType

string

"group"

parent

l\_dbid

Net or xnet owning the pinpair.

parentGroups

l\_dbid

Lists match groups that have this pinpair. May also list other parent groups.

rpd

l\_rpd

For each match group that has this pinpair as a member, will list as a list of lists. (mg\_dbid t\_relatePropDelay)

type

string

"PIN\_PAIR"

##### NET\_GROUP Attributes

**Note:**Use axlDBCreateGroup family of commands to add, delete and modify these groups.

**Attribute Name**

**Type**

**Description**

groupMembers

l\_dbid

members of the group (net\_groups, nets, xnets,diffpairs, buses)

name

string

Name of group

objType

string

"group"

type

string

"NET\_GROUP"

isInterfaceTop

t/nil

If t, group is the top of a definition-driven interface instance.

##### PORT\_GROUP Attributes

groupMembers

l\_dbid

members of the group (port\_groups, pins, functionpins)

name

string

Name of group

objType

string

"group"

type

string

"PORT\_GROUP"

isInterfaceTop

t/nil

If t, group is the top of a definition-driven interface instance.

##### RATSNEST Attributes

bus

t/nil

Currently being shown with bus routes option

objType

string

Type of object, in this case "ratsnest"

pinsConnected

t/nil

Ratsnest not displayed (both pins on same branch)

pins

l\_dbid

The two pins (or ratTs) that the rats connect

pwrAndGnd

t/nil

Net is power and ground scheduled

ratnest

t/nil

Two dbids of the next ratsnest for dbid's of the pins attribute.

ratsPlaced

t/nil

User defined rats only, one or more pins unplaced

userDefined

t/nil

Ratsnest is user defined

##### XNET Attributes

**Note:**  
1) This attribute can only be defined indirectly from the SigNoise model assignment.  
2) For more information on rpd, see axlMatchGroupCreate.

bus

dbid

Bus dbid if part of a bus.

diffpair

dbid

differential pair dbid if part of a differential pair.

groupMembers

l\_dbid

List of nets of the xnet.

name

string

Name of the xnet.

objType

string

"group"

pinpair

l\_dbid

List of pinpairs associated with xnet.

rpd

l\_rpd

For each match group that has this xnet as a member, lists as a list of lists (mg\_dbid t\_relatePropDelay).

type

string

"XNET".

### Parameter类型

Parameter的简单理解就是Allegro中个各个设置参数，举个简单的例子，系统(Design)级别的参数列表。Design Parameter属性

暂略，待补充