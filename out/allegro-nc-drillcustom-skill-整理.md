---
title: '【skill源码】Allegro NC DrillCustom Skill 整理'
date: Thu, 03 Sep 2020 09:31:54 +0000
draft: false
tags: ['Allegro Skill']
---

1、源代码：  

---------

@Vincent\_杜(695744007)

axlCmdRegister("quicksetnccus " 'quicksetnccus

defun( quicksetnccus ()

```
axlPurgePadstacks('padstacks nil)
axlPurgePadstacks('via nil)
axlShapeDynamicUpdate(nil nil)
let( ()

;get  & set thr padstacks' drillcharactor

            allpadID = axlDBGetDesign()->padstacks


            thrcplist = throplist = thrrplist = list()
            foreach(one allpadID
                drilltype = one->holeType

                if(drilltype == "circle_drill" then
                    drill_dia = one->drillDiameter
                    if(drill_dia>0 then
                        thrcplist = append1(thrcplist one)
                    )                   

                )


                if(drilltype == "oval_slot" then
                    o_drill_width= one->drillSizeWidth
                    o_drill_heigth= one->drillSizeHeight
                    if(o_drill_width>0 && o_drill_heigth>0 then
                        throplist = append1(throplist one)
                    )                   

                )                   


                if(drilltype == "RECTANGLE_SLOT" then
                    r_drill_width= one->drillDiameter
                    r_drill_width= one->drillDiameter
                    if(r_drill_width>0 && r_drill_heigth>0 then
                        thrrplist = append1(thrrplist one)
                    )                   

                )                       




            )


;make a list of the circle drillhole  by the drillDiameter

             newthrcplist = list()
             i = 0
             j = 1
             oldlength = length(thrcplist)
             while(i<oldlength
                minp = nth(0 thrcplist)
                minpd = minp->drillDiameter
                j = 1
                while(j<length(thrcplist)
                    temppad = nth(j thrcplist)
                    temppadd = temppad->drillDiameter
                    if(minpd > temppadd
                       then
                       minp = temppad
                       minpd = minp->drillDiameter
                       )
                    j= j +1
                    )
                 newthrcplist = append1(newthrcplist minp)
                 thrcplist = remd(minp thrcplist)
                 i = i+1
                 )







          newThrpadID = append(newthrcplist append(throplist thrrplist))




            beginint = 49
            foreach(padtid newThrpadID


                drill_type = padtid->holeType

                cond(
                    (equal(drill_type "circle_drill")   axlPadstackEdit(padtid 'drillFigureName "CIRCLE"))
                    (equal(drill_type "oval_slot") axlPadstackEdit(padtid 'drillFigureName "OBLONG"))
                    (equal(drill_type "RECTANGLE_SLOT") axlPadstackEdit(padtid 'drillFigureName "RECTANGLE"))
                )


                if(beginint <= 57
                  then
                    axlPadstackEdit(padtid 'drillChar symbolToString(intToChar(beginint)))
                    beginint = beginint+1
                else
                    n_left = (beginint-48)/10
                    n_right = mod((beginint-48) 10)
                    firstChar = intToChar(n_left+48)
                    secondChar = intToChar(n_right+48)
                    DoubChar = strcat(symbolToString(firstChar) symbolToString(secondChar))
                    axlPadstackEdit(padtid 'drillChar DoubChar)
                    beginint = beginint+1

                )  

            )




)
```

2、参考代码：
-------

```
@H●Horven（707577845）
procedure( quicksetnccus()
	let(()
		dillpads = setof(x0 axlDBGetDesign()->padstacks x0->drillDiameter > 0)
		foreach(n0 dillpads
			tt = setof(x0 dillpads n0->drillDiameter == x0->drillDiameter && n0->plating = x0->plating && n0->drillFigureName = x0->drillFigureName )
			when(tt
				println(n0->??)
				println(tt)
				)
			)
		)
	)
```

3、修改后：
------

```
axlCmdRegister("quicksetnccus " 'quicksetnccus )

defun( quicksetnccus ()
	let( ()
		axlPurgePadstacks('padstacks nil)
		axlPurgePadstacks('via nil)
		axlShapeDynamicUpdate(nil nil)

		newThrpadID = setof(x0 axlDBGetDesign()->padstacks x0->drillDiameter > 0)
		tempSize = unique(newThrpadID~>drillDiameter)
		tempSize = sort(tempSize 'lessp)
		i = 49
		(foreach item tempSize
		    (foreach padtid setof(x0 axlDBGetDesign()->padstacks x0->drillDiameter == item)
		    	drill_type = padtid->holeType
				cond(
					(equal(drill_type "circle_drill") 	axlPadstackEdit(padtid 'drillFigureName "CIRCLE"))
					(equal(drill_type "oval_slot") axlPadstackEdit(padtid 'drillFigureName "Oblong Y"))
					(equal(drill_type "RECTANGLE_SLOT") axlPadstackEdit(padtid 'drillFigureName "RECTANGLE"))
					)
			    if(i <= 57
				then
					axlPadstackEdit(padtid 'drillChar symbolToString(intToChar(i)))
				else
					n_left = (i-48)/10
					n_right = mod((i-48) 10)
					firstChar = intToChar(n_left+48)
					secondChar = intToChar(n_right+48)
					DoubChar = strcat(symbolToString(firstChar) symbolToString(secondChar))
					axlPadstackEdit(padtid 'drillChar DoubChar)
				)
		    )
			i = i+1
		)
	)
)
```

4、运行效果：
-------

![](https://a1024.synology.me:1024/wp-content/uploads/2020/09/123-1.jpg)

```
(equal(drill_type "oval_slot") axlPadstackEdit(padtid 'drillFigureName "Oblong Y"))
drillFigureName的类型不匹配，有兴趣自行研究
```