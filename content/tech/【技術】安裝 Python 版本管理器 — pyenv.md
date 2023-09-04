---
title: "【技術】pyenv Python 版本管理器"
date: 2023-09-04T14:29:13+08:00
draft: false
---

## 前言

pyenv 是 python 版本管理器，如果在電腦上會裝很多版本的 python ，就建議裝。

網上很多教學文，但每篇都寫得不太一樣，乾脆自己整理一篇來紀錄一下。

官方說明文件：https://github.com/pyenv/pyenv

## 安裝 pyenv

### 安裝 pyenv (mac os)
在 mac 可以使用 brew。

```shell
brew update
brew install pyenv
```

### 安裝 pyenv (Ubuntu)

在 ubuntu 不建議使用 apt-get ，抓不到最新版，建議使用 git clone 抓。

```shell
git clone https://github.com/pyenv/pyenv.git ~/.pyenv
```

## 設定環境

要設定環境變數，不然使用 pyenv 會沒反應。

實際設定可能會因套件更新而改變，建議參考文件說明的做法。

### 設定環境(以 MacOS、zsh 為例)

```shell
alias brew='env PATH="${PATH//$(pyenv root)\\/shims:/}" brew'
echo 'export PYENV_ROOT="$HOME/.pyenv"' >> ~/.zshrc
echo 'command -v pyenv >/dev/null || export PATH="$PYENV_ROOT/bin:$PATH"' >> ~/.zshrc
echo 'eval "$(pyenv init -)"' >> ~/.zshrc
exec "$SHELL"
```
### 設定環境(以 Ubuntu、bash 為例)

```shell
echo 'export PYENV_ROOT="$HOME/.pyenv"' >> ~/.bashrc
echo 'command -v pyenv >/dev/null || export PATH="$PYENV_ROOT/bin:$PATH"' >> ~/.bashrc
echo 'eval "$(pyenv init -)"' >> ~/.bashrc
echo 'export PYENV_ROOT="$HOME/.pyenv"' >> ~/.profile
echo 'command -v pyenv >/dev/null || export PATH="$PYENV_ROOT/bin:$PATH"' >> ~/.profile
echo 'eval "$(pyenv init -)"' >> ~/.profile
echo 'export PYENV_ROOT="$HOME/.pyenv"' >> ~/.bash_profile
echo 'command -v pyenv >/dev/null || export PATH="$PYENV_ROOT/bin:$PATH"' >> ~/.bash_profile
echo 'eval "$(pyenv init -)"' >> ~/.bash_profile
```

## 使用 pyenv

### 使用方法

- 方法： `pyenv install <版號>`
- 安裝 3.7.6： `pyenv install 3.7.6`
- 其他 python 版本：https://www.python.org/downloads/

### 設定指定路徑下的 python 版本

- 說明： 指定本目錄下使用的版本，通常一個專案，會設定一個版本。
- 方法： `pyenv local <版號>`
- 使用 3.7.6： `pyenv local 3.7.6`

### 設定全域的 python 版版

- 說明： 指定全域下(系統)的預設版本。
- 方法： `pyenv global <版號>`
- 使用 3.11.2： `pyenv global 3.11.2`

## 補充說明

- 其他方法
  - 可以看文件說明：https://github.com/pyenv/pyenv#switch-between-python-versions
- 確認有沒有安裝成功
  - 可以用 which python 或 which pyenv 檢查
  - 然後用 pip list 看看，應該是看到空空的(這個是系統 pip)

## 其他事項
- 參考：https://github.com/pyenv/pyenv
