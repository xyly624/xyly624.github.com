---
layout: post
title: 试用 requests 库
category: Python
tags: [Python, example, requests]
keywords: Ubuntu,Python,requests,re,ip 
description: 试用 requests 库编写的简单例子
---

### 前提  

本文中需要使用到 [requests][1] ，可用 `pip install requests` 进行安装。  

*我在安装时碰到个问题，详见[上一篇][2] 博文。*

### 例子：获取外网 IP (返回 text 格式)   

主要代码如下：  

<script src="https://gist.github.com/xyly624/5195763.js" > </script>

### 例子：获取 IP 区域信息 (返回 json 格式)   

主要代码如下：

<script src="https://gist.github.com/xyly624/5195982.js"> </script>

Gist 引用后格式有点乱，请戳代码块下方的文件名查看正确版本。  

 *本文的環境爲 Utubut 12.04 , Python 2.7.3 , requests 1.1.0 。*   

[1]:https://github.com/kennethreitz/requests
[2]:http://xyly624.github.com/2013/03/09/python-nameerror
