---
layout: post
title: "為 Octopress 加上 Last.fm 支援"
date: 2011-12-03 13:44
comments: true
categories: [octopress, javascript, music]
---
想在側邊欄利用 [Last.fm](http://www.last.fm/) 分享最近聽過的歌。雖然 Last.fm 官方其實是可以幫你產生[一段 HTML](http://www.last.fm/tools/charts) 方便你直接放在自己的網站上的，不過看來看去總覺得沒有任何一個符合目前的版型，於是作罷。

剛好自己來練習寫一個。

## 架構

看了一下 Octopress 關於 [template](http://octopress.org/docs/theme/template/) 的文件之後，才發現它的架構非常有彈性。任何客製化的內容都放在 `source/_includes/custom/` 裡面，而 sidebars 的內容放在 `asides` 裡。

使用的時候必須要在 `_config.yml` 裡面將自己寫好的 aside 加到 `_config.yml` 的 `default_asides` 陣列裡才會生效。出現的順序跟在陣列裡的順序是一樣的。

架構都搞清楚了，接下來問題就是怎麼寫 aside 了。

## 實作

參考了內建 delicious 支援的

```
source/javascripts/octopress.js
source/_includes/asides/delicious.html
```

兩個檔案，發現只需要拿到網站提供的 JSON 之後事情就簡單了。

Last.fm 有很詳細的[手冊](http://www.last.fm/api/account)提供給 Developer 參考，不過你必須先申請一個 API Key，才能利用 API 取用這些資料。在這裡我們需要的是 `user.getRecentTracks` 這個方法。

接下來只需要把

{% gist 1426209 %}

放到 `source/_includes/custom/asides/lastfm.html` 裡，並且把這個路徑加到 `default_asides`。

然後在 `_config.yml` 裡新增下面三個參數

``` yaml _config.yml
lastfm_user:
lastfm_count:
lastfm_api:
```

填上自己的設定就搞定啦，打完收工！
