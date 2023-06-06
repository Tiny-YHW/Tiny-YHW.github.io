---
title: 'Allegro Symphony Team Design模式下使用Skill'
date: Wed, 22 Jun 2022 00:54:32 +0000
draft: false
tags: ['Allegro Skill']
---

在Allegro Symphony协同时，默认是所有skill命令都不被支持的。因为Symphony协同模式本身就有很多全局或网表命令都是不被支持的，而Skill命令是可以操作板中所有对象的，所以Skill不能被使用也是理所应当的

但有时候部分特别常用的Skill功能如果在协同模式下不能被正常使用，会大大影响设计效率

为此设计软件允许用户在Symphony协同时使用部分Skill功能

使用限制
----

*   所有只读类型的skill命令（后文统称为只读Skill）只要被允许后都是可以被正常使用的（如切换显示层，切换格点）
*   所有对数据库内容进行改动（后文统称读写Skill）的操作（对板中的任何实体对象（cline、shape、line、via等）则按照以下模式进行。（rw标志在后文描述）
    *   不带rw标志的命令：只接受只读操作，所有对数据库进行改动的操作均不被接受
    *   带rw标志：接受数据库改动，允许用户使用Skill命令修改数据库（慎用，后文详述）

Tips：部分读写Skill实测使用后，从当时的板子看是成功了，但这些内容不能同步更新到最新的数据库，设计重新打开后操作的内容都不会被保存上，注意查看设计如果这个功能被使用后经过done命令后，其它一起协同的数据都被同时更新上才算成功。

Symphony Skill使用方法.
-------------------

将需要使用的skill命令写入symphony\_skill.txt即可

### symphony\_skill.txt

第一次使用 Symphony协同服务时，会在环境变量pcbenv下生成symphony\_skill.txt文档

symphony\_skill.txt和env文件类似，一经生成，可以一直使用不会被强制更新

Tips：同时还有安装目录两个位置（\\share\\pcb\\text\\和\\share\\local\\pcb\\）同时生成symphony\_skill.txt

![](https://a1024.synology.me:222/images/blog2022/getting_started-63.gif)

### 录入Skill命令

把你需要使用的命令添加到symphony\_skill.txt中即可

*   每行作为一个命令输入，同一行不能有多个命令
*   如果命令包含空格，则一定要使用双引号把整个命令括起来，为了保险起见你也可以全加双引号
*   每一行分号后面的文本均为注释内容，不会被编译
*   空行自动被忽略
*   新修改的命令需要重启Allegro后生效
*   只读Skill命令输入命令名称即可，eg：“command”、“21”、“colora”
*   读写Skill命令需要在命令后增加rw标志，eg：“command” rw、“cvn” rw

关于rw下面是原文翻译，总的来说就是读写skill加上rw标志后有可能不能100%被接受，若要使用rw请先自行验证这些功能是可以被成功接受的

*   没有“rw”标志的命令被认为是只读的，并且该命令所做的数据库更改不会发送到 Symphony 服务器。
*   只允许带有 'rw' 标志的命令发送数据库更新。 只有经过验证可在 Symphony 环境中工作的命令才应具有“rw”关键字。