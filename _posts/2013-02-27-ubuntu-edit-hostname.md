---
layout: post
title: 在Ubuntu下修改主機名
category: Ubuntu
tags: [Ubuntu, 技巧]
keywords: Ubuntu,hostname,主機名,service,vim
description: 修改Ubuntu系統的主機名
---
Ubuntu 12.04下修改主機名的步驟：  
1. 編輯hostname中的主機名：`sudo vim /etc/hostname`  
2. 編輯hosts中的主機名：`sudo vim /etc/hosts`  
3. 重啓hostname服務：`sudo service hostname restart`  
4. 驗證：`hostname`  

以上在Ubuntu 12.04 下測試通過。