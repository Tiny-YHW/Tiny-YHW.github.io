---
title: '网站数据爬取web scraper'
date: Fri, 08 May 2020 05:31:39 +0000
draft: false
tags: ['技术讨论', '软件应用']
---

**官网：**[https://www.webscraper.io/](https://www.webscraper.io/)  
**官网视频教程：**  
[https://v.qq.com/x/page/j0904jsza43.html](https://v.qq.com/x/page/j0904jsza43.html)    
[https://v.qq.com/x/page/l0904am419m.html](https://v.qq.com/x/page/l0904am419m.html)    
[https://v.qq.com/x/page/v0904snimmp.html](https://v.qq.com/x/page/v0904snimmp.html)  
**其他教程：**[https://www.yuanrenxue.com/earn-money/web-scraper-tutorial.html](https://www.yuanrenxue.com/earn-money/web-scraper-tutorial.html)  
**中文论坛：**[http://www.iwebscraper.com/](http://www.iwebscraper.com/)  
**常见问题：**[https://www.jianshu.com/p/cd5124ac0871](https://www.jianshu.com/p/cd5124ac0871)

指定范围内的多个网址
----------

如果站点在页面URL中使用编号，则创建范围起始url比创建用于导航站点的_链接选择器_要简单得多。要指定范围网址，请使用范围定义-替换起始网址的数字部分`[1-100]`。如果网站在网址中使用零填充，则将零填充添加到范围定义-中`[001-100]`。如果要跳过某些URL，则还可以指定增量`[0-100:10]`。

将这样的范围网址`http://example.com/page/[1-3]`用于这样的链接：

*   `http://example.com/page/1`
*   `http://example.com/page/2`
*   `http://example.com/page/3`

`http://example.com/page/[001-100]` 对于这样的链接，请使用带有零填充的范围网址，如下所示：

*   `http://example.com/page/001`
*   `http://example.com/page/002`
*   `http://example.com/page/003`

像这样`http://example.com/page/[0-100:10]`将链接的范围网址用于增量：

*   `http://example.com/page/0`
*   `http://example.com/page/10`
*   `http://example.com/page/20`

使用多个不连续的网址作为起始页
---------------

*   创建Sitemap时**Start URL**填入任意两个
*   完成抓取参数设置
*   导出Sitemap的文本格式内容，内容大致如下

```
{"id":"nxp","startUrl":["https://www.nxp.com/products/product-selector:PRODUCT-SELECTOR#/keyword/PCU","https://www.nxp.com/products/product-selector:PRODUCT-SELECTOR#/keyword/BFQ"],"selectors":[{"id":"chaeck","type":"SelectorElementClick","parentSelectors":["_root"],"selector":"a strong","multiple":true,"delay":0,"clickElementSelector":".css-pu3z7r input","clickType":"clickOnce","discardInitialElements":"do-not-discard","clickElementUniquenessType":"uniqueText"},{"id":"part","type":"SelectorText","parentSelectors":["chaeck"],"selector":"_parent","multiple":false,"regex":"","delay":0}]}
```

*   拆解startUrl部分可发现多个网址的写法为加双引号并使用逗号分隔
*   使用Excel或其他工具构建上述多个网址的格式，替换应内容
*   导入修改后的Sitemap即可

**安装并配置 CouchDB**
-----------------

[http://couchdb.apache.org/#download](http://couchdb.apache.org/#download)  
进入后下载合适你电脑系统的 CouchDB。

不要安装到C盘

浏览器打开 [http://127.0.0.1:5984/\_utils/](http://127.0.0.1:5984/_utils/)，别打开错了。

然后创建一个数据库，命名为 scraper-sitemaps

右键 Web Scraper，然后点击选项，进入设置界面

Storage type 改成 CouchDB

Sitemap db 填写 [http://localhost:5984/scraper-sitemaps](http://localhost:5984/scraper-sitemaps)

Data db 填 [http://localhost:5984/](http://localhost:5984/)保存之后重启浏览器，然后 Web Scraper 爬取下来的数据就是有序的。

进入 [http://127.0.0.1:5984/\_utils/](http://127.0.0.1:5984/_utils/) 能看到创建的数据库，点击进去能看到 Sitemap。

原文: [https://lbjheiheihei.xyz/2019/02/06/Install-CouchDB.html](https://lbjheiheihei.xyz/2019/02/06/Install-CouchDB.html)

案例
--

### [赛宝电子元器件数据平台](http://www.cepreidata.com/index.html)

```
{"_id":"saibao","startUrl":["http://search.cepreidata.com/pc/searchProduct/search?searchKeyWords=CAK55-C"],"selectors":[{"id":"saibao-duixiang","type":"SelectorElementClick","parentSelectors":["_root"],"selector":".products tr:nth-of-type(n+2)","multiple":true,"delay":0,"clickElementSelector":".next a","clickType":"clickMore","discardInitialElements":"do-not-discard","clickElementUniquenessType":"uniqueText"},{"id":"part-number","type":"SelectorText","parentSelectors":["saibao-duixiang"],"selector":"td:nth-of-type(3)","multiple":false,"regex":"","delay":0}]}
```

### [赛思库电子元器件专业云采购平台](https://www.cisscloud.com/)

```
{"_id":"saisiceshi1","startUrl":["https://www.cisscloud.com/platform/search/components?category_id=1103&key=JCA45&sub_key="],"selectors":[{"id":"sad","type":"SelectorElementClick","parentSelectors":["_root"],"selector":"div.ciss-product-item","multiple":true,"delay":"2000","clickElementSelector":"i.icon-xiangyou","clickType":"clickMore","discardInitialElements":"do-not-discard","clickElementUniquenessType":"uniqueText"},{"id":"asdsd","type":"SelectorText","parentSelectors":["sad"],"selector":".name a","multiple":false,"regex":"","delay":0}]}
```