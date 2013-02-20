---
layout: post
title: 單用戶環境下使用本地Git倉庫的操作步驟
category: Git
tags: [Git]
keywords: git,local repository,file system
description: 單用戶環境下通過本地Git倉庫來備份資料。
---

本文僅記錄了在本地使用Git庫地操作步驟，我將對該操作步驟的兩種使用情況分別說明：  
1. 新項目：先建本地git庫後建項目；  
2. 舊項目：先有項目後建本地git庫。  

_本文所說本地git庫類似分佈式環境下的服務器端的git庫，只不過存儲在本地而已。操作系統環境爲Ubuntu 12.04_。

###新項目
<pre class="prettyprint linenums">
# 新建本地git庫
# 切換至home目錄
cd ~
# 切換至bak目錄下    
cd bak
# 創建本地git庫目錄   
mkdir test.git
# 切換至test.git目錄
cd test.git
# 初始化本地git庫
git init --bare 

# 新建項目
# 切換至home目錄
cd ~
# 切換至work目錄
cd work
# clone git庫
git clone file:///home/user/bak/test.git
# 切換至test下
cd test
# 新建文件：README
echo "Hello Git" >> README
# 提交
git add README
git commit -m "new file:README"
git push origin master
</pre>

###舊項目
<pre class="prettyprint linenums">
# 新建項目庫
# 切換至home目錄
cd ~
# 切換至work目錄
cd work
# 創建項目: old
mkdir old
# 切換至old目錄
cd old
# 新建文件：README
echo "Hello Git" >> README
# 初始化爲git庫
git init
# 提交
git add README
git commit -m "init proejct"

# 新建git庫
# 切換至home目錄
cd ~
# 切換至work目錄
cd work
# 通過項目庫生成本地git庫
git clone --bare old old.git
# 移動至～/bak目錄下
mv old.git ~/bak/

# 給項目添加git庫地址
cd ~/work/old
git remote add origin  file:///home/user/bak/old.git
# 或者
cd ~/work
rm -rf old
git clone file:///home/user/bak/old.git
</pre>