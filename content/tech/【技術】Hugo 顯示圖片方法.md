---
title: "【技術】Hugo 顯示圖片方法"
date: 2023-09-24T12:11:24+08:00
draft: false
---

### 說明

圖片應該要放在哪裡，取決於使用的 template。

這邊是以 [hugo-coder](https://github.com/luizdepra/hugo-coder) 為例來說明。

圖片就放置在 static 這個資料夾。

Hugo 檔案目錄

```
├── config.toml
├── content
├── README.md
├── static <------------- 檔案都放在這裡
└── themes
```

### 自己習慣

會在加一層跟文章標題相同的資料夾，方便做檔案管理。

- 在 vs code 預覽檢視
  - 結構：`![Alt text](</文章標題/檔名>)`
- 本地端 server 運行
  - `![Alt text](</文章標題/檔名>)`
- 部屬端 server 運行
  - `![Alt text](<repo 名稱/文章標題/檔名>)`

