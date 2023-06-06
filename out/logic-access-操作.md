---
title: 'Logic Access 操作'
date: Wed, 26 Jan 2022 08:45:45 +0000
draft: false
tags: ['Allegro Skill']
---

操作系统的一些Logic类型的信息，比如DiffPair，MatchGroup，pinpair等等

### axlDiffPair

生成，修改，删除Diffpair

```
Example 1：Creates a differential pair and names it DP1.
DPdbid = axlDiffPair("DP" "NET1+" "NET2-")


Example 2：Modifies a differential pair.
DPdbid = axlDiffPair(DPdbid "NET1+" "NET1-")

Example 3：Deletes a differential pair.
axlDiffPair(DPdbid)

Example 4：Delete all differential pairs in design.
axlDiffPair(axlDBGetDesign()->diffpair)
```

### axlDiffPairAuto

根据条件自动创建差分

```
Two nets called NET1+ and NET1- are passed to this function.

Example 1：Shows diffpair creation and name generation. Results in one diffpair called DP_NET1 with members NET1+ and NET1-.
axlDiffPairAuto("DP_" "+" "-")

Example 2：Gives the same result as the previous example, but names the diffpair NET1.
axlDiffPairAuto("" "+" "-")
```

### axlDiffPairDBID

根据差分name获得差分dbid，如果name不存在则返回nil

```
axlDiffPairDBID(t_name)
```

axlMatchGroupAdd(); 添加成员到某个MatchGroup

axlWriteDeviceFile(); 输出Device信息到相应的文件

axlDbidName(); 得到dbid对应的名字

axlDBAssignNet  
axlDBCreateConceptComponent  
axlDBCreateComponent  
axlDBCreateManyModuleInstances  
axlDBCreateModuleDef  
axlDBCreateModuleInstance  
axlDBCreateNet  
axlDBCreateSymDefSkeleton  
axlDBDummyNet  
axlMatchGroupCreate  
axlMatchGroupDelete  
axlMatchGroupProp  
axlMatchGroupRemove  
axlNetSched  
axlPinPair  
axlPinPairSeek  
axlPinsOfNet  
axlRemoveNet  
axlRenameNet  
axlRenameRefdes  
axlSchedule  
axlScheduleNet  
axlWritePackageFile