---
layout: post
title: GitHub编写Markdown基本撰写和格式语法
categories: [Markdown]
description: 记录一些测试结果description。
keywords: Markdown, GitHub
mermaid: false
sequence: false
flow: false
mathjax: false
mindmap: false
mindmap2: false
---

官方文档：https://docs.github.com/zh/get-started/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax

段落之间尽量空一个空行

> Markdown 是一种轻量级标记语言，创始人为 John Gruber。它允许人们「使用易读易写的纯文本格式编写文档，然后转换成有效的 XHTML（或者 HTML）文档」。——维基百科

**目录**

<!-- vim-markdown-toc GFM -->


* [优点](#优点)
* [语法](#语法)
    * [标题](#标题)
    * [段落](#段落)
    * [文本样式](#文本样式)
    * [引用](#引用)
    * [超链接](#超链接)
    * [图片](#图片)
    * [列表](#列表)
    * [代码块](#代码块)
    * [水平分割线](#水平分割线)
    * [嵌入 HTML](#嵌入-html)
* [扩展语法](#扩展语法)
    * [表格](#表格)
    * [任务列表](#任务列表)
    * [自动链接](#自动链接)
    * [emoji](#emoji)
* [奇技淫巧](#奇技淫巧)
    * [画流程图和时序图](#画流程图和时序图)
    * [插入数学公式](#插入数学公式)
    * [用 Markdown 做 PPT](#用-markdown-做-ppt)
    * [用 Markdown 写微信公众号](#用-markdown-写微信公众号)
    * [更多](#更多)
* [参考](#参考)

<!-- vim-markdown-toc -->

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

>[!NOTE]
>
>This is a standard NOTE block.

>[!TIP]
>
>This is a standard TIP.
>

>[!IMPORTANT]
>
>This is an IMPORTANT note.

### 标题

要创建标题，请在标题文本前添加一至六个 # 符号。 你使用的 # 数量将决定层次结构级别和标题的大小。
标题其实和HTML中的h系列很像，想要设置为标题的文字前面加#来表示
一个#是一级标题，二个#是二级标题，以此类推。支持六级标题。
注：标准语法一般在#后跟个空格再写文字，
示例：
```
# 这是一级标题
## 这是二级标题
### 这是三级标题
#### 这是四级标题
##### 这是五级标题
###### 这是六级标题
```
**预览效果：**

# 这是一级标题
## 这是二级标题
###### 这是六级标题

使用两个或多个标题时，GitHub 会自动生成一个目录，可以通过单击文件标题中的右侧控件来访问该目录。 每个标题都列在目录中，可以单击某个标题导航到所选部分。

### 段落

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

### 文本样式

**加粗** 要加粗的文字左右分别用两个\*号包起来

_斜体_ 要倾斜的文字左右分别用一个\*号或者用\_包起来

***斜体加粗*** 要倾斜和加粗的文字左右分别用三个\*号包起来

~~删除线~~ 要加删除线的文字左右分别用两个\~\~号包起来

示例：
**Markdown：**

```
**这是加粗的文字**
*这是倾斜的文字*`
***这是斜体加粗的文字***
~~这是加删除线的文字~~
```

**预览效果：**

**这是加粗的文字**

*这是倾斜的文字*`

***这是斜体加粗的文字***

~~这是加删除线的文字~~


### 引用
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

**对应 HTML：**

```html
<blockquote>
  <p>引用块段落一。</p>
  <p>引用块段落二。</p>
  <blockquote>
    <p>内嵌引用块段落一。</p>
  </blockquote>
  <h3 id="引用块内的标题">引用块内的标题</h3>
</blockquote>
```

### 超链接
本标签页
[超链接名](超链接地址 "超链接title")
title可加可不加
[百度](http://baidu.com)
[example](http://yinping4256.github.io)
<http://yinping4256.github.io>

新标签页
最简单的办法是，只需要在我上面两种方法后面添加{:target="_blank"}.
[example](http://yinping4256.github.io){:target="_blank"}
<http://yinping4256.github.io>{:target="_blank"}

Markdown 支持行内式链接和引用式链接。

**Markdown：**

```
行内式 [博客](https://mazhuang.org "我的个人博客") 链接，带 title。

行内式 [GitHub](https://github.com/mzlogin) 链接。

引用式 [博客][1] 链接。

引用式 [GitHub][2] 链接，带 title。

[1]: https://mazhuang.org
[2]: https://github.com/mzlogin "我的 GitHub 主页"
```

**预览效果：**

行内式 [博客](https://mazhuang.org "我的个人博客") 链接，带 title。

行内式 [GitHub](https://github.com/mzlogin) 链接。

引用式 [博客][1] 链接。

引用式 [GitHub][2] 链接，带 title。

[1]: https://mazhuang.org
[2]: https://github.com/mzlogin "我的 GitHub 主页"

**对应 HTML：**

```html
<p>行内式 <a href="https://mazhuang.org" title="我的个人博客">博客</a> 链接，带 title。</p>

<p>行内式 <a href="https://github.com/mzlogin">GitHub</a> 链接。</p>

<p>引用式 <a href="https://mazhuang.org">博客</a> 链接。</p>

<p>引用式 <a href="https://github.com/mzlogin" title="我的 GitHub 主页">GitHub</a> 链接，带 title。</p>
```

### 图片

在超链接的写法前加一个 `!`，就是引用图片的方法。

![图片alt](图片地址 ''图片title'')

图片alt就是显示在图片下面的文字，相当于对图片内容的解释。
图片title是图片的标题，当鼠标移到图片上时显示的内容。title可加可不加

**Markdown：**

```
![Alt text](https://mazhuang.org/favicon.ico "favicon")
```

**预览效果：**

![Alt text](https://mazhuang.org/favicon.ico "favicon")

**对应 HTML：**

```html
<img src="https://mazhuang.org/favicon.ico" alt="Alt text" title="favicon">
```


### 列表
包括有序列表和无序列表。
无序列表
语法：
无序列表用 - + * 任何一种都可以
注意：- + * 跟内容之间都要有一个空格  
- 列表内容  
+ 列表内容  
* 列表内容  

语法：
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

**对应 HTML：**

```html
<ul>
  <li>苹果</li>
  <li>葡萄</li>
  <li>榴莲</li>
</ul>
<ol>
  <li>苹果</li>
  <li>葡萄</li>
  <li>榴莲</li>
</ol>
```

注意：序号跟内容之间要有空格

列表嵌套
上一级和下一级之间敲三个空格即可

#
### 代码
支持行内代码和代码块。
语法：
单行代码：代码之间分别用一个反引号包起来  
`代码内容`

代码块：代码之间分别用三个反引号包起来，且两边的反引号单独占一行
```java
public void error(String format, Object... arguments);
```

**Markdown：**

    Android 里使用 `TextUtils` 类的 `isEmpty` 方法来判断字符串是否为空。

    ```java
    if (TextUtils.isEmpty(text)) {
        return null;
    }
    ```

**预览效果：**

Android 里使用 `TextUtils` 类的 `isEmpty` 方法来判断字符串是否为空。

```java
if (TextUtils.isEmpty(text)) {
    return null;
}
```

**对应 HTML：**

```html
<p>Android 里使用 <code>TextUtils</code> 类的 <code>isEmpty</code> 方法来判断字符串是否为空。</p>

<div class="highlight highlight-source-java"><pre><span class="pl-k">if</span> (<span class="pl-smi">TextUtils</span><span class="pl-k">.</span>isEmpty(text)) {
    <span class="pl-k">return</span> <span class="pl-c1">null</span>;
}</pre></div>
```

上例中的语言标记 `java` 可选填，可用于在编辑器和渲染后的效果里添加语法高亮。

块式代码也可以对整个代码段缩进四个空格，或一个 Tab 来实现。

### 水平分割线

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

**对应 HTML：**

```
<hr />

<hr />

<hr />
```

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
文字默认居左
-两边加：表示文字居中
-右边加：表示文字居右
注：原生的语法两边都要用 | 包起来。此处省略

| 表头 | 表头 | 表头 |
| --- | --- | --- |
|第一行|第一行|第一行|
|第二行|第二行|第二行|
|第三行|第三行|第三行|

*Markdown：**

    | 编号  | 姓名（左） | 年龄（右） | 性别（中） |
    | ----- | :--------  | ---------: | :------:   |
    | 0     | 张三       | 28         | 男         |
    | 1     | 李四       | 29         | 男         |

**预览效果：**

| 编号  | 姓名（左） | 年龄（右） | 性别（中） |
| ----- | :--------  | ---------: | :------:   |
| 0     | 张三       | 28         | 男         |
| 1     | 李四       | 29         | 男         |

**对应 HTML：**

```html
<table>
  <thead>
    <tr>
      <th>编号</th>
      <th align="left">姓名（左）</th>
      <th align="right">年龄（右）</th>
      <th align="center">性别（中）</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>0</td>
      <td align="left">张三</td>
      <td align="right">28</td>
      <td align="center">男</td>
    </tr>
    <tr>
      <td>1</td>
      <td align="left">李四</td>
      <td align="right">29</td>
      <td align="center">男</td>
    </tr>
  </tbody>
</table>
```
### 任务列表

在 GitHub / GitLab 里有较好的支持。

**Markdown：**

```
- [x] 洗碗
- [ ] 清洗油烟机
- [ ] 拖地
```

**预览效果：**

- [x] 洗碗
- [ ] 清洗油烟机
- [ ] 拖地

**对应 HTML：**

```html
<ul class="contains-task-list">
  <li class="task-list-item"><input type="checkbox" id="" disabled="" class="task-list-item-checkbox" checked=""> 洗碗</li>
  <li class="task-list-item"><input type="checkbox" id="" disabled="" class="task-list-item-checkbox"> 清洗油烟机</li>
  <li class="task-list-item"><input type="checkbox" id="" disabled="" class="task-list-item-checkbox"> 拖地</li>
</ul>
```

如果是在 GitHub / GitLab 的 Issue 里，会附赠任务完成比例提示效果：

![task list 1](https://raw.githubusercontent.com/mzlogin/markdown-intro/master/assets/task-list-1.png)

还可以直接在网页上拖动调整顺序，勾选和取消勾选。

![task list 2](https://raw.githubusercontent.com/mzlogin/markdown-intro/master/assets/task-list-2.png)

### 自动链接

自动链接扩展，即：当识别到 URL，或用 `<`、`>` 包括的 URL 时，会自动为其生成 `a` 标签。

**Markdown：**

```
https://github.com

<example@gmail.com>
```

**预览效果：**

https://github.com

<example@gmail.com>

**对应 HTML：**

```html
<p><a href="https://github.com">https://github.com</a></p>

<p><a href="mailto:example@gmail.com">example@gmail.com</a></p>
```

### emoji

以 GitHub Pages 为例。

**Markdown：**

```
:camel: :blush: :smile:
```

**预览效果：**

:camel: :blush: :smile:

**对应 HTML：**

```html
<p>
  <img class="emoji" title=":camel:" alt=":camel:" src="https://assets-cdn.github.com/images/icons/emoji/unicode/1f42b.png" height="20" width="20">
  <img class="emoji" title=":blush:" alt=":blush:" src="https://assets-cdn.github.com/images/icons/emoji/unicode/1f60a.png" height="20" width="20">
  <img class="emoji" title=":smile:" alt=":smile:" src="https://assets-cdn.github.com/images/icons/emoji/unicode/1f604.png" height="20" width="20">
</p>
```

## 奇技淫巧

脑洞清奇的工程师们还发掘了很多使用 Markdown 的方法，大部分都是引入第三方 JavaScript 插件来实现。对这部分我只做简述，对其中的部分功能比如作图等，还是推荐用专门的可视化工具去做。

### 画流程图和时序图

有部分网站和编辑器实现了对 Markdown 里流程图和时序图的支持，比如我们使用的项目管理工具 TAPD 的在线编辑器，还有 VSCode + 插件 Markdown Preview Enhanced 等。

以我们使用的项目管理工具 TAPD 的在线编辑器为例：

![流程图](https://raw.githubusercontent.com/mzlogin/markdown-intro/master/assets/tapd-markdown-flowchart.png)

![时序图](https://raw.githubusercontent.com/mzlogin/markdown-intro/master/assets/tapd-markdown-seq.png)

### 插入数学公式

仍然以 TAPD 为例：

![数学公式](https://raw.githubusercontent.com/mzlogin/markdown-intro/master/assets/tapd-markdown-math.png)

应该是利用 JavaScript 支持了 LaTeX 公式语法。

### 用 Markdown 做 PPT

有专门的工具 [Marp](https://github.com/yhatt/marp)，另外使用 VSCode + 插件 Markdown Preview Enhanced 也可以实现。

### 用 Markdown 写微信公众号

可以将公众号素材用 Markdown 编辑好后，贴到在线排版工具以后，复制到公众号编辑器里即可。有多种页面主题和代码主题可选择。

我维护的工具地址：<https://md.mazhuang.org>

![微信公众号](https://raw.githubusercontent.com/mzlogin/markdown-intro/master/assets/wechat-markdown.png)

### 更多

想象力丰富的工程师们还扩展了很多基于 Markdown 的玩法，包括但不限于：

* 自动生成 / 更新 Table of Contents
* 流程图 / 时序图
* 制作幻灯片
* 集成 PlantUML / GraphViz 的能力
* 导出 HTML / PDF / 电子书
* ...

以上功能基本都可以用 VSCode + 插件 Markdown Preview Enhanced 实现。

另外可以参考我以前的一篇博客 [关于 Markdown 的一些奇技淫巧](https://mazhuang.org/2017/09/01/markdown-odd-skills/)。

## 参考

* [Markdown: Syntax - DARING FIREBALL](https://daringfireball.net/projects/markdown/syntax)
* [Markdown - 维基百科](https://zh.wikipedia.org/wiki/Markdown)
* [GitHub Flavored Markdown Spec](https://github.github.com/gfm/)
* [关于 Markdown 的一些奇技淫巧](https://mazhuang.org/2017/09/01/markdown-odd-skills/)

---
