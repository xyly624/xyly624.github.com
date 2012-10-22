---
layout: post
title: 解决Ubuntu下exaile中文乱码的问题
category: Ubuntu
tags: [Ubuntu, 技巧]
keywords: Ubuntu,exaile,中文,乱码,python
description: 解决Ubuntu下exaile中文乱码的问题
---
此方法仅针对exaile v0.3.2.2版本，测试成功。  
        exaile --version #查看版本号
        sudo vim /usr/lib/exaile/xl/metadata/_id3.py #修改代码  
原89行：`ret.extend([unicode(x.replace('\n','').replace('\r','')) \`  
现改为：`ret.extend([unicode(x.replace('\n','').replace('\r','')).encode('iso-8859-1').decode('gb18030') \`  

重新打开exaile，清空音乐库后再重新导入音乐即可。
