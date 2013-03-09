---
layout: post
title: CERT_NONE is not defined
category: Pythoh
tags: [Python, 開發, requests]
keywords: Ubuntu,Python,pythonz,pip,virtualenv,virtualenwrapper,ssl,NameError,CERT_NONE,requests
description: NameError 的解決辦法
---

### 緣起
突然想學習下[requests][1]，不過在安裝[requests][1] 時卻報了這個錯誤：“NameError: name 'CERT_NONE' is not defined”。  
在[Googole][2]上搜索之後才知道，[requests] [1]需要 ssl 的支持，源碼編譯安裝的 [Python][3]若需要提供 ssl 的支持，在編譯前需要系統已安裝了 `libssl-dev` 庫。  
而我使用的是通過 [Pythonz][4]編譯安裝的[Python][3]，經驗證是未提供 ssl 的支持。（驗證方法見下文。）

### 解決方法
知道原因後就好辦了，解決方法如下：  
1. 在系統中安裝必要的庫：`sudo apt-get install libssl-dev` ；  
2. 刪除通過[Pythonz][4]安裝的 [Python][3]：`pythonz uninstall 2.7.3`；  *（詳細的安裝[Python][3]方法見[上一篇博文][5]）*  
3. 重新編譯安裝[Python][3]：`pythonz install 2.7.3`；  
4. 驗證 ssl ：`python -c "import ssl" `；（若未報錯即已支持；反之，請繼續[Google][2]，我也愛莫能助了。）  
5. 安裝 [requests][1]：`pip install requests` 。

希望對你有所幫助，特此分享之。

 *本文的系統環境爲 Utubut 12.04 。*   

[1]:https://github.com/kennethreitz/requests
[2]:www.google.com.hk/
[3]:http://www.python.org/ 
[4]:https://github.com/saghul/pythonz
[5]:http://xyly624.github.com/2013/03/05/support-multiple-versions-of-Python-environment/
