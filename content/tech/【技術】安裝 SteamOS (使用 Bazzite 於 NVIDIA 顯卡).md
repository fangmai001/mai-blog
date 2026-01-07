---
title: "【技術】安裝 SteamOS (使用 Bazzite 於 NVIDIA 顯卡)"
date: 2026-01-08T00:12:07+08:00
draft: false
---

# 緣起

- 2025 年 Steam OS 新聞
- 有客廳打電動需求，不想買 PS5 ，只想玩 PC

# 為甚麼要 SteamOS

- 大銀幕模式，仍有缺點，不能開機即玩，仍需要經過 Windows 登入

# NVIDIA 顯卡

- 預設情況下，SteamOS是沒有支援 NVIDIA 顯卡，只支援 AMD 顯卡
  - 聽說是因為 AMD 生態系較為開放，NVIDIA 較為封閉 (~~就像台灣半導體廠一樣封閉~~) 

# SteamOS

- 官方網站沒有提供桌面版 ISO ，只有 SteamDeck 的
- 但是 ISO 有開源，所以可以找其他人提供的版本安裝

# Bazzite

- 參考
  - https://www.youtube.com/watch?v=X2g2hofWNZ4
- 可以解決 SteamOS 不支援 NVIDIA 顯卡
- 就不會像 SteamOS 使用 Arch ，而是安裝 Fedora 作業系統
- 直接通過網站下載：https://bazzite.gg/#image-picker

![alt text](</mai-blog/【技術】安裝 SteamOS (使用 Bazzite 於 NVIDIA 顯卡)/image.png>)

- 要選下面的按鈕
  - 上面的，不會經過安裝設定，會直接進入系統，彷彿就像進入免安裝模式，
- 使用 Fedora Media Writer 燒錄安裝隨身碟
  - https://www.fedoraproject.org/workstation/download
  - 要仔細看 Fedora Media Writer 這個才對，我差點下載錯
- 使用隨身碟開機

![alt text](</mai-blog/【技術】安裝 SteamOS (使用 Bazzite 於 NVIDIA 顯卡)/IMG_4379.JPG>)

![alt text](</mai-blog/【技術】安裝 SteamOS (使用 Bazzite 於 NVIDIA 顯卡)/IMG_4380.JPG>)

- 成功


# 可能問題：硬碟尚未格式化

- 參考
  - https://www.reddit.com/r/LinuxOnAlly/comments/1ejfs15/device_is_active_when_installing_bazzite/
- 於 installer 按 CTRL + ALT + F1 進入終端機
- 輸入 `lsblk ` 顯示硬碟清單
- 輸入 `fdisk /dev/<你的硬碟名稱>` 進行格式化
- 格式化過程，會問問題，依序輸入 `p` 、 `d`、 `w` 即可

# 可能問題：安裝完成，無法進入系統

- 要去 BIOS 把安全模式關掉
- 我的主機板，沒找到安全模式，反而找到啟動設定，改成 Linux 即可

# 可能問題：畫面閃爍

- 沒查到其他人有跟我一樣問題，後來問 ChatGPT 有得到線索
- 開啟 Steam 側邊選單(鍵盤、手把按法很特殊，可自己查)
- 模式選「無」以外選項即可