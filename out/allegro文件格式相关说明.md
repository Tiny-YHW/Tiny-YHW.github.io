---
title: 'Allegro文件格式相关说明'
date: Mon, 29 Mar 2021 07:04:36 +0000
draft: false
tags: ['Allegro']
---

brd：Board的简称，代表PCB设计文件  
pad：焊盘文件  
dra：Package Symbol文件的drawing档，及Package Symbol的设计文档，可生成Package Symbol

psm：Package Symbol即PCB Foorprint文件  
osm：Format Symbol，制造组装或logo图形文件  
ssm：Shape Symbol，Shape格式文件一般应用在pad设计中加载异形图形  
bsm：Mechanical Symbol，无电气特性的零件  
fsm：Flash Symbol，负片导通孔的连接方式.

art：光绘底片数据文档

rou：椭圆孔钻孔文件

tap：NC drill的文字文件，即钻孔文件  
sav：进行DBchaeck时如果产生错误有概率出现，可使用Allegro再次打开作为设计文件

scr：script 或macro记录文件  
color：View层面切换文件。可视性设置文件

jrl：Allegro事件记录文档  
log：日志记录文件  
mdd：module模块，可在Allegro建立，包含已placed，routed的数据，模块文件，可以对相同的电路进行设计布局和布线的复用

form：Allegro表单文件一般配合skill程序使用  
men：菜单文件

il、ile、ils、cxt：skill格式文件

tech：存储规则管理设置参数、层叠属性、用户属性  
xtb：Crosstalk table files (design data)

dpf：设计分区文件，协同分割板子工作时会使用

[环境变量pcbenv目录文件说明](https://a1024.synology.me:1024/?p=3496)