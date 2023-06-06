---
layout: post
title: Jekyll 资源、博客迁移、模版
date: 2023-06-06
categories: Jekyll
---

* * *

**目录**

*   [《Jekyll使用教程笔记 一：简介、快速开始、基本用法、目录结构》](https://juejin.cn/post/6844903623567081486 "https://juejin.cn/post/6844903623567081486")
*   [《Jekyll使用教程笔记 二：配置》](https://juejin.cn/post/6844903629246169096 "https://juejin.cn/post/6844903629246169096")
*   [《Jekyll使用教程笔记 三：Front Matter、写文章》](https://juejin.cn/post/6844903629682376711 "https://juejin.cn/post/6844903629682376711")
*   [《Jekyll使用教程笔记 四：创建页面、静态文件、变量》](https://juejin.cn/post/6844903629934084109 "https://juejin.cn/post/6844903629934084109")
*   [《Jekyll使用教程笔记 五：合集、数据文件》](https://juejin.cn/post/6844903630001160199 "https://juejin.cn/post/6844903630001160199")
*   [《Jekyll使用教程笔记 六：资源、博客迁移、模版》](https://juejin.cn/post/6844903632882630664 "https://juejin.cn/post/6844903632882630664")

* * *


资源
==

Jekyll 提供了对 Sass 的内建支持，还能通过安装相应的 Ruby gem 支持 CoffeeScript。使用时只需创建以 `.sass`、`.scss` 或 `.coffee` 为扩展名的文件，**_并以两行 `---` 开头即可_**，例如：

```
---
---

// start content
.my-definition
  font-size: 1.2em
```

Jekyll 将这些文件的输出存放在同一目录下，例如网站源目录下的 `css/styles.scss`，Jekyll 会处理生成网站目标目录下的 `css/styles.css`。

##### Jekyll 会处理 asset 文件中的所有 Liquid 过滤器和标签

如果你在使用 [Mustache](http://mustache.github.io/) 或其他会与 [Liquid 模板语法](http://jekyllcn.com/docs/templates/) 冲突的 JavaScript 模板语言，那么你需要将你的代码放在 `{% raw %}` 和 `{% endraw %}` 标签内。

Sass/SCSS
---------

Jekyll 允许在某些方面自定义 Sass 转换。

你需要将所有需要导入的部分文件放在 `sass_dir` 下，该路径默认是 `<source>/_sass`；而主 SCSS / Sass 文件放在你希望输出文件所在的目录下，如 `<source>/css`。详情可以参考 [示例网站](https://github.com/jekyll/jekyll-sass-converter/tree/master/example)。

如果你在使用 Sass 的 `@import` 语句，则需要确保你的 `sass_dir` 已设为 Sass 文件所在的目录。你可以这样设置：

```
sass:
    sass_dir: _sass
```

Sass 转换器默认配置中的 `sass_dir` 为 `_sass`。

##### `sass_dir` 只用于 Sass

注意 `sass_dir` 只是 Sass 的导入目录，没有其他作用。这意味着 Jekyll 并不直接知晓这些文件，所以这里的文件不应该包含 YAML 头信息，它们亦不会被转换。该目录只应该包含导入文件。

你也可以在 `_config.yml` 的 `style` 选项中指定输出样式：

```
sass:
    style: compressed
```

这些设置将传递给 Sass，因此所有 Sass 支持的输出样式在这里都可以使用。

Coffeescript
------------

为了确保 Coffeescript 能在 Jekyll 3.0 使用，你必须：

*   安装 `jekyll-coffeescript` gem
*   确保你的 `_config.yml` 包含下列设置并更新（即重新 `jekyll serve`）：

```
gems:
 - jekyll-coffeescript
```

[原文链接](http://jekyllrb.com/docs/assets/)