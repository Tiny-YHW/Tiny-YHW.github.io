---
layout: post
title: 简介、快速开始、基本用法、目录结构
categories: Jekyll
date: 2023-06-06
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