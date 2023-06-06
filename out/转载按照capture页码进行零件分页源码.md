---
title: '【skill源码】[转载]按照Capture页码进行零件分页源码'
date: Wed, 17 Jun 2020 09:35:41 +0000
draft: false
tags: ['Allegro Skill']
---

;-------------------------------------------------------------------------------------------------------------------------------------------------------------------  
;      pg\_placement.il    ver0.1  
;                                           ------------by  shirdon  
;     This program can attach the page property to component.  
;     I can be reached by:  
;                shirdon1@163.com  
; 对于该程序的执行方式请参照 deargds的  [http://www.eda365.com/thread-4373-1-1.html](http://www.eda365.com/thread-4373-1-1.html)  【将xpart.xrf 改为pg.xrf即可，也可按照自己的习惯更改】  
;-------------------------------------------------------------------------------------------------------------------------------------------------------------------

```
axlCmdRegister( "pp" '_pg_placement)
defun(_pg_placement ()
 prog((pgfile )
 pgFile = infile( "./pg.xrf" ); read a file named pg.xrf
 when(pgFile ;pg.xrf existed
 while(gets(nextline pgFile) ;-read a line from the file [loop] until readling finished
 line_lst = parseString(nextline "\t");-make some line from string to list
 when( length(line_lst) >5
 refdes_name = nthelem(3 line_lst) ;-get the third element from the list[line_lst]
 page_no = nthelem(5 line_lst);-get the fifth element from the list[line_lst]
 if(atof(page_no) then ;-atof(page_no) whether number
 axlClearSelSet()  
 axlSetFindFilter(?enabled '("noall" "alltypes" "nameform")
 ?onButtons "alltypes")
 axlSingleSelectName( "component" refdes_name)
 axlDBCreatePropDictEntry( "Page"  "INTEGER"  list( "components"))    ;-set the page property rule
 axlDBAddProp(axlGetSelSet() list( "Page" truncate(atof(page_no)))) ;-attach the page property to the component
         sprintf(info_n "%s has attached the property Page %s" refdes_name page_no)
 println(info_n)
 );end if
 );end if
 );end while
 );end when
        print("Page property ok")
 close(pgFile)
 axlClearSelSet()
 )
)
```