---
title: 建立这个博客
date: 2018-08-09 09:38:58
description: 简单记录
categories:
- tech
tags:
- blog
- GitHub
- Hexo
---

## 前言

我的这个[“柯善康的博客”](https://www.shankangke.com/)是部署在GitHub上，托管在GitHub Pages上，通过Hexo程序生成静态文件。日常管理采用Git版本控制，也不必担心写废。

GitHub的公开库是免费的，GitHub Pages也免费提供二级域名，并且支持SSL部署。如果你不使用自己的独立域名，完全可以做到0成本运行一个博客。

## 基本知识

如果是小小白，可以先去了解一下：

- Git
- GitHub
- GitHub Pages
- Hexo
- Markdown

#### Git

关于Git，这里有一些资源：

- [Git网站](https://git-scm.com/)
- [Git中文书籍](https://git-scm.com/book/zh/)
- [Git简明指南](http://rogerdudler.github.io/git-guide/index.zh.html)

采用GitHub部署博客，只需简单了解Git即可。

#### GitHub

[GitHub](https://github.com/)是一个网站、远程仓库，用于托管Git仓库，今年6月被微软收购，截至本文发布时公开库仍然免费。我们部署博客不需要对GitHub了解太多。

#### GitHub Pages

GitHub上的库可以免费托管在GitHub Pages上，我们只需了解怎么操作即可。

#### Hexo

Hexo是一个使用Node.js编写的博客框架，简单、快速、高效、可扩展性强。

由于生成静态文件，所以通常情况下只要托管文件的服务器不出问题，就不存在安全问题。

[Hexo中文网站](https://hexo.io/zh-cn/)

#### Markdown

Markdown是一种轻量级标记语言，Hexo支持Markdown语法。关于Markdown的详细资料可以自行查询，我们这里只需要掌握如何使用Markdown即可。

这里有一些Markdown学习资源：

- [Markdown 语法说明(简体中文版)](https://www.appinn.com/markdown/)
- [Markdown - 中文维基百科](https://zh.wikipedia.org/wiki/Markdown)
- [献给写作者的 Markdown 新手指南 - 简书](https://www.jianshu.com/p/q81RER)
- [Markdown Guide](https://www.markdownguide.org/)

## 基本配置

### Git

#### 安装Git

一般情况下，Windows系统直接下载Git安装包即可：[Git官网下载](https://git-scm.com/downloads)

#### 配置Git

安装完Git之后，需要配置用户名和邮箱地址，因为Git提交需要这些信息，且这些信息会写入提交无法更改。

使用以下命令配置用户名和邮箱地址（把example_username替换为你的用户名、把example_email@example.com替换为你的邮箱地址）：

```
git config --global user.name "example_username"
git config --global user.email "example_email@example.com"
```

### GitHub

#### 创建GitHub账户

打开[GitHub官网](https://github.com/)，注册就不用细说了吧～

#### 创建GitHub Pages仓库

要想使用GitHub Pages，需要创建对应的仓库。仓库不对应则无法使用。

GitHub Pages有两种类型：

1. User/Organization Pages
2. Project Pages

两种类型的具体区别可以查看官方文档：[User, Organization, and Project Pages](https://help.github.com/articles/user-organization-and-project-pages/)

简单介绍一下区别：

- User/Organization Pages