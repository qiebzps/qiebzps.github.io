---
layout: post
title:  "GitHub+Jekyll创建个人博客"
date:   2018-11-25 19:49:00 +0800
tags:   GitHub Jekyll 博客
---
折腾了好半天，现在记录一下。我自己的机器是Ubuntu，所以请在Linux环境下尝试以下步骤。
1. 在[GitHub][github]上创建一个[GitHub Pages][github_pages]
官方的安装过程很详细，也很简单，请参看[GitHub Pages][github_pages]。

2. Jekyll安装
	> Jekyll 是一个简单的博客形态的静态站点生产机器。

	Jekyll可以让我们专注于博客内容本身而不是花时间在管理上。

	详细安装过程可参看Jekyll安装文档(https://jekyllrb.com/docs/installation/ubuntu/)

3. 用Jekyll管理GitHub Pages

主要是这第3步让我做了一遍又了遍，不是因为它难，只是因为我不懂。

* 将你的仓库克隆到本地
``` shell
git clone https://github.com/username/username.github.io
```
* 应用Jekyll
``` shell
cd username.github.io
jekyll new ./
```
* 上传
``` shell
git add --all
git commit -m "Initial commit"
git push -u origin master
```
* 完成

[github]: https://github.com
[github_pages]: https://pages.github.com
