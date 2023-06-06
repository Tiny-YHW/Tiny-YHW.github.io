---
layout: post
title: Jekyll 配置
permalink: /Jekyll-configuration/
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

配置
==

Jekyll允许你用任何你可以想象的方式调试你的网站，这要感谢这些强大而灵活的配置选项。这些选项可以在放置在站点根目录中的`_config.yml`文件中指定，也可以在终端中指定为jekyll的flags。

配置设置
----

### 全局配置

下表列出了Jekyll的可用设置，以及控制它们的各种`options`（在配置文件中指定）和`flags`（在命令行中指定）。

| 设置 | `options` | `flags` |
| --- | --- | --- |
| **网站源文件**  
改变Jekyll读取文件的文件夹 | `source: DIR` | `-s, --source DIR` |
| **网站生成位置**  
改变Jekyll写入文件的文件夹 | `destination: DIR` | `d, --destination DIR` |
| **安全**  
禁用[自定义插件，并忽略符号链接](https://link.juejin.cn/?target=https%3A%2F%2Fjekyllrb.com%2Fdocs%2Fplugins%2F "https://jekyllrb.com/docs/plugins/")。 | `safe: BOOL` | `--safe` |
| **排除**  
在转换过程中排除目录和/或文件。这些排除的文件必须在网站的源目录之内，不能在源目录之外。 | `exclude: [DIR, FILE, ...]` |  |
| **包含**  
在转换过程中强制包含目录和/或文件。 `.htaccess`是一个很好的例子，因为默认情况下dotfiles是被排除的。 | `include: [DIR, FILE, ...]` |  |
| **时区**  
设置网站生成的时区。这设置了`TZ`环境变量，Ruby用它来处理时间和日期的创建和操作。[IANA时区数据库](https://link.juejin.cn/?target=https%3A%2F%2Fen.wikipedia.org%2Fwiki%2FTz_database "https://en.wikipedia.org/wiki/Tz_database")中的所有条目均有效，例如，`America/New_York`。所有可用值都可以在这个列表中找到。在本地机器上运行时，默认时区是你的操作系统设置的时区。但是，当在远程主机/服务器上时，默认时区取决于服务器的设置或位置。 | `timezone: TIMEZONE` |  |
| **编码格式**  
按名称设置文件的编码格式（仅适用于Ruby 1.9或更高版本）。 缺省值是从2.0.0开始的`utf-8`，在2.0.0之前为`nil`，这将使用默认的`ASCII-8BIT`。可用的编码可以通过命令`ruby -e 'puts Encoding::list.join("\n")'`展示。 | `encoding: ENCODING` |  |
| **默认**  
为[YAML Front Matter](https://link.juejin.cn/?target=https%3A%2F%2Fjekyllrb.com%2Fdocs%2Ffrontmatter%2F "https://jekyllrb.com/docs/frontmatter/")变量设置默认值。 | 见[下文](https://link.juejin.cn/?target=https%3A%2F%2Fjekyllrb.com%2Fdocs%2Fconfiguration%2F%23front-matter-defaults "https://jekyllrb.com/docs/configuration/#front-matter-defaults") |  |

> **警告：目标文件夹在网站构建的时候会被清空**
> 
> 默认情况下，当网站构建的时候，`<destination>`中的内容会被自动的清空。不是被你的网站构建时所创建的文件和文件夹都会被删除。可以在<keep\_files>配置指令中指定你希望保留在中的文件和文件夹。
> 
> 不要设置为重要本地路径；相反，应该将其用作暂存区域并将文件从那里复制到你的Web服务器。

### 构建（编译）配置选项

| 设置 | `options` | `flags` |
| --- | --- | --- |
| **生成更新**  
修改文件时启用站点的自动生成更新。 |  | `-w, --[no-]watch` |
| **构造**  
指定配置文件而不是使用默认的`_config.yml`。后设置的文件中的设置会覆盖之前文件中的设置。 |  | `--config FILE1[,FILE2,...]` |
| **草稿**  
处理并渲染草稿文章。 | `show_drafts: BOOL` | `--drafts` |
| **环境**  
使用指定的环境构建。 |  | `JEKYLL_ENV=production` |
| **未来**  
发布尚未到达日期的文章或文集。 | `future: BOOL` | `--future` |
| **未公开**  
渲染未公开的文章。 | `unpublished: BOOL` | `--unpublished` |
| **LSI**  
生成相关文章的索引。需要[classifier-reborn](https://link.juejin.cn/?target=http%3A%2F%2Fwww.classifier-reborn.com%2F "http://www.classifier-reborn.com/")插件。 | `lsi: BOOL` | `--lsi` |
| **限制文章数量**  
限制解析和发布文章的数量。 | `limit_posts: NUM` | `--limit_posts NUM` |
| **强制轮询**  
强制使用轮询检测更新 |  | `--force_polling` |
| **输出详情**  
打印详细的输出 |  | `-V, --verbose` |
| **静默输出**  
在构建过程中让Jekyll保持正常输出 |  | `-q, --quiet` |
| **增量构建**  
启用增量构建的试验功能。增量构建仅重新构建已更改的文章和页面，从而显着改善大型网站的性能，但也可能在某些情况下破坏网站生成。 | `incremental: BOOL` | `-I, --incremental` |
| **Liquid分析**  
生成Liquid渲染配置文件以帮助你识别性能瓶颈 | `profile: BOOL` | `--profile` |
| **严格格式模式**  
如果页面前端存在YAML语法错误，则会导致构建失败。 | `strict_front_matter: BOOL` | `--strict_front_matter` |

服务命令选项
------

除了以下选项之外，`serve`子命令还可以接受`build`子命令的所有选项，然后将这些选项应用于在站点提供之前发生的站点构建。

| 设置 | `options` | `flags` |
| --- | --- | --- |
| **本地服务器端口**  
监听给定的端口号 | `port: PORT` | `--port PORT` |
| **本地服务器主机名**  
监听给定的主机名 | `host: HOSTNAME` | `--host HOSTNAME` |
| **基本地址**  
从给定的基本网址提供网站 | `baseurl: URL` | `--baseurl URL` |
| **分离**  
从终端分离服务器 | `detach: BOOL` | `-B, --detach` |
| **跳过最初的网站构建**  
跳过服务器启动之前发生的初始站点构建。 |  | `--skip-initial-build` |
| **X.509 (SSL) 私钥**  
SSL私钥 |  | `--ssl-key` |
| **X.509 (SSL) 证书**  
SSL公共证书 |  | `--ssl-cert` |

> **警告：不要在配置文件中使用tab**
> 
> 这将导致解析错误，或者Jekyll将恢复使用默认设置。请改用空格。

自定义WEBrick标题
------------

你可以通过添加它们到`_config.yml`来为你的网站提供自定义标头

```
# File: _config.yml
webrick:
  headers:
    My-Header: My-Value
    My-Other-Header: My-Other-Value

```

### 默认

我们默认提供Content-Type和Cache-Control响应头文件：一个动态为了指定被服务的数据的性质，另一个静态为了禁用缓存。所以当你处于开发模式时，你不必与Chrome的缓存作斗争。

在构建时指定一个Jekyll环境
----------------

在`build`（或`serve`）参数中，你可以指定Jekyll环境和值。然后，`build`将在你的内容中的所有条件语句中应用此值。

例如，假设你在代码中设置了这个条件语句：

```
{% if jekyll.environment == "production" %}
   {% include disqus.html %}
{% endif %}

```

当你构建Jekyll站点时，除非你在`build`命令中指定`production`环境，否则`if`语句内的内容将不会运行，如下所示：

```
JEKYLL_ENV=production jekyll build

```

指定环境值可让你仅在特定环境中使某些内容可用。

`JEKYLL_ENV`的默认值是`development`。因此，如果你从构建参数中省略`JEKYLL_ENV`，则会使用默认值为`JEKYLL_ENV=development`。那么`{% if jekyll.environment == "development" %}`标签中的所有内容都会自动出现在构建中。

构建环境的值可以是你想要的任何值（不只是`development`或`production`）。你可能希望在开发环境中隐藏一些元素，比如说Disqus评论表单或Google Analytics。相反，你也可能想在开发环境中展示“在GitHub中编辑我”的按钮，但不想将其展示在生产环境中。

通过在build命令中指定选项，可避免在从一个环境转换到另一个环境时必须更改配置文件中的值。

Front Matter defaults
---------------------

使用[YAML Front Matter](https://link.juejin.cn/?target=https%3A%2F%2Fjekyllrb.com%2Fdocs%2Ffrontmatter%2F "https://jekyllrb.com/docs/frontmatter/")是使你可以在网站的页面和文章中指定配置的一种方式。设置默认布局或自定义标题，或为文章指定更精确的日期/时间等都可以添加到你的页面或文章中。

很多时候，你会发现你重复了很多配置选项。比如在每个文件中设置相同的布局，将相同的一个或多个类别添加到文章等。你甚至可以添加自定义变量，如作者姓名，这些可能与博客上大多数文章中的相同。

Jekyll提供了一种在网站配置中设置这些默认值的方法，而不是每次创建新文章或页面时重复此配置。为此，你可以使用项目根目录中的`_config.yml`文件中的`defaults`指定站点范围的默认值。

`defaults`包含一个由`scope/values`对组成的数组，用于定义应为特定文件路径设置哪些默认值，以及可选的文件类型。

假设你想要将默认布局添加到网站中的所有页面和文章中。你可以将它添加到你的`_config.yml`文件中：

```
defaults:
  -
    scope:
      path: "" # 这里的空字符串表示项目中的所有文件
    values:
      layout: "default"

```

> **注意：请停止并重新运行`jekyll serve`命令。**
> 
> `_config.yml`主要配置文件会在执行时读取一次全局配置和变量定义。在下次执行之前，不会加载在自动生成更新期间对`_config.yml`所做的更改。
> 
> 注意，自动生成更新过程中会对[Data Files](https://link.juejin.cn/?target=https%3A%2F%2Fjekyllrb.com%2Fdocs%2Fdatafiles "https://jekyllrb.com/docs/datafiles")重新加载。

在这里，我们将`values`设定到`scope`路径中存在的所有文件。由于路径设置为空字符串，因此它将应用于项目中的**所有文件**。你可能不希望在项目中的每个文件上设置同样的布局——比如css文件，那么你还可以在`scope`下指定一个`type`。

```
defaults:
  -
    scope:
      path: "" # 这里的空字符串表示项目中的所有文件
      type: "posts" # previously `post` in Jekyll 2.2.
    values:
      layout: "default"

```

现在，只会为类型为`posts`的文件设置布局。你可以使用的类型有`pages`，`posts`，`drafts`或你网站中的任何合集。虽然`type`是可选的，但你在创建一个`scope/values`对时必须为`path`指定一个值。

如前所述，你可以将多个`scope/values`对设置为`defaults`。

```
defaults:
  -
    scope:
      path: ""
      type: "pages"
    values:
      layout: "my-site"
  -
    scope:
      path: "projects"
      type: "pages" # previously `page` in Jekyll 2.2.
    values:
      layout: "project" # 覆盖之前的默认布局
      author: "Mr. Hyde"

```

使用这些默认值，所有页面都将使用`my-site`布局。存在于`projects/`文件夹中的所有html文件（如果存在）都将使用`project`布局，这些文件还将具有设置为`Mr. Hyde`的`page.author` [liquid variable](https://link.juejin.cn/?target=https%3A%2F%2Fjekyllrb.com%2Fdocs%2Fvariables%2F "https://jekyllrb.com/docs/variables/")。

```
collections:
  my_collection:
    output: true

defaults:
  -
    scope:
      path: ""
      type: "my_collection" # a collection in your site, in plural form
    values:
      layout: "default"

```

在这个例子中，名称为`my_collection`的合集中的`layout`被设置为`default`。

### Glob patterns in Front Matter defaults

当匹配默认值时，也可以使用glob模式（当前仅限于包含`*`的模式）。例如，可以为`section`文件夹的任何子文件夹中的每个`special-page.html`设置特定的布局。`[3.7.0]`

```
collections:
  my_collection:
    output: true

defaults:
  -
    scope:
      path: "section/*/special-page.html"
    values:
      layout: "specific-layout"

```

> **警告：Globbing and Performance**
> 
> 请注意，已知使用glob模式会对性能产生负面影响，目前尚未优化，尤其是在Windows上。使用glob模式将按照关联的合集目录的多少增加构建时间。

### 优先权

Jekyll将应用你在`_config.yml`文件的`defaults`部分中指定的所有配置设置。但是，你可以选择通过为`scope`指定更具体的`path`来覆盖其他`scope/values`对中的设置。

你可以在上面的倒数第三个例子中看到。首先，我们将默认页面布局设置为`my-site`。然后，使用更具体的路径，我们将`projects/`路径中的页面的默认布局设置为`project`。这可以通过你在页面或后置事项中设置的任何值来完成。

最后，如果你通过向`_config.yml`文件添加默认部分来在网站配置中设置默认值，则可以通过文章或页面文件中的这些设置进行覆盖。你需要做的就是在文章或页面front matter中指定设置。例如：

```
# In _config.yml
...
defaults:
  -
    scope:
      path: "projects"
      type: "pages"
    values:
      layout: "project"
      author: "Mr. Hyde"
      category: "project"
...
# In projects/foo_project.md
---
author: "John Smith"
layout: "foobar"
---
The post text goes here...

```

`projects/foo_project.md`布局将被设置为`foobar`而不是`project`，并且在构建站点时将`author`设置为`John Smith`而不是`Mr. Hyde`。

默认选项
----

Jekyll默认运行下列配置选项。可以在配置文件或命令行中明确指定来替换对应的这些选项的设置。

> **警告：有两个不支持的`kramdown`选项**
> 
> 请注意，在Jekyll中，`remove_block_html_tags`和`remove_span_html_tags`目前都不受支持，因为它们不包含在kramdown HTML转换器中。

```
# Where things are
source:          .
destination:     ./_site
collections_dir: .
plugins_dir:     _plugins
layouts_dir:     _layouts
data_dir:        _data
includes_dir:    _includes
collections:
  posts:
    output:   true

# Handling Reading
safe:                false
include:             [".htaccess"]
exclude:             ["Gemfile", "Gemfile.lock", "node_modules", "vendor/bundle/", "vendor/cache/", "vendor/gems/", "vendor/ruby/"]
keep_files:          [".git", ".svn"]
encoding:            "utf-8"
markdown_ext:        "markdown,mkdown,mkdn,mkd,md"
strict_front_matter: false

# Filtering Content
show_drafts: null
limit_posts: 0
future:      false
unpublished: false

# Plugins
whitelist: []
plugins:   []

# Conversion
markdown:    kramdown
highlighter: rouge
lsi:         false
excerpt_separator: "\n\n"
incremental: false

# Serving
detach:  false
port:    4000
host:    127.0.0.1
baseurl: "" # does not include hostname
show_dir_listing: false

# Outputting
permalink:     date
paginate_path: /page:num
timezone:      null

quiet:    false
verbose:  false
defaults: []

liquid:
  error_mode:       warn
  strict_filters:   false
  strict_variables: false

# Markdown Processors
rdiscount:
  extensions: []

redcarpet:
  extensions: []

kramdown:
  auto_ids:      true
  entity_output: as_char
  toc_levels:    1..6
  smart_quotes:  lsquo,rsquo,ldquo,rdquo
  input:         GFM
  hard_wrap:     false
  footnote_nr:   1
  show_warnings: false

```

Liquid选项
--------

Liquid对错误的响应可以通过设置`error_mode`进行配置。选项是

*   `lax` — 忽略所有错误。
*   `warn` — 在控制台中输出每一个错误的警告。
*   `strict` — 遇到错误打印并停止构建。

你还可以配置Liquid的渲染器，通过分别将`strict_variables`和/或`strict_filters`设置为`true`来捕获未分配的变量和不存在的过滤器。**`[3.8.0]`**

请注意，尽管`error_mode`配置了Liquid的解析器，但`strict_variables`和`strict_filters`选项配置了Liquid的渲染器，因此是互不干扰的。

Markdown选项
----------

Jekyll支持的各种Markdown渲染器有时会提供额外的选项。

### Redcarpet

可以通过提供`extensions`子设置来配置Redcarpet，其值应该是一个字符串数组。每个字符串都应该是`Redcarpet::Markdown`类的扩展名之一;如果存在于数组中，它会将相应的扩展名设置为`true`。

Jekyll处理两个特殊的Redcarpet扩展：

*   `no_fenced_code_blocks` —— 默认情况下，Jekyll将`fenced_code_blocks`扩展名（用于将具有\`\`\`或三个反引号的代码块）设置为`true`，可能是因为GitHub急于采用它们开始使它们成为不可避免的。与Jekyll一起使用时，Redcarpet的正常`fenced_code_blocks`扩展是惰性的; 相反，你可以使用此反向版本的扩展来禁用代码块。

请注意，你也可以在第一个分隔符之后指定一种突出显示的语言：

```
    ```ruby
    # ...ruby code
    ```

```

同时启用代码块和荧光笔，这将静态突出显示代码;如果没有任何语法高亮显示，它会向`<code>`元素添加`class="LANGUAGE"`属性，该元素可用作各种JavaScript代码高亮显示库的提示。

*   `smart` —— 这个伪扩展打开SmartyPants，它将直引号转换为卷曲引号和连字符运行到em（`---`）和en（`--`）破折号。

所有其他扩展名保留了来自Redcarpet的通常名称，并且在Jekyll中不能指定除`smart`之外的渲染器选项。[可用的扩展名列表可以在Redcarpet README文件中找到](https://link.juejin.cn/?target=https%3A%2F%2Fgithub.com%2Fvmg%2Fredcarpet%2Fblob%2Fv3.2.2%2FREADME.markdown%23and-its-like-really-simple-to-use "https://github.com/vmg/redcarpet/blob/v3.2.2/README.markdown#and-its-like-really-simple-to-use")。确保你正在查看适合版本的Redcarpet的README：Jekyll目前使用v3.2.x. 最常用的扩展名是：

*   `tables`
*   `no_intra_emphasis`
*   `autolink`

### 自定义Markdown处理器

如果你有兴趣创建自定义Markdown处理器，那么你很幸运！在`Jekyll::Converters::Markdown`命名空间中创建一个新类：

```
class Jekyll::Converters::Markdown::MyCustomProcessor
  def initialize(config)
    require 'funky_markdown'
    @config = config
  rescue LoadError
    STDERR.puts 'You are missing a library required for Markdown. Please run:'
    STDERR.puts '  $ [sudo] gem install funky_markdown'
    raise FatalException.new("Missing dependency: funky_markdown")
  end

  def convert(content)
    ::FunkyMarkdown.new(content).convert
  end
end

```

一旦你创建了你的类，并且正确地将它设置为`_plugins`文件夹中的一个插件或一个gem，请在`_config.yml`中指定它：

```
markdown: MyCustomProcessor

```

Incremental Regeneration
------------------------

> **警告：Incremental regeneration仍是一个实验性的功能**
> 
> 尽管Incremental regeneration将适用于最常见的情况，但它在任何情况下都有可能无法正常工作。请谨慎使用该功能，并通过在[GitHub上打开问题](https://link.juejin.cn/?target=https%3A%2F%2Fgithub.com%2Fjekyll%2Fjekyll%2Fissues%2Fnew "https://github.com/jekyll/jekyll/issues/new")来报告以下未列出的任何问题。

Incremental regeneration有助于缩短构建时间，只生成自上一次构建后更新的文档和页面。它通过跟踪文件修改时间和`.jekyll-metadata`文件中的文档间依赖关系来实现这一点。

在当前的实现下，Incremental regeneration只会生成文档或页面（如果它或其某个依赖项被修改）。目前，跟踪的依赖类型有引用（使用`{% include %}`标记）和布局。这意味着对其他文档的简单引用（例如，在文章列表页面上迭代 `site.posts`的常见情况）将不会被检测为依赖项。

为了弥补这些不足之处，在文档的前端添加`regenerate: true`将迫使Jekyll重新生成它，无论它是否已被修改。请注意，这只会生成指定的文档;对其他文档的内容的引用将不起作用，因为它们不会被重新渲染。

可以通过命令行中的`--incremental`标志（简称`-I`）或通过在配置文件中设置`incremental: true`来启用Incremental regeneration。

  

本文转自 [https://juejin.cn/post/6844903629246169096](https://juejin.cn/post/6844903629246169096)，如有侵权，请联系删除。