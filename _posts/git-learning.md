---
layout: post
title:  "Git Learning Note"
date:   2025-11-30 20:00:00 +0800
categories: git learning
---

## 关于git

Git是一个开源的分布式版本控制系统，可以有效、高速地处理从很小到非常大的项目版本管理。GitHub是一个面向开源及私有软件项目的托管平台，因为只支持Git作为唯一的版本库格式进行托管，故名GitHub。（来自[Git工作流和核心原理](https://www.bilibili.com/video/BV1r3411F7kn/)）

## 一些帮助

- 练习git工具的网站：[Learn Git Branching](https://learngitbranching.js.org/?locale=zh_CN)
- 简易工作图解：Made By [Excalidraw Whiteboard](https://excalidraw.com/)

<!-- 
注意：下面这个图片链接是本地路径，发布到 GitHub Pages 后无法显示。
请将图片上传到仓库中（例如创建一个 assets/images 目录），然后修改路径为相对路径，例如：
![image-20251130195318238](/assets/images/image-20251130195318238.png)
-->
![image-20251130195318238](/images/image-20251130195318238.png)

- git下载地址：[Git](https://git-scm.com/)

## 初始化设置

```shell
cd xxx //进入项目文件夹

git config --global user.name xxx //设置用户名（名字带空格需加引号，例如"xxx xxx"）
git config --global user.email xxx //设置邮箱

git init //项目初始化（"git的所有记录均在隐藏文件夹 `.git` 里"）
```

**项目初始化后默认位于主分支里**

## 常用命令及文件

### git status

用于查询操作状态

### git add

用于将文件从工作区添加到缓存区

### git commit

用于提交

>Git 仓库中的提交记录保存的是你的目录下所有文件的快照，就像是把整个目录复制，然后再粘贴一样，但比复制粘贴优雅许多！Git 希望提交记录尽可能地轻量，因此在你每次进行提交时，它并不会盲目地复制整个目录。条件允许的情况下，它会将当前版本与仓库中的上一个版本进行对比，并把所有的差异打包到一起作为一个提交记录。Git 还保存了提交的历史记录。这也是为什么大多数提交记录的上面都有 parent 节点的原因 —— 我们会在图示中用箭头来表示这种关系。对于项目组的成员来说，维护提交历史对大家都有好处。关于提交记录太深入的东西咱们就不再继续探讨了，现在你可以把提交记录看作是项目的快照。提交记录非常轻量，可以快速地在这些提交记录之间切换！

```shell
git commit //进入vim里编辑提交信息
git commit -m "xxx" //引号里写入简短的提交信息
git commit -a -m "xxx" //" 简写 `git add` "
git commit -am "xxx" //" 简写 `git add` 以及 `-m` "
```

### git log

用于查看前面版本

### git branch

用于创建新分支

```shell
git branch xxx //创建新分支
git branch //可用于查询分支
git branch -d xxx //删除分支
git branch -D xxx //强制删除分支
```

### git checkout

用于切换分支

```shell
git checkout xxx //切换至新分支
git checkout -b xxx //创建并切换至新分支
```

### git merge

用于把别的分支合并到当前所处分支

### git remote

用于查看本地仓库与那些远程仓库有联系

```shell
git remote -v
```

默认用**origin**来表示远程仓库的名字，方便在`push` 时替代`url`

### git fetch

用于将远程仓库拉取到本地版本仓库

### git diff

用于知晓本地版本库与远程仓库的区别

```shell
git diff <远程仓库名>/<分支名>
```

### git pull

用于将远程仓库的内容整合至本地工作区

### gitignore文件

用于忽略提交文件

可用 `touch .gitignore` 命令创建

## 远程

- 用 `git clone <url>` 来克隆远程项目

- `git push` 时用 `TOKEN` 连接而非**密码**

## VS Code 与 Git 和 GitHub

- 左侧栏点击初始化按钮来初始化git，相当于`git init`

- "+"号相当于 `git add` ，"-"号相当于取消

- 在commit栏输入提交信息并提交→`git commit`

### 创建新分支

- 顶部三个点→Branch→Create Branch→在弹出的提示框中输入新分支名即可

- 创建成功后会直接切换至新分支

### 合并分支

- 左下角选择分支，切换回主分支
- 顶部三个点→Branch→Merge Branch→选择需合并分支

### 提交

- 点击**Publish Branch**提交

- 进行授权和输入用户名及密码

## 鸣谢

- [技术蛋老师的B站视频](https://www.bilibili.com/video/BV1r3411F7kn)
