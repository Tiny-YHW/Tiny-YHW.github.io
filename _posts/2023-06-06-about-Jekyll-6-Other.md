---
layout: post
title: Jekyll 资源、博客迁移、模版
permalink: /Jekyll-Other/
date: 2023-06-06
categories: Jekyll
---
* * *
* * *

**目录**

*   [《Jekyll使用教程笔记 一：简介、快速开始、基本用法、目录结构》](https://juejin.cn/post/6844903623567081486 "https://juejin.cn/post/6844903623567081486")
*   [《Jekyll使用教程笔记 二：配置》](https://juejin.cn/post/6844903629246169096 "https://juejin.cn/post/6844903629246169096")
*   [《Jekyll使用教程笔记 三：Front Matter、写文章》](https://juejin.cn/post/6844903629682376711 "https://juejin.cn/post/6844903629682376711")
*   [《Jekyll使用教程笔记 四：创建页面、静态文件、变量》](https://juejin.cn/post/6844903629934084109 "https://juejin.cn/post/6844903629934084109")
*   [《Jekyll使用教程笔记 五：合集、数据文件》](https://juejin.cn/post/6844903630001160199 "https://juejin.cn/post/6844903630001160199")
*   [《Jekyll使用教程笔记 六：资源、博客迁移、模版》](https://juejin.cn/post/6844903632882630664 "https://juejin.cn/post/6844903632882630664")

* * *

资源（Assets）
==========

Jekyll内置了对Sass的支持，并且可以通过一个Ruby gem使用CoffeeScript。为了使用它们，你必须首先使用适当的扩展名（`.sass`，`.scss`或`.coffee`之一）创建一个文件，然后**在文件头部使用两行三个连着的短横线**，如下所示：

```
---
---
// start content
.my-definition
  font-size: 1.2em

```

Jekyll将这些文件视为常规页面，因为输出的文件将放置在与其源文件相同的目录中。例如，如果你的站点的源文件夹中有一个名为`css/styles.scss`的文件，Jekyll会对其进行处理并将其放入站点的`css/styles.scss`。

> **注意：Jekyll处理资源文件中的所有Liquid过滤器和标签**
> 
> 如果你正在使用与[Liquid模板语法](https://link.juejin.cn/?target=https%3A%2F%2Fjekyllrb.com%2Fdocs%2Ftemplates%2F "https://jekyllrb.com/docs/templates/")冲突的[Mustache](https://link.juejin.cn/?target=https%3A%2F%2Fmustache.github.io%2F "https://mustache.github.io/")或其他JavaScript模板语言，则需要在代码外围放置`{% raw %}`和`{% endraw %}`标签。

Sass/SCSS
---------

Jekyll允许你以某种方式自定义你的Sass转换。

将所有分支放在`sass_dir`中，默认为`<source>/_sass`。将主SCSS或Sass文件放在希望它们位于输出文件中的位置，如`<source>/css`。例如，[在Jekyll中使用Sass支持](https://link.juejin.cn/?target=https%3A%2F%2Fgithub.com%2Fjekyll%2Fjekyll-sass-converter%2Ftree%2Fmaster%2Fdocs "https://github.com/jekyll/jekyll-sass-converter/tree/master/docs")来查看这个示例站点。

如果你使用的是Sass `@import`语句，则需要确保将`sass_dir`设置为包含Sass文件的基础目录。你可以这样做：

```
sass:
    sass_dir: _sass

```

Sass转换器会将`sass_dir`配置选项默认为`_sass`。

> **注意：`sass_dir`只被Sass使用**
> 
> 请注意，`sass_dir`成为Sass导入的加载路径，仅此而已。这意味着Jekyll不直接了解这些文件，因此这里的任何文件都不应该包含上述的YAML Front Matter，也不会像上面描述的那样进行转换。该文件夹应该只包含导入。

你也可以在`_config.yml`文件中使用`style`选项指定输出样式：

```
sass:
    style: compressed

```

这些传递给Sass，所以Sass支持的任何输出样式选项在这里也是有效的。

Coffeescript
------------

要在Jekyll 3.0及更高版本中启用Coffeescript，你必须这样做

*   安装`jekyll-coffeescript` gem
    
*   确保你的`_config.yml`是最新的并包含以下内容：
    
    ```
    plugins:
     - jekyll-coffeescript
    
    ```
    

博客迁移
====

如果你从另一个博客系统切换到Jekyll，Jekyll的importers可以帮助你迁移。 要了解有关将你的网站导入Jekyll的更多信息，请访问我们的[`jekyll-import`文档网站](https://link.juejin.cn/?target=https%3A%2F%2Fimport.jekyllrb.com%2Fdocs%2Fhome%2F "https://import.jekyllrb.com/docs/home/")。

模版（Templates）
=============

Jekyll使用[Liquid](https://link.juejin.cn/?target=https%3A%2F%2Fshopify.github.io%2Fliquid%2F "https://shopify.github.io/liquid/")模板语言来处理模板。支持所有标准Liquid[标签](https://link.juejin.cn/?target=https%3A%2F%2Fshopify.github.io%2Fliquid%2Ftags%2Fcontrol-flow%2F "https://shopify.github.io/liquid/tags/control-flow/")和[过滤器](https://link.juejin.cn/?target=https%3A%2F%2Fshopify.github.io%2Fliquid%2Ffilters%2Fabs%2F "https://shopify.github.io/liquid/filters/abs/")。为了简化常见任务，Jekyll甚至还增加了一些方便的过滤器和标签，你可以在此页面上找到所有这些过滤器和标签。Jekyll甚至允许你通过插件提出自己的标签。

过滤器（Filters）
------------

| 说明 | 过滤器 | 输出结果 |
| --- | --- | --- |
| **相对URL**  
将`baseurl`值添加到输入中。如果你的站点托管在子路径而不是域的根目录，则非常有用。 | `{{ "/assets/style.css" | relative_url }}` | `/my-baseurl/assets/style.css` |
| **绝对URL**  
将`url`和`baseurl`值添加到输入中。 | `{{ "/assets/style.css" | absolute_url }}` | `http://example.com/my-baseurl/assets/style.css` |
| **日期转XML架构**  
将日期格式化为XML架构（ISO 8601）格式。 | `{{ site.time | date_to_xmlschema }}` | `2008-11-07T13:07:54-08:00` |
| **日期转RFC-822格式**  
将日期格式化为用于RSS源的RFC-822格式。 | `{{ site.time | date_to_rfc822 }}` | `Mon, 07 Nov 2008 13:07:54 -0800` |
| **日期转字符串**  
将日期格式化为短格式。 | `{{ site.time | date_to_string }}` | `07 Nov 2008` |
| **日期转为`ordinal` `US`风格的字符串**  
将日期格式化为ordinal，US，短格式。 | `{{ site.time | date_to_string: "ordinal", "US" }}` | `Nov 7th, 2008` |
| **日期转长字符串**  
将日期格式化为长格式。 | `{{ site.time | date_to_long_string }}` | `07 November 2008` |
| **日期转为`ordinal` `UK`风格的长字符串**  
将日期格式化为ordinal，UK，长格式。 | `{{ site.time | date_to_long_string: "ordinal" }}` | `7th November 2008` |
| **Where**  
选择数组中指定key对应的对象。 | `{{ site.members | where:"graduation_year","2014" }}` |  |
| **Where Expression**  
选择数组中表达式为true的所有对象。**`[3.2.0]`** | `{{ site.members | where_exp:"item", "item.graduation_year == 2014" }}`  
`{{ site.members | where_exp:"item", "item.graduation_year < 2014" }}`  
`{{ site.members | where_exp:"item","item.projects contains 'foo'" }}` |  |
| **分组**  
按给定属性对数组的项进行分组。 | `{{ site.members | group_by:"graduation_year" }}` | `[{"name"=>"2013", "items"=>[...]}, {"name"=>"2014", "items"=>[...]}]` |
| **按表达分组**  
使用Liquid表达式对数组的项进行分组。**`[3.4.0]`** | `{{ site.members | group_by_exp:"item", "item.graduation_year | truncate: 3, \"\"" }}` | `[{"name"=>"201...", "items"=>[...]},{"name"=>"200...", "items"=>[...]}]` |
| **XML转义**  
转义一些文本以便在XML中使用。 | `{{ page.content | xml_escape }}` | \`\` |
| **CGI转义**  
CGI转义字符串以便在URL中使用。用适当的`%XX`替换替换任何特殊字符。CGI转义通常用加号`+`替换空格。 | `{{ "foo, bar; baz?" | cgi_escape }}` | `foo%2C+bar%3B+baz%3F` |
| **URI转义**  
使用百分比对URI中的任何特殊字符进行编码。URI转义通常用`%20`替换空格。[保留字符](https://link.juejin.cn/?target=https%3A%2F%2Fen.wikipedia.org%2Fwiki%2FPercent-encoding%23Types_of_URI_characters "https://en.wikipedia.org/wiki/Percent-encoding#Types_of_URI_characters")不会被转义。 | `{{ "http://foo.com/?q=foo, \bar?" | uri_escape }}` | `http://foo.com/?q=foo,%20%5Cbar?` |
| **字数**  
计算某些文本中的单词数。 | `{{ page.content | number_of_words }}` | `1337` |
| **数组转句子**  
将数组转换为句子。用于列出标签。  
连接器有可选参数。 | `{{ page.tags | array_to_sentence_string }}`  
或  
`{{ page.tags | array_to_sentence_string: 'or' }}` | `foo, bar, and baz`  
或  
`foo, bar, or baz` |
| **Markdownify**  
将Markdown格式的字符串转换为HTML。 | `{{ page.excerpt | markdownify }}` |  |
| **Smartify**  
将“引号”转换为“智能引号”。 | `{{ page.title | smartify }}` |  |
| **转换Sass/SCSS**  
将Sass或SCSS格式的字符串转换为CSS。 | `{{ some_scss | scssify }}`  
`{{ some_sass | sassify }}` |  |
| **Slugify**  
将字符串转换为小写URL“slug”。请参阅下面的选项。 | `{{ "The _config.yml file" | slugify }}`  
或  
`{{ "The _config.yml file" | slugify: 'pretty' }}`  
或  
`{{ "The _cönfig.yml file" | slugify: 'ascii' }}`  
或  
`{{ "The cönfig.yml file" | slugify: 'latin' }}` | `the-config-yml-file`  
或  
`the-_config.yml-file`  
或  
`the-c-nfig-yml-file`  
或  
`the-config-yml-file` |
| **数据转JSON**  
将哈希或数组转换为JSON。 | `{{ site.data.projects | jsonify }}` |  |
| **规范化空格**  
用单个空格替换任何出现的多个连续空格。 | `{{ "a \n b" | normalize_whitespace }}` |  |
| **排序**  
对数组进行排序。  
哈希的可选参数：  
1.属性名称  
2.nils顺序（`first`或`last`）。 | `{{ page.tags | sort }}`  
或  
`{{ site.posts | sort: 'author' }}`  
或  
`{{ site.pages | sort: 'title', 'last' }}` |  |
| \*\*\*\*  
从数组中选择一个随机值。  
可选：选择多个值。 | `{{ site.pages | sample }}`  
或  
`{{ site.pages | sample:2 }}` |  |
| **转为整数**  
将字符串或布尔值转换为整数。 | `{{ some_var | to_integer }}` |  |
| **过滤器数组**  
从数组中push、pop、shift和unshift元素。  
这些都是**非破坏性的**，即它们不会改变源数组，而是复制一个再改变这个新的数组。 | `{{ page.tags | push: 'Spokane' }}`  
或  
`{{ page.tags | pop }}`  
或  
`{{ page.tags | shift }}`  
或  
`{{ page.tags | unshift: "Olympia" }}` | `['Seattle', 'Tacoma', 'Spokane']`  
或  
`['Seattle']`  
或  
`['Tacoma']`  
或  
`['Olympia', 'Seattle', 'Tacoma']` |
| **检查**  
将对象转换为String表示以进行调试。 | `{{ some_var | inspect }}` |  |

### `slugify`过滤器的选项

`slugify`过滤器接受一个选项，每个选项指定要过滤的内容。默认值为`default`。 它们如下（用它们过滤的内容）：

*   `none`：没有字符
*   `raw`：空格
*   `default`：空格和非字母数字字符
*   `pretty`：除`._~!$&'()+,;=@`之外的空格和非字母数字字符
*   `ascii`：空格，非字母数字和非ASCII字符
*   `latin`：和`default`一样，除了拉丁字符首先被音译（例如`àèïòü`转为`aeiou`）**`[3.7.0]`**

标签（Tags）
--------

*   [引用](https://link.juejin.cn/?target=)
*   [代码块高亮显示](https://link.juejin.cn/?target=)
*   [链接到页面，合集和文章（新的和改进的方式）](https://link.juejin.cn/?target=)
*   [链接到文章（旧方式）](https://link.juejin.cn/?target=)

### 引用（Includes）

如果你希望在网站的多个位置引用小的网页摘要，请将摘要保存为_引用文件_，并使用`include`标记将其插入到需要的位置：

```
{% include footer.html %}

```

Jekyll希望所有_引用文件_都放在源目录根目录的`_includes`目录中。在上面的示例中，这会将`_includes/footer.html`的内容嵌入到调用文件中。

有关使用引用的更多高级信息，请参阅[引用](https://link.juejin.cn/?target=https%3A%2F%2Fjekyllrb.com%2Fdocs%2Fincludes "https://jekyllrb.com/docs/includes")。

### 代码块高亮显示

由于[Rouge](https://link.juejin.cn/?target=http%3A%2F%2Frouge.jneen.net%2F "http://rouge.jneen.net/")，Jekyll已经支持超过60种语言的语法高亮显示。Rouge是Jekyll 3及以上版本的默认语法高亮引擎。要在Jekyll 2中使用它，请将`highlighter`设置为`rouge`，并确保正确安装了`rouge` gem。

或者，你可以使用[Pygments](https://link.juejin.cn/?target=http%3A%2F%2Fpygments.org%2F "http://pygments.org/")高亮显示你的代码块。要使用Pygments，必须在系统上安装Python，安装`pygments.rb` gem并将`highlighter`设置为站点配置文件中的`pygments`。Pygments支持[超过100多种语言](https://link.juejin.cn/?target=http%3A%2F%2Fpygments.org%2Flanguages%2F "http://pygments.org/languages/")

要使用语法高亮显示渲染代码块，请按如下方式包裹代码：

```
{% highlight ruby %}
def foo
  puts 'foo'
end
{% endhighlight %}

```

`highlight`标记的参数（上例中的`ruby`）是语言标识符。要查找要用于要高亮显示的语言的相应标识符，请在[Rouge wiki](https://link.juejin.cn/?target=https%3A%2F%2Fgithub.com%2Fjayferd%2Frouge%2Fwiki%2FList-of-supported-languages-and-lexers "https://github.com/jayferd/rouge/wiki/List-of-supported-languages-and-lexers")或[Pygments的Lexers页面](https://link.juejin.cn/?target=http%3A%2F%2Fpygments.org%2Fdocs%2Flexers%2F "http://pygments.org/docs/lexers/")上查找“短名称”。

> **注意：Jekyll处理代码块中的所有Liquid过滤器**
> 
> 如果你使用的语言包含大括号，则可能需要在代码周围放置`{% raw %}`和`{% endraw %}`标记。

#### 行号

`highlight`的第二个参数是名为`linenos`的可选项。有`linenos`参数则将在高亮显示的代码块中强制显示行号。例如，以下代码块将有每行旁边的行号：

```
{% highlight ruby linenos %}
def foo
  puts 'foo'
end
{% endhighlight %}

```

#### 语法高亮的样式

为了显示高亮，你需要包含高亮显示样式表。有关示例样式表，你可以查看[syntax.css](https://link.juejin.cn/?target=https%3A%2F%2Fgithub.com%2Fmojombo%2Ftpw%2Ftree%2Fmaster%2Fcss%2Fsyntax.css "https://github.com/mojombo/tpw/tree/master/css/syntax.css")。这些与GitHub使用的样式相同，你可以自由地将它们用于你自己的站点。如果使用`linenos`，你可能希望在`syntax.css`中为`.lineno` class添加一个额外的CSS class定义，以区分行号和高亮显示的代码。

链接（Links）
---------

### 链接到页面

要链接到文章，页面，合集项或文件，`link`标记将为你指定的路径生成正确的永久链接URL。例如，如你您使用`link`标记链接到`mypage.html`，即使你更改固定链接样式以包含文件扩展名或省略它，`link`标记形成的URL也始终有效。

使用`link`标记时，你必须包含文件的原始扩展名。这里有些例子：

```
{{ site.baseurl }}{% link _collection/name-of-document.md %}
{{ site.baseurl }}{% link _posts/2016-07-26-name-of-post.md %}
{{ site.baseurl }}{% link news/index.html %}
{{ site.baseurl }}{% link /assets/files/doc.pdf %}

```

您还可以使用`link`标记在Markdown中创建链接，如下所示：

```
[Link to a document]({{ site.baseurl }}{% link _collection/name-of-document.md %})
[Link to a post]({{ site.baseurl }}{% link _posts/2016-07-26-name-of-post.md %})
[Link to a page]({{ site.baseurl }}{% link news/index.html %})
[Link to a file]({{ site.baseurl }}{% link /assets/files/doc.pdf %})

```

（包含`{{ site.baseurl }}`是可选的——这取决于你是否要在页面URL前加上`baseurl`值。）

到文章，页面或合集的路径是定义为相对于根目录（配置文件所在的位置）到文件的路径，而不是从现有页面到另一页面的路径。

例如，假设你在`page_a.md`（存储在`pages/folder1/folder2`中）中创建了一个链接到`page_b.md`（存储在`pages/folder1`中）。你在链接中的路径不会是`../page_b.html`，而是`/pages/folder1/page_b.md`。

如果你不确定路径，请将`{{ page.path }}`添加到页面，它将显示路径。

使用`link`或`post_url`标记的一个主要好处是链接验证。如果该链接不存在，Jekyll将不会构建你的网站。这是一件好事，因为它会提醒你一个错误的链接，以便你可以修复它（而不是允许你构建和部署具有错误链接的站点）。

请注意，你无法向`link`标记添加过滤器。例如，你不能使用Liquid过滤器追加字符串，例如`{% link mypage.html | append: "#section1" %}`。要链接到页面上的部分，你需要使用常规HTML或Markdown链接技术。

### 链接到文章

如果你想在网站上添加指向文章的链接，则`post_url`标记会为你指定的文章生成正确的永久链接网址。

```
{{ site.baseurl }}{% post_url 2010-07-21-name-of-post %}

```

如果你在子目录中放置文章，则需要包含文章的子目录路径：

```
{{ site.baseurl }}{% post_url /subdir/2010-07-21-name-of-post %}

```

使用`post_url`标记时无需包含文件扩展名。

你还可以使用此标记在Markdown中创建指向文章的链接，如下所示：

```
[Name of Link]({{ site.baseurl }}{% post_url 2010-07-21-name-of-post %})

```

  

本文转自 [https://juejin.cn/post/6844903632882630664](https://juejin.cn/post/6844903632882630664)，如有侵权，请联系删除。