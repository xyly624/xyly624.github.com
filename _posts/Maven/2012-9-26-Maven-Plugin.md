---
layout: post
title: Maven插件 
category: Maven
tags: [Maven,插件]
keywords: Maven,Plugin,插件,目标,Goal
description: Maven的核心概念之一：插件.
---
Maven本质上就是一个插件框架，所谓的构建任务都是由插件来完成的。
当执行一条命令时，就是通过插件目标完成了一个任务。
即一个任务对应着一个插件目标，而每个插件含一个或多个目标。  

例如插件[Maven Help Plugin] [1]就有8个目标，当执行以下命令时：  
>  mvn help:system  

其实就是通过Help插件的system目标完成了列出系统变量的任务。

附上Maven插件查询学习网址：  
1.  GroupId: [org.apache.maven.plugins](http://maven.apache.org/plugins/index.html)  
2.  GroupId: [org.codehaus.mojo](http://mojo.codehaus.org/plugins.html) 


[1]:http://maven.apache.org/plugins/maven-help-plugin/
