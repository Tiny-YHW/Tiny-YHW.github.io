---
layout: post
title: Markdown基本撰写和格式语法
categories: [Markdown]
description: 记录一些测试结果description。
keywords: Markdown
mermaid: false
sequence: false
flow: false
mathjax: false
mindmap: false
mindmap2: false
---

**目录**

* TOC
{:toc}


[官方文档](https://docs.github.com/zh/get-started/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax){:target="_blank"}


段落之间尽量空一个空行

> Markdown 是一种轻量级标记语言，创始人为 John Gruber。它允许人们「使用易读易写的纯文本格式编写文档，然后转换成有效的 XHTML（或者 HTML）文档」。——维基百科

## 优点

1. 专注于文字内容；

2. 纯文本，易读易写，可以方便地纳入版本控制；

3. 语法简单，没有什么学习成本，能轻松在码字的同时做出美观大方的排版。

## 语法
要忽略 Markdown 格式字符，请在字符前添加 \：
This is not \*italicized\* type.

### 表达键盘按键时使用

```
<kbd>Tab</kbd> 
<kbd>Alt+X</kbd>
```

**预览效果：**

<kbd>Tab</kbd> 

<kbd>Alt+X</kbd>


## 标题

要创建标题，请在标题文本前添加一至六个 # 符号。 你使用的 # 数量将决定层次结构级别和标题的大小。

注：标准语法一般在#后跟个空格再写文字，

```
# 一级标题 #
一级标题
====
## 二级标题 ##
二级标题
----
### 三级标题 ###
#### 四级标题 ####
##### 五级标题 #####
###### 六级标题 ######
```


使用两个或多个标题时，GitHub 会自动生成一个目录，可以通过单击文件标题中的右侧控件来访问该目录。 每个标题都列在目录中，可以单击某个标题导航到所选部分。

## 段落

中间没有空行的连续不断的几行文字被视为一个段落。

一个enter字符不代表换行，一行最后留两个空格代表换行

**Markdown：**

```
白日依山尽，

黄河入海流。
（句号后面没空格）

欲穷千里目，

更上一层楼。  
（句号后面有俩空格）
```

**预览效果：**

白日依山尽，

黄河入海流。
（句号后面没空格）

欲穷千里目，

更上一层楼。  
（句号后面有俩空格）

## 文本样式

### **粗体**

```
**粗体**
__粗体__
```

### *斜体*

```
*斜体*
_斜体_
```

### ***斜体加粗***

```
***斜体加粗***
```

### ~~删除线~~

```
~~这是加删除线的文字~~
```

### ++下划线++

```
++下划线++
```


## 引用文本
在引用的文字前加>即可。引用也可以嵌套，如加两个>>三个>>>
n个...

**Markdown：**

```
> 引用块段落一。
>
> 引用块段落二。
>> 内嵌引用块段落一。
>
> ### 引用块内的标题
```

**预览效果：**

> 引用块段落一。
>
> 引用块段落二。
>
> > 内嵌引用块段落一。
>
> ### 引用块内的标题


## 引用代码

支持行内代码和代码块。

单行代码：代码之间分别用一个反引号包起来 

`代码内容`

代码块：代码之间分别用三个反引号包起来，且两边的反引号单独占一行
```java
public void error(String format, Object... arguments);
```

上例中的语言标记 `java` 可选填，可用于在编辑器和渲染后的效果里添加语法高亮。

块式代码也可以对整个代码段缩进四个空格，或一个 Tab 来实现。

## 超链接

### **本标签页**

```
[百度](http://baidu.com "title")
```

title可加可不加

[百度](http://baidu.com)

### **新标签页**

```
[百度](http://baidu.com "title"){:target="_blank"}
```


Markdown 支持行内式链接和引用式链接。

**Markdown：**

```
行内式 [博客](https://mazhuang.org "我的个人博客") 链接，带 title。

行内式 [GitHub](https://github.com/mzlogin) 链接。

引用式 [博客][1] 链接。

引用式 [GitHub][2] 链接，带 title。
```

**预览效果：**

行内式 [博客](https://mazhuang.org "我的个人博客") 链接，带 title。

行内式 [GitHub](https://github.com/mzlogin) 链接。

引用式 [博客][1] 链接。

引用式 [GitHub][2] 链接，带 title。


您可以通过加载 Markdown 文件而不进行 Markdown 渲染来链接到 Markdown 文件中的特定行。 要在不呈现的情况下加载 Markdown 文件，可以在文件的 URL 末尾使用 ?plain=1 参数。 例如，github.com/<organization>/<repository>/blob/<branch_name>/README.md?plain=1。

您可以在代码中以同样的方式链接到 Markdown 文件中的特定行。 在 URL 末尾的行号处附加 #L。 例如，github.com/<organization>/<repository>/blob/<branch_name>/README.md?plain=1#L14 将在纯文本 README.md 文件中突出显示第 14 行。


## 自动链接

自动链接扩展，即：当识别到 URL，或用 `<`、`>` 包括的 URL 时，会自动为其生成 `a` 标签。

**Markdown：**

```
https://github.com

<example@gmail.com>
```

**预览效果：**

https://github.com

<example@gmail.com>


## 图片

在超链接的写法前加一个 `!`，就是引用图片的方法。
图片alt就是显示在图片下面的文字，相当于对图片内容的解释。
图片title是图片的标题，当鼠标移到图片上时显示的内容。title可加可不加

**Markdown：**

```
![Alt text](https://mazhuang.org/favicon.ico "favicon")
```

**预览效果：**

![Alt text](https://mazhuang.org/favicon.ico "favicon")


## 列表

包括有序列表和无序列表。

**无序列表**

无序列表用 - + * 任何一种都可以

注意：- + * 跟内容之间都要有一个空格  

**有序列表**

数字加点

1.列表内容
2.列表内容
3.列表内容

**Markdown：**

```
- 苹果
- 葡萄
- 榴莲

1. 苹果
2. 葡萄
3. 榴莲
```

**预览效果：**

- 苹果
- 葡萄
- 榴莲

1. 苹果
2. 葡萄
3. 榴莲

注意：序号跟内容之间要有空格

列表嵌套
上一级和下一级之间敲三个空格或一个Tab键即可

## 分割线

使用一个单独行里的三个或以上 `*`、`-` 来生产一条水平分割线，它们之间可以有空格。

**Markdown：**

```
***

-----

- - -
```

**预览效果：**

***

-----

- - -

### 嵌入 HTML

Markdown 标记语言的目的不是替代 HTML，也不是发明一种更便捷的插入 HTML 标签的方式。它对应的只是 HTML 标签的一个很小的子集。

对于那些没有办法用 Markdown 语法来对应的 HTML 标签，直接使用 HTML 来写就好了。

### 表格

表头|表头|表头
---|:--:|---:
内容|内容|内容
内容|内容|内容

第二行分割表头和内容。

- 有一个就行，为了对齐，多加了几个
- 文字默认居左
- 两边加：表示文字居中
- 右边加：表示文字居右

注：原生的语法两边都要用 | 包起来。可以省略


**Markdown：**

    | 编号  | 姓名（左） | 年龄（右） | 性别（中） |
    | ----- | :--------  | ---------: | :------:   |
    | 0     | 张三       | 28         | 男         |
    | 1     | 李四       | 29         | 男         |

**预览效果：**

| 编号  | 姓名（左） | 年龄（右） | 性别（中） |
| ----- | :--------  | ---------: | :------:   |
| 0     | 张三       | 28         | 男         |
| 1     | 李四       | 29         | 男         |


## 注释

既然Markdown内嵌html语法，那么就可以用可以用隐藏的html标签。


### html注释
```
<!--哈哈我是注释，不会在浏览器中显示。-->

<!--
哈哈我是多段
注释，
不会在浏览器中显示。
-->
```

<!--哈哈我是注释，不会在浏览器中显示。-->

<!--
哈哈我是多段
注释，
不会在浏览器中显示。
-->

### hack方法


```
[//]: # (哈哈我是注释，不会在浏览器中显示。)

[^_^]: # (哈哈我是注释，不会在浏览器中显示。)

```

[//]: # (哈哈我是注释，不会在浏览器中显示。)

[^_^]: # (哈哈我是注释，不会在浏览器中显示。)