---
layout: post
title: Ubuntu下关闭笔记本自带摄像头
category: Ubuntu
tags: [Ubuntu, 技巧]
keywords: Ubuntu,camera,摄像头,modprobe,uvcvideo
description: Ubuntu下关闭笔记本自带摄像头
---
### 临时关闭
        sudo modprobe -rv uvcvideo # 卸载uvcideo驱动
        sudo modprobe -v uvcvideo # 安装uvcvideo驱动 

### 永久关闭
        sudo vim /etc/modprobe.d/blacklist.conf # 编辑,添加如下内容
            blacklist uvcvideo
