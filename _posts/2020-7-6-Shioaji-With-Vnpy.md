---
layout: post
title: 在 VNPY 上交易台灣股票、期貨
---

前言
==
[Shioaji]([https://www.](https://sinotrade.github.io/)) 是台灣證券市場上，首創 **跨平台** 的 Python API，提供**行情**、**交易**、**帳務**等功能，目前針對台灣股票、權證、期貨、選擇權，皆已上線運行。

| 支持項目   |   	|   	|   	|   	|
|:-:	|:---:	|---	|---	|---	|
|  功能分類 	| 委託交易  	| 行情提供  	|   帳務查詢	|  |
|  支援市場 	| 台灣證期權  | 海期(未開發)  	| 複委託(未開發)  	|   	|
| 支援平台  	| Windows 64bit  	| Liuux 64bit  	|  OSX(無下單)	|   	|
| 支援語言| Python>=3.6|C++(開發中)| C#(暫定)


為了示範 Shioaji API 的功能，而 [VNPY](https://github.com/vnpy/vnpy) 是基於 Python的開源量化交易系統開發框架，所以這邊會一步步的帶大家如何在自己的電腦上，使用VNPY 交易台灣的證券、期貨市場

環境建立
==
由於 VNPY 只支持 Python 3.7 64位元版本，所以先透過 Anaconda 建立 Python 環境

0. 下載、安裝 [Anaconda](https://www.anaconda.com/download/)。
[安裝教學](https://medium.com/python4u/anaconda%E4%BB%8B%E7%B4%B9%E5%8F%8A%E5%AE%89%E8%A3%9D%E6%95%99%E5%AD%B8-f7dae6454ab6)

1. 執行 Anaconda Prompt，並建立 Python 3.7 環境
    ```bash
    (base) D:\vnpy_demo>conda create -n vnpy_env python=3.7↩
    ```
    ![Andconda Install](https%3A//i.imgur.com/RKI11nV.png)  


2. 切換至 Python 3.7 環境
    ```bash
    (base) D:\vnpy_demo>conda activate vnpy_env↩
    (vnpy_env) D:\vnpy_demo>
    ```
3. 下載 VNPY-SHIOAJI 檔案，並使用 <font color=red> SinopacGateway </font> Branch

    * <font color=green>由於目前 VNPY 還未整併 Shioaji 所提交的合併申請，所以目前先從Shioaji專案庫安裝</font>

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

    <font color=green>Windows 請使用 install.bat</font>

    <font color=green>Linux 請使用 ./install.sh</font>

    <font color=green>OSX 請使用 ./install_osx.sh</font>

    ```bash
    (vnpy_env) D:\vnpy_demo\vnpy>install.bat
    ```



