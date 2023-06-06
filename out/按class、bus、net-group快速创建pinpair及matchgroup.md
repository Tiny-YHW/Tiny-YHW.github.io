---
title: 'Setup->Pinpair By Class or Bus快速创建Pinpair及Matchgroup'
date: Thu, 20 Aug 2020 08:21:18 +0000
draft: false
tags: ['TY-Skill']
---

功能说明
----

![](https://a1024.synology.me:222/images/blog2023/Pinpair-By-Class-or-Netgroup.jpg)

根据板中已创建的Class、Bus或Net Group，批量创建Pinpair并生成Matchgroup

本功能

│ ├─ 作 者：kevin wong  
│ ├─ Q Q：263350809

Tiny\_Y有对程序进行编辑更新

关联阅读：[SigXplorer 等长设置方法](https://a1024.synology.me:1024/?p=533)

使用方法
----

[抖音视频演示链接](https://v.douyin.com/kfrVFfp/) 或者抖音扫描下方二维码访问

![pinpair2.png](https://a1024.synology.me:222/images/blog2023/pinpair2.png)

老程序代码及UI（原作者的，本人更新部分不做公开）
-------------------------

![](https://a1024.synology.me:222/images/blog2022/pinpair2.png)

```
/* 
├─ 
│ ├─        程序名称：Quick_pinpair.il
│ ├─        程序功能：快速创建选择BUS/CLASS对应的pin pair
│ ├─        创建时间：2014年10月31日 
│ ├─        作    者：kevin wong
│ ├─        Q      Q：263350809
├─ 


1，2014.10.31开始构建主函数思路；
2，2014.11.07完成初步功能，测试通过；
3，2014.12.31修改添加部分按钮，提示；
4, 2020.08.20创建pinpair区分"Net Class" "Bus" "Net Group"，默认全不选，修改UI布局 BY:Tiny_Y
*/ 


axlCmdRegister( "quickpinpair" 'Quick_PinPair)
axlSetAlias("cpp" "quickpinpair")

;skill load("Quick_pinpair.il")

defun(Quick_PinPair ()
      let( (one allclass)
      	alleleclass_name =  list()
      	listtype = '("Net Class" "Bus" "Net Group")
      	ret = axlUIMultipleChoice("Please select a group type to creat pinpairs" listtype "which one")
      	(case ret
      		(0 allclass = axlDBGetDesign()->netclass selecttext = "Net Class")
      		(1 allclass = axlDBGetDesign()->bus selecttext = "Bus")
      		(2 allclass = axlDBGetDesign()->netGroup selecttext = "Net Group")
      	)
      foreach(one allclass
				 alleleclass_name = cons(list(one->name one) alleleclass_name)
			  )
      Quick_pinpairform()	  
	  )
  )


defun(Quick_pinpairform ()
        let( (curclass)
        Formfile = "./pinpairform.form"
		formport = outfile(Formfile "w")
		fprintf(formport "FILE_TYPE=FORM_DEFN VERSION=2\n")
        fprintf(formport "FORM\n") 
        fprintf(formport "FIXED\n")
		fprintf(formport "PORT 30 1\n")
        fprintf(formport "HEADER \"PinPair\"\n")
        fprintf(formport "TILE\n")   	
		
		fprintf(formport "\n")
		fprintf(formport "TEXT \"Select the object to create piniars\"\n")
		fprintf(formport "TLOC 2 1\n")
		fprintf(formport "ENDTEXT\n")



        fprintf(formport "FIELD sel\n")
        fprintf(formport "FLOC %d %d\n" 4 4)
        fprintf(formport "MENUBUTTON \"Select All\" 10 4\n")
        fprintf(formport "ENDFIELD \n\n")	
		
        fprintf(formport "FIELD desel\n")
        fprintf(formport "FLOC %d %d\n" 16 4)
        fprintf(formport "MENUBUTTON \"Deselect All\" 10 4\n")
        fprintf(formport "ENDFIELD \n\n")

		
        x = 2 
		y = 8
		foreach(curclass alleleclass_name
		         fieldname = car(curclass)
		fprintf( formport "FIELD %s\n" fieldname)
		fprintf( formport "FLOC %d %d\n" x+1 y)
		fprintf( formport "CHECKLIST \" %s\"\n" fieldname)		
		fprintf( formport "ENDFIELD\n\n")
		y= y+2
		       )
			   
        fprintf(formport "FIELD create\n")
        fprintf(formport "FLOC %d %d\n" x+2 y+1)
        fprintf(formport "MENUBUTTON \"Create\" 10 4\n")
        fprintf(formport "ENDFIELD \n\n")	
		
        fprintf(formport "FIELD cacel\n")
        fprintf(formport "FLOC %d %d\n" x+14 y+1)
        fprintf(formport "MENUBUTTON \"Close\" 10 4\n")
        fprintf(formport "ENDFIELD \n\n")
		
		fprintf(formport "ENDTILE\n")
        fprintf(formport "ENDFORM\n") 
        close(formport)
		
		displayform = axlFormCreate((gensym) Formfile '(ne inner) 'createpinpairact t)
		axlFormDisplay(displayform)
		
		foreach(curclass alleleclass_name
	            axlFormSetField(displayform car(curclass) nil)
				)
;		axlUIWPrint(displayform "Kevin Wong") 
		deleteFile("pinpairform.form")
     )
	)


defun(createpinpairact (displayform)
	  let( (membersel curclass onecl one alldp2net)

	alleleclass_name =  list()
      	(case ret
      		(0 allclass = axlDBGetDesign()->netclass selecttext = "Net Class")
      		(1 allclass = axlDBGetDesign()->bus selecttext = "Bus")
      		(2 allclass = axlDBGetDesign()->netGroup selecttext = "Net Group")
      	)
      foreach(one allclass
				 alleleclass_name = cons(list(one->name one) alleleclass_name)
			  )


	  membersel = displayform->curField
      case(membersel
	       ("sel" 
		        foreach(curclass alleleclass_name
	            axlFormSetField(displayform car(curclass) t)
				axlUIWPrint(displayform "Select All") 
				)		   
		   )
		   ("desel"
		        foreach(curclass alleleclass_name
	            axlFormSetField(displayform car(curclass) nil)
				axlUIWPrint(displayform "Deselect All") 
				)		   
		   )
		   ("create"
		    axlUIWPrint(displayform "Create the pinpair of selected BUS/Class") 
		    foreach(onecl alleleclass_name
			    alldp2net = cadr(onecl)->groupMembers
				  foreach(one alldp2net
				          if(one->type == "DIFF_PAIR" 
						     alldp2net = append(remove(one alldp2net) one->groupMembers)
							 )
						  )
			
			       if(axlFormGetField(displayform car(onecl))
			        then
			         curMGname = strcat("MG_" car(onecl))
				     allpinslist = list()
				     foreach(one alldp2net   
				         allpinslist = append1(allpinslist axlPinsOfNet(one 'pin))
						 )

				 get_min_pinlist(allpinslist)  
				     if(length(result) == 1
					      then
						  axlUIConfirm(strcat("there is some thing wrong with the BUS/Class " car(onecl)))
					    else
						  if(length(result) == 2
						    then
						    get_main_pinlist()
							Creat_Match_Group()
							else
							if(length(result) >= 3
							then
							  choice = axlUIMultipleChoice("Choose a device as a starting point"
							                       result strcat(selecttext " : " car(onecl)))
							  maindev = nth(choice result)
						        get_main_pinlist()
							    Creat_Match_Group()							  
							  )
							
							)
						)
				 )
				 )
             axlUIWPrint(displayform "Create the pinpair successfully!")			 
			)
		   ("cacel"
		        axlUIWPrint(displayform "Exit")
                axlFormClose(displayform)
                deleteFile(Formfile)		   
		   )
		   
		   
	       ) 

		 ) )       

defun( get_min_pinlist (allpinslist) 
      let( (one mlist pin2netlist i j curlist okflag)
	   mlist = list()
	      foreach(one nth(0 allpinslist)
		          mlist= cons(one->component->name mlist)   ;list(U1 U2)
				  )	  
       result = mlist   
	   foreach(pin2netlist allpinslist
	             curlist = pin2netlist 
				 
				 i = 0
	            while( (i < length(mlist))
				    j = nth(i mlist)
                     okflag = 0	
					  foreach(one curlist  
							  if(j == one->component->name
							     okflag++
							     )
							  ) 
							  
				        if(okflag == 0
					       result = remove(j result)   
					       ) 
					  i++
					  )  
					  
			   )  
			 ))
	          
defun( get_main_pinlist ()	

     	let( (curcalcu pinid containflag)	
	 pinneedres = list()	
     foreach(curcalcu allpinslist
			curcalcu = car(allpinslist)
			allpinslist = remove(curcalcu allpinslist)
			  foreach(pinid curcalcu
					 containflag = 0
					  foreach(one result
					          if(pinid->component->name == one
							     containflag++
							    )
							  )
					     if(containflag == 0
					        curcalcu = remove(pinid curcalcu)	)	
					 )
              if(length(result)>=3
                 then			 
				 foreach(one curcalcu
				         if(one->component->name == maindev
						    
							curcalcu = cons(one remove(one curcalcu))
							)
						 )
			      pinneedres = append1(pinneedres curcalcu)
			      else	
			  
			      pinneedres = append1(pinneedres curcalcu)
			  )
			  )
	  ))

	  
	  
defun( Creat_Match_Group ()
      let( (lastpinlist onepinlist lastpins onespin onelist curpinpair ref one onepin)
	  lastpinlist = list()
	  foreach(onepinlist pinneedres
	              lastpins = list()
	              foreach(one onepinlist
	                      onespin = strcat(strcat(one->component->name ".") one->number)
						  lastpins = append1(lastpins onespin)
			             )
			   lastpinlist = cons(lastpins lastpinlist)
			  )
	  if(length(result) == 2
	     then
		 axlMatchGroupDelete(curMGname)
		 axlMatchGroupCreate(curMGname)
		 
		 foreach(onelist lastpinlist
		         curpinpair = axlPinPair(car(onelist) cadr(onelist))
				 axlMatchGroupAdd(curMGname curpinpair)
				 )
		 else   
		 if(length(result)>=3
		 then
		 groupneedsuf = remove(maindev result)
		 foreach(ref groupneedsuf
		         axlMatchGroupDelete(strcat(strcat(curMGname "_") ref))
		         axlMatchGroupCreate(strcat(strcat(curMGname "_") ref))
				 )  
				 
		 foreach(one lastpinlist  
		         pinpre = car(one)  
				 pinsuflist = cdr(one)
				 
				 foreach(onepin pinsuflist
						 curpinpair = axlPinPair(pinpre onepin)
						 car(parseString(onepin "."))
						 axlMatchGroupAdd(strcat(strcat(curMGname "_") car(parseString(onepin "."))) curpinpair)
						 )
				 )
		 
		 
		   )
		 )

	  )) 
```