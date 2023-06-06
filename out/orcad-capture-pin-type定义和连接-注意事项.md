---
title: 'OrCAD Capture Pin Type定义和连接 注意事项'
date: Sat, 06 Mar 2021 02:13:25 +0000
draft: false
tags: ['设计资料/文档']
---

3-state
-------

A 3-state pin has three possible states: low, high, and high impedance.  
In its high impedance state, a 3-state pin looks like an open circuit. For  
example, the 74LS373 latch has 3-state pins.

Bidirectional
-------------

A bidirectional pin acts as both input and output. For example, pin 2  
on the 74LS245 bus transceiver is a bidirectional pin. The value at pin 1  
(an input) determines the activity of pin 2, as well as others.

Input
-----

An input pin is one to which you apply a signal. For example, pins 1  
and 2 on the 74LS00 NAND gate are input pins.

Open collector
--------------

An open collector gate omits the collector pull-up. Use an open  
collector to make “wired-OR” connections between the collectors of  
several gates and to connect with a single pull-up resistor. For  
example, pin 1 on the 74LS01 NAND gate is an open collector gate.

Open emitter
------------

An open emitter gate omits the emitter pull-down. The proper  
resistance is added externally. ECL logic uses an open emitter gate and  
is analogous to an open collector gate. For example, the MC10100 has  
an open emitter gate.

Output
------

An output pin is one to which the part applies a signal. For example,  
pin 3 on the 74LS00 NAND gate is an output pin.

Passive
-------

A passive pin is typically connected to a passive device. A passive  
device does not have a source of energy. For example, a resistor lead is  
a passive pin.

*   Passive属性Pin Name不能相同，否则导网表会报错

Power
-----

A power pin expects either supply voltage or ground. For example, on  
the 74LS00 NAND gate, pin 14 is VCC and pin 7 is GND.

*   Power属性Pin Name可以相同
*   Power属性需要连接Net，不能悬空
*   如果Power属性Pin悬空，网表将按Pin Name名称分配网络名

### Caution

Power pins set to visible in the library will not be global in nature  
when the part is placed in a design. You will have to connect these  
pins to a net. If you want a power pin to be visible on the schematic  
page and global in nature, set it to invisible in the library. After  
placing the pin, double-click on the part, and set power pins to be  
visible.

### Note

Power pins that are invisible are not connected using wires and  
buses, but instead are connected globally via name.