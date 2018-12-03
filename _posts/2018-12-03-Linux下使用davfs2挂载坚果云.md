---
layout: posted
title: "Linux下使用davfs2挂载坚果云"
date:  2018-12-03 13:56:00 +0800
---

主要参看了Uranus Zhou的[解决Linux下使用davfs2挂载坚果云的问题][1]这篇文章，Uranus Zhou在其中分析了其中的问题，查看了davfs2的源码解决了问题，我暂时没有这个能力。只知其然，若想知其所以然，请自行前往。感谢Uranus Zhou。我在这里只说一下如何做。
1. 安装davfs2
	sudo apt install davfs2
2. 修改/etc/davfs2/davfs2.conf
	#去掉注释并将0置为1
	ignore_dav_header 1
3. 挂载坚果云
	#也可以挂载到其他地方
	mount -t davfs https://dav.jianguoyun.com/dav /mnt
	#之后输入帐号和应用密码就可以了
