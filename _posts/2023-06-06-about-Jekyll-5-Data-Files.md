---
layout: post
title: Jekyll 合集、数据文件
permalink: /Jekyll-Data-Files/
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
* * *

**目录**

*   [《Jekyll使用教程笔记 一：简介、快速开始、基本用法、目录结构》](https://juejin.cn/post/6844903623567081486 "https://juejin.cn/post/6844903623567081486")
*   [《Jekyll使用教程笔记 二：配置》](https://juejin.cn/post/6844903629246169096 "https://juejin.cn/post/6844903629246169096")
*   [《Jekyll使用教程笔记 三：Front Matter、写文章》](https://juejin.cn/post/6844903629682376711 "https://juejin.cn/post/6844903629682376711")
*   [《Jekyll使用教程笔记 四：创建页面、静态文件、变量》](https://juejin.cn/post/6844903629934084109 "https://juejin.cn/post/6844903629934084109")
*   [《Jekyll使用教程笔记 五：合集、数据文件》](https://juejin.cn/post/6844903630001160199 "https://juejin.cn/post/6844903630001160199")
*   [《Jekyll使用教程笔记 六：资源、博客迁移、模版》](https://juejin.cn/post/6844903632882630664 "https://juejin.cn/post/6844903632882630664")

* * *

合集
==

并非所有内容都是文章或页面。也许你想记录开源项目中的各种方法、团队成员、或会议中的会话。合集允许你定义一种类似页面或文章那样正常工作的新类型的文档，但也具有其自己的唯一属性和名称空间。

使用合集
----

开始使用合集，需要一下三步：

*   第一步：告诉Jekyll读取你的合集
*   第二步：添加你的内容
*   第三步：有选择地将你的合集文档渲染为独立的文件

### 第一步：告诉Jekyll读取你的合集

将以下内容添加到你的网站的`_config.yml`文件中，将`my_collection`替换为你的合集的名称：

```
collections:
- my_collection

```

你可以在配置中为你的合集指定元数据：

```
collections:
- my_collection:
    foo: bar

```

也可以为合集设置默认属性：

```
defaults:
  - scope:
      path: ""
      type: my_collection
    values:
      layout: page

```

> **重要：Gather your collections`[3.7.0]`**
> 
> 你可以使用`collections_dir: my_collections`选择指定一个目录来将所有合集存储在同一个位置。
> 
> 然后，Jekyll将在`my_collections/_books`中查找`books`合集，并在`y_collections/_recipes`中查找`recipes`合集。

> **警告：确保将草稿和文章移动到自定义合集目录中**
> 
> 使用`collections_dir: my_collections`选择指定一个目录来将所有合集存储在同一个位置，则需要将`_drafts`和`_posts`目录移至`my_collections/_drafts`和`my_collections/_posts`。请注意，你的合集目录的名称不能以下划线（`_`）开头。

### 第二步：添加你的内容

创建一个相应的文件夹（例如`<source>/_my_collection`）并添加文档。如果存在Front Matter，则处理YAML Front Matter，并将Front Matter之后的所有内容都推送到文档的`content`属性中。如果没有提供YAML Front Matter，Jekyll将不会在你的合集中生成该文件。

> **注意：确保正确命名你的文件夹**
> 
> 该文件夹必须与你在`_config.yml`文件中定义的合集命名相同，并在前面添加`_`字符。

### 第三步：有选择地将你的合集文档渲染为独立的文件

如果你希望Jekyll为你的合集中的每个文档创建一个面向公共的渲染版本，请在你的`_config.yml`中的合集元数据中将`output`设置为`true`：

```
collections:
  my_collection:
    output: true

```

这将为合集中的每个文档生成一个文件。例如，如果你有`_my_collection/some_subdir/some_doc.md`，它将使用你选择的Liquid和Markdown转换器进行渲染，并写入`<dest>/my_collection/some_subdir/some_doc.html`。

如果你希望在访问`/my_collection/`时显示指定页面，只需将永久链接：`/my_collection/index.html`添加到页面即可。要列出合集中的项目，在该页面或任何其他项目中，你可以使用：

```
{% for item in site.my_collection %}
  <h2>{{ item.title }}</h2>
  <p>{{ item.description }}</p>
  <p><a href="{{ item.url }}">{{ item.title }}</a></p>
{% endfor %}

```

> **注意：不要忘记添加YAML进行处理**
> 
> 合集中的文件没有Front Matter的将被视为[静态文件](https://juejin.cn/post/6844903629934084109#heading-7 "https://juejin.cn/post/6844903629934084109#heading-7")，只是简单地复制到其输出位置而不进行处理。

配置合集的永久链接
---------

如果你希望为合集网页所在的网址指定自定义模式，则可以使用[永久链接属性](https://link.juejin.cn/?target=https%3A%2F%2Fjekyllrb.com%2Fdocs%2Fpermalinks%2F "https://jekyllrb.com/docs/permalinks/")进行设置：

```
collections:
  my_collection:
    output: true
    permalink: /:collection/:name

```

### 例子

对于具有以下源文件结构的合集，

```
_my_collection/
└── some_subdir
    └── some_doc.md

```

以下每个`permalink`配置中的每一个都会生成下面显示的文档结构。

*   **默认** 与`permalink: /:collection/:path`一样。```
    _site/
    ├── my_collection
    │   └── some_subdir
    │       └── some_doc.html
    ...
    
    ```
    
*   **`permalink: pretty`** 与`permalink: /:collection/:path/`一样。```
    _site/
    ├── my_collection
    │   └── some_subdir
    │       └── some_doc
    │           └── index.html
    ...
    
    ```
    
*   **`permalink: /doc/:path`**```
    _site/
    ├── doc
    │   └── some_subdir
    │       └── some_doc.html
    ...
    
    ```
    
*   **`permalink: /doc/:name`**```
    _site/
    ├── doc
    │   └── some_doc.html
    ...
    
    ```
    
*   **`permalink: /:name`**```
    _site/
    ├── some_doc.html
    ...
    
    ```
    

### 模板变量

| 变量 | 说明 |
| --- | --- |
| `:collection` | 包含合集的标签。 |
| `:path` | 文档相对于合集目录的路径。 |
| `:name` | 文档的基本文件名，每个空格和非字母数字字符序列都用连字符替换。 |
| `:title` | 如果文档中存在文件，则`:title`模板变量将采用[Front Matter](https://link.juejin.cn/?target=)中`slug`变量值;如果没有定义那么`:title`将等同于`:name`，也就是通过文件名生成的`slug`。 |
| `:output_ext` | 输出文件的扩展名。（默认情况下有扩展名，但通常是不需要的。） |

Liquid属性
--------

### 合集

每个合集都可以作为`site`变量中的字段来访问。例如，如果你想访问`_albums`中的`albums`合集，则可以使用`site.albums`。

每个合集本身都是一系列文档（例如，`site.albums`是一组文档，与`site.pages`和`site.posts`非常相似）。请参阅下表以了解如何访问这些文档的属性。

这些合集也可以在`site.collections`下找到，并含有你在`_config.yml`中指定的元数据（如果存在）以及以下信息：

| 变量 | 说明 |
| --- | --- |
| `label` | 你的合集的名称，例如：`my_collection`。 |
| `docs` | [文档](https://link.juejin.cn/?target=https%3A%2F%2Fjekyllrb.com%2Fdocs%2Fcollections%2F%23documents "https://jekyllrb.com/docs/collections/#documents")数组。 |
| `files` | 合集中的静态文件数组。 |
| `relative_directory` | 合集源目录的路径，相对于站点源。 |
| `directory` | 合集的源目录的完整路径。 |
| `output` | 该合集的文档是否将作为单个文件输出。 |

> **注意：硬编码合集**
> 
> 除了你自己创建的合集外，`posts`合集还被Jekyll硬编码，不管是否存在`_posts`目录。在迭代`site.collections`时，需要注意这点，因为你可能需要将其过滤掉。
> 
> 你可能希望使用过滤器来查找in的合集：`{{ site.collections | where: "label", "myCollection" | first }}`。

> **注意：合集和时间**
> 
> 除了默认硬编码合集`posts`中的文档外，你创建的合集中的所有文档均可通过Liquid进行访问，而不考虑其指定日期（如果有），因此可以进行渲染。
> 
> 但是，只有在相关合集元数据`output: true`时，才会尝试将文档写入磁盘。此外，未来日期的文件只有在`site.future`也是`true`的情况下才会写入。
> 
> 通过在文档的Front Matter设置`published: false`（默认为true），可以对正在写入磁盘的文档进行更细致的控制。

### 文档

除文档相应文件中提供的任何YAML Front Matter外，每个文档还具有以下属性：

| 变量 | 说明 |
| --- | --- |
| `content` | 文件的（未提及的）内容。如果没有提供YAML Front Matter，则Jekyll将不会在你的合集中生成该文件。如果使用YAML Front Matter，则这是Front Matter的终止符`---`后面的所有内容。 |
| `output` | 基于`content`渲染文档的输出。 |
| `path` | 文档源文件的完整路径。 |
| `relative_path` | 文档源文件相对于网站源的路径。 |
| `url` | 渲染的合集的URL。只有当它所属的合集在站点配置中具有`output：true`时，才会将文件写入目标。 |
| `collection` | 文档合集的名称。 |
| `date` | 文档合集的日期。 |

访问合集属性
------

来自YAML Front Matter的属性可以作为数据在网站中任何地方被访问。使用上面的示例将一个合集配置为`site.albums`，你可能会在单个文件中构建如下的Front Matter（它必须使用支持的标记格式，并且不能使用`.yaml`扩展名保存）：

```
title: "Josquin: Missa De beata virgine and Missa Ave maris stella"
artist: "The Tallis Scholars"
director: "Peter Phillips"
works:
  - title: "Missa De beata virgine"
    composer: "Josquin des Prez"
    tracks:
      - title: "Kyrie"
        duration: "4:25"
      - title: "Gloria"
        duration: "9:53"
      - title: "Credo"
        duration: "9:09"
      - title: "Sanctus & Benedictus"
        duration: "7:47"
      - title: "Agnus Dei I, II & III"
        duration: "6:49"

```

合集中的每个专辑都可以使用模板在单个页面上列出：

```
{% for album in site.albums %}
  <h2>{{ album.title }}</h2>
  <p>Performed by {{ album.artist }}{% if album.director %}, directed by {{ album.director }}{% endif %}</p>
  {% for work in album.works %}
    <h3>{{ work.title }}</h3>
    <p>Composed by {{ work.composer }}</p>
    <ul>
    {% for track in work.tracks %}
      <li>{{ track.title }} ({{ track.duration }})</li>
    {% endfor %}
    </ul>
  {% endfor %}
{% endfor %}

```

数据文件
====

除了Jekyll提供的[内置变量](https://juejin.cn/post/6844903629934084109#heading-9 "https://juejin.cn/post/6844903629934084109#heading-9")之外，你还可以指定自己的自定义数据，这些数据可以通过[Liquid模板系统访问](https://link.juejin.cn/?target=https%3A%2F%2Fwiki.github.com%2Fshopify%2Fliquid%2Fliquid-for-designers "https://wiki.github.com/shopify/liquid/liquid-for-designers")。

Jekyll支持从位于`_data`目录中的[YAML](https://link.juejin.cn/?target=http%3A%2F%2Fyaml.org%2F "http://yaml.org/")，[JSON](https://link.juejin.cn/?target=http%3A%2F%2Fwww.json.org%2F "http://www.json.org/")和[CSV](https://link.juejin.cn/?target=https%3A%2F%2Fen.wikipedia.org%2Fwiki%2FComma-separated_values "https://en.wikipedia.org/wiki/Comma-separated_values")文件加载数据。请注意，CSV文件_必须_包含标题行。

这个强大的功能可以避免模板中的重复，并且可以在不更改`_config.yml`的情况下设置特定于站点的选项。

插件/主题还可以利用数据文件来设置配置变量。

数据文件夹
-----

正如在[目录结构](https://juejin.cn/post/6844903623567081486#heading-6 "https://juejin.cn/post/6844903623567081486#heading-6")页面上所解释的那样，`_data`文件夹是你可以在其中存储Jekyll生成站点时使用的其他数据的位置。这些文件必须是YAML，JSON或CSV文件（使用`.yml`，`.yaml`，`.json`或`.csv`扩展名），并且可以通过`site.data`访问它们。

示例：成员列表
-------

以下是使用数据文件避免在Jekyll模板中复制大量代码的基本示例：

在`_data/members.yml`中：

```
- name: Eric Mill
  github: konklone

- name: Parker Moore
  github: parkr

- name: Liu Fengyun
  github: liufengyun

```

或`_data/members.csv`中：

```
name,github
Eric Mill,konklone
Parker Moore,parkr
Liu Fengyun,liufengyun

```

这些数据可以通过`site.data.members`进行访问（请注意，文件名决定变量名称）。

你现在可以在模板中呈现成员列表：

```
<ul>
{% for member in site.data.members %}
  <li>
    <a href="https://github.com/{{ member.github }}">
      {{ member.name }}
    </a>
  </li>
{% endfor %}
</ul>

```

> **注意：**
> 
> 如果你的Jekyll站点有很多页面，例如文档网站，请参阅详细示例以了解[如何为你的站点构建强大的导航](https://link.juejin.cn/?target=https%3A%2F%2Fjekyllrb.com%2Ftutorials%2Fnavigation%2F "https://jekyllrb.com/tutorials/navigation/")。

示例：组织
-----

数据文件也可以放在`_data`文件夹的子文件夹中。每个文件夹级别将被添加到变量的命名空间中。下面的示例显示了如何在`orgs`文件夹下的文件中分别定义GitHub组织：

在`_data/orgs/jekyll.yml`中：

```
username: jekyll
name: Jekyll
members:
  - name: Tom Preston-Werner
    github: mojombo

  - name: Parker Moore
    github: parkr

```

在`_data/orgs/doeorg.yml`中：

```
username: doeorg
name: Doe Org
members:
  - name: John Doe
    github: jdoe

```

然后可以通过`site.data.orgs`访问组织，后面接是文件名：

```
<ul>
{% for org_hash in site.data.orgs %}
{% assign org = org_hash[1] %}
  <li>
    <a href="https://github.com/{{ org.username }}">
      {{ org.name }}
    </a>
    ({{ org.members | size }} members)
  </li>
{% endfor %}
</ul>

```

示例：访问特定的作者
----------

页面和文章也可以访问特定的数据项。以下示例显示了如何访问特定项目：

`_data/people.yml`：

```
dave:
    name: David Smith
    twitter: DavidSilvaSmith

```

然后，作者可以被指定为文章Front Matter的页面变量：

```
---
title: sample post
author: dave
---
{% assign author = site.data.people[page.author] %}
<a rel="author"
  href="https://twitter.com/{{ author.twitter }}"
  title="{{ author.name }}">
    {{ author.name }}
</a>

```

有关如何为你的站点构建强大的导航的信息（特别是如果你有文档网站或其他类型的Jekyll站点并且需要组织许多页面），请参阅[导航](https://link.juejin.cn/?target=https%3A%2F%2Fjekyllrb.com%2Ftutorials%2Fnavigation "https://jekyllrb.com/tutorials/navigation")。

  

本文转自 [https://juejin.cn/post/6844903630001160199](https://juejin.cn/post/6844903630001160199)，如有侵权，请联系删除。