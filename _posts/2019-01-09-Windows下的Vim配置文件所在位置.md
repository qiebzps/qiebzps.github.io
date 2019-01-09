---
layout : post
title : "Windows下的Vim配置文件所在位置"
date : 2019-01-09 23:40:00 +0800
tags: Vim Windows
---

今天在Windows上使用Vim时需要用到Vim的配置文件，对应在Linux下就是```~/.vimrc```这个文件，在Windows上打开Vim之后在命令行模式下输入```version```，回车就可以看得到了，如下：

![Windows下的Vim配置文件所在位置01.png][01]

如何查看环境变量```$HOME```，在命令行中执行以下命令，```set```的用法可以用```set/?```查看

```powershell
set HOME
```

[01]:{{site.url}}/images/Windows下的Vim配置文件所在位置01.png
