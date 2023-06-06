---
title: '【skill源码】导出库中焊盘和封装的skill源码'
date: Wed, 17 Jun 2020 09:04:04 +0000
draft: false
tags: ['Allegro Skill']
---

导出allegro 焊盘和封装库，如不同目录下有相同焊盘或封装只导出最新的文件  
默认路径 "D:/ExportLib/",如元件比较多请耐心等待

![](http://a1024.synology.me:222/images/blog2022/allegro%20%E5%AF%BC%E5%87%BA%E5%BA%93%E4%B8%AD%E7%84%8A%E7%9B%98%E5%92%8C%E5%B0%81%E8%A3%85%E7%9A%84skill%E6%BA%90%E7%A0%811.jpg)

![](http://a1024.synology.me:222/images/blog2022/allegro%20%E5%AF%BC%E5%87%BA%E5%BA%93%E4%B8%AD%E7%84%8A%E7%9B%98%E5%92%8C%E5%B0%81%E8%A3%85%E7%9A%84skill%E6%BA%90%E7%A0%812.jpg)

![](http://a1024.synology.me:222/images/blog2022/allegro%20%E5%AF%BC%E5%87%BA%E5%BA%93%E4%B8%AD%E7%84%8A%E7%9B%98%E5%92%8C%E5%B0%81%E8%A3%85%E7%9A%84skill%E6%BA%90%E7%A0%813.jpg)

```
/**
  * @author #hyper
  * @desc #描述
  导出allegro 焊盘和封装库，如不同目录下有相同焊盘或封装只导出最新的文件
  默认路径 "D:/ExportLib/",如元件比较多请耐心等待
  * @date 2019-06-05 17:56:21
  */

(axlCmdRegister "ExportLib" (quote ExportLib) ?cmdType "general") 

procedure( ExportLib()
    prog( nil
	ExportLib_Init()
	ExportLib_NewDir((ExportLib_gdata->lib_dir))
	ExportLib_CreateDir()
	foreach( item (ExportLib_gdata->dir_list)
	    ExportLib_MoveFiles(item)
	)
	;临时修改库路径，关闭brd后再打开无效，永久的方法是修改env
	/*foreach( item (ExportLib_gdata->path_list)
	    ExportLib_ClsPath(item)
	)
	foreach( item (ExportLib_gdata->path_list)
	    case( item
		("padpath"
		    ExportLib_AddPath(item 
			strcat((ExportLib_gdata->lib_dir) 
			    nth(5 
				(ExportLib_gdata->dir_list)
			    )
			)
		    ))
		("psmpath"
		    foreach( selpath remove("pad_pad" 
			(ExportLib_gdata->dir_list)
		    )
			ExportLib_AddPath(item 
			    strcat((ExportLib_gdata->lib_dir) selpath)
			)
		    ))
	    )
	    ExportLib_AddPath(item "./")
	)*/
	return()
    )
)

procedure( ExportLib_AddPath(tVarName tPath)
    let((lVarPath x) 
	(lVarPath = axlGetVariableList(tVarName)) 
	unless(listp(lVarPath) 
	    (lVarPath = list(lVarPath))
	) 
	unless(exists(x lVarPath 
		(x == tPath)
	    ) 
	    axlSetVariable(tVarName 
		cons(tPath lVarPath)
	    )
	)
    )
)

procedure( ExportLib_ClsPath(tVarName)
    prog( nil
	axlSetVariable(tVarName nil)
	return()
    )
)

procedure( ExportLib_CreateDir()
    prog( nil
	foreach( item (ExportLib_gdata->dir_list)
	    (item = strcat((ExportLib_gdata->lib_dir) item))
	    ExportLib_NewDir(item)
	)
	return()
    )
)

procedure( ExportLib_GetFiles(path file_ext)
    let((objs full_path) 
	(full_path = list()) 
	(path = simplifyFilename(path)) 
	(objs = ((isDir(path) && getDirFiles(path)) || nil)) 
	(paths = rexMatchList(file_ext objs))
	foreach( item paths
	    (full_path = cons(strcat(path "/" item) full_path))
	) full_path
    )
)

procedure( ExportLib_GetPath(tVarName)
    prog( nil
	return(axlGetVariableList(tVarName))
    )
)

procedure( ExportLib_Init()
    prog( nil
	unless(boundp('ExportLib_gdata) 
	    iliDefstruct('defstruct(ExportLib_gdata_struct dir_list lib_dir lib_exsit path_list)) 
	    defvar(ExportLib_gdata nil)
	)
	if( !ExportLib_gdata
	    then
	    (ExportLib_gdata = make_ExportLib_gdata_struct(?dir_list 
		    list("shape_ssm" "package_psm" "mechanical_bsm" "format_osm" "flash_fsm"
			"pad_pad"
		    ) ?lib_dir "D:/ExportLib/" ?lib_exsit
		    nil ?path_list 
		    list("padpath" "psmpath")
		))
	    else
	    (ExportLib_gdata->lib_exsit = t)
	)
	return()
    )
)

procedure( ExportLib_MoveFiles(typeStr)
    prog( (matchp file_ext dirs files file_name
	obj_path a b
    )
	(matchp = nth(1 
		parseString(typeStr "_")
	    ))
	(file_ext = strcat("." matchp "$"))
	if( rexMatchp("pad" matchp)
	    then
	    (dirs = ExportLib_GetPath("padpath"))
	    else
	    (dirs = ExportLib_GetPath("psmpath"))
	)
	foreach( item dirs
	    (files = ExportLib_GetFiles(item file_ext))
	    foreach( padfile files
		when(rexMatchp(file_ext padfile) 
		    (file_name = nth(2 
			    axlDMFileParts(padfile)
			)) 
		    (obj_path = strcat((ExportLib_gdata->lib_dir) typeStr "/" file_name)) 
		    if( isFile(obj_path)
			then
			(a = fileTimeModified(obj_path))
			(b = fileTimeModified(padfile))
			case( (a >= b)
			    (t
				nil)
			    (nil
				when(deleteFile(obj_path) 
				    axlOSFileCopy(padfile obj_path nil)
				))
			)
			else
			axlOSFileCopy(padfile obj_path nil)
		    )
		)
	    )
	)
	return()
    )
)

procedure( ExportLib_NewDir(dir_name)
    prog( nil
	if( isDir(dir_name)
	    then
	    unless(axlRecursiveDelete(dir_name) 
		axlUIConfirm("Delete File is false, Close the source and try again" 
		    'warn
		) 
		return()
	    )
	    createDir(dir_name)
	    else
	    createDir(dir_name)
	)
    )
)

procedure( ExportLib_SetPath(tVarName path_list)
    prog( nil
	axlSetVariable(tVarName path_list)
	return()
    )
) 
```