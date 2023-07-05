---
layout: post
title: Allegro Skill Form Interface Functions
categories: Allegro Skill
date: 2023-07-05
permalink: allegro-skill-form-interface-functions
excerpt: allegro有很多的form，比如artwork，比如status，还有些在Options Tab上显示的如change命令的form...... 能自己创建一些form会很有意思，也很有用。
---

## Form基本介绍

allegro有很多的form，比如artwork，比如status，还有些在Options Tab上显示的如change命令的form...... 能自己创建一些form会很有意思，也很有用。

### Form参考案例

*   C:\\Cadence\\SPB\_16.6\\share\\pcb\\examples\\skill\\form\\basic
*   C:\\Cadence\\SPB\_17.2\\share\\pcb\\examples\\skill\\form\\basic
*   C:\\Cadence\\SPB\_16.6\\share\\pcb\\examples\\skill\\form\\grid
*   C:\\Cadence\\SPB\_17.2\\share\\pcb\\examples\\skill\\form\\grid

### Form常规程序

1.  打开表单(axlFormCreate)
2.  初始化字段(axlFormSetField)
3.  显示表单(axlFormDisplay)
4.  与用户交互(axlFormCallback)
5.  关闭表单(axlFormClose)

## Form操作

### 通用控制

### axlFormSetField;axlFormGetField

为Form中的变量指定值；获取Form中变量的值

```lisp
axlFormSetField(form "user_age" 24)
axlFormGetField(form "user_age" ); ＝>24
```

### axlFormSetFieldEditable

将 individual form fields设置为可编辑 (t) 或灰色 (nil)。

```lisp
(axlFormSetFieldEditable form "diff-del" nil)
(axlFormSetFieldEditable form "diff-del" t)
```

### axlFormSetFieldVisible

### axlFormColorize

对Form中的控件定义背景色或字体颜色

```lisp
You can find an example in axlform.il.

axlFormColorize(f1s "string" 'text 'red)
Sets text of string control to red.

Example 2

axlFormColorize(f1s "string" 'background 'green)
Sets background of string control to green.

Example 3

axlFormColorize(f1s "string" 'text nil)
axlFormColorize(f1s "string" 'background nil)
Sets control back to default.

Example 4

axlFormColorize(f1s "string" 'background 1)
Sets control background to Allegro PCB Editor database color 1
```

```lisp
(axlFormColorize antiFormPort "anti_name" 'text 'red) 
(axlFormColorize antiFormPort "anti_author" 'text 'blue) 
(axlFormColorize antiFormPort "anti_date" 'text 'blue)
(axlFormColorize antiFormPort "anti_web" 'text 'blue) 
```

## multi-select list box控件控制

### axlFormListSelAll

对multiselect多选框进行全选和全不选

```lisp
axlFormListSelAll(fw "mlistfield" t)
axlFormListSelAll(fw "mlistfield" nil)
```

### axlFormListGetSelItems

仅适用于multi-select list box (OPTIONS multiselect in form file)

获取multiselect多选框已经被选择的值，返回值为选择对象的list，当没有任何选择或选择错误时返回nil

```lisp
axlFormListGetSelItems(fw "mlistfield")
```

### axlFormListGetSelCount

获取multiselect多选框被选择的数量，返回整数值，如果对象不是多选框时返回nil

```lisp
axlFormListGetSelCount(fw "mlistfield")
```

### axlFormListDeleteItem

删除列表中的指定项目。 您可以按字符串或按位置删除。 如果所有项目都是唯一的，则按字符串删除效果最好。 如果您让列表对添加到其中的项目进行排序，则位置可能会出现问题。注意：按列表删除仅支持字符串列表。

```lisp
axlFormListDeleteItem(setupdiff_symbol "mlistfieldndp" diffname);移除一条
while(axlFormListDeleteItem(form "activewidth" 0) nil);移除所有
```

## Form基本元素

form的define信息一般保存在一个.form的文件中，

文件的开头一般都是FILE\_TYPE=FORM\_DEFN VERSION=2。

正式的form信息从FORM关键字开始，以ENDFORM结束。

最常用的form元素有FIELD，TEXT，BUTTON。其它常用的还有Checkbox，Radiobox，Group。

