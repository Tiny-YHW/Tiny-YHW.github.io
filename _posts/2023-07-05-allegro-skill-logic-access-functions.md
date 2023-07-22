---
layout: post
title: Allegro Skill Logic Access Functions
categories: Allegro Skill
date: 2023-07-22
permalink: allegro-skill-logic-access-functions
excerpt: 操作系统的一些Logic类型的信息，比如DiffPair，MatchGroup，pinpair等等
---

## axlPinsOfNet

返回网络或 xnet 上的 pin 和ratT 列表。 第一个参数可以是网络、xnet dbid 或网络名称（不支持 xnet 名称）。 第二个选项 g_mode 可以是“pin”以仅返回引脚，“ratT”返回ratT 列表或“nil”以返回引脚和ratT。 返回的项目列表中没有传达任何含义。

```lisp
;All pins on GND:
net = car(axlSelectByName("NET" "GND"))
lpins = axlPinsOfNet(net, 'pins)

;All pins and ratTs on first xnet in design root (could be a net):
xnet = car( axlDBGetDesign()->xnet )
lpins = axlPinsOfNet(xnet, nil)
```

## axlDiffPair

生成，修改，删除Diffpair

```lisp
;Example 1：Creates a differential pair and names it DP1.
DPdbid = axlDiffPair("DP" "NET1+" "NET2-")


;Example 2：Modifies a differential pair.
DPdbid = axlDiffPair(DPdbid "NET1+" "NET1-")

;Example 3：Deletes a differential pair.
axlDiffPair(DPdbid)

;Example 4：Delete all differential pairs in design.
axlDiffPair(axlDBGetDesign()->diffpair)
```

## axlDiffPairAuto

根据条件自动创建差分

```lisp
;Two nets called NET1+ and NET1- are passed to this function.

;Example 1：Shows diffpair creation and name generation. Results in one diffpair called DP_NET1 with members NET1+ and NET1-.
axlDiffPairAuto("DP_" "+" "-")

;Example 2：Gives the same result as the previous example, but names the diffpair NET1.
axlDiffPairAuto("" "+" "-")
```

## axlDiffPairDBID

根据差分name获得差分dbid，如果name不存在则返回nil

```lisp
axlDiffPairDBID(t_name)
```


## axlDBDummyNet 获取所有空网络对象

支持pin、shape

```lisp
axlDBDummyNet (g_mode);-> lo_dbid/nil

p = axlDBDummyNet(nil);获取设计中所有空网络对象

p = axlDBDummyNet('pin)
p = axlDBDummyNet('shape)

```

## axlDbidName 得到dbid对应的名字

提供数据库对象的标准 Allegro PCB Editor 名称。 许多命名的 Allegro PCB Editor 对象（例如网络）都在名称属性中定义了名称（例如 dbid->name），但其他对象（例如 clines 和 pin）要么没有所需的报告名称，要么未命名。

## axlNetSched 等于 net schedule command

axlMatchGroupAdd(); 添加成员到某个MatchGroup

axlWriteDeviceFile(); 输出Device信息到相应的文件



axlDBAssignNet  

axlDBCreateConceptComponent  

axlDBCreateComponent  

axlDBCreateManyModuleInstances  

axlDBCreateModuleDef  

axlDBCreateModuleInstance  

axlDBCreateNet  

axlDBCreateSymDefSkeleton  

axlMatchGroupCreate  

axlMatchGroupDelete  

axlMatchGroupProp  

axlMatchGroupRemove  



axlPinPair  

axlPinPairSeek  



axlRemoveNet  

axlRenameNet  

axlRenameRefdes  

axlSchedule  

axlScheduleNet  

axlWritePackageFile