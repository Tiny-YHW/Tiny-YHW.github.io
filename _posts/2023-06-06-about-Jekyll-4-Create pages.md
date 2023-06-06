---
layout: post
title: Jekyll 创建页面、静态文件、变量
permalink: /Jekyll-Create-pages/
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

草稿
==

草稿是文件名中没有日期的文章。它们是你仍在编辑中的、不想发布的文章。要启动并运行草稿，请在站点根目录中创建一个`_drafts`文件夹（如[站点结构](https://juejin.cn/post/6844903623567081486#heading-6 "https://juejin.cn/post/6844903623567081486#heading-6")部分中所述）并创建第一个草稿：

```
|-- _drafts/
|   |-- a-draft-post.md

```

要在你的网站中预览草稿，只需使用`--drafts`开关运行`jekyll serve`或`jekyll build`。每个草稿将被自动设置修改时间，因此你看到的是按照最近编辑时间的顺序显示的草稿。

创建页面
====

除了[撰写文章](https://juejin.cn/post/6844903629682376711#heading-4 "https://juejin.cn/post/6844903629682376711#heading-4")外，你还可能希望将静态页面（不是基于日期的内容）添加到Jekyll站点。通过利用Jekyll复制文件和目录的方式，这将很容易实现。

首页
--

几乎所有你遇到的Web服务器配置都会在网站的根目录中查找名为`index.html`的HTML文件（按惯例），并将其显示为主页。除你使用的Web服务器被配置为查找某个不同的文件名作为默认文件名，否则该文件将是你的Jekyll生成站点的主页。

> **重要提示™：对你的首页使用布局**
> 
> 你网站上的所有HTML文件都可以使用布局和/或引用，包括主页。常见的内容，如页眉和页脚，最好是抽取到布局中。

其他网页的位置
-------

你为网页添加HTML或[Markdown](https://link.juejin.cn/?target=https%3A%2F%2Fdaringfireball.net%2Fprojects%2Fmarkdown%2F "https://daringfireball.net/projects/markdown/")文件的方式取决于你希望网页的工作方式。主要有两种创建页面的方法：

*   在网站的根目录中放置每个页面，并给HTML或Markdown文件命名。
*   将页面放在文件夹和子文件夹中，并将其命名为任何你希望的。

两种方法都可以正常工作（并且可以相互结合使用），唯一的区别就是生成的URL。默认情况下，页面在`_site`中保留与源目录中相同的文件夹结构。

### 为HTML文件命名

添加页面的最简单方法就是在根目录中添加一个HTML文件，其中包含要创建的页面的合适名称。对于包含主页，关于页面和联系页面的网站，以下是根目录和关联网址的结构：

```
.
|-- _config.yml
|-- _includes/
|-- _layouts/
|-- _posts/
|-- _site/
|-- about.html    # => http://example.com/about.html
|-- index.html    # => http://example.com/
|-- other.md      # => http://example.com/other.html
└── contact.html  # => http://example.com/contact.html

```

如果你有很多页面，则可以将这些页面放到子文件夹中。当你的网站建立时，用于在我们项目的源代码中对你的网页进行分组的相同子文件夹将存在于\_site文件夹中。

将子文件夹中的页面构建展示到根目录中
------------------

如果你的页面被放到你的源文件夹中的子文件夹中，并且想要将它们构建展示在根目录中，则必须直接在页面的Front Matter中添加永久属性，如下所示：

```
---
title: My page
permalink: mypageurl.html
---

```

### 命名文件夹包含索引HTML文件

如果你不希望文件扩展名（.html）出现在你的页面网址中（文件扩展名是默认存在的），你可以选择具有尾部斜线而不是文件扩展名的永久链接样式。

请注意，如果你希望在没有Jekyll预览服务器的情况下离线查看你的网站，你的浏览器将需要文件扩展名来显示页面，并且所有资源都需要是相对链接，这样这些链接才可以在没有服务器基础的情况下运行。

静态文件
====

除了可渲染和可转换内容之外，我们还有**静态文件**。

静态文件是一个不包含任何YAML Front Matter的文件，包括了图像，PDF和其他不被渲染的内容。

它们可以通过`site.static_files`在Liquid中访问，并包含以下元数据：

| 变量 | 说明 |
| --- | --- |
| `file.path` | 文件的相对路径，例如：`/assets/img/image.jpg` |
| `file.modified_time` | 该文件最后修改的时间, 例如：`2016-04-01 16:35:26 +0200` |
| `file.name` | 文件的字符串名称, 例如：`image.jpg for image.jpg` |
| `file.basename` | 文件的字符串基本名称, 例如：`image.jpg`的`image` |
| `file.extname` | 文件的扩展名, 例如：`image.jpg`的`.jpg` |

请注意，在上表中，`file`可以是任何东西。它只是一个在你自己的逻辑中使用的任意设置的变量（例如在for循环中）。它不是网站或页面的全局变量。

给静态文件添加Front Matter
-------------------

尽管无法直接将Front Matter添加到静态文件，但可以通过配置文件中的默认属性设置Front Matter。当Jekyll构建网站时，它将使用你设置的Front Matter。

这是一个例子：

在你的`_config.yml`文件中，将下列值添加到`defaults`属性中：

```
defaults:
  - scope:
      path: "assets/img"
    values:
      image: true

```

这假定你的Jekyll站点的文件夹路径为`assets/img`，你可以在其中存储图像（静态文件）。当Jekyll构建网站时，它会将每个图像视为含有Front Matter的值：`image: true`。

假设你想要列出`assets/img`中包含的所有图像资源。你可以使用这个for循环来查看`static_files`对象并获得所有具有这个Front Matter属性的静态文件：

```
{% assign image_files = site.static_files | where: "image", true %}
{% for myimage in image_files %}
  {{ myimage.path }}
{% endfor %}

```

当你构建你的站点时，输出将列出符合此前提条件的每个文件的路径。

变量
==

Jekyll遍历你的网站寻找要处理的文件。任何带有[YAML Front Matter](https://juejin.cn/post/6844903629682376711#heading-0 "https://juejin.cn/post/6844903629682376711#heading-0")的文件都将受到处理。对于这些文件中的每一个，Jekyll都会通过[Liquid模板系统](https://link.juejin.cn/?target=https%3A%2F%2Fgithub.com%2FShopify%2Fliquid%2Fwiki "https://github.com/Shopify/liquid/wiki")提供各种数据。以下是可用数据的参考。

全局变量
----

| 变量 | 说明 |
| --- | --- |
| `site` | 来自`_config.yml`的全站信息+配置设置。详情请参阅下文。 |
| `page` | 页面特有信息+[YAML Front Matter](https://juejin.cn/post/6844903629682376711#heading-0 "https://juejin.cn/post/6844903629682376711#heading-0")。通过YAML Front Matter设置的自定义变量也会在此处提供。详情请参阅下文。 |
| `layout` | 布局特有信息+[YAML Front Matter](https://juejin.cn/post/6844903629682376711#heading-0 "https://juejin.cn/post/6844903629682376711#heading-0")。通过YAML Front Matter设置的自定义变量也会在此处提供。详情请参阅下文。 |
| `content` | 在布局文件中，包装好的文章或页面的渲染内容。 文章或页面文件中没有这个变量的定义。 |
| `paginator` | 当`paginate`配置选项被设置时，这个变量才可以使用。有关详细信息，请参阅[分页](https://link.juejin.cn/?target=https%3A%2F%2Fjekyllrb.com%2Fdocs%2Fpagination%2F "https://jekyllrb.com/docs/pagination/")。 |

`site`变量
--------

| 变量 | 说明 |
| --- | --- |
| `site.time` | 当前时间（当你运行jekyll命令时的时间）。 |
| `site.pages` | 所有页面的列表。 |
| `site.posts` | 所有文章的按时间顺序的倒序列表。 |
| `site.related_posts` | 如果正在处理的是文章，则其中最多包含10个相关文章的列表。默认情况下，这些是最近发布的十个文章。对于高质量但计算结果较慢的情况，请使用`--lsi`（潜在语义索引）选项运行`jekyll`命令。另外请注意，GitHub Pages在生成网站时不支持`lsi`选项。 |
| `site.static_files` | 所有静态文件的列表（即未由Jekyll转换器或Liquid渲染器处理的文件）。每个文件都有五个属性：`path`，`modified_time`，`name`，`basename`和`extname`。 |
| `site.html_pages` | `site.pages`的一个子集，列出以`.html`结尾的内容。 |
| `site.html_files` | `site.static_files`的一个子集，列出以`.html`结尾的内容。 |
| `site.collections` | 一个所有合集的列表 |
| `site.data` | 包含从位于`_data`目录中的YAML文件加载的数据的列表。 |
| `site.documents` | 每个合集中的所有文档的列表。 |
| `site.categories.CATEGORY` | `CATEGORY`类别中的所有文章的列表。 |
| `site.tags.TAG` | 标签是`TAG`的所有文章的列表 |
| `site.url` | 在`_config.yml`中配置的网站的网址。例如，如果你的配置文件中包含`url: http://mysite.com`，则可以在Liquid中以`site.url`的形式访问它。对于开发环境，有[一个例外](https://link.juejin.cn/?target=https%3A%2F%2Fjekyllrb.com%2Fnews%2F%233-siteurl-is-set-by-the-development-server "https://jekyllrb.com/news/#3-siteurl-is-set-by-the-development-server")，如果你运行`jekyll serve`，在开发环境中`site.url`将被设置为与`host`、`port`和`SSL`相关选项的值。 默认为`url: http://localhost:4000`。 |
| `site.[CONFIGURATION_DATA]` | 所有通过命令行设置的变量和你的`_config.yml`都可以通过`site`变量获得。例如，如果你在你的配置文件中有`foo: bar`，那么它可以在Liquid中通过`site.foo`访问。Jekyll不会在`watch`模式下解析对`_config.yml`的更改，你必须重新启动Jekyll以查看对变量的更改。 |

页面变量
----

| 变量 | 说明 |
| --- | --- |
| `page.content` | 页面的内容，渲染或不渲染取决于Liquid正在处理什么以及页面是什么。 |
| `page.title` | 页面的标题 |
| `page.excerpt` | 未渲染的文档摘录 |
| `page.url` | 只有前导斜杠，但不含域名的文章地址，例如：`/2008/12/14/my-post.html` |
| `page.date` | 文章指定的日期。这可以通过指定`YYYY-MM-DD HH:MM:SS`（假设UTC）或`YYYY-MM-DD HH:MM:SS +/-TTTT`（ 使用与UTC的偏移来指定时区，例如`2008-12-14 10:30:00 +0900`）。 |
| `page.id` | Collection或Post中文档的唯一标识符（在RSS提要中有用）。例如 `/2008/12/14/my-post` `/my-collection/my-document` |
| `page.categories` | 此文章所属类别的列表。类别来自`_posts`目录上方的目录结构。例如，`/work/code/_posts/2008-12-24-closures.md`中的文章可能会将此字段设置为\['work'，'code'\]。 这些也可以在[YAML Front Matter](https://juejin.cn/post/6844903629682376711#heading-0 "https://juejin.cn/post/6844903629682376711#heading-0")中指定。 |
| `page.tags` | 此文章所属的标签列表。这些可以在[YAML Front Matter](https://juejin.cn/post/6844903629682376711#heading-0 "https://juejin.cn/post/6844903629682376711#heading-0")中指定。 |
| `page.path` | 原始文章或页面的路径。用法示例：链接回GitHub上的页面或文章的源代码。这可以在[YAML Front Matter](https://juejin.cn/post/6844903629682376711#heading-0 "https://juejin.cn/post/6844903629682376711#heading-0")中重写。 |
| `page.next` | 下一篇文章相对于`site.posts`中当前文章的位置。最后一个文章会返回`nil`。 |
| `page.previous` | 上一篇文章相对于`site.posts`中当前文章的位置。最后一个文章会返回`nil`。 |

> **重要提示™：使用自定义的Front Matter**
> 
> 你指定的任何自定义Front Matter将在`page`下提供。例如，如果你在页面的Front Matter中指定了`custom_css: true`，则该值将作为`page.custom_css`提供。
> 
> 如果你在布局中指定Front Matter，请通过`layout`访问。例如，如果在布局的Front Matter中指定`class: full_page`，则该值将在布局及其父项中作为`layout.class`提供。

分页
--

| 变量 | 说明 |
| --- | --- |
| `paginator.per_page` | 每页文章数。 |
| `paginator.posts` | 该页面可用的文章。 |
| `paginator.total_posts` | 文章总数。 |
| `paginator.total_pages` | 总页数。 |
| `paginator.page` | 当前页面的编号。 |
| `paginator.previous_page` | 上一页的编号。 |
| `paginator.previous_page_path` | 上一页的路径。 |
| `paginator.next_page` | 下一页的编号。 |
| `paginator.next_page_path` | 下一页的路径。 |

> **注意：分页变量可用性**
> 
> 这些仅在索引文件中可用，但它们可以位于子目录中，例如`/blog/index.html`。

  

本文转自 [https://juejin.cn/post/6844903629934084109](https://juejin.cn/post/6844903629934084109)，如有侵权，请联系删除。