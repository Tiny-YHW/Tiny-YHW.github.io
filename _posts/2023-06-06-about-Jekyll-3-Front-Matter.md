---
layout: post
title: Front Matter
permalink: /Front-Matter/
date: 2023-06-06
categories: Jekyll
---


Front Matter
============

Front Matter是Jekyll开始变得非常酷的地方。任何包含[YAML](https://link.juejin.cn/?target=http%3A%2F%2Fyaml.org%2F "http://yaml.org/") front matter块的文件都将由Jekyll作为特殊文件进行处理。Front Matter必须是文件中的第一个事物，并且必须采用在三条虚线之间设置的有效YAML的形式。这是一个基本的例子：

```
---
layout: post
title: Blogging Like a Hacker
---

```

在这些三条虚线之间，你可以设置预定义的变量（参见下面的参考），甚至可以创建自己的自定义变量。这些变量随后可供你使用Liquid标签进行访问，无论是在文件中还是在任何布局中，或者包括所涉及的页面或帖子都依赖于这些变量。

> **警告：UTF-8字符编码警告**
> 
> 如果你使用UTF-8编码，请确保文件中不存在BOM标题字符，否则Jekyll会发生非常非常糟糕的情况。如果你在Windows上运行Jekyll，这尤其重要。

> **重要提示™：Front Matter变量是可选的**
> 
> 如果你想在Front Matter中使用[Liquid标签和变量](https://link.juejin.cn/?target=https%3A%2F%2Fjekyllrb.com%2Fdocs%2Fvariables%2F "https://jekyllrb.com/docs/variables/")，但不需要任何东西，就把它留空！三条虚线之间即使没有任何内容仍然会让Jekyll处理你的文件。（这对CSS和RSS提要等很有用！）

预定义的全局变量
--------

有许多预定义的全局变量，你可以在页面或文章的Front Matter中设置。

| 变量 | 说明 |
| --- | --- |
| `layout` | 如果设置，则指定要使用的布局文件。使用不带文件扩展名的布局文件名。布局文件必须放置在`_layouts`目录中。
*   使用`null`将产生一个不使用布局文件的文件。但是，如果该文件是文章/文档并且具有在[Front Matter默认值](https://link.juejin.cn/?target=)中定义的布局，则这`null`将被覆盖重写。
*   从版本3.5.0开始，无论Front Matter设置如何，对文章/文档中使用`none`将不会使用布局文件生成文件。 然而，在页面中不使用任何内容，都会导致Jekyll尝试使用名为“none”的布局。

 |
| `permalink` | 如果你需要将处理后的博客文章网址设置为网站范围样式以外的内容（默认为`/year/month/day/title.html`），则可以设置此变量并将其用作最终网址。 |
| `published` | 如果你不想在网站生成时显示特定文章，请将这个设置为`false`。 |

> **重要提示™：展示标记为未发布的文章**
> 
> 要预览未发布的页面，只需使用`--unpublished`开关运行`jekyll serve`或`jekyll build`。Jekyll还有一个专门为博客文章量身打造的非常方便的草稿功能。

自定义变量
-----

Front Matter中所有非预定义的变量都会合并到数据中，在转换期间发送到Liquid模板引擎中。例如，如果你设置了标题，则可以在布局中使用该标题来设置页面标题：

```
<!DOCTYPE HTML>
<html>
  <head>
    <title>{{ page.title }}</title>
  </head>
  <body>
    …

```

文章的预定义变量
--------

这些都可以在直接使用。

| 变量 | 说明 |
| --- | --- |
| `date` | 此处的日期会覆盖文章名称中的日期。这可以用来确保文章的正确排序。 日期以`YYYY-MM-DD HH:MM:SS +/-TTTT`格式指定;小时，分钟，秒和时区偏移量是可选的。 |
| `category`  
`categories` | 你可以指定文章所属的一个或多个类别，而不是将文章置于文件夹内。当网站生成后，该文章就会按照设置的这些类别分类。类别（`categories`）可以被指定为YAML列表或空格分隔的字符串。 |
| `tags` | 与类别类似，可以将一个或多个标签添加到帖子中。与类别一样，标签可以被指定为YAML列表或空格分隔的字符串。 |

> **重要提示™：不要重复自己**
> 
> 如果你不想重复写经常使用的Front Matter变量，只需定义它们的默认值，并在必要时（或根本不需要）覆盖它们。这适用于预定义和自定义变量。

写文章
===

Jekyll的一个最好的方面是它是“博客意识”。这到底意味着什么？好吧，简而言之，这意味着博客已经渗透到Jekyll的功能中。如果你撰写文章并在线发布，你可以简单地通过管理计算机上的文本文件夹来发布和维护博客。与配置和维护数据库以及基于Web的CMS系统的麻烦相比，这将是一个值得欢迎的改变！

文章文件夹
-----

正如在目录结构页面上所解释的那样，`_posts`文件夹是你的博客文章存储的位置。 这些文件通常是[Markdown](https://link.juejin.cn/?target=https%3A%2F%2Fdaringfireball.net%2Fprojects%2Fmarkdown%2F "https://daringfireball.net/projects/markdown/")或HTML，但也可以使用安装了对应转换器的其他格式。所有文章都必须包含YAML Front Matter，它们将被从源格式转换为静态网站一部分的HTML页面。

### 创建文章文件

要创建新文章，你只需在`_posts`目录中创建一个文件即可。如何命名文件夹中的文件非常重要。Jekyll需要根据以下格式命名博客文章文件：

```
YEAR-MONTH-DAY-title.MARKUP

```

`YEAR`是四位数字，`MONTH`和`DAY`都是两位数字，`MARKUP`是表示文件中使用的格式的文件扩展名。例如，下面是有效的文件名的例子：

```
2011-12-31-new-years-eve-is-awesome.md
2012-09-12-how-to-write-a-blog.md

```

> **重要提示™：链接到其他文章**
> 
> 使用`post_url`标记链接到其他文章，就不必担心网站固定链接样式发生更改时网址会404。

### 内容格式

所有博客文章必须以[YAML Front Matter](about:blank# "#")开始。之后，这只是决定你喜欢哪种格式的问题。Jekyll支持直接使用[Markdown](https://link.juejin.cn/?target=https%3A%2F%2Fdaringfireball.net%2Fprojects%2Fmarkdown%2F "https://daringfireball.net/projects/markdown/")，并且还有[其他格式的无数扩展](https://link.juejin.cn/?target=https%3A%2F%2Fjekyllrb.com%2Fdocs%2Fplugins%2F%23converters-1 "https://jekyllrb.com/docs/plugins/#converters-1")，包括流行的[Textile](https://link.juejin.cn/?target=http%3A%2F%2Fredcloth.org%2Ftextile "http://redcloth.org/textile")格式。这些格式都有自己的方式来标记文章中的不同类型的内容，因此你应该熟悉这些格式并确定哪一种最适合你的需求。

> **注意：了解字符集**
> 
> 内容处理器可以修改某些字符，使其看起来更好。例如，Redcarpet中的`smart`扩展可将标准ASCII引号字符转换为Unicode字符。为了让浏览器正确显示这些字符，通过在布局的中包含来定义字符集元值。

引用图像和资源
-------

在某些情况下，你可能希望将图片，下载或其他数字资源与文字内容一起包含在内。虽然Markdown和Textile链接到这些资源的语法各不相同，但如何将这些文件存储在网站中是每个人都将面临的问题。

在Jekyll中有很多方法可以包含数字资源。一种常见的解决方案是在项目目录的根目录中创建一个名子类似`assets`的文件夹，其中放置所有图像，文件或其他资源。然后，从任何文章内，它们可以链接到使用该网站的根作为资源引用的路径。同样，这将取决于你的网站（子）域和路径的配置方式，但以下是Markdown中关于如何使用文章中的`absolute_url`过滤器执行此操作的示例。

在文章中包含图片资源：

```
... which is shown in the screenshot below:
![My helpful screenshot]({{ "/assets/screenshot.jpg" | absolute_url }})

```

连接到一个PDF供读者下载：

```
... you can [get the PDF]({{ "/assets/mydoc.pdf" | absolute_url }}) directly.

```

一个典型的文章
-------

Jekyll可以处理你可能与“文章”关联的想法的许多不同迭代，但标准博客样式文章（包括标题，布局，发布日期和类别）可能如下所示：

```
---
layout: post
title:  "Welcome to Jekyll!"
date:   2015-11-17 16:16:01 -0600
categories: jekyll update
---
You’ll find this post in your `_posts` directory. Go ahead and edit it and re-build the site to see your changes. You can rebuild the site in many different ways, but the most common way is to run `bundle exec jekyll serve`, which launches a web server and auto-regenerates your site when a file is updated.

To add new posts, simply add a file in the `_posts` directory that follows the convention `YYYY-MM-DD-name-of-post.ext` and includes the necessary front matter. Take a look at the source for this post to get an idea about how it works.

```

第一个`---`和第二个`---`之间的所有内容都是YAML Front Matter的一部分，第二个`---`之后的所有内容都将使用Markdown进行渲染并显示为“内容”。

显示文章的索引
-------

在一个文件夹中有文章很正常，但是对于一个博客来说是不够的，你还少一个文章列表。通过使用Liquid模板语言及其标签，在另一个页面（或模板中）创建文章索引很容易。以下是如何创建博客文章链接列表的基本示例：

```
<ul>
  {% for post in site.posts %}
    <li>
      <a href="{{ post.url }}">{{ post.title }}</a>
    </li>
  {% endfor %}
</ul>

```

当然，你可以完全控制你显示文章的方式（以及位置），以及如何组织你的网站。 如果你想了解更多信息，你应该阅读更多关于[模板如何与Jekyll合作](https://link.juejin.cn/?target=https%3A%2F%2Fjekyllrb.com%2Fdocs%2Ftemplates%2F "https://jekyllrb.com/docs/templates/")的内容。

请注意，`post`变量只存在于上面的`for`循环中。如果你想访问当前呈现的页面/文章的变量（包含`for`循环的文章/页面的变量），请改用`page`变量。

显示文章类别或标签
---------

嘿，这很整洁，但是如何显示你的一些相互关联的文章？为此，你可以使用[Front Matter中定义的任何变量](https://link.juejin.cn/?target=https%3A%2F%2Fjekyllrb.com%2Fdocs%2Ffrontmatter%2F "https://jekyllrb.com/docs/frontmatter/")。在“一个典型的文章”部分中，你可以看到如何定义类别。只需将类别以yaml列表的形式添加到你的Front Matter中。

既然你的文章有一个或多个类别，你可以让页面或模板显示你指定的类别中的文章。 以下是如何根据特定类别创建文章列表的基本示例。

首先，在`_layouts`目录中创建一个名为`category.html`的新文件——在该文件中至少放置以下内容：

```
---
layout: page
---
{% for post in site.categories[page.category] %}
    <a href="{{ post.url | absolute_url }}">
      {{ post.title }}
    </a>
{% endfor %}

```

接下来，在Jekyll安装的根目录中，创建一个名为`category`的新文件夹，然后为要列出的每个类别创建一个文件。例如，如果你有一个`blog`类别，则至少在新文件夹中创建一个名为`blog.html`的文件。

```
---
layout: category
title: Blog
category: blog
---

```

在文章头部如上的情况下，列表页面可以通过`{baseurl}/category/blog.html`来访问。

尽管类别和标签非常相似，它们都用于对文章进行分组，但它们之间存在一些差异。类别和子类别会创建层次结构，默认情况下会反映在你网站的目录结构中。 具有以下头部的文章

```
---
layout: post
title: A Trip
category: [ blog, travel ]
---

```

将可以通过`{baseurl}/blog/travel/year/month/day/A-Trip.html`访问。而另一方面，一个有标签的文章：

```
---
layout: post
title: A Trip
tags: [ blog, travel ]
---

```

将保存为`{baseurl}/year/month/day/A-Trip.html`。你可以按照上述与类别的相同方式创建`{baseurl}/tag/blog.html`和`{baseurl}/tag/travel.html`。

虽然此示例是使用标记和类别完成的，但你也可以轻松地将你的列表扩展为使用扩展创建的任何其他变量进行过滤。

文章摘录
----

每篇文章都会自动将第一个文本块从内容的开始处移至`excerpt_separator`的第一处，并将其设置在文章的数据散列中。以上面的文章索引为例。也许你想通过添加每篇文章的第一段来引入关于文章内容的一点提示：

```
<ul>
  {% for post in site.posts %}
    <li>
      <a href="{{ post.url }}">{{ post.title }}</a>
      {{ post.excerpt }}
    </li>
  {% endfor %}
</ul>

```

因为Jekyll抓取了文章第一段，并且将抓取的内容放在了`p`标签中，所以你不需要在`p`标签中包含摘录。如果你不想将抓取的摘录内容放在`p`标签中，还可以使用下面方式删除这些标签：

```
{{ post.excerpt | remove: '<p>' | remove: '</p>' }}

```

如果你不喜欢自动抓取的文章摘录，可以通过向文章的YAML Front Matter中的`excerpt`赋值来显式的覆盖它。或者，你可以选择在文章的YAML Front Matter容中定义一个自定义的`excerpt_separator`：

```
---
excerpt_separator: <!--more-->
---
Excerpt
<!--more-->
Out-of-excerpt

```

你也可以在你的`_config.yml`配置文件中全局设置`excerpt_separator`。

将`excerpt_separator`设置为`""`，表示完全禁用摘录。

此外，与`Liquid`标签生成的任何输出一样，你可以通过传递`| strip_html`过滤器来删除输出中的所有html标签。如果你希望在文章头部中输出文章摘要作为`meta="description"`标签，或者在其他任何有html标签并且内容不符合要求的地方，这将特别有用。

高亮代码语法
------

Jekyll还内置了对使用Pygments或Rouge代码片段的语法突出显示的支持，所以在任何文章中都包含代码片段很容易。只需使用专用Liquid标签，如下所示：

```
{% highlight ruby %}
def show
  @widget = Widget(params[:id])
  respond_to do |format|
    format.html # show.html.erb
    format.json { render json: @widget }
  end
end
{% endhighlight %}

```

输出结果如下所示：

```
def show
  @widget = Widget(params[:id])
  respond_to do |format|
    format.html # show.html.erb
    format.json { render json: @widget }
  end
end

```

> **重要提示™：显式行号**
> 
> 你可以通过在开头高亮标记的末尾添加单词`linenos`来使代码片段包含行号，例如：`{% highlight ruby linenos %}`。

这些基本知识应该足以让你开始写你的第一篇文章。当你准备好深入了解其他可能的情况时，你可能会对[自定义文章的永久链接](https://link.juejin.cn/?target=https%3A%2F%2Fjekyllrb.com%2Fdocs%2Fpermalinks%2F "https://jekyllrb.com/docs/permalinks/")或在自己的文章和你网站上的其他位置使用[自定义变量](https://link.juejin.cn/?target=https%3A%2F%2Fjekyllrb.com%2Fdocs%2Fvariables%2F "https://jekyllrb.com/docs/variables/")感兴趣。

  

本文转自 [https://juejin.cn/post/6844903629682376711](https://juejin.cn/post/6844903629682376711)，如有侵权，请联系删除。