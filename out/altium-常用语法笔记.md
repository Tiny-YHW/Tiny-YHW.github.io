---
title: 'Altium 常用语法笔记'
date: Sat, 11 Apr 2020 01:59:33 +0000
draft: false
tags: ['Altium']
---

[官网资料](https://www.altium.com/cn/documentation/altium-designer/working-with-the-query-language)

**常用语法**
--------

### **逻辑表达**

位于区间：`AsMM(ArcRadius) Between 10.16 And 17.78`  
不等于：`ArcRadius <> 550`  
小于等于：`AsMils(ArcRadius) <= 650`  
等于：`AsMM(ArcRadius) = 6.35`  
大于等于：`AsMM(PolygonGridSize) >= 0.254`  
文本包含：`Net Like '*G*'`

### **功能**

包含单位  
`AsMils(ArcRadius) > 500  
AsMM(ArcRadius) = 6.35`

`NetPinCount > 10`  同网络的Pin对象个数大于10个的 网络  
`NetViaCount < 6`  同网络的via对象个数小于6个的 网络

`AsMils(OverallHeight) > 80` 元器件高度属性超过80mil的元器件

### 应用

BGA所有数字引脚标号

```
(ObjectKind = 'Text') And (Layer = 'TopOverlay') And ((StringText like '1*') or (StringText like '2*') or  (StringText like '3*') or (StringText like '4')or (StringText like '5')or (StringText like '6')or (StringText like '7')or (StringText like '8')or (StringText like '9'))
```

BGA所有字母引脚标号

```
(ObjectKind = 'Text') And (Layer = 'TopOverlay') And Not ((StringText like '1*') or (StringText like '2*') or  (StringText like '3*') or (StringText like '4')or (StringText like '5')or (StringText like '6')or (StringText like '7')or (StringText like '8')or (StringText like '9'))
```

### **用于统计**

空网络焊盘：`IsPad and ( Not InAnyNet)`  
元器件总焊点数：`IsComponentPad`  
元器件有效连接数：`IsComponentPad and NetPinCount > 1`  
单点网络：`IsComponentPad and NetPinCount = 1`

```
总pin
expr=IsComponentPad|mask=True|apply=True|select=True

有连接的pin
expr=IsComponentPad and NetPinCount > 1|mask=True|apply=True|select=True

单点pin
expr=IsComponentPad and NetPinCount = 1|mask=True|apply=True|select=True

空焊盘
expr=IsPad and ( Not InAnyNet)|mask=True|apply=True|select=True|zoom=True
```

### **用于检查**

```
expr=|mask=True|apply=True|select=True|zoom=True

孔径大于6mm的Pad：
AsMM(HoleSize) > '6'

expr=AsMM(HoleSize) > '6'|mask=True|apply=True|select=True|zoom=True

Plane层铜皮无网络：
IsSplitPlane And (Net = 'No Net')

expr=IsSplitPlane And (Net = 'No Net')|mask=True|apply=True|select=True|zoom=True

电气层无网络铜皮、过孔、线：
(InPoly or IsWire or isVia) and not InAnyNet and not IsKeepOut

expr=(InPoly or IsWire or isVia) and not InAnyNet and not IsKeepOut|mask=True|apply=True|select=True|zoom=True

阻焊过小
IsPad AND ((AsMM(SolderMaskExpansion) < 0.05) or (SolderMaskTentingBottom <> 'False') or (SolderMaskTentingTop <> 'False'))

expr=IsPad AND ((AsMM(SolderMaskExpansion) < 0.05) or (SolderMaskTentingBottom <> 'False') or (SolderMaskTentingTop <> 'False'))|mask=True|apply=True|select=True|zoom=True


非金属化孔盘孔不等大：
ispad And (PadIsPlated = 'False') And ((PadShape_AllLayers <> HoleType) Or (HoleDiameter <> PadXSize_TopLayer) Or (HoleDiameter <> PadYSize_TopLayer) Or (HoleDiameter <> PadXSize_MidLayer1) Or (HoleDiameter <> PadYSize_MidLayer1) Or (HoleDiameter <> PadXSize_BottomLayer) Or (HoleDiameter <> PadYSize_BottomLayer))

expr=ispad And (PadIsPlated = 'False') And ((PadShape_AllLayers <> HoleType) Or (HoleDiameter <> PadXSize_TopLayer) Or (HoleDiameter <> PadYSize_TopLayer) Or (HoleDiameter <> PadXSize_MidLayer1) Or (HoleDiameter <> PadYSize_MidLayer1) Or (HoleDiameter <> PadXSize_BottomLayer) Or (HoleDiameter <> PadYSize_BottomLayer))|mask=True|apply=True|select=True|zoom=True

金属化孔盘不大于孔：
ispad And (HoleSize > '0') And (PadIsPlated = 'True') And ((HoleDiameter > PadXSize_TopLayer) Or (HoleDiameter > PadYSize_TopLayer) Or (HoleDiameter > PadXSize_MidLayer1) Or (HoleDiameter > PadYSize_MidLayer1) Or (HoleDiameter > PadXSize_BottomLayer) Or (HoleDiameter > PadYSize_BottomLayer))

expr=ispad And (HoleSize > '0') And (PadIsPlated = 'True') And ((HoleDiameter > PadXSize_TopLayer) Or (HoleDiameter > PadYSize_TopLayer) Or (HoleDiameter > PadXSize_MidLayer1) Or (HoleDiameter > PadYSize_MidLayer1) Or (HoleDiameter > PadXSize_BottomLayer) Or (HoleDiameter > PadYSize_BottomLayer))|mask=True|apply=True|select=True|zoom=True

字符方向检查底层上到下：
(ObjectKind = 'Text') And (StringType = 'Designator') And (StrokeFont <> 'Sans Serif') or (ObjectKind = 'Text') And (StringType = 'Designator') And (Layer = 'TopOverlay') And (Rotation = '270.000') OR (ObjectKind = 'Text') And (StringType = 'Designator') And (Layer = 'TopOverlay') And (Rotation = '180.000') or (ObjectKind = 'Text') And (StringType = 'Designator') And (Layer = 'BottomOverlay') And (Mirror <> 'True') or (ObjectKind = 'Text') And (StringType = 'Designator') And (Layer = 'TopOverlay') And (Mirror <> 'False') or (ObjectKind = 'Component') And (ShowName = 'False') or (ObjectKind = 'Text') And (StringType = 'Designator') And (Layer = 'BottomOverlay') And (Rotation = '270.000') OR (ObjectKind = 'Text') And (StringType = 'Designator') And (Layer = 'BottomOverlay') And (Rotation = '180.000')

expr=(ObjectKind = 'Text') And (StringType = 'Designator') And (StrokeFont <> 'Sans Serif') or (ObjectKind = 'Text') And (StringType = 'Designator') And (Layer = 'TopOverlay') And (Rotation = '270.000') OR (ObjectKind = 'Text') And (StringType = 'Designator') And (Layer = 'TopOverlay') And (Rotation = '180.000') or (ObjectKind = 'Text') And (StringType = 'Designator') And (Layer = 'BottomOverlay') And (Mirror <> 'True') or (ObjectKind = 'Text') And (StringType = 'Designator') And (Layer = 'TopOverlay') And (Mirror <> 'False') or (ObjectKind = 'Component') And (ShowName = 'False') or (ObjectKind = 'Text') And (StringType = 'Designator') And (Layer = 'BottomOverlay') And (Rotation = '270.000') OR (ObjectKind = 'Text') And (StringType = 'Designator') And (Layer = 'BottomOverlay') And (Rotation = '180.000')|mask=True|apply=True|select=True|zoom=True


字符方向检查底层下到上：
(ObjectKind = 'Text') And (StringType = 'Designator') And (StrokeFont <> 'Sans Serif') or (ObjectKind = 'Text') And (StringType = 'Designator') And (Layer = 'TopOverlay') And (Rotation = '270.000') OR (ObjectKind = 'Text') And (StringType = 'Designator') And (Layer = 'TopOverlay') And (Rotation = '180.000') or (ObjectKind = 'Text') And (StringType = 'Designator') And (Layer = 'BottomOverlay') And (Mirror <> 'True') or (ObjectKind = 'Text') And (StringType = 'Designator') And (Layer = 'TopOverlay') And (Mirror <> 'False') or (ObjectKind = 'Component') And (ShowName = 'False') or (ObjectKind = 'Text') And (StringType = 'Designator') And (Layer = 'BottomOverlay') And (Rotation = '90') OR (ObjectKind = 'Text') And (StringType = 'Designator') And (Layer = 'BottomOverlay') And (Rotation = '180.000')

expr=(ObjectKind = 'Text') And (StringType = 'Designator') And (StrokeFont <> 'Sans Serif') or (ObjectKind = 'Text') And (StringType = 'Designator') And (Layer = 'TopOverlay') And (Rotation = '270.000') OR (ObjectKind = 'Text') And (StringType = 'Designator') And (Layer = 'TopOverlay') And (Rotation = '180.000') or (ObjectKind = 'Text') And (StringType = 'Designator') And (Layer = 'BottomOverlay') And (Mirror <> 'True') or (ObjectKind = 'Text') And (StringType = 'Designator') And (Layer = 'TopOverlay') And (Mirror <> 'False') or (ObjectKind = 'Component') And (ShowName = 'False') or (ObjectKind = 'Text') And (StringType = 'Designator') And (Layer = 'BottomOverlay') And (Rotation = '90') OR (ObjectKind = 'Text') And (StringType = 'Designator') And (Layer = 'BottomOverlay') And (Rotation = '180.000')|mask=True|apply=True|select=True|zoom=True

板子字符图形镜像：
((ObjectKind = 'Text') And (Layer = 'BottomOverlay') And (Mirror <> 'True') or (ObjectKind = 'Text') And (Layer = 'TopOverlay') And (Mirror <> 'False')) and not IsComment

expr=((ObjectKind = 'Text') And (Layer = 'BottomOverlay') And (Mirror <> 'True') or (ObjectKind = 'Text') And (Layer = 'TopOverlay') And (Mirror <> 'False')) and not IsComment|mask=True|apply=True|select=True|zoom=True

元器件非法同层镜像检查：
((IsDesignator or IsComment) and (Mirror=true) and OnTopSilkscreen) or ((IsDesignator or IsComment) and (Mirror=false) and OnBottomSilkscreen)

expr=((IsDesignator or IsComment) and (Mirror=true) and OnTopSilkscreen) or ((IsDesignator or IsComment) and (Mirror=false) and OnBottomSilkscreen)|mask=True|apply=True|select=True|zoom=True

丝印线过细：
(IsTrack or IsArc) and OnSilkscreen and (Width<AsMils(4))

expr=(IsTrack or IsArc) and OnSilkscreen and (Width<AsMils(4))|mask=True|apply=True|select=True|zoom=True

字符层面镜像错误：
InComponentClass('bottom side Components') and (((IsDesignator and OnTopSilkscreen) or (IsTrack or IsArc) and OnTopSilkscreen) or IsSMTPin and OnTopLayer) or InComponentClass('top side Components') and ((IsDesignator and OnBottomSilkscreen)or ((IsTrack or IsArc) and OnBottomSilkscreen) or IsSMTPin and OnBottomLayer) or ((IsDesignator or IsComment) and not (OnTopSilkscreen or OnBottomSilkscreen))

expr=InComponentClass('bottom side Components') and (((IsDesignator and OnTopSilkscreen) or (IsTrack or IsArc) and OnTopSilkscreen) or IsSMTPin and OnTopLayer) or InComponentClass('top side Components') and ((IsDesignator and OnBottomSilkscreen)or ((IsTrack or IsArc) and OnBottomSilkscreen) or IsSMTPin and OnBottomLayer) or ((IsDesignator or IsComment) and not (OnTopSilkscreen or OnBottomSilkscreen))|mask=True|apply=True|select=True|zoom=True


未调整的字符:
(ObjectKind = 'Text') And (StringType = 'Designator') And (AutoPosition <> 'Manual')

expr=(ObjectKind = 'Text') And (StringType = 'Designator') And (AutoPosition <> 'Manual')|mask=True|apply=True|select=True|zoom=True
```

### Altium内置案例

![](https://a1024.synology.me:222/images/blog2023/Altiumfilterexample.png)

```
Source=Example|
0.Hidden comments strings
IsComment And (Hide = True)
1.Locked components
IsComponent and (Locked = True)
2.Pads and vias with a hole size between 15 and 30
(IsPad Or IsVia) And (HoleSize > 15) And (HoleSize < 30)
3.Teacks less than 2 units long
IsTrack And (Sqrt(Sqr(X1-X2) + Sqr(Y1-Y2)) < 2)
4.All testpoints
(TestPointTop = True) Or (TestPointBottom = True)
5.Component track and arc silkscreen primitives
OnSilkscreen And (IsTrack Or IsArc) And IsComponentPrimitive
6.Components not on a 5 mil grid
IsComponent And ((Frac(X1/5) <> 0) Or (Frac(Y1/5) <> 0))
7.Signal layer tracks at an odd angle
Not(IsHorizontal Or IsVertical Or IsOblique) And IsTrack And OnSignal
8.Top signal layer keep objects
IsKeepout And OnTopLayer
9.Non-horizontal designators
IsDesignator And (Rotation <> 0) And (Rotation <> 360)
```

### 其它

```
expr=|mask=True|apply=True|select=True|zoom=True

加泪滴对象
((ObjectKind = 'Via') And (ViaDiameter <= AsMils(28))) or IsWire
expr=((ObjectKind = 'Via') And (ViaDiameter <= AsMils(28))) or IsWire|mask=False|apply=True|select=True|zoom=True

3D对象
(ObjectKind = '3D Body') And (Layer = 'Top 3D')
expr=(ObjectKind = '3D Body') And (Layer = 'Top 3D')|mask=True|apply=True|select=True|zoom=True

(ObjectKind = '3D Body') And (Layer = 'Bottom 3D')
expr=(ObjectKind = '3D Body') And (Layer = 'Bottom 3D')|mask=True|apply=True|select=True|zoom=True 
```

### **对象**

**ObjectKind：Kind = ObjectKind\_String、ObjectKind = ObjectKind\_String**  
'Acute Angle Rule' , 'Angular Dimension' , 'Arc' , 'Baseline Dimension' , 'Broken Nets Rule' , 'Center Dimension' ,  
'Class' , 'Clearance Rule' , 'Component' , 'Component Clearance Rule' , 'Component Rotations Rule' , 'Confinement  
Constraint Rule' , 'Coordinate' , 'Daisy Chain Stub Length Rule' , 'Datum Dimension' , 'Fanout Control Rule' , 'Fill' ,  
'Flight Time Falling Edge Rule' , 'Flight Time Rising Edge Rule' , 'From To' , 'Layer Pair Rule' , 'Leader Dimension' ,  
'Linear Diameter Dimension' , 'Linear Dimension' , 'Matched Lengths Rule' , 'Max Min Height Rule' , 'Max Min Hole  
Size Rule' , 'Max Min Impedance Rule' , 'Max Min Length Rule' , 'Max Min Width Rule' , 'Max Slope Falling Edge  
Rule' , 'Max Slope Rising Edge Rule' , 'Maximum Via Count Rule' , 'Minimum Annular Ring Rule' , 'Net' , 'Nets To  
Ignore Rule' , 'Original Dimension' , 'Overshoot Falling Edge Rule' , 'Overshoot Rising Edge Rule' , 'Pad' , 'Parallel  
Segment Rule' , 'Paste Mask Expansion Rule' , 'Permitted Layers Rule' , 'Poly' , 'Polygon Connect Style Rule' ,  
'Power Plane Clearance Rule' , 'Power Plane Connect Style Rule' , 'Radial Diameter Dimension' , 'Radial Dimension'  
, 'Routing Corner Style Rule' , 'Routing Layers Rule' , 'Routing Priority Rule' , 'Routing Topology Rule' , 'Routing Via  
Style Rule' , 'Short Circuit Rule' , 'Signal Base Value Rule' , 'Signal Stimulus Rule' , 'Signal Top Value Rule' , 'SMD  
Neck Down Rule' , 'SMD To Corner Rule' , 'SMD To Plane Rule' , 'Solder Mask Expansion Rule' , 'Supply Nets Rule'  
, 'Test Point Style Rule' , 'Test Point Usage Rule' , 'Text' , 'Track' , 'Unconnected Pin Rule' , 'Undershoot Falling  
Edge Rule' , 'Undershoot Rising Edge Rule' , 'Via' , 'Vias Under SMD Rule' , 'Violation'

**Layer：ExistsOnLayer(LayerString)、L = Layer\_String、Layer = Layer\_String、OnLayer(Layer : Layer\_String)**  
'NoLayer'  
'TopLayer' ,'MidLayer1' ,'MidLayer2' ,…… ,'MidLayer30' ,'BottomLayer'  
'TopOverlay' ,'BottomOverlay' ,'TopPaste' ,'BottomPaste' ,'TopSolder' ,'BottomSolder'  
'InternalPlane1','InternalPlane2' ,……,'InternalPlane16'  
'DrillGuide'  
'KeepOutLayer'  
'Mechanical1' ,'Mechanical2' ,……,'Mechanical32'  
'DrillDrawing'  
'MultiLayer'  
'ConnectLayer'  
'BackGroundLayer'  
'DRCErrorLayer'  
'HighlightLayer'  
'GridColor1' ,'GridColor10'  
'PadHoleLayer' ,'ViaHoleLayer'

**Layer Class：InLayerClass(Name : String)   eg：(InLayerClass('Component Layers'))**  
'Electrical Layers'：所有导电层  
'Component Layers'：'TopLayer' + 'BottomLayer'  
'Signal Layers'：'Component Layers' + 'MidLayer1-30'  
'Electrical Layers'：'Signal Layers' + 'InternalPlane1-16'  
'All Layers'：所有层

IsPolygon = IsPoly：All Layers的Poly  
IsFill：所有Fill类型对象  
IsRegion：所有Region类型对象  
IsKeepOut：'KeepOutLayer' 层对象和带有KeepOut属性的对象  
IsPad：所有Pad类型对象  
IsVia：所有Via类型对象  
IsText：所有Text类型对象  
IsTrack：所有Track类型对象  
OnBottom（OnTop）：all objects on the Bottom (Signal), Bottom Overlay, Bottom Paste Mask, and Bottom Solder Mask layers;  
OnBottomLayer（OnTopLayer）：all objects on the Bottom (Signal) layer  
OnBottomPaste（OnTopPaste）  
OnBottomSilkscreen（OnTopSilkscreen）  
OnBottomSolderMask（OnTopSolderMask）  
OnMultiLayer

OnCopper：Top (Signal), Bottom (Signal), and Multi-Layer layers, and all objects on any internal  
Signal and Internal Plane layers  
OnInverted：all objects on the Top Paste Mask, Bottom Paste Mask, Top Solder Mask, and Bottom Solder Mask layers,and on any Internal Plane layers  
OnMechanical：all objects on any Mechanical layers  
OnMid Layer：all objects on any internal Signal layers  
OnOutside Layer：all objects on the Top (Signal) and Bottom (Signal) layers. The objects returned include all components, as those objects either have a Top (Signal) or Bottom (Signal) Layer property.  
OnPaste：Top Paste Mask and Bottom Paste Mask layers的对象和带有Paste的表贴Pad  
OnSilkscreen：Top Overlay and Bottom Overlay layers的所有对象  
OnSolderMask：Top Solder Mask and Bottom Solder Mask的所有对象  
OnPlane：Internal Plane layers的所有对象  
OnSignal：Top (Signal), Bottom (Signal), and Multi-Layer layers，internal Signal layers的所有对象

InPoly = InPolygon：Signal layer 和 Multi-Layer layer的Poly  
IsElectrical：有Net属性且Net不为'No Net'的对象  
IsWire：arcs and tracks on the Signal layers and Multi-Layer layer  
IsComponentBody：3D封装体图形IsConnection：飞线  
IsComponentPrimitive：元器件的子元素，包含元器件本身IsBoardCutoutRegion：定义为BoardCutout的Region  
Keepout：有Keepout属性的 all Arc, Fill, and Track objects

对应封装类型的元器件，每种封装类型有其对应的判断规则  
IsBGA、IsDIP、IsEdgeConnector、IsLCC、IsPGA、IsSIP、IsSMSIP、IsSMTComponent、IsSOIC

Net：Net = 'GND'、N = 'GND'    
Arc, Fill, Pad, Track, Via, From To, and Polygon objects whose Net property complies with the Query.

PadIsPlated = 'True'：Plated属性为Ture的Pad