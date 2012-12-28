---
layout: post
title: 將HOME目錄下的默認目錄該爲英文目錄的方法
category: Ubuntu
tags: [Ubuntu, 技巧]
keywords: Ubuntu,目錄,中文,英文,python,freedesktop.org
description: Ubuntu下修改HOME目錄下的中文目錄爲英文目錄的方法
---

Ubuntu中文語言安裝後，HOME下的默認目錄均爲中文，例如：下載、文檔、視頻、音樂、圖片等。因爲需要切換輸入法，在Shell中切換目錄不是很方便。而通過[freedesktop.org][1]推出的工具[xdg-user-dirs][2] 可將目錄改爲英文目錄。    
#####在終端輸入以下命令：
<pre class="prettyprint linenums">
   export LANG=en_US
   xdg-user-dirs-gtk-update
   #此時會彈出配置界面，提升將目錄從中文該爲英文；
   #選中"不再提示"，並確定。
   #若中文目錄爲空則會刪除，若有文檔則會保留。
   #創建默認的英文目錄
   export LANG=zh_CN.UTF-8
</pre>
Ubuntu 12.04 下測試通過，其他版本未知。

[1]: http://www.freedesktop.org/
[2]: http://www.freedesktop.org/wiki/Software/xdg-user-dirs
