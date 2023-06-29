---
layout: post
title: GitHub 折腾笔记
categories: GitHub
date: 2023-06-29
permalink: github-debug
excerpt: GitHub 折腾笔记
---

## 如何使用git命令

安装git

在指定文件夹下右键选择 *Git Bash Here* 弹出命令交互页面，输入命令

## 回滚到指定commit的sha码

回滚后本地文件将更新为 GitHub 中指定版本的状态

```
git reset --hard commit_sha
```

## 如何查看commit_sha

在 GitHub Code 标签页点击左侧文件列表顶部右侧 XXXX commits

从列出来的更新记录中右侧可直接复制此代码

## 将本地内容推送到 GitHub

```
git push -f
```

## fatal: unable to access : Recv failure: Connection was reset

可能是代理模式问题，尝试关闭代理或挂全局代理


## 清除代理设置

```
git config --global --unset http.proxy
git config --global --unset https.proxy

```

***

# 其它抄来的

## 常用命令

| 功能                      | 命令                                  |
|:--------------------------|:--------------------------------------|
| 添加文件/更改到暂存区     | git add filename                      |
| 添加所有文件/更改到暂存区 | git add .                             |
| 提交                      | git commit -m msg                     |
| 从远程仓库拉取最新代码    | git pull origin master                |
| 推送到远程仓库            | git push origin master                |
| 查看配置信息              | git config --list                     |
| 查看文件列表              | git ls-files                          |
| 比较工作区和暂存区        | git diff                              |
| 比较暂存区和版本库        | git diff --cached                     |
| 比较工作区和版本库        | git diff HEAD                         |
| 从暂存区移除文件          | git reset HEAD filename               |
| 查看本地远程仓库配置      | git remote -v                         |
| 回滚                      | git reset --hard 提交SHA              |
| 强制推送到远程仓库        | git push -f origin master             |
| 修改上次 commit           | git commit --amend                    |
| 推送 tags 到远程仓库      | git push --tags                       |
| 推送单个 tag 到远程仓库   | git push origin [tagname]             |
| 删除远程分支              | git push origin --delete [branchName] |
| 远程空分支（等同于删除）  | git push origin :[branchName]         |
| 查看所有分支历史          | gitk --all                            |
| 按日期排序显示历史        | gitk --date-order                     |


### 恢复单个文件到指定版本

```sh
git reset 5234ab MainActivity.java
```

### 查看某次 commit 的修改内容

```sh
git show <commit-hash-id>
```

### 查看某个文件的修改历史

```sh
git log -p <filename>
```

### 查看最近两次的修改内容

```sh
git log -p -2
```

