---
layout: post
title: Markdown Cheat Sheet 
category: Jekyll
tags: [Jekyll,Markdown]
keywords: github,pages,jekyll,markdown
description: Markdown基本语法.
---

### 标题
    # 标题1 
    ## 标题2 
    ### 标题3 
    #### 标题4 
    ##### 标题5 

### 字体
    _斜体_  
    *斜体* 

    __粗体__
    **粗体**

    *斜__粗__组合*

### 无序列表
    * 项目1
    - 项目2
    + 项目3
        * 子项1
        * 子项2
	* 项目4

### 有序列表
	1. 项目1
	2. 项目2
	3. 项目3
	    1. 子项1
	    2. 子项2
    4. 项目4

### 链接
    [Google HK](http://www.google.com.hk/ "Google HK") 
    [GitHub] [1] 

    <http://www.taobao.com>
    <test@test.com>

    [1]:https://github.com

### 图片
    ![site ico](/favicon.ico "favicon ico") 
    ![site ico][id]
    [id]: /favicon.ico  "favicon ico"

    ![Google Logo](http://www.google.com.hk/intl/zh-CN/images/logo_cn.png) 

    ![Google Logo][googlelogo]

    [googlelogo]: http://www.google.com.hk/intl/zh-CN/images/logo_cn.png

### 引用
    > 《老子》：道可道，非常道。

### 代码
    连续3个`符号: 
	 ```
	    function Hello(){
		     alert("Hello!");
		}
	 ```
	 连续4个空格:
	 function Hello(){
	     alert("Hello!");
	 }

	 内嵌代码用单个`符号:
	 Python代码：`print "Hello!"`


### 表格
    | 列1  | 列2   | 列3   |
    | :---- | :----: | ----: |
    |  11  |  12  |   13  |
    |  21  |  22  |   23  |

    外框为可选。
    冒号用于对齐：左或右,左右都有为居中

### 脚注
    脚注[^1]需要有一个 标签[^2]及一个 定义[^3]。

    [^1]: 这个一个脚注。
    [^2]: 这是脚注的标签。
    [^3]: 这里定义了脚注的内容。

### 段落和换行
    段落分割：由空行区分；
    换行：行尾加两个空格后再按回车键；

### 转义符: \
    在以下符号前添加可转义：
    \   反斜杠
    `   反引号
    *   星号
    _   下划线
    {}  大括号
    []  中括号
    ()  括号
    #   井号
    +   加号
    -   减好
    .   英文句号
    !   感叹号

