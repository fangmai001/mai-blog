---
title: "【技術】pipenv pip 套件管理器"
date: 2023-09-04T14:29:23+08:00
draft: true
---

## 前言

網上很多教學文，但每篇都寫得不太一樣，乾脆自己整理一篇來紀錄一下。
官方說明文件：https://github.com/pypa/pipenv

### pipenv 功能
- 虛擬環境功能
  - 就是用 virtualenvs。
  - 用法有點類似，建立一個虛擬 bash 環境。
  - 建立一個與系統環境獨立互不影響的環境，可以在這環境自由安裝新套件，而不會影響主環境的套件。
- 套件管理功能
  - 使用 pipfile 設定安裝的套件，。
  - 使用 Pipfile.lock 紀錄套件相依版本。

### 注意

如果要建立新的環境，只能基於在系統環境端擁有的 python 版本建立。

也就是說，如果電腦上沒有 python 3.7.6 就是不能建立 3.7.6 虛擬環境。

## 與 pyenv 搭配使用

### 以安裝 python 3.7.6 為例

```shell
pyenv install 3.7.6 ## 如果已經安裝了，可以省略該動作
pyenv local 3.7.6 ## 指定本地端的 python 版本

```

確認設定是否成功，可以用 `which python` 或 `python -V` 來看看。

## 安裝

### 安裝 pipenv

```shell
pip install pipenv
pip install --upgrade pip ## 可以的話，也跑一下升級
```

### 安裝虛擬環境

```shell
pipenv install
```

執行下去，他就會安裝虛擬環境了，可能會需要跑一段時間。

如果想確認環境是否安裝成功，可以使用： `pipenv run pip list`

### 安裝虛擬環境(建議)

```shell
pipenv sync
```

上述 `pipenv install` 這方法，並不會按照 Pipfile.lock 的套件相依版本來安裝，若是安裝運行較久的專案，就會發生套件版本不同，而無法運行專案的問題。

建議使用 `pipenv sync` ，這就會按照 Pipfile.lock 的套件相依版本來安裝，就可以「避免」上述問題。

這邊要強調「避免」，其實在 pipenv 有蠻多詬病的，所以後來就有出來 poetry 的用法，詳細介紹：https://blog.kyomind.tw/python-poetry/#pip-%E7%9A%84%E6%9C%80%E5%A4%A7%E4%B8%8D%E8%B6%B3。

### 進入虛擬環境

```shell
pipenv shell
```

### 執行虛擬環境指令

```shell
pipenv run <指令>
```

如果不想要進去虛擬環境，可以用這個。

舉例，我想要看虛擬環境下安裝了什麼套件： `pipenv run pip list`

### 刪除虛擬環境

```shell
pipenv --rm
```

刪除本目錄下的虛擬環境。
