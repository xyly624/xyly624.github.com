---
layout: post
title: 設置一個支持多種版本的 Python 環境
category: Pythoh
tags: [Ubuntu, Python, 開發]
keywords: Ubuntu,Python,pythonz,多版本,vim,pip,virtualenv,virtualenwrapper,Pypy
description: 在 Ubuntu 下設置一個支持多種版本的 Python 環境.
---
### 起因
爲了以下目的才有了本文：  
1. 學習 Python 3 。
2. 使系統 Python 環境不再受污染。

### 前提
配置過程中需要用到以下軟件：  
* Python 2.7.3 ( 通過`python -V`確認 )  
* pip ( 通過 `pip help`確認 )  
* curl ( 通過 `curl --help` 確認 )  
* libsqlite3-dev ( 可選，若要 Python 支持 sqlite3 ，請先安裝 `sudo apt-get instll libsqlite3-dev` )

若未安裝請參考 [Google][1] 安裝後繼續。  

### 安裝 Pythonz

[Pythonz][2] 可以讓用戶在 $home 目錄下通過源碼自動構建和安裝多種版本的 Python ，其源自 
[pythonbrew][3] 。個人覺得 [Pythonz][2] 功能簡單就幫你安裝各種版本的 Python ，至少目前是這樣。  

安裝步驟如下：  

    # 默認安裝在 ~/.pythonz 下  
    curl -kL https://raw.github.com/saghul/pythonz/master/pythonz-install | bash
    # 配置 ~/.zshrc ( zsh用戶，就像我 ) 或 ~/.bashrc （ bash用戶 ）
    echo "[[ -s $HOME/.pythonz/etc/bashrc ]] && source $HOME/.pythonz/etc/bashrc" >> ~/.zshrc

### 安裝 Python

通過 [Pythonz][2] 安裝各種 Python :  
    
    # 查看支持的 Python
    pythonz list -a
  
    # 安裝 Python 2.7.3  
    pythonz install 2.7.3    

    # 安裝 Python 3.3.0  
    pythonz install 3.3.0  

    # 安裝 Pypy 1.9
    pythonz install -t pypy --url https://bitbucket.org/pypy/pypy/downloads/pypy-1.9-linux.tar.bz2 1.9
    
    # 查看已安裝的 Python
    pythonz list

詳細命令請見`pythonz help` 或 [pythonz][2] 。

### 安裝 virtualenv 和 virtualenvwrapper

[virtualenv][4] 用於隔離 Python 環境，而 [virtualenvwrapper][5] 爲前者提供了一些命令上的封裝方便使用。 

安裝步驟如下：  

    # 安裝 virtualenvwrapper ，會自動安裝依賴 virtualenv  
    sudo pip install virtualenvwrapper  

    #配置 ~/.zshrc 或 ~/.bashrc  
    echo "source /usr/local/bin/virtualenvwrapper.sh" >> ~/.zshrc   

### 創建 Python 環境

通過 [virtualenvwrapper][5] 的命令 `mkvirtualenv` 命令創建不同版本的乾淨的獨立 Python 環境。

創建三個版本的 Python 環境:

    # 針對 Python 2.7.3   
    mkvirtualenv -p ~/.pythonz/pythons/CPython-2.7.3/bin/python cpython273 && deactivate  

    # 針對 Python 3.3.0  
    mkvirtualenv -p ~/.pythonz/pythons/CPython-3.3.0/bin/python3 cpython330 && deactivate

    # 針對 Pypy 1.9  
    mkvirtualenv -p ~/.pythonz/pythons/PyPy-1.9/bin/python pypy19 && deactivate  

以上環境基本沒有任何包 ( Python 2.7.3 和 pypy 1.9 會有個 wsgiref 包, Python 3.3.0 會有個 distribute 包 ) ；
默認都支持 `pip` 和 `easy_install` 工具。 可通過 `pip freeze` 命令查看當前環境安裝的包。

### 使用 Python 環境

個人使用 Python 環境流程：  
  
    # 查看當前擁有的環境
    lsvirtualenv

    # 從之前建立的 Python 環境中複製一個過來用於學習或開發；
    # 基本上不會在那三個基礎環境安裝任何東西。
    # 複製後會自動切換進複製後的 Python 環境 ( 如下爲： cpython273_test ) 
    cpvirtualenv cpython273 cpython273_test

    # 查看當前 Python 版本
    python -V

    # 查看當前環境已安裝的包
    pip freeze

    # 安裝 Django
    pip install django

    # 再次查看 
    pip freeze

    # 退出當前虛擬環境返回系統環境
    deactivate

想瞭解 virtualenvwrapper 更多信息，請參考 [virtualenvwrapper 文檔][6] 。

 *本文在 Utubut 12.04 下配置成功。*    

### 附：配置快捷命令

配置快捷命令，如下爲 zsh 中的，bash 請參考 [Google][1] ：  
  
<pre class="prettyprint linenums">
# 編輯 ~/.zshrc 新增以下內容
alias v='workon'
alias v.ls='lsvirtualenv'
alias v.cp='cpvirtualenv'
alias v.quit='deactivate'
alias v.mk='mkvirtualenv'
alias v.rm='rmvirtualenv'
alias v.switch='workon'
</pre>

[1]:www.google.com.hk
[2]:https://github.com/saghul/pythonz
[3]:https://github.com/utahta/pythonbrew
[4]:https://pypi.python.org/pypi/virtualenv
[5]:https://pypi.python.org/pypi/virtualenvwrapper
[6]:http://virtualenvwrapper.readthedocs.org/en/latest/
