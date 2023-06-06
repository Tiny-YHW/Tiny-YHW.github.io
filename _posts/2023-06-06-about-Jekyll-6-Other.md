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

博客迁移
====

如果你要从其他博客迁移到 Jekyll，Jekyll 导入器可以帮助你。想了解更多关于导入站点至 Jekyll 的信息，请查看我们的 [`jekyll-import`文档页面](http://import.jekyllrb.com/docs/home/)。

模板
==

Jekyll 使用 [Liquid](http://wiki.shopify.com/Liquid) 模板语言，支持所有标准的 Liquid [标签](http://wiki.shopify.com/Logic)和[过滤器](http://wiki.shopify.com/Filters)。Jekyll 甚至增加了几个过滤器和标签，方便使用。

过滤器
---

| 描述 | 过滤器 和 输出 |
| --- | --- |
| 
**日期转化为 XML 模式**

将日期转化为 XML 模式 (ISO 8601) 的格式。

 | 

`{{ site.time | date_to_xmlschema }}`

`2008-11-17T13:07:54-08:00`

 |
| 

**日期转化为 RFC-822 格式**

将日期转化为 RFC-822 格式，用于 RSS 订阅。

 | 

`{{ site.time | date_to_rfc822 }}`

`Mon, 17 Nov 2008 13:07:54 -0800`

 |
| 

**日期转化为短格式**

将日期转化为短格式。

 | 

`{{ site.time | date_to_string }}`

`17 Nov 2008`

 |
| 

**日期转化为长格式**

将日期转化为长格式。

 | 

`{{ site.time | date_to_long_string }}`

`17 November 2008`

 |
| 

**检索**

选取键值对应的所有对象，返回一个数组。

 | 

`{{ site.members | where:"graduation_year","2014" }}`

 |
| 

**判断**

选取表达式正确的所有对象，返回一个数组。

 | 

`{{ site.members | where_exp:"item", "item.graduation_year == 2014" }}` `{{ site.members | where_exp:"item", "item.graduation_year < 2014" }}` `{{ site.members | where_exp:"item", "item.projects contains 'foo'" }}`

 |
| 

**分组**

根据所给属性将对象分组，返回一个数组。

 | 

`{{ site.members | group_by:"graduation_year" }}`

`[{"name"=>"2013", "items"=>[...]},   {"name"=>"2014", "items"=>[...]}]`

 |
| 

**XML 转码**

对一些字符串转码，已方便显示在 XML 。

 | 

`{{ page.content | xml_escape }}`

 |
| 

**CGI 转码**

CGI 转码，用于 URL 中，将所有的特殊字符转化为 %XX 的形式。

 | 

`{{ “foo,bar;baz?” | cgi_escape }}`

`foo%2Cbar%3Bbaz%3F`

 |
| 

**URI 转码**

URI 转码。

 | 

`{{ “'foo, bar \\baz?'” | uri_escape }}`

`foo,%20bar%20%5Cbaz?`

 |
| 

**统计字数**

统计文章中的字数。

 | 

`{{ page.content | number_of_words }}`

`1337`

 |
| 

**数组转换为句子**

将数组转换为句子，列举标签时尤其有用。

 | 

`{{ page.tags | array_to_sentence_string }}`

`foo, bar, and baz`

 |
| 

**Markdown 支持**

将 Markdown 格式的字符串转换为 HTML 。

 | 

`{{ page.excerpt | markdownify }}`

 |
| 

**Sass / SCSS 转换**

将 Sass / SCSS 格式的字符串转换为 CSS

 | 

`{{ some_scss | scssify }}`

`{{ some_sass | sassify }}`

 |
| 

**Slugify**

将字符串转换为小写字母 URL “slug”。详见下面的参数。

 | 

`{{ "The _config.yml file" | slugify }}`

`the-config-yml-file`

`{{ "The _config.yml file" | slugify: 'pretty' }}`

`the-_config.yml-file`

 |
| 

**JSON 转换**

将 Hash / 数组 格式的字符串转换为 JSON

 | 

`{{ site.data.projects | jsonify }}`

 |
| 

**排序**

对数组排序，可选参数为：1.排序属性；2.顺序（正序或倒序）

 | 

`{{ page.tags | sort }}`

`{{ site.posts | sort: 'author' }}`

`{{ site.pages | sort: 'title', 'last' }}`

 |
| 

**样本**

从数组中选取一个随意值。可选参数为：选取个数

 | 

`{{ site.pages | sample }}`

`{{ site.pages | sample:2 }}`

 |
| 

**数组筛选**

从一个数组中 Push, pop, shift, and unshift 元素。

这些命令对原数组是**无影响的**。它们不会改变数组本身，而是创建副本后，对副本进行操作。

 | 

`{{ page.tags | push: 'Spokane' }}`

`['Seattle', 'Tacoma', 'Spokane']`

`{{ page.tags | pop }}`

`['Seattle']`

`{{ page.tags | shift }}`

`['Tacoma']`

`{{ page.tags | unshift: "Olympia" }}`

`['Olympia', 'Seattle', 'Tacoma']`

 |
| 

**Inspect**

将对象转换为其字符串表示形式，用于调试

 | 

`{{ some_var | inspect }}`

 |

### `Slugify` 的可选参数

`Slugify` 接受一个参数，用来设定具体的过滤字符。默认值为`default`。可选参数如下（含过滤字符）：

*   `none`：不过滤字符
*   `raw`：空格
*   `default`：空格和非字母数字字符
*   `pretty`：空格和非字母数字字符，`._~!$&'()+,;=@`除外

标签
--

### 引用

如果你需要在多个地方引用一小代码片段，可以使用 `include` 标签。

```
{% include footer.html %}
```

Jekyll 要求所有被引用的文件放在根目录的 `_includes` 文件夹，上述代码将把 `<source>/_includes/footer.html` 的内容包含进来。

##### 提示™：使用变量作为文件名

文件名可以是文字（如上面的例子），也可以是 liquid 标记的使用变量，如`{% include {{my_variable}} %}`。

你还可以对 include 传递参数。省略引用标记来传递变量： Liquid 弯括号不能在此处使用：

```
{% include footer.html param="value" variable-param=page.variable %}
```

这些变量可以通过 Liquid 调用：

```
{{ include.param }}
```

#### 相对于其他文件的 Permalink 引入

你也可以选择相对当前文件，引入其他文件的片段：

```
{% include_relative somedir/footer.html %}
```

引入的内容未必总在 `_includes` 文件夹。当该标签被使用时，引入的内容应位于对应的相对路径下。例如，`_posts/2014-09-03-my-file.markdown`文件使用了`include_relative`标签，引入的文件需要位于 `_posts` 文件夹或其子文件夹。在其他路径下将无法引入。

`include` 标签的其他特征也同样适用于 `include_relative` 标签，如使用变量。

### 代码高亮

Jekyll 已经支持超过 60 种语言的代码高亮显示，在此感谢 [Rouge](http://rouge.jneen.net/)。Rouge 在 Jekyll 3 及以上版本是默认高亮脚本。若想在 Jekyll 2 中使用 Rouge，需要设置 `highlighter` 为 `rouge` 并确保 `rouge` gem 正确安装。

另外，你也可以使用 [Pygments](http://pygments.org/) 实现代码高亮。要使用 Pygments，你必须在你系统上安装 Python，安装 `pygment.rb` gem 并在配置文件中设置 `highlighter` 为 `pygments`。Pygments 支持超过 [一百种语言](http://pygments.org/languages/)。

使用代码高亮的例子如下：

```
{% highlight ruby %}
def foo
  puts 'foo'
end
{% endhighlight %}
```

`highlight` 的参数 (本例中的 `ruby`) 是识别所用语言。为了确定最适合你所用语言的高亮方式，你可以在 [Rouge wiki](https://github.com/jayferd/rouge/wiki/List-of-supported-languages-and-lexers) 和 [Pygments’ Lexers page](http://pygments.org/docs/lexers/) 寻找对应语言的 “short name”。

#### 行号

`highlight` 的第二个可选参数是 `linenos` 。使用了 `linenos` 会强制在代码上加入行号。例如：

```
{% highlight ruby linenos %}
def foo
  puts 'foo'
end
{% endhighlight %}
```

#### 代码高亮的样式

要使用代码高亮，你还需要包含一个样式表。例如 [syntax.css](http://github.com/mojombo/tpw/tree/master/css/syntax.css) 。它包含了和 GitHub 一样的样式，并且免费。如果你使用了 `linenos` ，可能还需要在 `syntax.css` 加入 `.lineno` 样式。

### 链接

如果你要创建一组文档、博文、页面或文件的链接，使用 `link` 标签可以正确生成指定路径的永久链接。

```

{% link _collection/name-of-document.md %}
{% link _posts/2016-07-26-name-of-post.md %}
{% link news/index.html %}
{% link /assets/files/doc.pdf %}


```

还可以使用这个标签在MarkDown文件中创建一个链接：

```

[Link to a document]({% link _collection/name-of-document.md %})
[Link to a post]({% link _posts/2016-07-26-name-of-post.md %})
[Link to a page]({% link news/index.html %})
[Link to a file]({% link /assets/files/doc.pdf %})


```

### 博文链接（Post URL）

如果你想使用你某篇文章的链接，标签 `post_url` 可以满足你的需求。

```
{% post_url 2010-07-21-name-of-post %}
```

如果你使用了子文件夹来组织你的博文，你需要在路径中加入子文件夹：

```
{% post_url /subdir/2010-07-21-name-of-post %}
```

当使用`post_url`标签时，不需要写文件后缀名。

还可以用 Markdown 这样为你的文章生成超链接：

```
[Name of Link]({% post_url 2010-07-21-name-of-post %})
```

### Gist

使用 `gist` 标签可以轻松的把 GitHub Gist 签入到网站中，对于公有和私有的 gist 均有效：

```
{% gist parkr/931c1c8d465a04042403 %}
```

你也可以为 gist 设置文件名：

```
{% gist parkr/931c1c8d465a04042403 jekyll-private-gist.markdown %}
```

为使用 `gist` 标签，你需要添加 [jekyll-gist](https://github.com/jekyll/jekyll-gist) gem 到你的项目中。
