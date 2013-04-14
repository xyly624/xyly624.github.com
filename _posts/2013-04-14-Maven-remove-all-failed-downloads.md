---
layout: post
title: Maven無法下載依賴時的解決方案
category: Maven
tags: [Maven, shell]
keywords: Maven, shell, 依賴, 技巧
description: 當 Maven 無法下載依賴包時的解決方案
---
今天在做個測試時，發現在 pom 文件內添加了一個新 jar 包的配置後報錯。  
第一反應是拼寫格式錯。但目測格式都正確，不得已只能從 [Maven 中央庫][1] 直接複製配置，錯誤還是存在。  
第二反應是 Maven 下載依賴失敗。進本地庫目錄查看果然只有 pom 文件存在，jar 包不存在。果斷架起梯子再次更新還是不更新 jar 包。映像中若目錄下存在"lastUpdated"後綴的文件代表更新失敗，但該目錄下沒有此類文件啊！奇怪了。翻開 [印象筆記][2] 找了下之前記錄下來的腳本，嘗試了下竟然成功了，說明**有相關依賴未成功下載導致該 jar 包不能下載** 。故特此分享下。  

bash 腳本（**該腳本來源於網絡**）：  

    #移除所有失敗的下載  
    find ~/.m2 -name "*.lastUpdated" -exec grep -q "Could not transfer" {} \; -print -exec rm {} \;  

*以上在Ubuntu 12.04 下測試通過。*

![Maven](https://lh6.googleusercontent.com/-r7pzJEQ8LBk/UWqmI1brbkI/AAAAAAAAAYU/bkDWSef-dvw/s414/s4524240.jpg)
  
[1]:http://search.maven.org/
[2]:http://www.yinxiang.com/
