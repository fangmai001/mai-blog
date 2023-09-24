---
title: "【技術】社區固定 IP 申請心得"
date: 2023-09-24T10:52:33+08:00
draft: true
---

# 緣起

一直以來都還蠻想要申請一個屬於自己的對外 IP，未來可以拿來做 server 或是自己架網站之類的。

碩士畢業後，搬回台中後，一直都是使用手機網路分享，後來決定投資些錢在網路架設方面(也不想要每次回家都要開手機分享)，所以決定買社區網路服務。

## 環境

這邊使用路由器(AP)，是使用 TP-Link MESH，使用的設定介面是 Deco APP。

## Step 0: 網路安裝

我找的網路業者是「亞太寬頻」。雖然印象中他們的網路不太好，但他們家的價格最合適，我們家用不到太快的網路([詳細心得](<mai-blog/tech/技術家用網速申請心得/>))。

決定好網路業者後，支付費用後，他們就會安排工程師前來拉網路線，安裝網路。

## Step 1: 路由器設定

網路業者會提供的網路設定資訊，照著這個設定，到路由器那邊設定就好了。

網路設定資訊，長得會像這樣：

```
IP位址: 172.XXX.XXX.XXX
子網遮罩: 255.255.0.0
預設閘道: 172.XXX.XXX.XXX
DNS: 168.XXX.XXX.XXX
DNS: 8.8.8.8
```

#### TP-Link 設定

![Alt text](</mai-blog/【技術】社區固定 IP 申請心得/A4CC1F5A-9B37-4A0D-80E7-918C506FC2D5.jpg>)

![Alt text](</mai-blog/【技術】社區固定 IP 申請心得/09EA2FFA-5206-427A-9E2A-2D38E80471A5.jpg>)

![Alt text](</mai-blog/【技術】社區固定 IP 申請心得/4401F494-5686-46AE-8EC4-854A65F7BA11.jpg>)

## Step 2: 申請對外IP

我的們社區沒有固定 IP 可以分給我用，所以他開指定的 DDNS 跟對外 port。

對外網路資訊，長得會像這樣：

```
DDNS: 250.XXXXX.tw
對外 port: 6600
```

#### DDNS 說明

- 由於這個社區沒有固定對外 IP ，所以使用 DDNS 來對接浮動 IP。
- 網路業者會提供我一個 DDNS Domain Name，這個就是我的 IP。

#### 對外 PORT 說明

- 網路業者有提供一組 PORT 號，這就是對外的 port 號，伺服器也要用這個 port 號做設定

## Step 3: 設定對外IP

這邊，我們要做的設定，是要告訴網路業者，我家的對外網路，預設是要導入到某某台電腦。

這裡的設定，就要去路由器那裏設定了。

分別有「位址保留」、「通訊阜轉發」要設定

#### TP-Link 「位址保留」設定

![Alt text](</mai-blog/【技術】社區固定 IP 申請心得/A4CC1F5A-9B37-4A0D-80E7-918C506FC2D5.jpg>)

![Alt text](</mai-blog/【技術】社區固定 IP 申請心得/1099F121-CDB5-4628-9A18-42C8034A432F.jpg>)

![Alt text](</mai-blog/【技術】社區固定 IP 申請心得/E0CD41F7-6434-4FDF-B395-8DC35E87C5CC.jpg>)

![Alt text](</mai-blog/【技術】社區固定 IP 申請心得/F2D5F31A-C058-422A-AD36-BE4D66948442.jpg>)

![Alt text](</mai-blog/【技術】社區固定 IP 申請心得/C4E5068C-DDFE-4660-89BF-AF7094B0191D.jpg>)

![Alt text](</mai-blog/【技術】社區固定 IP 申請心得/7BA9F26C-1122-476B-BF6D-348A6362D681.jpg>)

#### TP-Link 「通訊阜轉發」設定

![Alt text](</mai-blog/【技術】社區固定 IP 申請心得/A4CC1F5A-9B37-4A0D-80E7-918C506FC2D5.jpg>)

![Alt text](</mai-blog/【技術】社區固定 IP 申請心得/F0218D09-8C07-479F-99F0-6D1B8E778DA4.jpg>)

![Alt text](</mai-blog/【技術】社區固定 IP 申請心得/1CF31018-D7E7-47F5-A60C-F6633D896D2C.jpg>)

![Alt text](</mai-blog/【技術】社區固定 IP 申請心得/2686C79F-8140-4E28-BF89-68FCBEE8D264.jpg>)

![Alt text](</mai-blog/【技術】社區固定 IP 申請心得/F6518C9F-3B55-4823-B41E-15CD224A49B5.jpg>)

## Step 4: 如何使用

之後使用，就是路由器設定的電腦，這台電腦設定的 6600 port 就是會變成 `250.XXXXX.tw` 這個 URL 會轉址的目標了。
