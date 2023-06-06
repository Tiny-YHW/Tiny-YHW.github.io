---
title: 'WordPress 角色和权限终极指南'
date: Tue, 14 Apr 2020 05:50:48 +0000
draft: false
tags: ['Wordpress']
---

WordPress 在 2.0 版本中引入了[角色和权限](https://codex.wordpress.org/Roles_and_Capabilities)（Roles and Capabilities）系统，以前的[用户等级的方法](https://codex.wordpress.org/User_Levels)（User Levels）已经被弃用。但是还是有很多插件和主题仍然使用用户级别的方法来控制用户查看设置页面和其他功能。所以这篇指南将详细介绍 WordPress 的角色和权限系统，最终将让你在你的插件和主题中能够正确使用。

什么是角色和权限？
---------

和其他 CMS 或者 Web 程序一样，WordPress 也有一个内置的系统来验证一个特定的用户是否有足够的权限来进行某种动作。WordPress 这个内置的系统就是角色和权限系统，它首先将用户分为角色（Role），然后给每个角色都分配一定的权限。

下面是 WordPress 默认的用户角色：

*   **管理员** -拥有所有的管理权限
*   **编辑** -发表文章，编辑文章，以及编辑其他人的文章，等等。
*   **作者**\-发布和编辑自己的文章
*   **投稿者** -撰写和编辑自己的文章，但不能发布
*   **订阅者** -查看评论/添加评论/查看文章，等等。

WordPress 的角色和权限系统比用户等级的方法灵活得多，它支持对现有用户角色添加，删除和重新分配权限，甚至还可以添加更多的用户角色，并且不破坏系统原有内置的用户角色。

用户权限和后台菜单
---------

很多插件都都会在 WordPress 后台添加一个管理页面，让用户自定义插件选项，一般我们可以通过下面的函数实现：

```
// 添加主菜单
add_menu_page(page_title, menu_title, capability, handle, [function], [icon_url]);

// 添加子菜单
add_submenu_page(parent, page_title, menu_title, capability, file/handle, [function]);

//添加选项菜单子菜单
add_options_page(page_title, menu_title, capability, handle, [function]);

//添加工具菜单子菜单
add_management_page(page_title, menu_title, capability, handle, [function]);

//添加页面菜单子菜单
add_pages_page( page_title, menu_title, capability, handle, [function]);

//添加文章菜单子菜单
add_posts_page( page_title, menu_title, capability, handle, [function]);

//添加主题菜单子菜单
add_theme_page( page_title, menu_title, capability, handle, [function]);
```

我们很容易发现，这些函数都会有个参数：`capability`，这个参数就是用来指定用户看到该菜单所需要的权限。一般它的值是一个代表某种权限的字符串，比如：`edit_posts`。所以使用这些额函数在 WordPress 后台中添加的菜单以及与这些菜单相关联的页面，是只有拥有指定的权限的用户才可以看到和访问的。

如果你的主题或者插件有设置页面，应该正确的控制哪些用户有权限可以访问这些页面，比如，添加的是一个主题选项页面，就应该使用 `edit_themes` 权限，而添加的是一个插件选项页面的话，使用的应该是 `edit_plugins` 权限，当然也可以直接 `manage_options` 权限来控制访问插件和主题选项页面。

许多插件仍然使用用户等级系统（用从0到10的数字代表用户的权限），但是 WordPress 已经废弃了等级系统，不应该再被使用。所以使用权限系统，就不必去担心 WordPress 不再支持用户等级系统，并且如果想添加和使用自定义的权限，也只能使用权限系统。

检查用户的权限
-------

如果使用的插件或主题允许用户更改博客的数据（添加新的内容或编辑现有的内容等），那么我们就要检测当前用户是否有足够的权限来执行这些动作，这个时候我们可以使用 **[current\_user\_can()](https://blog.wpjam.com/function_reference/current_user_can/)** 这个函数：

```
if ( current_user_can( $capability ) ) {
//如果用户拥有 $capability 的权限时执行的动作。
}
```

此函数也可以接受一个可选的参数：postID，用来检查当前用户是否有权限对特定文章进行某种操作：

```
// 检测用户对 ID 为 $post_ID 的日志是否有编辑的权限
current_user_can( 'edit_post', $post_id );
```

还有另外一个函数：**[author\_can()](https://blog.wpjam.com/function_reference/author_can/)**，可以用来检查某个文章的作者是否具有一定的权限：

```
if ( author_can( $post, $capability ) ) {
// 如果文章 $post 的作者拥有 $capability 时执行的动作
}
```

函数 `author_can` 第一个参数可以是一个 $post 对象，或一个 Post ID。

添加自定义用户角色
---------

有时需要为插件添加新的用户角色，比方说，我们要编写一个新的相册插件，用户可以注册并上传照片到网站，但是我们不希望这些注册用户可以添加或修改网站上任何其他类型的内容（如文章或页面）。为了做到这一点，最好的办法就是添加一个新的自定义用户角色：

添加自定义用户角色用到的函数是：**[add\_role()](https://blog.wpjam.com/function_reference/add_role/)**，它会添加含有一组权限的一个新的用户角色，这里我添加一个叫做 'photo\_uploader' 的用户角色，它显示的名字是：'Photo Uploader'，它默认的权限是：'organize\_gallery'：

```
add_role( 'photo_uploader', 'Photo Uploader', array( 'organize_gallery' ) );
```

创建好用户角色之后，当一个用户创建，编辑或上传相册的时候，我们就可以使用 `current_user_can( 'organize_gallery' )` 来检查当前用户是否有权限了。

并且被赋予了这个角色的用户只可以 `organize_gallery` ，但不能 `edit_posts` 或 `publish_posts`，所以我们无需担心他会修改网站其他内容了。

要删除一个角色，使用 **[remove\_role()](https://blog.wpjam.com/function_reference/remove_role/)** 函数，比如当用户决定卸载插件时，就应该有一个选项让插件的用户可以删除这些自定义角色：

```
remove_role( 'photo_uploader' );
```

添加自定义用户权限
---------

如果我们想为现有用户添加权限该怎么办呢？继续我们的相册插件的例子，我们想让作者也有上传图片的权限，我们可以使用 **[add\_cap()](https://blog.wpjam.com/function_reference/add_cap/)** 函数：

```
//获取 "author" 的角色对象
$role = get_role( 'author' );

//为角色对象添加 "organize_gallery" 权限
$role->add_cap( 'organize_gallery' );
```

WordPress的权限类
-------------

我们已经讨论过了检查和添加权限，以及添加角色，这是管理 WordPress 用户权限最常用的函数。然而，正如这篇文章的标题包含“终极”二字一样，我们会介绍WordPress 用于角色和权限幕后工作的三个类，以及这些类提供的接口，我们可以在插件中进行高级权限管理。这三个类是：

*   WP\_Roles
*   WP\_Role
*   WP\_User

这三个类的源代码可以在 `wp-includes/capabilities.php` 中找到，源代码注释写得很详细，下面总结一下怎样使用这些类：

### WP\_Roles 类

WP\_Roles 是一般的角色管理类，当我们在插件中使用的时候，可以不用实例化一个新的对象，而是直接使用 WordPress 默认创建的一个全局对象 `$wp_roles`，可以在任何地方使用它，只要事先声明 `global` 即可：

```
global $wp_roles;
```

我们上面使用的函数 `add_role()` 和 `remove_role()` 实际上是 `$wp_roles->add_role()` 和 `$wp_roles->remove_role()` 的别名。因此，我们也可以直接使用 `$wp_roles` 对象添加和删除角色，例如：

```
global $wp_roles;
//添加新角色,和add_role()功能一样
$wp_roles->add_role( $role, $display_name, $capabilities )

//删除角色, 和remove_role()功能一样
$wp_roles->;remove_role( $role );
```

同样也可以使用这种方法得到一个角色：

```
global $wp_roles;

//通过角色名称得到一个角色,和get_role()功能一样
$wp_roles->get_role( $role );
```

还可以得到一个可用角色列表，含有角色的名称和角色的显示名称。这个对想为用户提供一个接口，改变权限分配时候非常有用的。

```
global $wp_roles;

//得到一个值列表包括 $role_name => $display_name
$roles = $wp_roles->get_names();
```

最后可以使用 `$wp_roles` 添加和删除权限，此对象几乎包括所有的角色和权限操作。

```
global $wp_roles;

//为角色$role添加权限$cap
$wp_roles->add_cap( $role, $cap );

//为角色$role删除权限$cap
$wp_roles->remove_cap( $role, $cap );

//例子
$wp_roles->add_cap( 'administrator', 'manage_galleries' );
$wp_roles->remove_cap( 'subscriber', 'view_galleries' );
```

### WP\_Role 类

这是一个非常简单的类，它的功能就是添加和删除权限。

```
//得到角色对象
$role_object = get_role( $role_name );

//为角色对象添加权限$cap
$role_object->add_cap( $capability_name );

//为角色对象删除权限$cap
$role_object->remove_cap( $capability_name );
```

### WP\_User类

这个类可以管理每个用户的角色和权限，这意味着可以为一个特定具体的用户分配多个角色，或者为当前用户添加特定的权限，不论他目前是什么角色。

首先需要获取用户对象来操纵它的角色和权限：

```
//通过用户ID得到用户对象
$user = new WP_User( $id );

//或者通过用户名
$user = new WP_User( null, $name );
```

我们可以通过用户ID或用户名得到一个用户对象。对于第二种方法，第一个参数必须是空的（`null`或空字符串），如：

```
//通过ID得到管理员对象
$admin = new WP_User( 1 );

//通过用户名得到管理员对象
$admin = new WP_User( null, 'admin' );
```

一旦得到了用户对象，就可以为这个用户的添加另一个角色，而无需修改他目前的角色，这意味着用户可以有多个角色：

```
$user->add_role( $role_name );
```

也可以使用 `remove_role()`，来为该用户删除某个角色：

```
$user->remove_role( $role_name );
```

还可以为该用户设置一个角色，这意味着该用户将被删除当前所有的角色，并分配一个新的角色：

```
$user->set_role( $role_name );
```

对于权限操作，也有很多的方法来做各种事情：

```
//检查该用户是否具有某种权限或角色名称
if ( $user->has_cap( $cap_name ) ) {
    //做一些事
}

//为用户添加权限
$user->add_cap( $cap_name );

//为用户删除权限
$user->remove_cap( $cap_name );

//删除用户所有权限
$user->remove_all_caps();
```