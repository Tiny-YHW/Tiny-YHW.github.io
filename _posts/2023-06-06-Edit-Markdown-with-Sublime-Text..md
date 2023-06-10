---
layout: post
title: 用 Sublime Text 编辑 Markdown
categories: Markdown
date: 2023-06-06
---


## 需要插件
- MarkdownEditing
- MarkdownPreview
- LiveReload

## MarkdownEditing

[项目地址](https://github.com/SublimeText-Markdown/MarkdownEditing)
[使用说明](https://sublimetext-markdown.github.io/MarkdownEditing/usage/)

方便的在Sublime Text编辑Markdown文件的特殊格式
主题方案，高亮固定格式
kbd
### MarkdownEditing快捷键
- 插入链接。输入 mdl 然后按下Tab键
- 插入图片链接。输入 mdi 然后按下Tab键、win + shift + k
- 插入代码块。输入 mdc 然后按下Tab键
- 插入各级标题。 输入mdh1、mdh2、mdh3,分别对应一级标题、二级标题、三级标题。
- 更改标题级别。选中标题（包括'#'）,然后按下Ctrl + Number，Number 代表标题级别。
- Alt + B 加粗
- Alt + I 斜体
- Ctrl + R 跳转标题选择

### 命令
按Ctrl+Shift+P输入命令
切换自动链接URL折叠（可以使用URL快捷检索）
- MarkdownEditing: Toggle Automatic Link URL Folding
切换颜色主题
- MarkdownEditing: Select Color Scheme

## LiveReload
### 命令
设置网页自动刷新（可以从菜单Preferences-Package Settings-LiveReload-Plugins快捷选择）
- LiveReload: Enable/disable plugins
