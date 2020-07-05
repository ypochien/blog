---
layout: post
title: 在 VNPY 上交易台灣股票、期貨
---

前言
==
[Shioaji]([https://www.](https://sinotrade.github.io/)) 是台灣證券市場上，首創 **跨平台** 的 Python API，提供**行情**、**交易**、**帳務**等功能，目前針對台灣股票、權證、期貨、選擇權，皆已上線運行。

| 支持項目   |   	|   	|   	|   
|:-:	|:---:	|:---:	|:--- |:---:	
|  功能分類 	| 委託交易  	| 行情提供  	|   帳務查詢	|  
|  支援市場 	| 台灣證期權  | 海期(未開發)  	| 複委託(未開發)  	|   	
| 支援平台  	| Windows 64bit  	| Liuux 64bit  	|  OSX(無下單)	|   	
| 支援語言| Python>=3.6|C++(開發中)| C#(暫定)


為了示範 Shioaji API 的功能，而 [VNPY](https://github.com/vnpy/vnpy) 是基於 Python的開源量化交易系統開發框架，所以這邊會一步步的帶大家如何在自己的電腦上，使用VNPY 交易台灣的證券、期貨市場

Python環境建立
==
由於 VNPY 只支持 Python 3.7 64位元版本，所以先透過 Anaconda 建立 Python 環境

0. 下載、安裝 [Anaconda](https://www.anaconda.com/download/)。
[安裝教學](https://medium.com/python4u/anaconda%E4%BB%8B%E7%B4%B9%E5%8F%8A%E5%AE%89%E8%A3%9D%E6%95%99%E5%AD%B8-f7dae6454ab6)

1. 執行 Anaconda Prompt，並建立 Python 3.7 環境
    ```bash
    (base) D:\vnpy_demo>conda create -n vnpy_env python=3.7↩
    ```
    ![Andconda Install](https://i.imgur.com/RKI11nV.png)


2. 切換至 Python 3.7 環境
    ```bash
    (base) D:\vnpy_demo>conda activate vnpy_env↩
    (vnpy_env) D:\vnpy_demo>
    ```

VNPY安裝
==
3. 下載 VNPY-SHIOAJI 檔案，並使用 SinopacGateway branch

    * 由於目前 VNPY 還未整併 Shioaji 所提交的合併申請，所以目前先從Shioaji專案庫安裝

    ```bash
    (vnpy_env) D:\vnpy_demo>
    (vnpy_env) D:\vnpy_demo>git clone https://www.github.com/ypochien/vnpy
    Cloning into 'vnpy'...
    warning: redirecting to https://github.com/ypochien/vnpy.git/
    remote: Enumerating objects: 37726, done.
    remote: Total 37726 (delta 0), reused 0 (delta 0), pack-reused 37726R
    Receiving objects: 100% (37726/37726), 201.65 MiB | 4.60 MiB/s, done.
    Resolving deltas: 100% (25358/25358), done.
    Updating files: 100% (1882/1882), done.

    (vnpy_env) D:\vnpy_demo\vnpy>git checkout SinopacGateway
    Switched to a new branch 'SinopacGateway'
    Branch 'SinopacGateway' set up to track remote branch 'SinopacGateway' from 'origin'.

    (vnpy_env) D:\vnpy_demo\vnpy>
    ```
4. 進行安裝 VNPY，這部分安裝會需要一點時間

    * Windows 請使用 install.bat

    * Linux 請使用 ./install.sh

    * OSX 請使用 ./install_osx.sh

    ```bash
    (vnpy_env) D:\vnpy_demo\vnpy>install.bat
    ```

VNPY執行
==
5. 執行 VNPY
    ```bash
    (vnpy_env) D:\vnpy_demo\vnpy>python examples\vn_trader\run.py
    ```
    * 選擇 Sinopac 登入
    
        ![picture 3](https://i.imgur.com/5CfOXxR.png)  
    * 輸入登入資訊(使用測試環境)
        
        ![picture 1](https://i.imgur.com/wR7ag1L.png)  
    
    * 開始使用
        ![picture 2](https://i.imgur.com/0nnWqhj.png)  

補充說明
==
* 如何在 VNPY 訂閱報價
  * 選擇 TSE (台灣證券交易所) 和股票代碼(2330) Enter 可訂閱台積電
  * 選擇 TFE (台灣期貨交易所) 和期貨代碼(TXFG0) Enter 可訂閱台指期07
  * 交易商品列表，可在 *查詢合約* 功能查詢!
    
    ![contracts](https://i.imgur.com/hpnJrH3.png)
    ![picture 5](https%3A//i.imgur.com/Jpk0Gbn.png)  


* VNPY 功能
  * 可參考 run.py
    * GateWay 是下單管道
    * App 是屬於VNPY目前有實作的功能，例如 *行情紀錄*、*策略回測*、*演算法交易* 等等，細節請自行參考 VNPY 官方網站

Any Question?
==
有關於 [Shioaji](https://sinotrade.github.io/) 的任何提問或建議，歡迎至[Github Issue](https://github.com/Sinotrade/Shioaji/issues)中提出，
或者到 [GITTER](https://gitter.im/Sinotrade/Shioaji) 留言