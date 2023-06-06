---
layout: post
title: 简介、快速开始、基本用法、目录结构
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

简介
==

Jekyll是一个简单的，博客感知的静态站点生成器。

你将内容创建为文本文件（[Markdown](https://link.juejin.cn/?target=https%3A%2F%2Fdaringfireball.net%2Fprojects%2Fmarkdown%2F "https://daringfireball.net/projects/markdown/")），并将其放到到文件夹中。然后，使用[Liquid](https://link.juejin.cn/?target=https%3A%2F%2Fshopify.github.io%2Fliquid%2F "https://shopify.github.io/liquid/")\-enhanced HTML模板构建网站。Jekyll自动将内容和模板联系在一起，生成完全由静态资源组成的网站，它适合上传到任何服务器。

Jekyll恰好是[GitHub Pages](https://link.juejin.cn/?target=https%3A%2F%2Fpages.github.com%2F "https://pages.github.com/")的引擎，因此你可以在GitHub的服务器上免费托管项目的Jekyll页面/博客/网站。

快速开始
====

如果你已经安装了包含所有头文件和[RubyGems](https://link.juejin.cn/?target=https%3A%2F%2Frubygems.org%2Fpages%2Fdownload "https://rubygems.org/pages/download")的完整的[Ruby](https://link.juejin.cn/?target=https%3A%2F%2Fwww.ruby-lang.org%2Fen%2Fdownloads%2F "https://www.ruby-lang.org/en/downloads/")开发环境（请参阅Jekyll的[要求](https://link.juejin.cn/?target=https%3A%2F%2Fjekyllrb.com%2Fdocs%2Finstallation%2F%23requirements "https://jekyllrb.com/docs/installation/#requirements")），你可以通过执行以下操作来创建一个新的Jekyll站点：

```
# 通过RubyGems安装Jekyll和Bundler gems
gem install jekyll bundler
# 如果无法安装请尝试：sudo gem install jekyll bundler
# 上面两个命令都无法安装，请尝试：sudo gem install -n /usr/local/bin jekyll bundler
# 如果仍无法解决，请尝试关闭SIP

# 在./myblog创建一个新的Jekyll站点
jekyll new myblog

# 进入到生成的文件夹中
cd myblog

# 在本地预览服务中编译站点
bundle exec jekyll serve

# 浏览器里面打开 http://localhost:4000

```

如果你在上述过程中遇到任何意外错误，比如可能缺少开发头文件或其他先决条件，请参阅[故障排除](https://link.juejin.cn/?target=https%3A%2F%2Fjekyllrb.com%2Fdocs%2Ftroubleshooting%2F%23configuration-problems "https://jekyllrb.com/docs/troubleshooting/#configuration-problems")页面或前面提到的[需求](https://link.juejin.cn/?target=requirements "requirements")页面。

关于Bundler
---------

`gem install bundler`命令将通过[RubyGems](https://link.juejin.cn/?target=https%3A%2F%2Frubygems.org%2F "https://rubygems.org/")安装[bundler](https://link.juejin.cn/?target=https%3A%2F%2Frubygems.org%2Fgems%2Fbundler "https://rubygems.org/gems/bundler") gem。你只需要安装一次即可——不用每次创建一个Jekyll项目的时候都安装一次。这里有一些额外的细节：

*   `bundler`是一个管理其他Ruby gems的gem。它确保你的gems和gem版本兼容，并且确保包含每个gem需要的必须依赖。
    
*   `Gemfile`和`Gemfile.lock`文件将告知Bundler有关于你的站点中的gem依赖。如果你的站点没有这些`Gemfile`文件，则可以省略`bundle exec`命令，直接运行`jekyll serve`命令。
    
*   当你运行`bundle exec jekyll serve`时，Bundler使用`Gemfile.lock`中指定的gem和版本来确保你的Jekyll站点没有兼容性或依赖冲突。
    

有关如何在Jekyll项目中使用Bundler的更多信息，这个[教程](https://link.juejin.cn/?target=https%3A%2F%2Fjekyllrb.com%2Ftutorials%2Fusing-jekyll-with-bundler%2F "https://jekyllrb.com/tutorials/using-jekyll-with-bundler/")可以为最常见的问题提供答案，并解释如何快速启动和运行。

使用Jekyll创建一个新的站点的选项
-------------------

`jekyll new <PATH>`在指定的路径（相对于当前目录）安装一个新的Jekyll站点。 在上面列出的命令行的情况下，Jekyll将被安装在当前目录下的名为`myblog`的目录中。这里有一些额外的细节：

*   要将Jekyll站点安装到你当前所在的目录中，请运行`jekyll new .`。 如果现有的目录不是空的，你可以使用`jekyll new . --force`传递`--force`选项。
    
*   `jekyll new`会自动启动`bundle install`以安装所需的依赖关系。 （如果你不想让Bundler安装gem，请使用`jekyll new myblog --skip-bundle`。）
    
*   默认情况下，由`jekyll new`安装的Jekyll站点使用一个叫做为[Minima](https://link.juejin.cn/?target=https%3A%2F%2Fgithub.com%2Fjekyll%2Fminima "https://github.com/jekyll/minima")的基于gem的主题。使用基于gem的主题，一些目录和文件存储在gem主题中，隐藏在你的即时视图中。
    
*   我们建议你将Jekyll设置为基于gem的主题，但如果你想从空白的模版开始，请使用`jekyll new myblog --blank`。
    
*   要了解其他参数，你可以使用`jekyll new`，输入`jekyll new --help`即可。
    

> 如果有疑问，请使用`help`命令来提示你所有可用的选项和用法，它也适用于`new`和`build`以及`serve`命令，例如，`jekyll help new`或`jekyll help build`。

基本用法
====

Jekyll gem在终端窗口中为你提供了一个`jekyll`可执行文件。你可以通过多种方式使用此命令：

```
jekyll build
# => 当前文件夹中的内容将被生成到./_site

jekyll build --destination <destination>
# => 当前文件夹中的内容将被生成到<destination>

jekyll build --source <source> --destination <destination>
# => <source>文件夹中的内容将被生成到<destination>

jekyll build --watch
# => 当前文件夹中的内容将被生成到./_site,
#    检查改动，并自动重新生成。

```

重写默认开发配置
--------

开发环境的默认预览地址是`http://localhost:4000`。**`[3.3.0]`**

如果你想为你的生产环境构建：

*   在`_config.yml`中设置你的生产环境URL。例如：`https://example.com`。
*   运行`JEKYLL_ENV=production bundle exec jekyll build`。

> **注意: `_config.yml`的更改并不会在自动生成更新过程中生效。**
> 
> `_config.yml`主要配置文件会在执行时读取一次全局配置和变量定义。在下次执行之前，不会加载在自动生成更新期间对`_config.yml`所做的更改。
> 
> 注意，自动生成更新过程中会对[Data Files](https://link.juejin.cn/?target=https%3A%2F%2Fjekyllrb.com%2Fdocs%2Fdatafiles "https://jekyllrb.com/docs/datafiles")重新加载。

> **警告：目标文件夹在网站构建的时候会被清空**
> 
> 默认情况下，当网站构建的时候，`<destination>`中的内容会被自动的清空。不是被你的网站构建时所创建的文件和文件夹都会被删除。可以在<keep\_files>配置指令中指定你希望保留在中的文件和文件夹。
> 
> 不要设置为重要本地路径；相反，应该将其用作暂存区域并将文件从那里复制到你的Web服务器。

Jekyll还附带了一个内置的开发服务器，可以让你在本地浏览中浏览生成的网站。

```
jekyll serve
# => 开发服务将会运行在http://localhost:4000/
# 自动生成更新会被开启，如果不想开启请使用`--no-watch`。

jekyll serve --no-watch
# => 等同于`jekyll serve`，但是内容更改时不会自动生成新的。

jekyll serve --livereload
# LiveReload将在更新后刷新浏览器页面。

jekyll serve --incremental
# Incremental将会匹配更改部分，执行部分构建以减少自动生成更新时间。

jekyll serve --detach
# => 等同于`jekyll serve`，但是不会再当前终端中显示运行状态，而是转为后台模式。
#    如果你需要关闭服务，你可以`kill -9 1234`，这里的"1234"是PID。
#    如果你不知道PID，那么就执行`ps aux | grep jekyll`并关闭这个实例。

```

这些只是几个可用的[配置选项](https://juejin.cn/post/6844903629246169096 "https://juejin.cn/post/6844903629246169096")。许多配置选项可以在命令行中指定为flags，或者（更常见）它们可以在源目录的根目录下的`_config.yml`文件中指定。运行时，Jekyll会自动使用该文件中的选项。例如，如果将以下行放在`_config.yml`文件中：

```
source:      _source
destination: _deploy

```

那么以下两个命令将是等效的：

```
jekyll build
# 上面的命令添加过配置后等于下面的命令没加配置
jekyll build --source _source --destination _deploy

```

有关配置选项的更多信息，请参阅[配置](https://juejin.cn/post/6844903629246169096 "https://juejin.cn/post/6844903629246169096")页面。

> **注意：寻求帮助**
> 
> `help`命令总是在这里提示你所有可用的选项和用法，它也适用于`new`和`build`以及`serve`命令，例如，`jekyll help new`或`jekyll help build`。

如果你有兴趣想要随时浏览这些文档，请安装`jekyll-docs`gem，并在你的终端中运行`jekyll docs`。

目录结构
====

Jekyll的核心是一个文本转换引擎。这个系统的大概是：你给它的内容可以用你最喜欢的标记语言编写，可以是Markdown，是[Textile](https://link.juejin.cn/?target=https%3A%2F%2Fgithub.com%2Fjekyll%2Fjekyll-textile-converter "https://github.com/jekyll/jekyll-textile-converter")或者是纯粹的HTML，然后Jekyll通过一个或一系列布局文件混合它们。在整个过程中，你可以调整网站URL的样式，布局中显示的数据等等。这一切都是通过编辑文本文件完成的，而静态网站就是它的最终产品。

基本的Jekyll站点通常看起来像这样：

```
.
├── _config.yml
├── _data
|   └── members.yml
├── _drafts
|   ├── begin-with-the-crazy-ideas.md
|   └── on-simplicity-in-technology.md
├── _includes
|   ├── footer.html
|   └── header.html
├── _layouts
|   ├── default.html
|   └── post.html
├── _posts
|   ├── 2007-10-29-why-every-programmer-should-play-nethack.md
|   └── 2009-04-26-barcamp-boston-4-roundup.md
├── _sass
|   ├── _base.scss
|   └── _layout.scss
├── _site
├── .jekyll-metadata
└── index.html # can also be an 'index.md' with valid YAML Frontmatter

```

> **注意：使用基于gem的主题的Jekyll网站的目录结构**
> 
> 始于Jekyll 3.2，一个使用`jekyll new`创建的基于gem的主题来定义网站外观的新的Jekyll项目，会有一个比较简单的默认目录结构：默认情况下，\_layouts，\_includes和\_sass会被存储在theme-gem中，而不是放在项目目录中。
> 
> [minima](https://link.juejin.cn/?target=https%3A%2F%2Fgithub.com%2Fjekyll%2Fminima "https://github.com/jekyll/minima")是当前的默认主题，`bundle show minima`会告诉你minima主题的文件存储在计算机上的哪个位置。

目录结构说明：

| 文件/文件夹 | 说明 |
| --- | --- |
| `_config.yml` | 存储配置数据。这些配置中的许多选项都可以从命令行中指定，但在这里指定它们更加容易，并且你不必记住它们。 |
| `_drafts` | 草稿是未发布的文章。这些文件的命名格式是没有日期的：`title.MARKUP`。了解如何[使用草稿](https://link.juejin.cn/?target=https%3A%2F%2Fjekyllrb.com%2Fdocs%2Fdrafts%2F "https://jekyllrb.com/docs/drafts/")。 |
| `_includes` | These are the partials that can be mixed and matched by your layouts and posts to facilitate reuse. The liquid tag {% include file.ext %} can be used to include the partial in \_includes/file.ext. |
| `_layouts` | 这些是包装文章的模板。在[YAML Front Matter](https://link.juejin.cn/?target=https%3A%2F%2Fjekyllrb.com%2Fdocs%2Ffrontmatter%2F "https://jekyllrb.com/docs/frontmatter/")中逐层选择布局，这将在下一节中介绍。 The liquid tag `{{ content }}`用于将内容注入网页。 |
| `_posts` | 可以这么说，这里是你的动态内容。这些文件的命名约定很重要，并且必须遵循以下格式：`YEAR-MONTH-DAY-title.MARKUP`。可以为每篇文章指定[固定链接](https://link.juejin.cn/?target=https%3A%2F%2Fjekyllrb.com%2Fdocs%2Fpermalinks%2F "https://jekyllrb.com/docs/permalinks/")，但日期和MARKUP语言完全由文件名决定。 |
| `_data` | 格式良好的网站数据应该放在这里。Jekyll引擎将自动加载该目录中的所有数据文件（使用`.yml`，`.yaml`，`.json`或`.csv`格式和扩展名），并且可以通过`site.data`访问它们。如果目录下有文件`members.yml`，则可以通过`site.data.members`访问该文件的内容。 |
| `_sass` | 些是可以导入到`main.scss`中的sass部分，然后将它们处理成一个样式表`main.css`，该样式表定义了你的网站使用的样式。 |
| `_site` | 这是Jekyll完成转换后，生成的网站将被存放的（默认）位置。建议将它添加到`.gitignore`文件中。 |
| `.jekyll-metadata` | 临时文件，这些将帮助Jekyll追踪自上次构建站点后哪些文件未被修改，以及哪些文件需要在下一个版本中重新生成。该文件不会包含在生成的网站中。建议将它添加到.gitignore文件中。 |
| `index.html`或`index.md`或其他HTML、Markdown文件 | 假设该文件具有[YAML Front Matter](https://link.juejin.cn/?target=https%3A%2F%2Fjekyllrb.com%2Fdocs%2Ffrontmatter%2F "https://jekyllrb.com/docs/frontmatter/")部分，它将由Jekyll进行转换。网站根目录中的任何`.html`，`.markdown`，`.md`或`.textile`文件或上面未列出的目录也会发生同样的情况。 |
| 其他文件/文件夹 | 除了上面列出之外的其他文件夹和文件（例如`css`和`images`文件夹，`favicon.ico`文件等），将会被逐字复制到生成的网站中。如果你想知道它们是如何布置的，有[很多网站已经在使用Jekyll](https://link.juejin.cn/?target=https%3A%2F%2Fjekyllrb.com%2Fdocs%2Fsites%2F "https://jekyllrb.com/docs/sites/")。 |

  

本文转自 [https://juejin.cn/post/6844903623567081486](https://juejin.cn/post/6844903623567081486)，如有侵权，请联系删除。