---
layout: post
title:  "用AutoHotKey获取并输出当前日期"
date:   2020-07-18 03:41:11 +0800
tags:   AHK
---


经常会用到输出当前时间的情况，比如说写这篇文章的时候，但是输入法的
输出自己又不太满意--与自己需要的格式还是有区别，所以就用AHK实现一下。
 
```
^3::
FormatTime, OutputVar , YYYYMMDDHH24MISS, yyyy-MM-dd  hh:mm:ss +0800
clipboard = %OutputVar%
send, ^v
return
```

本来是参考了一个直接输出，但是被输入法给拦截了（类似自己手
动敲“年月日时间”，其中又有为了格式化加的字符“-”，在输出的时候就会
出现点问题，还发现会有漏字符的情况，所以就参考另外一篇文章将需要内容
传递给剪切板，直接Ctrl-v粘贴出来，就没有那么多异常了。

# 2020-07-18  17:34:09 更新：
在使用过程中发现点问题，上述解决办法是12小时制的，比如现在是17点，
输出的结果却是05点，查找[AutoHotKey 官方文档][03]之后修改如下：
```
^3::
clipboard = %A_YYYY%-%A_MM%-%A_DD% %A_Hour%:%A_Min%:%A_Sec% +0800
send, ^v
return
```

参考文章：
1. [AutoHotKey\|\|AHK\|\|获取当前日期时间][01]
2. [请问下AHK如何复制文件到剪切板呢？][02]
3. [AutoHotKey 官方文档][03]

[01]:https://blog.csdn.net/The_Time_Runner/article/details/84317066
[02]:https://www.zhihu.com/question/49411101/answer/466874158
[03]:https://wyagd001.github.io/zh-cn/docs/Variables.htm#date
