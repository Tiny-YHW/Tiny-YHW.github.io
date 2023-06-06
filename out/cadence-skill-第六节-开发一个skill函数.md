---
title: 'Cadence Skill 第六节 开发一个SKILL函数'
date: Thu, 09 Apr 2020 01:21:16 +0000
draft: false
tags: ['Allegro', 'Allegro Skill']
---

摘录自[电子布局网](http://www.eelayout.com/)

Developing a SKILL function includes the following tasks. 开发一个SKILL函数包含以下任务： 

*   Grouping several SKILL statements into a single SKILL statement 将几个SKILL语句组合进一个单一的SKILL语句。
*   Declaring a SKILL function with the _procedure_ function 用 _procedure _声明一个函数
*   Defining function parameters 定义函数参数
*   Maintaining your source code 维护您的源代码
*   Loading your SKILL source code  加载您的SKILL源代码
*   Redefining a SKILL function  重定义一个SKILL函数

群组SKILL语句
---------

Sometimes it is convenient to group several SKILL statements into a single SKILL statement. Use braces { and } to group a collection of SKILL statements into a single SKILL statement. The return value of the single statement is the return value of the last SKILL statement in the group. You can assign this return value to a variable.

有时将几个语句群组进一个语句是很方便的。使用大括号{}实现群组一个SKILL语句集。单一语句的返回值为群组中最后的SKILL语句的返回值。您可以将返回值赋值给一个变量。

This example computes the pixel height of _bBox_ and assigns it to the _bBoxHeight_ variable:

这个例子计算_bBox_像素高度，且将其赋值给变量_bBoxHeight_

```
bBoxHeight = {bBox = list( 100:150 250:400)
ll = car( bBox )
ur = cadr( bBox )
lly = yCoord( ll )
ury = yCoord( ur )
ury - lly }
```

*   The _ll_ and _ur_ variables hold the lower-left and upper-right coordinates of the bounding box. _ll_ 和 _ur_ 变量抓取边界框左下角和右上角坐标
*   The _xCoord_ and _yCoord_ functions return the _x_ and _y_ coordinate of a point._xCoord_ 和 _yCoord_ 函数返回一个点的x和y坐标
*   The _ury - lly _expression computes the height. This last statement in the group determines the return value of the group._ury - lly _计算高度，最后的语句确定群组的返回结果。
*   The return value is assigned to the _bBoxHeight_ variable. 返回值赋值给变量_bBoxHeight_

You can declare the variables _ll, ur, ury_, and _lly_ to be local variables. Use the _prog_ or _let_ functions to define a collection of local variables for a group of several statements. However, defining local variables is not recommended for novices.

您可以将_ll, ur, ury_, 和 _lly_声明为局部变量。使用prog 或 let 给群组的几个语句定义一个局部变量集。不过不建议初学者定义局部变量。

声明SKILL函数
---------

To refer to the group of statements by name, use the _procedure_ declaration to associate a name with the group. The group of statements and the name make up a SKILL function. 

群组语句通过名字引用，使用procedure函数声明与一个群组关联到一个名字，将群组语句和名字组成一个SKILL函数

*   The name is known as the function name. 群组的名字被作为函数命名。
*   The group of statements is the function body. 群组语句是函数体
*   To execute the group of statements, mention the function name followed immediately by ( ). 执行群组相当于函数名后紧跟着括号()

The _ComputeBBoxHeight_ function example below computes the pixel height of _bBox_.

下面例子的 _ComputeBBoxHeight _函数计算 _bBox _的像素高度

```
procedure( ComputeBBoxHeight( )
bBox = list( 100:150 250:400)
ll= car( bBox )
ur= cadr( bBox )
lly= yCoord( ll )
ury= yCoord( ur )
ury - lly ) ; procedure
bBoxHeight = ComputeBBoxHeight()
```

定义函数参数
------

To make your function more versatile, you can identify certain variables in the function body as formal parameters.

When you invoke your function, you supply a parameter value for each formal parameter.

In the following example, the _bBox_ is the parameter.

为了使您的函数更加灵活，您可以在函数体内确定某些变量作为形式参数（形参）。  
当您调用函数时，您需要提供的参数值给每个形参。  
在下面的例子中，BBOX 就是参数。

```
procedure( ComputeBBoxHeight( bBox )
ll = car( bBox )
ur = cadr( bBox )
lly = yCoord( ll )
ury = yCoord( ur )
ury - lly) ; procedure
```

To execute your function, you must provide a value for the parameter.

要执行函数，您必须提供一个参数值。

```
bBox = list( 100:150 250:400)
bBoxHeight = ComputeBBoxHeight( bBox )
```

为您的函数选择前缀
---------

With only a few exceptions, the SKILL functions in this manual do not use a prefix identifier. Many examples in this manual use a "tr" prefix to indicate they are created for training purposes. If you look in other SKILL manuals, you will notice that functions for tools are usually grouped with identifiable, unique prefixes.

For example, functions used for technology file administration are all prefixed with "tc". These prefixes vary across Cadence tools, but all use lowercase letters. It is recommended that you establish a unique prefix using uppercase letters for your own functions. 

只有少数例外情况外，本手册中的SKILL函数不使用前缀标识。本手册中的许多例子都使用了“TR”前缀，以表明他们是以训练为目的而创建的。如果你在其他SKILL手册中，你会发现对于工具的功能通常以能识别的独特的前缀来群组。

 例如，用于技术文件管理功能都带有前缀“TC”。这些前缀跨Cadence工具各不相同，但都使用小写字母。建议您使用大写字母为自己的函数建立唯一的前缀。

保持SKILL源代码Maintaining SKILL Source Code
---------------------------------------

The Cadence environment makes it easy to invoke an editor of your choice. Set the SKILL variable _editor_ to a UNIX command line able to launch your editor.

Cadence的环境可以很容易地调用你选择的编辑器。在UNIX命令行设置SKILL变量_editor_可以启动您的编辑器。

```
editor = "xterm -e vi"
```

The _ed_ function invokes an editor of your choice. If you optionally use the _edl_ function, the system loads your file when you quit the editor.

ed 函数调用您选择的一个编辑器。如果您选择使用 edl 函数，当您退出编辑器，系统加载你的文件。

ed( "myFile.il")

alternatively, you can use an editor independent of the Cadence environment.    

作为选择，您可以使用独立了Cadence环境的编辑器。

加载SKILL源代码
----------

The _load_ function  load 函数

*   Evaluates each expression in a source code file  评估源代码文件中的每个表达式
*   Is typically used to define a collection of functions  通常用于定义函数的集合
*   Returns _t_ if all expressions evaluate without errors  如果语句执行没有错误，则返回 t
*   Aborts if there are any errors, any expression following the offending expression is not evaluated 如果执行过程中存在任何错误，将放弃执行错误发生点后面的表达式。

相对路径
----

When you pass a relative path to the _load_ function, the system resolves it in terms of a list of directories called the SKILL path. You usually establish the SKILL path in your initialization file by using the _setSkillPath_ or _getSkillPath_ functions.

当您使用相对路径加载函数，系统根据被调用的SKILL路径目录的list来解决。您通常在您的声明文件中使用 _setSkillPath_ 或 _getSkillPath_ 函数来建立SKILL路径。

*   The _setSkillPath_ function sets the path to a list of directories. _setSkillPath_ 函数设定路径到一个目录的list
*   The _getSkillPath_ function returns a list of directories in search order. _getSkillPath_ 函数设定路径到一个目录的list

输入一个函数
------

    Sometimes you need to define a function without saving the source code file. Using the mouse in your editor, select and paste the function into the command input line.

    有时您需要不保存源代码文件的情况下定义一个文件。在编辑器中使用鼠标在命令输入行中选择和粘贴函数。

设定SKILL路径
---------

Use the _setSkillPath_ function in conjunction with the _prependInstallPath_ and _getSkillPath_ functions to set the SKILL path.

使用_setSkillPath _结合_ prependInstallPath _和_ getSkillPath _函数来设定_SKILL _路径

```
trSamplesPath = list(prependInstallPath( "etc/context" )
prependInstallPath( "local" ) 
prependInstallPath( "samples/local" )
)
```

Use the _prependInstallPath_ function to make a path relative to the installation directory. The function prepends `_your_install_dir_``/tools/dfII` to the path. Assuming your installation path is `/cds/9401 trSamplesPath` is now:

使用 _prependInstallPath _函数建立一个相对于安装目录的路径。函数预先将`_your_install_dir_``/tools/dfII赋给路径。假设您的安装路径是 /cds/9401 ，现在 trSamplesPath 为：`

```
(
"/cds/9401/tools.sun4/dfII/etc/context"
"/cds/9401/tools.sun4/dfII/local"
"/cds/9401/tools.sun4/dfII/samples/local"
)
```

假如 windows下为安装路径为 D:\\\\Cadence\\\\SPB\_16.6，则见下面代码：

```
**prependInstallPath**( "etc/context" )  
\=>"D:\\\\Cadence\\\\SPB\_16.6\\\\tools\\\\dfII\\\\etc\\\\context"
```

注：SKILL \\\\ 和 /  才是正确的路径符号。

Assuming your SKILL path is ("." "~"), you can set a new SKILL path using _setSkillPath_.

假设您的SKILL路径是("." "~"),您可以使用 _setSkillPath _设定SKILL路径

```
setSkillPath( append( trSamplesPath getSkillPath() ) )
```

The return value of _setSkillPath_ indicates a path that could not be located, not the actual SKILL path.

setSkillPath的返回值显示一个中不到的路径，而不是实际的SKILL路径。

```
("/cds/9401/tools.sun4/dfII/samples/local")
```

The actual SKILL path is 实际的SKILL路径是（list形式）

```
("/cds/9401/tools.sun4/dfII/etc/context"  "/cds/9401/tools.sun4/dfII/local"  "/cds/9401/tools.sun4/dfII/samples/local" "." "~")
```

重定义一个SKILL函数
------------

Users should be safeguarded against inadvertently redefining functions. Yet, while developing SKILL code, you often need to redefine functions.

The SKILL interpreter has an internal switch called _writeProtect_ to prevent the virtual memory definition of a function from being altered during a session.

By default _writeProtect_ is set to _nil_. SKILL functions defined while _writeProtect_ is _t_ cannot be redefined during the same session. Typically, you set the _writeProtect_ switch in your initialization file.

用户应该防止无意地重定义函数。然而为了开发SKILL代码，您经常需要重定义函数。SKILL解释器有一个叫writeProtect内部开关，以防止从一个会话期间改变函数的虚拟内存定义。

默认情况下_writeProtect _被设置为 nil 。当_writeProtect_ 为t ，已定义的SKILl函数在同一个会话期间不能被重新定义。通常的，您可以将_writeProtect _开关设在您的声明文件中。

```
sstatus( writeProtect t ) ;sets it to t
sstatus( writeProtect nil ) ;sets it to nil
```

This example tries to redefine _trReciprocal_ to prevent division by 0.

```
sstatus( writeProtect t ) => t
procedure( trReciprocal( x ) 1.0 / x ) => trReciprocal
procedure( trReciprocal( x )
when( x != 0.0 1.0 / x )
)
*Error* def: function name is write protected and cannot be redefined - trReciprocal
```