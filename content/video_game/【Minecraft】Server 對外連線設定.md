---
title: "【Minecraft】Server 對外連線設定"
date: 2023-09-24T10:59:29+08:00
draft: false
---

## 從單人遊戲中，讓玩家加入

直接在遊戲中，開啟「開放遊戲」的選項。

缺點就是，必須開房人在遊戲中，才可以玩。少了開房人，遊戲就不能玩。

## 建立 minecraft server

普遍建議作法，也是比較硬核的方案。

## 使用巴友方案：Fastinstaller

沒有提供原始碼，感覺有點抖。

## 使用巴友方案：魷魚懶人包

沒有提供原始碼，需自行評估一下。

- 參考
    - https://forum.gamer.com.tw/C.php?bsn=18673&snA=183653&tnum=69&subbsn=11

## 使用 Docker 架設

[docker-minecraft-server](https://github.com/itzg/docker-minecraft-server)

支援模組。

適用於 Linux 環境架設，就是如果你有一台專門的伺服器主機，就可以用這方案。

- 參考
    - https://github.com/itzg/docker-minecraft-server

# 使玩家加入至區域網段

---

## 使用社區對外 IP

很看網路公司，我的公司就設定 DDNS 給我，但我不是很熟 DDNS 的設定。

很吃網路架設的觀念。

## 使用 VPN

很看網路設備，如果家中網路設備沒有支援，就只能找其他廠商的方案，也有點像是要用傳統 Hamachi 的做法。

## 使用 ****ZeroTier****

比較新一套的軟體，是款開源的軟體。

### 參考資料

[Minecraft Java版局域網多人連線教學，使用ZeroTier區域連線，正版盜版皆可](https://www.youtube.com/watch?v=YX9x5wKn-R0)

[ZeroTier, Inc.](https://github.com/zerotier)

## 使用 Hamachi

很久沒有更新網站了，Copyright的日期都沒有更新，也沒有提供軟體版號，更沒有提供更新日誌，感覺會有資安問題。

## 使用 DDNS

就針對浮動 IP 的解決方案，只要透過自定義的域名，就可以連上。

不過前提是，我的對外 IP 要是真實的，而且可以連上。

[超詳細解說！域名是什麼？浮動 IP 有解方？如何利用 noip 架設伺服器？伺服器架設教學《CC字幕》](https://www.youtube.com/watch?v=TgMkvKSO0mI)