---
title: '【skill源码】为package（footprint）标注长宽高 skill源码'
date: Fri, 29 May 2020 06:19:41 +0000
draft: false
tags: ['Allegro', 'Allegro Skill']
---

标注对象"PACKAGE GEOMETRY/ASSEMBLY\_TOP"层图形的最大长度、最大宽度和"PACKAGE GEOMETRY/Place\_Bound\_Top"层Shape定义的最大高度

其它详见代码

![](http://a1024.synology.me:222/images/blog2022/DIMF.png)

```
;skill load("dimfootprint.il") 
(axlCmdRegister "df"
	'dimfootprint ?cmdType "general"
    )   
defun(dimfootprint nil 

	(unit = nthelem(1 
		(axlDBGetDesignUnits)
	    )) 
	if((unit == "mils") then 
	    (v100 = 6) 
	    (jiantoukuan = 4.72)
	    (jiantouchang = 9.65)
	    (offset = 0)
	    (beyondl = 0.12*39.37)
	    (v150 = 7) 
	    (v6 = 1)
	    (v25 = 0.5) 
	    (v50 = 10) 
	    (v1000 = 10) 
	    (v500 = 20) 
	    (v39 = 39.37)
	    (v600 = 6) 
	    (v300 = 3) 
	    (v750 = 7.5) 
	    (v250 = 2.5) 
	    (v350 = 3.5)
	) 
	if((unit == "millimeters") then 
	    (v100 = 6*0.0254) 
	    (jiantoukuan = 4.72*0.0254)
	    (jiantouchang = 9.65*0.0254)
	    (offset = 0*0.0254)
	    (beyondl = 0.12)
	    (v150 = 7*0.0254) 
	    (v6 = 1*0.0254)
	    (v25 = 0.5*0.0254) 
	    (v50 = 10*0.0254) 
	    (v1000 = 10*0.0254) 
	    (v500 = 20*0.0254) 
	    (v39 = 1)
	    (v600 = 6*0.0254) 
	    (v300 = 3*0.0254) 
	    (v750 = 7.5*0.0254) 
	    (v250 = 2.5*0.0254) 
	    (v350 = 3.5*0.0254)
	)
	(g_db_TxtBlockParam = (axlGetParam "paramTextBlock:1")) 
	(g_db_TxtBlockParam->width = v100) 
	(g_db_TxtBlockParam->photoWidth = v6) 
	(g_db_TxtBlockParam->lineSpace = v100) 
	(g_db_TxtBlockParam->height = v150)
	(g_db_TxtBlockParam->charSpace = v25) 
	(axlSetParam g_db_TxtBlockParam) 
	(text_size = (make_axlTextOrientation ?textBlock "1" ?rotation 0.0
		?mirrored nil ?justify "center"
	    )) 
	(text_size1 = (make_axlTextOrientation ?textBlock "1" ?rotation 90.0
		?mirrored nil ?justify "center"
	    )) 
	(x_list = nil)
	(y_list = nil) 
	(line_xy_list = nil) 
	(linelayer = "BOARD GEOMETRY/DIMENSION") 
	(linelayer1 = "PACKAGE GEOMETRY/ASSEMBLY_TOP") 
	(axlVisibleLayer linelayer t)
	(axlVisibleLayer linelayer1 t) 
	(axlFlushDisplay) 
	(axlSetFindFilter ?enabled 
	    list("noall" "lines" "shapes") ?onButtons 
	    list("noall" "lines" "shapes")
	) 
	(axlAddSelectAll) 
	(lines = (axlGetSelSet))
	(axlClearSelSet) 
	foreach(line_db lines 
	    (line_layer = (line_db->layer)) 
	    if((line_layer == "PACKAGE GEOMETRY/ASSEMBLY_TOP") then 
		foreach(linedb 
		    (line_db->segments) 
		    (line_xy = (linedb->startEnd)) 
		    (line_start = car(line_xy)) 
		    (line_xy_list = cons(line_start line_xy_list))
		    (line_end = nth(1 line_xy)) 
		    (line_xy_list = cons(line_end line_xy_list)) 
		    (line_x = car(line_start)) 
		    (x_list = cons(line_x x_list)) 
		    (line_x = car(line_end))
		    (x_list = cons(line_x x_list)) 
		    (line_y = nth(1 line_start)) 
		    (y_list = cons(line_y y_list)) 
		    (line_y = nth(1 line_end)) 
		    (y_list = cons(line_y y_list))
		)
	    )
	) 
	(x_list = sort(x_list 
		'lessp
	    )) 
	(y_list = sort(y_list 
		'lessp
	    )) 
	(x_min = car(x_list))
	(x_max = car(last(x_list))) 
	(y_min = car(y_list)) 
	(y_max = car(last(y_list))) 
	(line_width = 0) 
	(Path1 = list(((x_min + offset):y_min) ((x_min -  v500 - beyondl):y_min)	))
	(Path_1 = list(((x_min -  v500):y_min) (((x_min -  v500) - jiantoukuan/2):(y_min + jiantouchang)) ((x_min -  v500 + jiantoukuan/2):(y_min + jiantouchang)) ((x_min -  v500):y_min)  )) 
	(Path2 = list(((x_min + offset):y_max) ((x_min -  v500 - beyondl):y_max)  )) 
	(Path_2 = list(((x_min -  v500):y_max) (((x_min -  v500) - jiantoukuan/2):(y_max - jiantouchang)) ((x_min -  v500 + jiantoukuan/2):(y_max - jiantouchang))	((x_min -  v500):y_max)   )) 
	(Path_1_2 = list(((x_min -  v500):y_min) ((x_min -  v500):y_max)  )) 

	(Path3 = list((x_min:(y_max + offset)) (x_min:(y_max + v500 + beyondl)) ))
	(Path_3 = list((x_min:(y_max + v500)) ((x_min + jiantouchang):(y_max + v500 - jiantoukuan/2)) ((x_min + jiantouchang):(y_max + v500 + jiantoukuan/2))  (x_min:(y_max + v500))    )) 
	(Path4 = list((x_max:(y_max + offset)) (x_max:(y_max + v500 + beyondl))    )) 
	(Path_4 = list((x_max:(y_max + v500)) ((x_max - jiantouchang):(y_max + v500 - jiantoukuan/2)) ((x_max - jiantouchang):(y_max + v500 + jiantoukuan/2)) (x_max:(y_max + v500))    )) 
	(Path_3_4 = list((x_min:(y_max + v500)) (x_max:(y_max + v500))  )) 
	if((unit == "mils") then 
	    (changdu = ((x_max - x_min) / 39.37)) 
	    (kuandu = ((y_max - y_min) / 39.37)) 
	    sprintf(l_changdu "%0.2f" changdu)
	    sprintf(l_kuandu "%0.2f" kuandu) 
;	    (changdu_mil = (x_max - x_min)) 
;	    (kuandu_mil = (y_max - y_min)) 
;	    sprintf(l_changdu_mil "%0.2f" changdu_mil) 
;	    sprintf(l_kuandu_mil "%0.2f" kuandu_mil)
	)
	if((unit == "millimeters") then 
	    (changdu = (x_max - x_min)) 
	    (kuandu = (y_max - y_min)) 
	    sprintf(l_changdu "%0.2f" changdu)
	    sprintf(l_kuandu "%0.2f" kuandu) 
;	    (changdu_mil = ((x_max - x_min) * 39.37)) 
;	    (kuandu_mil = ((y_max - y_min) * 39.37)) 
;	    sprintf(l_changdu_mil "%0.2f" changdu_mil) 
;	    sprintf(l_kuandu_mil "%0.2f" kuandu_mil)
	) 
	(v_text_loc = (((x_max + x_min) / 2):(y_max + v500 + beyondl/2))) 
	(l_text_loc = ((x_min - v500 - beyondl/2):((y_max + y_min) / 2))) 
;	(v_text_loc_mil = (((x_max + x_min) / 2):(y_max + v500 + beyondl))) 
;	(l_text_loc_mil = ((x_max + v500 + beyondl):((y_max + y_min) / 2)))
	(axlDBCreateLine Path1 line_width linelayer) 
	(axlDBCreateLine Path_1 line_width linelayer) 
	(axlDBCreateLine Path2 line_width linelayer) 
	(axlDBCreateLine Path_2 line_width linelayer) 
	(axlDBCreateLine Path_1_2 line_width linelayer)
	(axlDBCreateLine Path3 line_width linelayer) 
	(axlDBCreateLine Path_3 line_width linelayer) 
	(axlDBCreateLine Path4 line_width linelayer) 
	(axlDBCreateLine Path_4 line_width linelayer) 
	(axlDBCreateLine Path_3_4 line_width linelayer)
	(axlDBCreateText l_changdu v_text_loc text_size linelayer) 
	(axlDBCreateText l_kuandu l_text_loc text_size1 linelayer) 
;	(axlDBCreateText l_changdu_mil v_text_loc_mil text_size linelayer) 
;	(axlDBCreateText l_kuandu_mil l_text_loc_mil text_size1 linelayer)
	
;);end jia mi when		
	axlVisibleLayer( "PACKAGE GEOMETRY/Place_Bound_Top" t )
	axlVisibleUpdate(t)
		axlSetFindFilter( ?enabled list("noall" "shapes") ?onButtons list("noall" "shapes"))
		axlClearSelSet()
		selObj = axlGetSelSet(axlAddSelectAll())
		selObjs = setof(x selObj x->layer == "PACKAGE GEOMETRY/PLACE_BOUND_TOP")
		selObjs2 = car(selObjs)
		height = selObjs2 ->prop ->PACKAGE_HEIGHT_MAX
		if( height == nil   then 
		vaheight = "Undefined"
		else 
		vaheight = atof(height) / v39
		sprintf(vaheight "%0.2f" vaheight)
		)
myorient = make_axlTextOrientation(?textBlock "1", ?rotation 0,?mirrored nil, ?justify "center")
	axlDBCreateText(vaheight,0:0,myorient,"BOARD GEOMETRY/DIMENSION",selObjs2)

	axlVisibleLayer( "PACKAGE GEOMETRY/PIN_NUMBER" nil )
	axlVisibleLayer( "REF DES/ASSEMBLY_TOP" nil )
	axlVisibleLayer( "DEVICE TYPE/ASSEMBLY_TOP" nil )
	axlVisibleLayer( "REF DES/SILKSCREEN_TOP" nil )

	axlSetActiveLayer("BOARD GEOMETRY/DIMENSION")
	axlVisibleUpdate(t)
;以下为设置标注尺寸参数的脚本，不需要的可以注释掉
when(axlVersion('version) == 16.2
script = outfile("./temp.scr")
fprintf(script "scriptmode +i +n\n")
fprintf(script "generaledit\ndraft param \n")
fprintf(script "setwindow form.draft_main\nFORM draft_main iso_standard YES \nFORM draft_main dim_text  \n")
fprintf(script "setwindow form.draft_dimtext\nFORM draft_dimtext text_block 1 \nFORM draft_dimtext done  \n")
fprintf(script "setwindow form.draft_main\nFORM draft_main dim_lines  \n")
fprintf(script "setwindow form.draft_dimline\nFORM draft_dimline arrow_length 0.240 \nFORM draft_dimline arrow_width 0.120 \nFORM draft_dimline done  \n")
fprintf(script "setwindow form.draft_main \nFORM draft_main dim_extension_lines  ")
fprintf(script "setwindow form.draft_extline\nFORM draft_extline offset 0.000 \nFORM draft_extline extension 0.120 \nFORM draft_extline done  \n")
fprintf(script "setwindow form.draft_main\nFORM draft_main done  \n")
fprintf(script "setwindow pcb\n")
	close(script)
	axlShell(strcat("replay " "./temp.scr"))
deleteFile("./temp.scr")
)

when(axlVersion('version) == 16.6
script = outfile("./temp.scr")
fprintf(script "scriptmode +i +n\n")
fprintf(script "generaledit\ndimension edit  \nprepopup\npop dyn_option_select @:@Parameters \n")
fprintf(script "setwindow form.draft_parms\nFORM draft_parms iso_standard YES \nFORM draft_parms text  \n")
fprintf(script "FORM draft_parms text_block_text 1  \nFORM draft_parms accuracy 2 \n")
fprintf(script "FORM draft_parms lines  \n")
fprintf(script "FORM draft_parms arrow_length '0.24 MM' \nFORM draft_parms arrow_width '0.12 MM' \n")
fprintf(script "FORM draft_parms offset '0 MM' \nFORM draft_parms extension '0.12 MM' \nFORM draft_parms done  \n")
fprintf(script "setwindow pcb\n FORM mini subcolor color 101\n")
	close(script)
	axlShell(strcat("replay " "./temp.scr"))
deleteFile("./temp.scr")
)

	)
```