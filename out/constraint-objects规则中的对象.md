---
title: 'Constraint Objects规则中的对象'
date: Mon, 27 Apr 2020 09:34:31 +0000
draft: false
tags: ['Allegro', '设计软件']
---

对象和优先级
------

Allegro中规则管理器的对象和优先级关系如下图（越靠下优先级越高）

![](http://a1024.synology.me:222/images/blog2022/Constraint%20Objects1.png)

Net Class
---------

使用Net Class将具有共同特征并需要类似约束要求的净对象进行分组。

Net Class中可以包含buses, net groups, differential pairs, Xnets, and nets.

Net Class Rules
---------------

以下规则适用于创建Net Class

*   You can constrain a Net Class with a CSet
*   You can override individual members of a Net Class
*   You can constrain a Net Class directly (though we recommend using a CSet)
*   As you create a Net Class in the Physical domain, you can specify that it also occurs in the in the Spacing domain. The converse is true.
*   A Net Class in the Electrical domain must be unique to that domain
*   A Net Class created in the Spacing domain carries over to the Same Net Spacing domain; the converse is also true
*   A net can be a member of only one Net Class per domain

*   你可以用CSet来约束一个Net Class
*   你可以覆盖一个Net Class中的单个成员
*   你可以直接约束一个Net Class（不过我们建议使用CSet）
*   当你在Physical域中创建一个Net类时，也出现在Spacing域中，你可以指定它。反之亦然
*   Electrical域中的Net Class必须是该域中唯一的。
*   在Spacing域中创建的Net Class也出现在Same Net Spacing域；反之亦然A
*   一个net只能包含在一个Net Class中，不能被2到多个Net Class共用

Match Groups
------------

以下规则适用于创建Match Groups

Match Group是nets、Xnets或pin pairs的集合，这些nets、Xnets或pin pairs必须全部匹配（在延迟或长度上）或相对于组内的target特定目标。

您可以通过直接向Xnets添加属性手动创建匹配组，或者使用约束管理器在电气CSet中定义pin pairs。无论选择哪种方法，匹配组都会解析到特定的pin pairs，并通过以下属性进一步定义Scope, Delta, Tolerance and Target.。

如果Match Groups中包含Xnet可以通过pin pairs的生成方式（All Drivers/All Receivers、Longest Driver/Receiver、Longest Pin Pair）分配或手动创建pin pairs（如果无法从可用的设置中获得您想要的Pin Pair，应该从Match Groups删除Xnet，手动创建您想要的Pin Pair，然后将这些Pin Pair添加到Match Groups中）

Match Group Rules
-----------------

*   You must specify a Match Group in only the Relative Propagation Delay worksheet of the Routing workbook.
*   You can set Match Group constraints for the entire group and override individual members of the group as desired, offering differing levels of delta and tolerance.
*   You specify Match Group delays at the design- or the system-level.
*   You can include a Match Group member in multiple Match Groups.
*   A match delay constraint from a pre-14.0 board database is upreved with a delta value of zero. This implies that all group members will match a specified target pin pair.
*   Note: Constraint Manager, when launched from Allegro® PCB Series L, supports Match Groups only on net-related objects, not on Electrical CSets.
*   If you are specifying a Bus- or Class-scope, you must create the Match Group in a CSet in the Electrical CSet folder.

*   必须仅在Relative Propagation Delay表中指定一个Match Group。
*   您可以为整个组设置Match Group约束，并可根据需要对组中的单个对象，提供不同的延迟和公差
*   可以在设计或系统级指定Match Group delays。
*   一个Net或Xnet可以被包含在多个Match Groups中
*   14.0之前的brd数据库的匹配延迟约束，delta值为0。这意味着Match Groups所有对象将匹配指定的target pin pair.
*   当从 Allegro® PCB 系列 L 启动时约束管理器仅支持与net相关对象的匹配组，而不支持Electrical CSets
*   如果要对Bus or Class指定等长规则，必须在电气 CSet 文件夹中的 CSet 中创建Match Group

Buses
-----

从16.6版本开始，Constraint Manager中不支持创建新的用户定义的Bus。要创建一个Net对象的集合，建议使用Net Groups。

Bus表示一个由differential-pairs, Xnets, or Nets.组成的命名集合。

你可以使用一个Bus来分组功能相似的differential-pairs, Xnets, or Nets。Bus上约束会被Bus的所有成员继承。

你可以根据Bus的特性创建一个电气CSet。然后你可以使用SigXplorer来定义总线成员的引脚连接顺序，增强约束信息。

Bus Rules
---------

*   You can create a bus in all net worksheets
*   When used in conjunction with Allegro® Design Entry HDL, Constraint Manager cannot create a bus. A bus is only realized with the appropriate property in the schematic
*   A bus must be at the design-level (not the system-level).

*   你可以在所有的Nets工作表中创建一个Bus
*   与 Allegro® Design Entry HDL 配合使用时，约束管理器不能创建Bus。Bus只有在原理图中使用适当的属性才能实现
*   Bus必须在设计级（而不是系统级）

Net Groups
----------

从16.6版本开始，Allegro设计工具中引入了一个新的Net对象，称为Net Group。

Net Group是一个由各种net (signal) 对象组成的集合。不同类型的net对象，如nets, buses, differential pairs, and XNets等，都可以成为Net Group的成员。定义在Net Groups上的约束条件适用于所有成员对象。

注意：引入了网组后，用户定义的Net Groups集合现在被创建为Net Groups而不是Bus。

Net Groups Rules
----------------

*   一个网对象只能是一个网组的成员。
*   网组是特定于设计的。

Nets and Xnets
--------------

Pin Pairs
---------

Ratsnest Bundle
---------------

Region
------

Region Class
------------