---
title: '本站WordPress已经添加的个性化设置记录'
date: Fri, 22 Apr 2022 02:59:21 +0000
draft: false
tags: ['Wordpress']
---

【WordPress】按文章修改时间排序
--------------------

使最新修改的文章排在最前面

在主题文件夹中模板函数 (functions.php)中添加文本：

```
// sort by modify time
function order_posts_by_mod_date($orderby) 
{   
    if  (is_home() || is_archive() || is_feed()) 
    {     
        $orderby = "post_modified_gmt DESC";   
    }   
    return $orderby; 
} 
add_filter('posts_orderby', 'order_posts_by_mod_date', 999);
```

修改摘要默认字数
--------

优点：操作简单。  
缺点：博客升级后会失  
效，需重新修改。

找到WorsPress目录wp－includes下formating.php文件，查找unction wp\_trim\_excerpt($text)函数，再找到excerpt\_length，默认值是55，修改成需要的值即可，本站使用值为120。

[WordPress 安装主题、插件、更新时需要FTP的解决办法](https://www.wpcom.cn/tutorial/101.html)
-------------------------------------------------------------------------

### 修改wp-config.php文件

对于没有服务器目录操作权限的用户来说，修改wp-config.php文件会比较简单快捷，只需要在wp-config.php文件添加以下代码：

```
define('FS_METHOD','direct');
```

可以加到`WP_DEBUG`那一行后面。