在Form中定义一个item，一般是Text和Field，Field包含除Text以外 的所有类型，先确定是Text还是Field，然后是相对位置Location，然后是具体的类型，最后结束这个Item的定义

### 开头结尾固定格式以及一个最简单的Form程序

```lisp
(defun formdemo ()
    let((file port x y)
        file = "formdemo.form";form文件存储位置和文件名
        port = outfile(file "w");定义一个port准者写入内容
        fprintf(port "FILE_TYPE=FORM_DEFN VERSION=2\n");固定格式
        fprintf(port "FORM\n") ;固定格式
        fprintf(port "FIXED\n") ;固定格式
        fprintf(port "PORT 50 0\n") ;50代表窗体宽度
        fprintf(port "HEADER \"form\"\n") ;对话框标题名form
        fprintf(port "TILE\n")

        
        x=0
        y=0
        x=x+10;可用坐标运算方便调整窗体元素位置
        fprintf(port "TEXT \"Hello Word\"\n");文本示例
        fprintf(port "FLOC %d %d\n" x y)
        fprintf(port "ENDTEXT\n")
        
        fprintf(port "TEXT \"Author:Tiny-Y\"\n");文本示例
        fprintf(port "FLOC 10 4\n");也可以直接用坐标定义位置
        fprintf(port "ENDTEXT\n")

        fprintf(port "ENDTILE\n") 
        fprintf(port "ENDFORM\n") 

        close(port)

        form = axlFormCreate((gensym) file nil 'formdemo_callback t)
        axlFormDisplay(form)
        deleteFile(file)
    )
)

(defun formdemo_callback (form)

    (case form->curField
        (nil t)    
    )
)

formdemo
```

### 标题

```lisp
fprintf(port "TILE\n")
fprintf(port "ENDTILE\n") 

TILE [<tileLabel>]
[TPANEL tileType]
[{text_def}]
[{group_def}]
[{field_def}]
[{button_def}]
[{grid_def}]
[{glex_def}]
ENDTILE
```

## Form控件


### 标签TABSET / TAB

为Form提供多个分标签页类似Allegro *prmed* 命令对应的Form

可以在TAB/ENDTAB关键字中嵌套其他表单控件。

TAB只有一个选项fieldLabel，TABSET只有一个选项- tabsetDispatch，当用户点击时fieldValue设置为“t”

```lisp
TABSET [label]
[OPTIONS tabsetOptions]
FLOC x y
FSIZE w h
{tab_def}
ENDTABSET

TAB "<display>" [<label>]
[{text_def}]
[{group_def}]
[{field_def}]
[{grid_def}]
ENDTAB
```

```lisp
TABSET "tab"
OPTIONS tabsetDispatch
FLOC 2 1
FSIZE 42 27

TAB "Fillins"
TEXT "Enum single/drop:"
FLOC 2 2
ENDTEXT
ENDTAB

TAB "Fillins2"
TEXT "Enum single/drop:"
FLOC 2 2
ENDTEXT
ENDTAB

ENDTABSET
```

### 组Group

围绕其它控件的可见框，可以设置宽度，高度和可选的文本。

```lisp
GROUP "display" [label]
FLOC x y
[INFO label]
FSIZE w h
ENDGROUP
```

```lisp
fprintf(form "GROUP \"CLines Para\"\n")
fprintf(form "GLOC 1 1\n")
fprintf(form "FSIZE 25 10\n")
fprintf(form "ENDGROUP\n")
```

### 文本Text

#### Form中显示文本，指定文本格式为加粗文本

```lisp
TEXT "display" [label]
FLOC x y
[FSIZE w h]
text_type
OPTIONS textOptions]
ENDTEXT
```

**可选项OPTIONS**

*   bold - 粗体
*   underline - 下划线
*   border - 凹陷的边框
*   prettyprint - 使用大写/小写字母使文本更易读

*   left - 左对齐
*   center - 居中对齐
*   right - 右对齐

```lisp
TEXT \"I did it!\"
TLOC 6 2
OPTIONS BOLD
ENDTEXT
```

```lisp
x=2
y=2
fprintf(port "TEXT \"Multiselect(hold shift/control key)\"\n")
fprintf(port "FLOC %d %d\n"  x y)
fprintf(port "ENDTEXT\n")
```

