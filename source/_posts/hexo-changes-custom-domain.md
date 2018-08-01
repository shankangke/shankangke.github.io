---
title: 解决Hexo部署之后改变GitHub自定义域名Custom Domain的问题
date: 2018-08-01 20:56:35
description: 分析并解决在GitHub部署Hexo后会自动改变自定义域名Custom Domain的问题。
categories:
- 技术
tags:
- GitHub
- Hexo
- Custom Domain
---

## 基本情况
把Hexo部署在GitHub，并且设置了自定义域名(Custom Domain)。
## 问题概况
每次Hexo部署完毕后，访问先前设置好的Custom Domain，都会提示404。
查看GitHub仓库(Repository)的设置(Settings)，发现自定义域名(Custom Domain)已经变成默认值（被清空）。
## 相关资料
查阅GitHub有关Custom Domain的文档得知：GitHub的自定义域名(Custom Domain)是通过master分支(branch)下的CNAME文件设置的。
## 原因分析
Hexo每次部署时，会先删除分支(branch)下的所有文件，再提交生成后的文件。在删除文件时，CNAME文件也被删除，造成自定义域名(Custom Domain)变成默认值（被清空）。
## 解决思路

1. 设置自定义域名(Custom Domain)，观察文件变动。
2. 使Hexo部署时模仿文件变动。

## 操作记录

1. 在GitHub仓库(Repository)的设置(Settings)页面，设置自定义域名(Custom Domain)为www.shankangke.com
2. 发现master分支(branch)下新建了一个CNAME文件
3. 查看CNAME文件内容，CNAME文件内容为先前设置的自定义域名(Custom Domain):www.shankangke.com
4. 在Hexo的source目录下新建一个CNAME文件，内容为自定义域名(Custom Domain):www.shankangke.com
5. 重新使用Hexo部署，问题解决。