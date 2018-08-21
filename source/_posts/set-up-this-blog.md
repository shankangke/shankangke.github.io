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

我的这个[“柯善康的博客”](https://www.shankangke.com/)是部署在 GitHub 上，托管在 GitHub Pages 上，通过 Hexo 程序生成静态文件。日常管理采用 Git 版本控制，也不必担心写废。

GitHub 的公开库是免费的， GitHub Pages 也免费提供二级域名，并且支持 SSL 部署。如果你不使用自己的独立域名，完全可以做到0成本运行一个博客。

## 基本知识

小小白们可以先去了解一下：

- Git
- GitHub
- GitHub Pages
- Hexo
- Markdown

#### Git

关于 Git ，这里有一些资源：

- [Git 网站](https://git-scm.com/)
- [Git 中文书籍](https://git-scm.com/book/zh/)
- [Git 简明指南](http://rogerdudler.github.io/git-guide/index.zh.html)

采用 GitHub 部署博客，只需简单了解Git即可。

#### GitHub

[GitHub](https://github.com/) 是一个网站、远程仓库，用于托管 Git 仓库，今年6月被微软收购，截至本文发布时公开库仍然免费。我们部署博客不需要对 GitHub 了解太多。

#### GitHub Pages

GitHub 上的库可以免费托管在 GitHub Pages 上，我们只需了解怎么操作即可。

#### Hexo

Hexo 是一个使用 Node.js 编写的博客框架，简单、快速、高效、可扩展性强。

由于生成静态文件，所以通常情况下只要托管文件的服务器不出问题，就不存在安全问题。

[Hexo 中文网站](https://hexo.io/zh-cn/)

#### Markdown

Markdown 是一种轻量级标记语言， Hexo 支持 Markdown 语法。关于 Markdown 的详细资料可以自行查询，我们这里只需要掌握如何使用 Markdown 即可。

这里有一些 Markdown 学习资源：

- [Markdown 语法说明(简体中文版)](https://www.appinn.com/markdown/)
- [Markdown - 中文维基百科](https://zh.wikipedia.org/wiki/Markdown)
- [献给写作者的 Markdown 新手指南 - 简书](https://www.jianshu.com/p/q81RER)
- [Markdown Guide](https://www.markdownguide.org/)

## 基本配置

### Git

#### 安装 Git

一般情况下， Windows 系统直接下载 Git 安装包即可： [Git 官网下载](https://git-scm.com/downloads)

#### 配置 Git

安装完 Git 之后，需要配置用户名和邮箱地址，因为 Git 提交需要这些信息，且这些信息会写入提交无法更改。

使用以下命令配置用户名和邮箱地址（把`example_username`替换为你的用户名、把`example_email@example.com`替换为你的邮箱地址）：

```
git config --global user.name "example_username"
git config --global user.email "example_email@example.com"
```

### GitHub

#### 创建 GitHub 账户

打开 [GitHub 官网](https://github.com/)，注册就不用细说了吧～

#### 创建 GitHub Pages 仓库

要想使用 GitHub Pages ，需要创建对应的仓库。仓库不对应则无法使用。

GitHub Pages 有两种类型：

1. User/Organization Pages
2. Project Pages

两种类型的具体区别可以查看官方文档： [User, Organization, and Project Pages](https://help.github.com/articles/user-organization-and-project-pages/)

简单介绍一下区别：

- User/Organization Pages 的源文件在`master`分支； Project Pages 的源文件在`gh-pages`分支。
- User/Organization Pages 通过`http(s)://<username/orgname>.github.io`访问； Project Pages 通过`http(s)://<username/orgname>.github.io/<projectname>`访问。
- User/Organization Pages 的仓库名称必须为`<username/orgname>.github.io`； Project Pages 的仓库名称没有特殊要求。
- 一个账户只能有一个 User/Organization Pages ，但却可以有很多 Project Pages 。

这里我直接使用了 User Pages ，创建一个名为`shankangke.github.io`的仓库。

### Node.js

#### nvm 安装(建议非 Windows 用户使用)

安装 Node.js 的最佳方式是使用 [nvm](https://github.com/creationix/nvm)

cURL 和 Wget 方式**任选一种**即可。

cURL:`curl https://raw.github.com/creationix/nvm/master/install.sh | sh`

Wget:`wget -qO- https://raw.github.com/creationix/nvm/master/install.sh | sh`

执行完成后，**重启终端**再执行该命令来安装 Node.js 稳定版:`nvm install stable`

#### 安装包安装(建议 Windows 用户使用)

*Windows 用户安装 Git 时会安装 Git Bash 。 Git Bash 提供了 Linux 风格的 shell ，所以可以直接用上面提到的命令通过 nvm 来安装 Node.js 。由于 Hexo 的很多操作都涉及到命令行，可以考虑始终使用 Git Bash 来进行操作。在任意位置单击右键，选择`Git Bash Here`即可打开 Git Bash 。

通过 [Node.js 官网](https://nodejs.org/)下载安装包，运行即可安装。**安装时，请勾选`Add to PATH`选项。**

### Hexo

所有必备的应用程序安装完成后，即可使用 npm 安装 Hexo 。

命令:`npm install -g hexo-cli`

安装 Hexo 完成后，请执行下列命令， Hexo 将会在指定的文件夹`<folder>`中新建所需要的文件，`<folder>`就是你期望的网站存放的地方。

```
hexo init <folder>
```

接着我们进入`<folder>`，并安装依赖。

```
cd <folder>
npm install
```

至此，我们已经成功完成了 Hexo 的安装，并初始化了本地的 Hexo 博客。更多设置可以查看 [Hexo 官方文档](https://hexo.io/zh-cn/docs/)

## 部署博客

之前，我们已经配置好了所需的所有东西，也成功地搭建并初始化了一个本地 Hexo 博客。但是，这个博客是本地的，别人无法访问。

现在，需要使用 GitHub Pages 搭建一个别人能够访问的 Hexo 博客了。

### 安装 Hexo 部署插件

由于我们是部署到 GitHub 上，所以我们需要安装的部署插件是`hexo-deployer-git`。

在我们之前的`<folder>`目录(即你的网站目录)下执行命令:`npm install hexo-deployer-git --save`

### 更改部署设置

更改之前`<folder>`目录(即你的网站目录)下的`_config.yml`文件。

和部署相关的设置，默认是这样的：

```
# Deployment
## Docs: https://hexo.io/docs/deployment.html
deploy:
  type:
```

我们需要以 Git 的方式，部署 Hexo 博客到我们的仓库`<username/orgname>.github.io`。

我的部署设置是这样的：

```
# Deployment
## Docs: https://hexo.io/docs/deployment.html
deploy:
  type: git
  repo: https://github.com/shankangke/shankangke.github.io.git
  branch: master
```

**请把`repo`参数更改为你自己的仓库地址！**

这里的`repo`参数可以是 HTTPS 地址，也可以是 SSH 地址。使用 HTTPS 地址需要每次输入 GitHub 的用户名和密码。使用 SSH 地址需要额外配置，但配置完成后不需要再输入 GitHub 的用户名和密码。

我这里为了安(tou)全(lan)使用的是 HTTPS 地址。

至此你已经完成了 Hexo 的部署设置，这个博客可以发布到公网了！

### 生成和部署

使用`hexo generate`命令，生成 Hexo 博客静态文件，生成的文件保存在之前`<folder>`目录(即你的网站目录)下的`public`目录中。

使用`hexo deploy`命令，部署刚刚生成的 Hexo 博客静态文件。

现在你可以打开浏览器，使用域名访问你的博客啦！

## 优化管理

刚刚我们通过命令部署的是生成后的静态文件(即 HTML 文件)，并没有提交源文件，源文件仍只保存在本地计算机。

什么意思？

就是说一旦你的电脑故障，或者是你更换电脑了，就无法再对你原来的博客进行任何更改。

再新建一个仓库来存放源文件又有些麻烦了。所以，我使用了分支。

### 部署

刚刚我们部署时，已经自动生成了`master`分支，我们只需要再新建一个分支用了存放源文件即可。

首先，在之前`<folder>`目录(即你的网站目录)的上一级目录中把刚刚的 Git 仓库克隆过来，执行`git clone <repo>`(把`<repo>`替换成你之前在配置文件中填写的 Git 仓库地址，比如我的 Git 仓库地址是`https://github.com/shankangke/shankangke.github.io.git`，那我就执行`git clone https://github.com/shankangke/shankangke.github.io.git`)。

克隆完毕后我们进入这个仓库目录，执行`cd <repo_name>`(把`<repo_name>`替换成你的仓库名称，比如我的仓库名称是`shankangke.github.io`，我就执行`cd shankangke.github.io`)。

接着，我们使用命令创建一个`hexo`分支(名字随便起，我这篇文章先按照这个分支名来写)，并切换到该分支：`git checkout -b hexo`

然后，把之前`<folder>`目录(即你的网站目录)下的文件全部复制过来，执行命令`cp -r ../<folder>/. ./`。

完成后，我们就打包并提交这个分支。依次(一行一行地)执行下列命令：

```
git add .
git commit -m "Set Hexo Up"
git push origin hexo
```

此时，你的 Hexo 网站源文件也已经提交到了 GitHub 的远程仓库，不再受单台电脑束缚，也不用担心文件意外丢失(只要你自己不去 GitHub 的远程仓库删除)。以后对网站进行改动，直接在此进行即可，`<folder>`目录(即你之前的网站目录)已经可以删除。

### 日常管理

当你在本地对网站进行了改动(比如新建或修改文章、更改主题模板等等)，按照下列步骤来保证你的更改能始终同步到 GitHub 的远程仓库，并能将网站正确发布。

改动完成后，在`hexo`分支，依次(一行一行地)执行下列命令：

```
git add .
git commit -m "Update Hexo"
git push origin hexo
```

此时，你的改动已经提交到 GitHub 的远程仓库。接下来，在当前目录执行`hexo g -d`即可生成并部署网站。

### 恢复

如果你的本地源文件不幸丢失，或者你换了一台新电脑，先确保已经达到了前文的基本配置(比如安装必要的环境软件等)，再按照下列步骤来找回你的源文件并恢复 Hexo 的正常功能。

首先，克隆仓库并切换到`hexo`分支，依次(一行一行地)执行下列命令：

```
git clone <repo>
cd <repo_name>
git checkout hexo
```

记得把`<repo>`替换成你的 Git 仓库地址，把`<repo_name>`替换成你的 Git 仓库名称。

这时，你已经把源文件找回，下面我们来恢复 Hexo 的正常功能。

依次(一步一步地)执行下列命令：

```
npm install -g hexo-cli
npm install
npm install hexo-deployer-git
```

至此，你的 Hexo 应该已经能够恢复使用了。尽情享受吧！

## 尾声

至此，正文内容已经结束，希望能够对你有所帮助！

这是我写过的最长的文章了，真的好累，终于体会到了那些大V们的不易。

如果你发现了这篇文章中存在任何错误，或者你有任何疑问、建议，都请与我取得联系。

我的邮箱地址是`shankangke@gmail.com`，期望收到你的来信，哪怕只是几句话。