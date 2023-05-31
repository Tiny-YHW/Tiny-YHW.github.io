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

#标题
要创建标题，请在标题文本前添加一至六个 # 符号。 你使用的 # 数量将决定层次结构级别和标题的大小。
标题其实和HTML中的h系列很像，想要设置为标题的文字前面加#来表示
一个#是一级标题，二个#是二级标题，以此类推。支持六级标题。
注：标准语法一般在#后跟个空格再写文字，
示例：
# 这是一级标题
## 这是二级标题
### 这是三级标题
#### 这是四级标题
##### 这是五级标题
###### 这是六级标题
使用两个或多个标题时，GitHub 会自动生成一个目录，可以通过单击文件标题中的右侧控件来访问该目录。 每个标题都列在目录中，可以单击某个标题导航到所选部分。

#文本样式

加粗
要加粗的文字左右分别用两个*号包起来

斜体
要倾斜的文字左右分别用一个*号或者用_包起来

斜体加粗
要倾斜和加粗的文字左右分别用三个*号包起来

删除线
要加删除线的文字左右分别用两个~~号包起来
或者加一个<del>

<del>f(n)</del>  
<del>= f(n-1) + f(n-2)</del>  
<del>= 2f(n-2) + f(n-3)</del>  
<del>= 3f(n-3) + 2f(n-4)</del>  
<del>= 5 f(n-4) + 3f(n-5)</del>  
<del>= 8f(n-5) + 5f(n-6)</del>  
<del>= ...</del>  
<del>= fibo(x+1)f(n-x)+fibo(x)f(n-(x+1))</del>  
<del>=...</del>  
<del>= fibo(n-1)f(n-(n-2)) + fibo(n-2)f(n-(n-1))</del>  
<del>= fibo(n-1)f(2) + fibo(n-2)f(1)</del>  

示例：

**这是加粗的文字**
*这是倾斜的文字*`
***这是斜体加粗的文字***
~~这是加删除线的文字~~

#引用
在引用的文字前加>即可。引用也可以嵌套，如加两个>>三个>>>
n个...

>这是引用的内容
>>这是引用的内容
>>>这是引用的内容

#四、分割线
三个或者三个以上的 - 或者 * 都可以。

示例：
---
***
#五、图片

![图片alt](图片地址 ''图片title'')

图片alt就是显示在图片下面的文字，相当于对图片内容的解释。
图片title是图片的标题，当鼠标移到图片上时显示的内容。title可加可不加

#六、超链接
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



#七、列表
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

注意：序号跟内容之间要有空格

列表嵌套
上一级和下一级之间敲三个空格即可

#八、表格
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

#九、代码
语法：
单行代码：代码之间分别用一个反引号包起来  
`代码内容`

代码块：代码之间分别用三个反引号包起来，且两边的反引号单独占一行
```java
public void error(String format, Object... arguments);
```
