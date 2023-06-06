---
title: 'Allegro DRC 错误代码 Dictionary of DRC Error Marker Codes'
date: Fri, 28 Aug 2020 08:53:57 +0000
draft: false
tags: ['Allegro']
---

DRC错误标记由带有两个字母的“领结”符号组成。字母代码指示违反了哪种约束类型。

_Net-to-Net Spacing_ DRC错误标记代码为大写；相反，_Same Net Spacing_代码是小写的。

DRC错误标记代码定义
-----------

下表列出了每种DRC错误标记代码组合及其关联的约束违例。该列表根据DRC错误标记中的字母按字母顺序排列。

**Code**

**Constraint Violation**

A – A

Acute angle to cavity edge

B – B

Bond Pad to Bond Pad

B – L

Bond Pad to Line

B – S

Bond Pad to Shape

C – C

Component to cavity edge  
Package to package  
Soldermask to soldermask

D – C

DFA Package to package

D – D

Mechanical Drill Hole to Mechanical Drill Hole  
Mechanical Drill Hole to Drill Hole  
Drill Hole to Drill Hole

D – I

Negative plane islands

D – L

Mechanical Drill Hole to Cline  
Drill Hole to Cline

D – P

Phase Tolerance - Tolerance  
Mechanical Drill Hole to Pin  
Drill Hole to Pin

D – S

Mechanical Drill Hole to Shape  
Drill Hole to Shape

D – V

Mechanical Drill Hole to Via  
Drill Hole to Via

E – D

Max Final Settle Max  
Min First Switch Min  
Noise Margin Min  
Overshoot Max  
Propagation Delay Max  
Propagation Delay Min  
Propagation Delay Path Type  
Relative Propagation Delay Delta  
Relative Propagation Delay Path Type  
Relative Propagation Delay Scope

E – L

Layer Sets  
Max Exposed Length  
Total Etch Length Max  
Total Etch Length Min

E – P

Parallelism

E – S

Max Stub Length

E – T

Verify Schedule

E – V

Max Via Count

E – X

Active Window  
Max Xtalk  
Max Peak Xtalk  
Sensitive Window  
Maximum Inter Crosstalk  
Maximum Intra Crosstalk

F – C

Bond finger to component  
Bond Pad to Component Edge  
Bond Finger to cavity edge

F – F

Bond Pad to Bond Pad (same net)  
Bond Pad to Bond Pad (different net)

I – M

Single-line Impedance Target and Tolerance

J – N

Allow - Ts

K – B

Bond Pad to Route Keepin  
Bond Pad to Route Keepout  
Bond Pad to Via Keepout

K – C

Package to place keepin  
Package to place keepout

K – L

Line to Route Keepin  
Line to Route Keepout

K – P

Thru Pin to Route Keepin  
Thru Pin to Route Keepout  
SMD to Route Keepin  
SMD to Route Keepout  
Test Pin to Route Keepin  
Test Pin to Route Keepout  
Test Pin to No Probe

K – S

Shape to Route Keepin  
Shape to Route Keepout

K – V

Via to Route Keepin  
Via to Route Keepout  
Via to Via Keepout  
BB Via to Route Keepin  
BB Via to Route Keepout  
BB Via to Via Keepout  
Test Via to Route Keepin  
Test Via to Route Keepout  
Test Via to Via Keepout  
Test Via to No Probe

L – L

Line to Line

L – S

Shape to Line

L – W

Line Width - Max  
Line Width - Min  
Neck - Max Length  
Neck - Min Width

M – A

Soldermask alignment  
Pad Soldermask Alignment  
Symbol Soldermask Alignment

M – C

Symbol Soldermask to Pad Soldermask  
Minimum Cavity Size

M – L

Soldermask to pad and cline

M – M

Pad Soldermask to Pad Soldermask  
Any Metal to Any Metal Spacing

M – P

Soldermask to Pin

M – S

Soldermask to shape

M – V

Soldermask to Via  
Matched Via count violation

N – S

Negative Plane to Sliver

O – C

Object exposure to cavity

P – B

Bond Pad to SMD Pin  
Bond Pad to Test Pin  
Bond Pad to Thru Pin

P – D

Mechanical Pin Antipad to Drill Hole

P – L

Line to SMD Pin  
Line to Test Pin  
Line to Thru Pin  
Mechanical Pin Antipad to Cline

P – M

Pastemask pad to pastemask pad  
Pastemask to package pastemask

P – P

SMD Pin to SMD Pin  
SMD Pin to Test Pin  
Test Pin to Test Pin  
Thru Pin to SMD Pin  
Thru Pin to Test Pin  
Thru Pin to Thru Pin  
Mechanical Pin Antipad to Pin

P – S

Shape to SMD Pin  
Shape to Test Pin  
Shape to Thru Pin  
Mechanical Pin Antipad to Shape

P – V

SMD Pin to BB Via  
SMD Pin to Test Via  
SMD Pin to Thru Via  
Test Pin to BB Via  
Test Pin to Test Via  
Test Pin to Thru Via  
Thru Pin to BB Via  
Thru Pin to Test Via  
Thru Pin to Thru Via  
Mechanical Pin Antipad to Via

R – C

Package to room

S – N

Allow - Etch

S – S

Shape to Shape

T – C

Testpoint loc. to component  
Testpoint pad to component  
Testpoint under component

V – B

Bond Pad to BB Via  
Bond Pad to Test Via  
Bond Pad to Thru Via

V – G

Allow - Pad-Pad Connect  
BB Via Stagger - Max  
BB Via Stagger - Min  
Min BB Via Gap

V – L

Line to BB Via  
Line to Test Via  
Line to Thru Via

V – N

Vias  
Vialist constraint violation

V – S

Shape to BB Via  
Shape to Test Via  
Shape to Thru Via

V – V

BB Via to BB Via  
BB Via to Test Via  
Test Via to Test Via  
Thru Via to BB Via  
Thru Via to Test Via  
Thru Via to Thru Via

W – A

Min. bonding wire length  
Wire to die edge angle

W – D

Bonding wire diameter

W – C

Wire to Cavity Edge Spacing  
Wire End to Cavity Edge Spacing

W – E

Wire end to wire end

W – F

Wire to bond finger

W – I

Max. bonding wire length

W – P

Wire to pin

W – W

Wire to wire (same profile)

W – X

Wire to wire (different profile)

X – D

Externally Determined Violation