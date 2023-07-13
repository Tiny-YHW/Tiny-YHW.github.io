---
layout: post
title: 自用env文件定义内容
categories: Allegro
permalink: cadence-allegro-personal-env
excerpt:
date: 2023-07-13
---

我自用的ENV配置，可做参考

```
#解决拖影BUG
#set infinite_cursor_bug_nt
#17.2 Xnet 问题修正
set CDS_XNET_STATE_UI = 1

#windows命令
alias ~N new
alias ~O open
alias ~S save
alias ~Z undo
alias ~Y redo

#方向键调整视图
set roamInc = 96
funckey Up        "roam y -$roamInc"
funckey Down      "roam y $roamInc"
funckey Left      "roam x -$roamInc"
funckey Right     "roam x $roamInc"

#选择对象，按格点移动
alias CUp "move;FORM mini rotate_point User Pick; ipick_to_gridunit 0; ipick_to_gridunit 0 +1"
alias CDown "move;FORM mini rotate_point User Pick; ipick_to_gridunit 0; ipick_to_gridunit 0 -1"
alias CLeft "move;FORM mini rotate_point User Pick; ipick_to_gridunit 0; ipick_to_gridunit -1"
alias CRight "move;FORM mini rotate_point User Pick; ipick_to_gridunit 0; ipick_to_gridunit +1"

#相对跳转一个格点
alias CSUp        "ipick_to_gridunit 0 +1"
alias CSDown      "ipick_to_gridunit 0 -1"
alias CSLeft      "ipick_to_gridunit -1"
alias CSRight     "ipick_to_gridunit +1"


#add line、add connect、Shape Add时线型模式切换，CF11切换直线和圆弧
alias changeline "options dyns_lock_mode Line;FORM mini lock_mode Line"
alias changearc "options dyns_lock_mode Arc;FORM mini lock_mode Arc"
alias CF11 'settoggle CMD changearc changeline;$CMD'

#add line、add connect、Shape Add时线型模式切换，CF12切换角度
alias changge45 "FORM mini lock_direction 45;FORM mini dyns_lock_mode Line 45"
alias changge90 "FORM mini lock_direction 90;FORM mini dyns_lock_mode Line Orthogonal"
alias changgeoff "FORM mini lock_direction Off;FORM mini dyns_lock_mode Line"
alias CF12 'settoggle CMD changge45 changge90 changgeoff;$CMD'

#Add Clines 线宽指定为15
alias F12 options acon_line_width 15

#同步AD
funckey l mirror
funckey S shadow toggle
funckey dr cmgr
funckey pl add line
funckey ps add text
funckey pf shape add rect
funckey dk xsection
funckey di netin
funckey dp dlib
funckey vf zoom fit
funckey nha unrats all
funckey nsa rats all
funckey nho unrats component
funckey nso rats component
funckey nhn unrats net
funckey nsn rats net
funckey td cns cmmodes
funckey rm show measure
funckey CInsert copy
funckey SInsert paste
funckey R 'settoggle mode Off "Hug only" "Shove preferred"; options bubble_space $mode'
#设置 空格为 旋转90度和改变差分扇孔方向
funckey ' ' "angle 90;pop viapattern next"

#查找元器件或网络对象
funckey jc "prepopup ; pop dyn_option_select 'Selection set@:@Clear all selections';set prompt;prompt 'Find Ref Des';refdes $prompt;zoom selection"
funckey jn "prepopup ; pop dyn_option_select 'Selection set@:@Clear all selections';set prompt;prompt 'Find Net Name';net $prompt;zoom selection"

#快捷键
funckey 7 copy
funckey 4 show measure
funckey 1 show element
funckey 8 change
funckey 5 spread between voids
funckey 0 net schedule
funckey X swap components
alias SF12 custom smooth
;alias SF8 replay C:/MentorGraphicsVX/EEVX.2.3/SDD_HOME/Valor_NPI/share/dofiles/cadence.PCname

#Layout高频按键-功能区
alias Del toggle
alias Insert oops
alias Home add connect
alias End slide
alias Pgup zoom in
alias Pgdown zoom out
alias CHome add line
alias CEnd vertex
alias CDel waive drc
alias SDel delete
alias SEnd delay tune
alias CPgup cancel
alias CPgdown next

#活动层切换
funckey + subclass -+
funckey - subclass --

#  replay 路径  为调用脚本 注意
#funckey 6 replay ~\pcbenv\scr\temp
alias mb replay ~\pcbenv\scr\moban
funckey ~0 replay ~\pcbenv\scr\dynfulltype
# funckey 和 alias 的区别 只可意会

#Shape全命令
alias SUp shape add
alias SDown shape edit boundary
alias SLeft shape select
alias SRight pop net list
alias CSEnd fse_shape_chamfer

#吸附快捷键
funckey ss "prepopup; pop dyn_option_select 'Snap pick to@:@Segment Vertex'"
funckey se "prepopup; pop dyn_option_select 'Snap pick to@:@Segment Midpoint'"
funckey sd "prepopup; pop dyn_option_select 'Snap pick to@:@Pin'"
funckey sa "prepopup; pop dyn_option_select 'Snap pick to@:@Arc/Circle Center'"
funckey sv "prepopup; pop dyn_option_select 'Snap pick to@:@Via'"
funckey si "prepopup; pop dyn_option_select 'Snap pick to@:@Intersection'"
funckey sx "prepopup; pop dyn_option_select 'Snap pick to@:@Pad Edge Vertex'"

#鼠标光标大十字和小十字切换
funckey = "settoggle pcb_cursor infinite cross"
#差分走线切换单线和双线模式，add connect时直接使用
funckey sx "prepopup;pop singletrace"

#debug skill
alias 63 skill 'load("ceshi.il")'
#set telskill 实为skill调试窗口 calc为计算器 此处可使用为借用计算功能
funckey calc set telskill

#重新加载env
alias renv 'source -q $localenv/env'
#重新打开上次保存的设计
alias reopen 'open -q $module'

#常用命令互通
alias window	zoom
alias hilite	hilight
alias dehilite	dehilight
alias pickx	pick
alias picky	pick l
alias ipickx	ipick
alias ipicky	ipick 0
alias x pick
alias y pick l
alias ix ipick
alias iy ipick 0

#滚轮功能
set buttonfactor = 1
button wheel_up "zoom in $buttonfactor"
button wheel_down "zoom out $buttonfactor"
button Cwheel_up "zoom in $buttonfactor"
button Cwheel_down "zoom out $buttonfactor"

#显示和取消显示全指令
alias scr+ "scriptmode +e"
alias scr- "scriptmode -e"

#用户设置
set logic_edit_enabled
set showmeasure_altunits = millimeters
set allegro_long_name_size = 255
set no_dragpopup
set padpath = . ../lib ./lib ./symbols D:/Archive/lib/padstacks
set psmpath = . ../lib ./lib ./symbols D:/Archive/lib/mech D:/Archive/lib/symbols
set steppath = . step ../step D:/Archive/lib/step
set acon_no_width_override_retain
set acon_oldhlt = all
set ipc356_nomechpin_warnings
set autosave
```