### field

包含多种表现形式

```lisp
FIELD label;指定标识名称
FLOC x y;放置位置
[FSIZE w h] (8);控件大小
field_type;控件类型
field_options;控件变体形式
ENDFIELD;结束标识
```

#### field\_type控件类型

决定了field是一个什么样式的空间

*   REALFILLIN w fieldLength：输入框
*   LONGFILLIN w fieldLength：输入框
*   STRFILLIN w fieldLength：输入框
*   INTSLIDEBAR w fieldLength：输入框
*   ENUMSET w \[h\]
*   CHECKLIST "display" \["radioLabel"\]：单选或多选框
*   LIST "" w h：多选框
*   TREEVIEW w h
*   COLOR w h
*   THUMBNAIL \[<bitmapFile>|#<resource>\]
*   PROGRESS w h
*   TRACKBAR w h

#### field\_options

对field进行一些样式变化或指定限制等

\[INFO\_ONLY\]

*   sets field to be read only.

\[POP ""\]

*   assigns a popup with the field.
*   a POPUP definition by the same name should exist.
*   supported by field\_types: xxxFILLIN, INTSLIDEBAR, MENUBUTTON,  
    ENUMSET

\[MIN \] \[MAX \]

*   assigns a min and/or max value that field might have.
*   both supported by field\_types: LONGFILLIN, INTSLIDEBAR, REALFILLIN.
*   value by either by an integer or floating point number.

\[DECIMAL \]

*   assigns a floating min and/or max value that field might have.
*   assigns number of decimal places field has (default is 2)
*   both supported by field\_types: REALFILLIN

\[VALUE ""\]

*   initial field value.
*   supported by field\_types: xxxFILLIN

\[SORT\]

*   alphanumberic sorted list (default order of creation)
*   supported by field\_type: LIST

\[OPTIONS dispatchsame\]

*   for enumset fields only.
*   if present will dispatch to application drop-down selection even if the same  
    as current. By default, the form's package filters out any user selection if it is  
    the same as what is currently displayed.

\[OPTIONS prettyprint\]

*   for enumset fields only
*   displays contents of ENUM field in a visually pleasing way

\[OPTIONS ownerdrawn\]

*   for enumset fields only
*   used to display color swatches in an ENUM field. See  
    axlFormBuildPopup.

\[OPTIONS space\]

*   string type only
*   preserves leading and trailing white space. By default this is stripped.

\[OPTIONS dropfile\]

*   string and multiline types only
*   Allows a file to be dropped into the field (Windows drag and drop)  
    Shortcuts are not resolved.

#### 输入框

REALFILLIN 输入框小数 float number
STRFILLIN 输入框文本 string
INTSLIDEBAR 输入框整数 integer number

```lisp
FIELD label
FLOC x y
REALFILLIN w fieldLength;输入框小数
LONGFILLIN w fieldLength;
STRFILLIN w fieldLength;输入框文本
INTSLIDEBAR w fieldLength;输入框整数
field_options
ENDFIELD
```

#### checkbox 复选框

t/nil

```lisp
FIELD checkbox
FLOC 2 4
CHECKLIST \"A checkbox\"
ENDFIELD
```

```lisp
x=1
y=1
fprintf(port "FIELD pdflinkzoom\n")
fprintf(port "FLOC %d %d\n" x y)
fprintf(port "CHECKLIST \"Zoom\"\n")
fprintf(port "ENDFIELD\n")
x=x+15
fprintf(port "FIELD pdflinkshadow\n")
fprintf(port "FLOC %d %d\n" x y)
fprintf(port "CHECKLIST \"Shadow\"\n")
fprintf(port "ENDFIELD\n")  
```

#### Radio Button 单选框

t/nil

```lisp
fprintf(port "FIELD bottom_90\n")
fprintf(port "FLOC 30 4\n")
fprintf(port "FGROUP \"dir1_bottom\"\n")
fprintf(port "CHECKLIST \"dir1_bottom_90 \" \"dir1_bottom\"\n")
fprintf(port "ENDFIELD\n")

fprintf(port "FIELD bottom_270\n")
fprintf(port "FLOC 30 6\n")
fprintf(port "FGROUP \"dir1_bottom\"\n")
fprintf(port "CHECKLIST \"dir2_bottom_270 \" \"dir1_bottom\"\n")
fprintf(port "ENDFIELD\n")
;…………
axlFormSetField(form "dir1_bottom_90"    t)
axlFormGetField(form "dir2_bottom_270") => nil
```

#### list 多选框

string

```lisp
FIELD label
FLOC x y
LIST "" w h
list_options
ENDFIELD
```

```lisp
(fprintf port "FIELD mlistfield\n")
(fprintf port "FLOC %d %d\n"  x y)
(fprintf port "LIST \"\"27 8\n")
(fprintf port "OPTIONS multiselect prettyprint\n")
(fprintf port "ENDFIELD\n")    
```


```lisp
items = '("NET1" "NET2" "NET3" "NET4" "NET10" "GND" "VCC" "DP1" "DP2" "BUS1")
axlFormSetField(form "mlistfield" items )	

while(axlFormListDeleteItem(fw "mlistfield" 0) nil);移除所有
```

#### button 按钮

dispatch action only (t)

```lisp
FIELD label
FLOC x y
[FSIZE w h]
MENUBUTTON "display" w h
button_options
ENDFIELD
```

```lisp
fprintf(port "FIELD done\n")
fprintf(port "FLOC 4 8\n")
fprintf(port "MENUBUTTON \"OK\" 9 3\n")
fprintf(port "ENDFIELD\n")
```

#### 下拉选择

```lisp
POPUP <horizontal_popup> \"0\" \"0\",\"180\" \"180\".

FIELD F_popTopLongSideX
FLOC %d %d
ENUMSET 4
POP \"horizontal_popup\"
ENDFIELD
```

#### grid

```lisp
GRID fieldName
FLOC x y
FSIZE w h (8)
[OPTIONS INFO | HLINES | VLINES | USERSIZE | MULTISELROW ]
[POP "<popupName>"]

[GHEAD TOP|SIDE]
[HEADSIZE h|w]
[OPTION 3D|NUMBER|MULTI]
[POP "<popupName>"]
[ENDGREADH]
ENDGRID
```

## Form显示控制axl函数

### axlFormCreate;axlFormDisplay

创建一个Form；将Form显示出来

axlFormCreate函数用于加载一个FORM，并返回创建FORM的DBID，axlFormCreate一般结构为：

```lisp
axlFormCreate(
	s_formHandle
	t_formfile
	[lt_placement]
	g_formAction
	g_nonBlock
	[g_stringOption]
	)
⇒ r_form/nil
```

注意，FORM必须为FIXED类型，否则将不能使用axlFormCreate创建form，使用该函数创建FORM后，并不会立即将FORM显示出来，必须使用axlFormDisplay函数显示FORM。

*   s\_formHandle : 这个代表FORM的句柄，简单的理解，就是该FORM在那个窗口上显示，一般这个参数我们使用 (gensym)
*   t\_formfile ：这个指定FORM文件的完整路径。
*   \[lt\_placement\] ：可选参数，这个代表FORM的显示位置。当使用nil 时，allegro会调用默认的位置显示。
*   下面是位置参数\[lt\_placement\](注，使用的时候选择括号中的字母即可)
    *   north(n) northeast(ne) east(e) southeast(se)
    *   south(s) southwest(sw) west(w) northwest(nw)
    *   center(c)
    *   Inner or Outer 设置FORM显示在ALLEGRO里面还是外面，默认为里面即 Inner
    *   Canvas or Window 设置FORM显示在drawing area还是整个windows，drawing area即allegro中绘制PCB的区域（简单理解，就是黑色的那个大区域）
    *   其他还包括Border or NoBorder、MsgLines (Default 1)，这儿就不说了，基本上很少用到。
    *   比如我想显示在左上角，即northwest(nw)，且在drawing area区域显示，那么lt\_placement参数就使用(nw Canvas)
*   g\_formAction ：对FORM所有触发事件响应的函数，比如对点击某个按钮，则会执行该函数。
*   g\_nonBlock ：可设置FORM是否在non-blocking模式下运行。
*   \[g\_stringOption\] ：可选参数，如果为t，那么form返回的所有值都为string格式。一般设置为nil

返回值：r\_form/nil ，加载成功则返回form的dbid，否则返回nil

一般form创建好后form文件应及时删除，避免成为垃圾文件

```lisp
form = axlFormCreate( (gensym) file nil `form_action t nil)
axlFormDisplay(form)
deleteFile(file)

