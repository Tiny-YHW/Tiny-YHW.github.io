---
title: 'VBA消息框（MsgBox）'
date: Thu, 16 Apr 2020 09:27:17 +0000
draft: false
tags: ['Excel+VBA']
---

`MsgBox`函数显示一个消息框，并等待用户点击一个按钮，然后根据用户点击的按钮执行相关的操作。

#### 语法

```
MsgBox(prompt[,buttons][,title][,helpfile,context])
```

**参数说明**

*   _prompt_ - 必需的参数。在对话框中显示为消息的字符串。提示的最大长度大约为`1024`个字符。 如果消息扩展为多行，则可以使用每行之间的回车符(`Chr(13)`)或换行符(`Chr(10)`)来分隔行。
*   _buttons_ - 可选参数。一个数字表达式，指定要显示的按钮的类型，要使用的图标样式，默认按钮的标识以及消息框的形式。如果留空，则按钮的默认值为`0`。
*   _title_ - 可选参数。 显示在对话框的标题栏中的字符串表达式。 如果标题留空，应用程序名称将被放置在标题栏中。
*   _helpfile_ - 可选参数。一个字符串表达式，标识用于为对话框提供上下文相关帮助的帮助文件。
*   _Context_ - 可选参数。一个数字表达式，用于标识由帮助作者分配给相应帮助主题的帮助上下文编号。 如果提供上下文，则还必须提供`helpfile`。

_Buttons_ 参数可以使用以下任何值 -

*   _0 vbOKOnly_ - 仅显示_“确定”_ 按钮。
*   _1 vbOKCancel_ - 显示_“确定”_ 和_“取消”_ 按钮。
*   _2 vbAbortRetryIgnore_ - 显示_“中止”_，_“重试”_和_“忽略”_ 按钮。
*   _3 vbYesNoCancel_ - 显示_“是”_，_“否”_和_“取消”_ 按钮。
*   _4 vbYesNo_ - 显示_“是”_和_“否”_按钮。
*   _5 vbRetryCancel_ - 显示_“重试”_和_“取消”_按钮。
*   _16 vbCritical_ - 显示严重消息图标。
*   _32 vbQuestion_ - 显示警告查询图标。
*   _48 vbExclamation_ - 显示警告消息图标。
*   _64 vbInformation_ - 显示信息消息图标。
*   _0 vbDefaultButton1_ - 第一个按钮是默认的。
*   _256 vbDefaultButton2_ - 第二个按钮是默认的。
*   _512 vbDefaultButton3_ - 第三个按钮是默认的。
*   _768 vbDefaultButton4_ - 第四个按钮是默认的。
*   _0 vbApplicationModal_ 应用程序模式 - 当前的应用程序将不会工作，直到用户响应消息框。
*   _4096 vbSystemModal_ 系统模式 - 所有的应用程序将不会工作，直到用户响应消息框。

上述值在逻辑上分为四组：第一组(`0`至`5`)指示要在消息框中显示的按钮。第二组(`16`,`32`,`48`,`64`)描述要显示的图标的样式，第三组(`0`,`256`,`512`,`768`)指示哪个按钮必须是默认的，第四组(`0`,`4096` )确定消息框的形式。

#### 返回值

`MsgBox`函数可以返回以下值之一，可用于标识用户在消息框中单击的按钮。

*   _vbOK_ - _确定_ 按钮被点击。
*   _vbCancel_ - _取消_ 按钮被点击。
*   _vbAbort_ - _中止_ 按钮被点击。
*   _vbIgnore_ - _忽略_ 按钮被点击。
*   _vbYes_ - _是_ 按钮被点击。
*   _vbNo_ - _否_ 按钮被点击。

#### 示例

```
Function MessageBoxDemo() 
   'Message Box with just prompt message '
   MsgBox("欢迎您~")     

   'Message Box with title, yes no and cancel Butttons  '
   result = MsgBox("你喜欢蓝色吗?", 3, "选择一个选项") 

   ' Assume that you press No Button  '
   MsgBox ("返回 result 的值是：" &result) 
End Function
```