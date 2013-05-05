---
layout: post
title: Datatables + Bootstrap 组合基础示例 2
category: code
tags: [code, web, Datatables, Bootstrap,runjs]
keywords: Datatables, Bootstrap, example, runjs,sco
description: Datatables 使用 Bootstrap 框架的基本示例，包含的功能：分頁、排序、過濾、json 数据源、数据导出 (需 flash 支持) 、 自定义列 、 自定义分页选项。
---
### 前言  
示例 1 请见[上一篇博文][1]。

### 示例 2  
Datatables 插件使用 Bootstrap 框架的组合示例。  
##### 功能  
分页 / 排序 / 过滤 / json 数据源 / 数据导出 (需 flash 支持) / 自定义列 / 自定义分页选项。  

##### 代码  
不多说，详细代码请[戳][2]，界面效果请[戳][3]。

##### 使用的插件  
* [jQuery][4]
* [Bootstrap][5]
* [Datatables][7]
* [TableTools][8]
* [Datatablsables Plugins][9]
* [sco][10]

###說明：  
1. 示例中的數據引用自 [Datatables][7]。  
2. 示例的代碼使用了 [runjs][11] 的服務。  
3. 由于数据导出及打印功能需 Flash 支持，而 [runjs][11] 不能上传 Flash,所以示例中删除了该功能的演示。请参考[TableTools][8] 自行添加。

[1]:http://xyly624.github.io/2013/04/30/code-datatables-example-1/
[2]:http://runjs.cn/detail/eufiyjvh
[3]:http://sandbox.runjs.cn/show/eufiyjvh
[4]:http://jquery.com/
[5]:https://github.com/twitter/bootstrap
[7]:http://www.datatables.net/
[8]:http://datatables.net/extras/tabletools/
[9]:https://github.com/DataTables/Plugins
[10]:https://github.com/terebentina/sco.js
[11]:http://runjs.cn/
