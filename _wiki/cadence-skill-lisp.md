---
layout: wiki
title: Lisp语法
cate1: Cadence Skill
cate2: 
keywords: 
---

##

*  [1 List Functions List函数](https://tiny-yhw.github.io//allegro-skill-lisp-list-functions){:target="_blank"}
*  [2 Data Structure](https://tiny-yhw.github.io//allegro-skill-lisp-data-structure){:target="_blank"}
*  [3 Data Operator Functions](https://tiny-yhw.github.io//allegro-skill-lisp-data-operator-functions){:target="_blank"}
*  [4 Type Conversion Functions](https://tiny-yhw.github.io//allegro-skill-lisp-type-conversion-functions){:target="_blank"}
*  [5 String Functions 字符串函数](https://tiny-yhw.github.io//allegro-skill-lisp-string-functions){:target="_blank"}
*  [6 Arithmetic （Trigonometric） Functions 算术（三角）函数](https://tiny-yhw.github.io//allegro-skill-lisp-arithmetic-functions){:target="_blank"}
*  [7 Bitwise Operator Functions](https://tiny-yhw.github.io//allegro-skill-lisp-bitwise-operator-functions){:target="_blank"}
*  [9 Logical and Relational Functions](https://tiny-yhw.github.io//allegro-skill-logical-and-relational-functions){:target="_blank"}
*  [10 Flow Control Functions](https://tiny-yhw.github.io//allegro-skill-lisp-flow-control-functions){:target="_blank"}
*  [11 Input Output Functions](https://tiny-yhw.github.io//allegro-skill-lisp-input-output-functions){:target="_blank"}
*  [12 Core Functions](https://tiny-yhw.github.io//allegro-skill-lisp-core-functions){:target="_blank"}
*  [13 Function and Program Structure](https://tiny-yhw.github.io//allegro-skill-lisp-functions-and-Program-Structure){:target="_blank"}
*  [14 Environment Functions](https://tiny-yhw.github.io//allegro-skill-lisp-environment-functions){:target="_blank"}
*  [15 Namespace Functions And More](https://tiny-yhw.github.io//allegro-skill-lisp-namespace-functions-and-more){:target="_blank"}

Cadence® SKILL 是一种基于流行的人工智能语言 Lisp 的高级交互式编程语言。





二、检验与逻辑运算功能函数

2.1（= 表达式1 表达式2）比较表达式1是否等于式2，适用数值及字符串

2.2 （／= 表达式1 表达式2）比较表达式1是否大于等于表达式2 2.3（＜ 表达式1 表达式2）比较表达式1是否＜小于表达式2

2.4（＜= 表达式1 表达式2）比较表达式1是否＜一小于等于表达式2

2.5（＞ 表达式1 表达式2）比较表达式1是否＞大于表达式2

2.6（＞= 表达式1 表达式2） 比较表达式1是否大于等于表达式2

2.7 （～ 数值）返回：数值的位 not值，（1的补码）

2.8 （and 表达式1 表达式2…）返回：逻辑and的结果

2.9（boole 函数 整数 整数…）返回：位式布尔运算

2.10（eq 表达式1 表达式2）比较表达式1与表达式2是否相同，适用列表比较（实际相同）

2.11（equal 表达式 1表达式 2［差量］）比较表达式 1与表达式 2是否相同，差量可省略（内容相同）

三、转换运算功能函数

3.1（angtof 字符串［模式］）返回：角度值的字符串转成实数

3.2（angtos 角度［模式［精度］］）返回：角度转成的字符串值

3.5 （cvunit 数值 原始单位 转换单位）返回：数值转换单位后的值转换根据acad.nut文件

3.6（distof 字符串 ［模式］）返回：根据模式将字符串转成实数值

3.7（itoa 整数）返回：整数转成字符串

3.8（rtos 数值 模式［精度］）返回：实数转成字符串

3.9 （trans 点 原位置 新位置［位移］） 返回：转换坐标系统值


五、字符串、字符、文件处理函数

5.1（ascii 字符串）返回：字符串第一个字符的“ASCII”码

5.2 （chr 整数）返回：整数所对应的ASCII单一字符串

5.3（close 文件 名称）关闭文件

5.4（open 文件名 模式）返回：打开文件代码，准备读取或写入信息

5.5（read 字符串）返回：列表中的字符串的第一组元素

5.6（read－char［文件代码］）返回：通过键盘或文件中读取单一字符

5.7（read－line ［文件代码］）返回：经由键盘或文件中读取一行字符串

5.8（strcase 字符串［字样］）返回：转换字符串大小写

5.9（strcat 字符串1字符串2…）返回：将各字符串合并为一个字符串

5.10（strlen 字符串）返回：字符串构成的字符数（即字符串长度）

5.11（substr 字符串 起始 长度）返回：取出于字符串‘

5.12（wcmatch 字符串 格式）返回：T或 nil，将字符串与通用字符进行比较

5.13（write－char数值［文件代码］）返回：将一ASCII字符写到文件或屏幕

5.14（write－line字符串［文件代码］）返回：将字符串写到文件或屏幕上