---
title: '【skill源码】bmp2layer 直接解析bmp源码，从网上ic用的skill移植过来，用于图像识别'
date: Wed, 17 Jun 2020 09:37:39 +0000
draft: false
tags: ['Allegro Skill']
---

1、适用性不高，仅供参考，  
2、可以作为图像识别的入口，只要你愿意深入研究，解析png,jpg等图片格式都不是问题

```
/**
  * @author #hyper
  * @desc #描述
  * @date 2017-12-14 18:59:59
  */


 axlCmdRegister("BMP_import" `BMP_import ?cmdType "general")


(procedure BMP_import()
 prog((win cv bmpfile bmpSize WORD Wnum number Grid Layer row column max_column
 i dot x y signature offset width height pixel ImageSize )
 
 ; win = hiGetCurrentWindow()
 
 ; cv = getEditRep(win)
 
 ; bmpfile = "~/number_mini.bmp" ;;; Input BMP File
 bmpfile = "./test.bmp" ;;; Input BMP File
 ; Layer = list("TTOPME" "drawing") ;;; Output Layer
 Grid = 3 ;;; Rectangle Size
 column = 0
 fid = nil
 
 ; (procedure MessageForm(text)
 ;     prog( ()
 ;  hiDisplayAppDBox(
 ;  ?name 'JWDBox_Message
 ;  ?dboxBanner "Message!!"
 ;  ?buttonLayout 'Close
 ;  ?dboxText text
 ;  )
 ;     );prog
 ; );procedure
 
 ;Read BMP file
 if(InFile = infile(bmpfile) then
 bmpSize = fileLength(bmpfile)
 declare(WORD[bmpSize])
 for(Wnum 0 bmpSize-1 WORD[Wnum] = charToInt(getc(InFile)) )
 close(InFile)
 else
 ; MessageForm("Input file does not exist!")
 return()
 )
 
 sprintf(signature "%02x%02x" WORD[0] WORD[1])
 offset = (WORD[0x0d]<<24) + (WORD[0x0c]<<16) + (WORD[0x0b]<<8) + WORD[0x0a]
 width  = (WORD[0x15]<<24) + (WORD[0x14]<<16) + (WORD[0x13]<<8) + WORD[0x12]
 height = (WORD[0x19]<<24) + (WORD[0x18]<<16) + (WORD[0x17]<<8) + WORD[0x16]
 pixel  = (WORD[0x1d]<<8) + WORD[0x1c]
 ImageSize = (WORD[0x25]<<24) + (WORD[0x24]<<16) + (WORD[0x23]<<8) + WORD[0x22]
 
 printf("--- BMP2LAY Start --- %L\n" getCurrentTime())
 printf("offset  : 0x%x \n" offset)
 printf("width   : 0x%x \n" width)
 printf("height  : 0x%x \n" height)
 printf("ImgSize : 0x%x \n" ImageSize)
 
 ;check bmp file
 if(!equal(signature "424d") then
 ; MessageForm("*ERROR* Standard Input is not a BMP file")
 return()
 )
 
 ;check mono bmp file
 if(!equal(pixel 0x01) then
 ; MessageForm("*ERROR* only supports mono bmp files")
 return()
 )
 
 ;BMP2LAY
 max_column = ImageSize/height<<3
 number = offset+ImageSize-1
 
 for(Wnum offset number
 row = fix((Wnum-offset)/(max_column>>3))
 y = Grid*row
 
 for(i 0 7
 dot = bitfield1(WORD[Wnum] 7-i) ; bit<7> ~ bit<0>
 x = Grid*column
 if(zerop(dot) && column<width then
 ; geSelectObject(dbCreateRect(cv Layer list(x:y x+Grid:y+Grid)))
 ; axlShell("pause 1")
 sid = axlDBCreateRectangle(list(x:y x+Grid:y+Grid) t axlGetActiveLayer())
 ; axlGRPDrwRectangle(r_graphics l_upper_left l_lower_right)
 ; axlZoomToDbid(car(sid)  t)
 ; axlWindowFit()
 
 )
 column++
 );for
 if(equal(column max_column) column=0)
 Wnum++
 );for
 ; axlWindowFit()
 ;hiZoomIn(win list(-10:-10 x+10:y+10))
 printf("--- BMP2LAY End ----- %L\nt\n" getCurrentTime())
 );end prog
);end procedure
```