form = axlFormCreate( (gensym) "form.form" '(se outer) '_formtestCallBk t )
axlFormDisplay(form)
deleteFile("form.form")
```

这里加载一个FORM，显示在southeast(se)，事件函数为\_formtestCallBk。

```lisp
fw = axlFormCreate('_mil_fw list("form" inLineForm) 
		'("msgLines" 0) 'mil_CB t nil)
axlFormDisplay(fw)
deleteFile("form")
```

## 创建一个简单的Form之callback函数

Form显示出来对应的是种前台操作，而响应用户相应的操作则可以称之为后台操作。创建一个Form的时候都会有个call back函数assign给它。 call back函数里面包含了对应各个Field的操作命令。比如：

```lisp
defun(form_callback (form)
    ;let((nil)
    case(form->curField;curField 将得到当前用户操作的Field名字                
        ("case1"                  
            axlMsgPut( sprintf( nil "current case1 %s" user_Form-> curValue ) ); curValue将得到当前Field的值
            )                 
        ("case2"  
            t; dosomething
            )              
        ("CloseForm"                  
            axlFormClose(form)
            )
        )
    )
```

### axlMiniStatusLoad

这个函数可以让用户定义的form显示在Options Tab上。

```lisp
fw = axlMiniStatusLoad('_mini_fw list("mini_test" inLineForm) 'mini_inlineCB)
```

### axlUIWExpose axlUIWExposeByName

打开并重新显示隐藏的的窗口， 将选择的窗口显示到最前端 。

如果为nil，则显示主窗口。

### axlUIWShow显示或隐藏某个窗口

axlUIWShow => axlUIWShow(userDefinedForm option);

option 'show =>显示并激活userDefinedForm; 'showna 显示但不激活; 'hide 窗口隐藏;

```lisp
(axlUIWShow Form 'hide)
(axlUIWShow Form 'show)
(axlUIWShow Form 'showna)
```

### axlFormClose关闭一个Form

```lisp
(case form->curField
  ("done"
   (axlFormClose form)
   (axlCancelEnterFun)
   (_extract)
   t)
```

### axlUIWPrint

在主窗口显示一条信息

```lisp
axlUIWPrint(r_window/nil t_formatString [g_arg1 ...])
axlUIWPrint(nil "Command Finished.") 
```

## 创建一个Grid Form

Grid比较适合制作表格形式的Form，比如假设我们想做个Form来显示当前工作文件夹下面的所有文件，用Grid就会比较合适，定义一个三列的表 格，第一列显示第几个文件，第二列显示文件名，第三列显示文件大小，而这用一般的Form形式来实现会比较麻烦。比如把下面这段Grid信息加入到一般的 form定义文件中，就会支持Grid的相关操作：

```lisp
"GRID crsGrid" "FLOC 2 1" "FSIZE 42 27" "OPTIONS HLINES VLINES USERSIZE"
"GHEAD TOP" "HEADSIZE 3" "OPTIONS 3D MULTI" "ENDGHEAD"
"GHEAD SIDE" "OPTIONS 3D NUMBER" "HEADSIZE 5" "ENDGHEAD"
```

"ENDGRID" 如下的代码则会帮助你设置这个Grid空间，比如这里设置了3列，每列各代表一些意思。

```lisp
tGridCol = make_formGridCol()
tGridCol->fieldType = 'LONG tGridCol->colWidth = 2 tGridCol->align = 'center tGridCol->headText = "Count" tGridCol->scriptLabel = nil
axlFormGridInsertCol( user_form "crsGrid" tGridCol )

tGridCol->fieldType = 'TEXT tGridCol->colWidth = 8 tGridCol->headText = "File Name" tGridCol->align = 'left tGridCol->scriptLabel = nil 
axlFormGridInsertCol( user_form "crsGrid" tGridCol )

tGridCol->fieldType = 'LONG tGridCol->colWidth = 2 tGridCol->align = 'center tGridCol->fieldLength = 4 tGridCol->min = 1 tGridCol->max = 10 tGridCol->headText = "Size"
axlFormGridInsertCol( user_form "crsGrid" tGridCol ) 
```

相应的form操作函数也包含了Grid关键字，如axlFormGridUpdate，axlFormGridOptions...

## 获取Form信息

Form的属性值

### curField

Form中当前操作的对象string
form->curField

### curValue

Form中当前操作对象对应的值
form->curValue

### curValueInt

Value dependant upon field type (2).

### doneState

int

0 = action; 1 = done; 2 = cancel; 3 = abort (1)

### form

string

Name of this form (form file name).

### isChanged

t / nil

t \= user has changed one or more fields.

### isValueString

t / nil

t all field values are strings.  
nil one or more fields are not strings.

### objType

string

Type of object; in this case form.

### type

string

Always fixed.

### fields

list of strings

All fields in the form (3).

### infos

list of strings

All info. fields in form (3).

### event

symbol

List, tree and grid control only.  
See axlFormGridDoc for grid info, otherwise see bullets 4 and 5 in the following **_Note_** section.

### row

integer

Grid control only.

### col

integer

Grid control only.

### treeViewSelState

integer

Tree control only.


## inLineForm弹出对话框

```lisp
inLineForm = '("

	FILE_TYPE=FORM_DEFN VERSION=2
	FORM
	FIXED
	PORT 16 4
	HEADER \"In-Line Example\"

	TILE

	TEXT \"I did it!\"
	TLOC 6 2
	OPTIONS BOLD
	ENDTEXT

	FIELD checkbox
	FLOC 2 4
	CHECKLIST \"A checkbox\"
	ENDFIELD

	FIELD done
	FLOC 4 8
	MENUBUTTON \"OK\" 9 3
	ENDFIELD
	ENDTILE

	ENDFORM
")

procedure( stand_inline()
    let( (fw)
    fw = axlFormCreate('_mil_fw list("myform" inLineForm) 
		'("msgLines" 0) 'mil_CB t nil)
    axlFormDisplay(fw)
))

procedure( mil_CB(fw)
    prog(()
     unless((fw->doneState == 0)
	 axlFormClose(fw)
	 return(t)
     )
))
```

## mini\_inlineForm内嵌Option页

```lisp
procedure( mini_inline()
    let( (fw)
    fw = axlMiniStatusLoad('_mini_fw list("mini_test" inLineForm) 'mini_inlineCB)
))

procedure( mini_inlineCB(fw)
     ; note cannot close the form
     printf("CURFIELD %L has value %L\n" fw->curField, fw->curValue)
)
mini_inline()()
```

axlFormAutoResize  
axlFormBNFDoc  
axlFormBuildPopup  
axlFormCallback  
axlFormClearMouseActive  
axlFormDefaultButton  
axlFormGetActiveField  
axlFormGetFieldType  
axlFormGridBatch  
axlFormGridCancelPopup  
axlFormGridDeleteRows .  
axlFormGridEvents  
axlFormGridGetCell  
axlFormGridInsertCol  
axlFormGridInsertRows  
axlFormGridNewCell  
axlFormGridOptions  
axlFormGridReset  
axlFormGridSelected  
axlFormGridSelectedCnt  
axlFormGridSetBatch  
axlFormGridSetSelectRows  
axlFormGridUpdate  
axlFormInvalidateField  
axlFormIsFieldEditable  
axlFormIsFieldVisible  
axlFormListAddItem  
axlFormListDeleteAll  
axlFormListGetItem  
axlFormListOptions  
axlFormListSelect  
axlFormMsg  
axlFormRestoreField  
axlFormSetActiveField  
axlFormSetDecimal  
axlFormSetEventAction  
axlFormSetFieldLimits  
axlFormSetInfo  
axlFormSetMouseActive  
axlFormTest  
axlFormTitle  
axlFormTreeViewAddItem  
axlFormTreeViewChangeImages  
axlFormTreeViewChangeLabel  
axlFormTreeViewGetImages  
axlFormTreeViewGetLabel  
axlFormTreeViewGetParents  
axlFormTreeViewGetSelectState  
axlFormTreeViewLoadBitmaps  
axlFormTreeViewSet  
axlFormTreeViewSetSelectState