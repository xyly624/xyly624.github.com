---
layout: post
title: 在 Ubuntu 下安装 Sigil 
category: Ubuntu
tags: [Ubuntu, 技巧, epub]
keywords: Ubuntu,sigil,epub
description: 在 Ubuntu 下安装 epub 编辑器 Sigil 
---
最近购置了台 [kindle paperwhite][1] ，用下来感觉看书的效果真好。就是对有些书的格式不是很满意，为此想编辑下。  
网上搜了下发现此款 ePub编辑器：[Sigil][2]  。  

[Sigil][2] 的简单介绍：  
1. 一款免费开源的ePub编辑器  
2. 跨平台：windows、linux、Mac  
3. 完美支持UTF-16 ( 支持中文 )  
4. 界面支持多语言：支持简体中文及繁体中文  
详细的文档请访问 [Sigil][2] 。  

在此分享下在 Ubutnu  系统下的安装过程：  
1. 添加源：`sudo add-apt-repository ppa:rgibert/ebook`  
2. 更新源：`sudo apt-fast update`  
3. 安装：`sudo apt-fast install sigil`  
4. 启动：`sigil` 或 "应用程序 --> 附件 --> Sigil"  

说明：[apt-fast][3] 是 `apt-get` 的加速工具，利用 `axel` 或 `aria2c` 进行下载。  
 
 *以上在Ubuntu 12.04 下測試通過。*

[1]:http://www.amazon.com/Kindle-Paperwhite-Touch-light/dp/B007OZNZG0
[2]:https://code.google.com/p/sigil/
[3]:https://github.com/ilikenwf/apt-fast

