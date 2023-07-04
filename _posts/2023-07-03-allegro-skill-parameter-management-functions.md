---
layout: post
title: Parameter Management Functions
categories: Allegro Skill
date: 2023-07-03
permalink: allegro-skill-parameter-management-functions
excerpt: 
---

# Overview

* axlcreate
* axlDBGridGet
* axlDBGridSet
* axlDBTextBlockCreate
* axlExportXmlDBRecords
* axlImportXmlDBRecords
* axlPadSuppressGet
* axlPadSuppressOkLayer
* axlPadSuppressSet
* axlGetParam
* axlSetParam

# Color Access

* axlColorDoc
* axlColorGet
* axlColorShadowGet
* axlColorShadowSet
* axlColorLoad
* axlColorOnGet - Obsolete Command
* axlColorOnSet - Obsolete Command
* axlColorPriorityGet - Obsolete Command
* axlColorPrioritySet - Obsolete Command
* axlColorSave
* axlColorSet
* axlCVFColorChooserDlg
* axlClearObjectCustomColor
* axlCustomColorObject
* axlLayerPriorityClearAll
* axlLayerPriorityGet
* axlLayerPriorityRestoreAll
* axlLayerPrioritySaveAll
* axlLayerPrioritySet
* axlIsCustomColored


# Database Layer Management

## axlVisibleLayer 开关图层

打开或关闭指定图层显示状态
```lisp
axlVisibleDesign(nil);关闭所有层
axlVisibleDesign(t);打开所有层
axlVisibleLayer( "REF DES/SILKSCREEN_TOP" t );打开指定Subclass
axlVisibleLayer( "REF DES/SILKSCREEN_TOP" nil );关闭指定Subclass
axlVisibleLayer( "REF DES" t );打开Class的所有层
axlVisibleLayer( "REF DES" nil );关闭Class的所有层
axlVisibleUpdate(t);更新视图,否则需要用户手动更新
```

* axlClasses
* axlDBGetLayerType
* axlGetXSection
* axlIsLayer
* axlIsVisibleLayer
* axlLayerCreateCrossSection
* axlLayerCreateNonConductor
* axlLayerGet
* axlVisibleDesign
* axlVisibleGet
* axlVisibleSet
* axlConductorBottomLayer
* axlConductorTopLayer
* axlDBCreateFilmRec
* axlSetPlaneType
* axlSubclasses
* axlSubclassRoute