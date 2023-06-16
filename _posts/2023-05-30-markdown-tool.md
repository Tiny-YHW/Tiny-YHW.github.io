---
layout: post
title: Markdown工具
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



### 用Markdown写微信公众号

<https://doocs.github.io/md/>

### 提取文章转换为Markdown

<https://www.helloworld.net/html2md>

### 表格转Markdown

<https://tableconvert.com/excel-to-markdown>

## 在表格单元格里换行

借助于 HTML 里的 `<br />` 实现。

示例代码：

```
| Header1 | Header2                          |
|---------|----------------------------------|
| item 1  | 1. one<br />2. two<br />3. three |
```

示例效果：

| Header1 | Header2                          |
|---------|----------------------------------|
| item 1  | 1. one<br />2. two<br />3. three |


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



### emoji

以 GitHub Pages 为例。

**Markdown：**

```
:camel: :blush: :smile:
```

**预览效果：**

:camel: :blush: :smile:

更多可用 Emoji 代码参见 <https://www.webpagefx.com/tools/emoji-cheat-sheet/>。


## 行首缩进

直接在 Markdown 里用空格和 Tab 键缩进在渲染后会被忽略掉，需要借助 HTML 转义字符在行首添加空格来实现，`&ensp;` 代表半角空格，`&emsp;` 代表全角空格。

示例代码：

```
&emsp;&emsp;春天来了，又到了万物复苏的季节。
```

示例效果：

&emsp;&emsp;春天来了，又到了万物复苏的季节。

## 展示数学公式

如果是在 GitHub Pages，可以参考 <http://wanguolin.github.io/mathmatics_rending/> 使用 MathJax 来优雅地展示数学公式（非图片）。

如果是在 GitHub 项目的 README 等地方，目前我能找到的方案只能是贴图了，以下是一种比较方便的贴图方案：

1. 在 <https://www.codecogs.com/latex/eqneditor.php> 网页上部的输入框里输入 LaTeX 公式，比如 `$$x=\frac{-b\pm\sqrt{b^2-4ac}}{2a}$$`；

2. 在网页下部拷贝 URL Encoded 的内容，比如以上公式生成的是 `https://latex.codecogs.com/png.latex?%24%24x%3D%5Cfrac%7B-b%5Cpm%5Csqrt%7Bb%5E2-4ac%7D%7D%7B2a%7D%24%24`；

   ![](/images/posts/markdown/latex-img.png)

3. 在文档需要的地方使用以上 URL 贴图，比如

   ```
   ![](https://latex.codecogs.com/png.latex?%24%24x%3D%5Cfrac%7B-b%5Cpm%5Csqrt%7Bb%5E2-4ac%7D%7D%7B2a%7D%24%24)
   ```

   示例效果：

   ![](https://latex.codecogs.com/png.latex?%24%24x%3D%5Cfrac%7B-b%5Cpm%5Csqrt%7Bb%5E2-4ac%7D%7D%7B2a%7D%24%24)

## 图文混排

使用 `<img>` 标签来贴图，然后指定 `align` 属性。

示例代码：

```
<img align="right" src="https://raw.githubusercontent.com/mzlogin/mzlogin.github.io/master/images/posts/markdown/demo.png"/>

这是一个示例图片。

图片显示在 N 段文字的右边。

N 与图片高度有关。

刷屏行。

刷屏行。

到这里应该不会受影响了，本行应该延伸到了图片的正下方，所以我要足够长才能确保不同的屏幕下都看到效果。
```
示例效果：

<img align="right" src="https://raw.githubusercontent.com/mzlogin/mzlogin.github.io/master/images/posts/markdown/demo.png"/>

这是一个示例图片。

图片显示在 N 段文字的右边。

N 与图片高度有关。

刷屏行。

刷屏行。

到这里应该不会受影响了，本行应该延伸到了图片的正下方，所以我要足够长才能确保不同的屏幕下都看到效果。

## 控制图片大小和位置

标准的 Markdown 图片标记 `![]()` 无法指定图片的大小和位置，只能依赖默认的图片大小，默认居左。

而有时候源图太大想要缩小一点，或者想将图片居中，就仍需要借助 HTML 的标签来实现了。图片居中可以使用 `<div>` 标签加 `align` 属性来控制，图片宽高则用 `width` 和 `height` 来控制。

示例代码：

```
**图片默认显示效果：**

![](/images/posts/markdown/demo.png)

**加以控制后的效果：**

<div align="center"><img width="65" height="75" src="https://raw.githubusercontent.com/mzlogin/mzlogin.github.io/master/images/posts/markdown/demo.png"/></div>
```

示例效果：

**图片默认显示效果：**

![](https://raw.githubusercontent.com/mzlogin/mzlogin.github.io/master/images/posts/markdown/demo.png")

**加以控制后的效果：**

<div align="center"><img width="65" height="75" src="https://raw.githubusercontent.com/mzlogin/mzlogin.github.io/master/images/posts/markdown/demo.png"/></div>


