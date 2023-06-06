---
title: '运用dir命令提取文件路径'
date: Mon, 20 Jun 2022 02:08:42 +0000
draft: false
tags: ['Excel+VBA']
---

DIR命令详情
-------

![docdir1.png](https://a1024.synology.me:222/images/blog2023/docdir1.png)

下面来说下我们用到的dir命令  
我们需要运用dir命令去提取文件夹中指定文件的路径，  
举个例子：**dir \*.fpx/B/S > fpx.txt**  
\*表示一个字符串 。  
/B 将只显示文件名与扩展名. /S显示指定目录和所有子目录中的文件。  
那么上面那个dir命令就是提取文件夹中后缀为.fpx的文件路径，并生成一个文件名为fpx的txt

![docdir2.gif](https://a1024.synology.me:222/images/blog2023/docdir2.gif)

当你运行一个bat文件时，它会迅速关闭，如果dir命令发生问题我们也无法判断。

![docdir3.gif](https://a1024.synology.me:222/images/blog2023/docdir3.gif)

在DOS命令中有一个命令是pause，它的作用是输出提示信息"Press any key to continue...“ ，然后用户随意敲一个键后程序继续运行。  
pause  它会提示“请按任意键继续...” ，pause命令没有任何的参数，它的命令就是它的本身，当pause命令运行后，会中断执行的语句。这个中断不是立即停止，只是暂停，按下任意键之后就会继续执行下面的语句。而且应该不止可以用一次，在一个批处理命令中，可以尝试使用多个pause命令。  
如下面gif所示

![docdir4.gif](https://a1024.synology.me:222/images/blog2023/docdir4.gif)