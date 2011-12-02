---
layout: post
title: "用 Git 得獎盃 - Git Achievements"
date: 2011-12-02 07:08
comments: true
categories: git
---
{% blockquote %}
已獲得獎盃。
Git - 擊倒 50 名敵人
{% endblockquote %}

這純粹是我自己的想像，因為最近都在玩再度成為經典的[秘境探險 3](http://acg.gamer.com.tw/acgDetail.php?s=42215)的關係。

[icefox](https://github.com/icefox) 的 [git-achievements](https://github.com/icefox/git-achievements) 是一個很有意思的專案，在公司已經用了大概半年。它利用類似 PS3 的[獎盃](http://www.yourgamercards.net/profile/alecchen)系統，可以讓你在枯燥的工作環境增加一點小小的趣味。


## 安裝

首先當然是 clone 一份來。

```
git clone https://github.com/icefox/git-achievements
```

先別跟著做，因為這樣不是很正確，你只能自己欣賞你的獎盃，沒辦法跟別人分享。

[git-achievements](https://github.com/icefox/git-achievements) 內建 github pages 支援，可以自動發佈你最新的成就，免功夫免技術，不用實在就太可惜囉。前提是你需要一個 github 帳號（沒有的快去申請！）。

正確的方式是 fork 一份之後，再從自己的 repo clone 下來

```
git clone git@github.com:<username>/git-achievements.git
```

最後改一下 shell 的環境變數（這是 bash，其他什麼 *sh 的請自行想像）


``` bash
export PATH="$PATH:~/git/git-achievements"
alias git="git-achievements"
```

接著就不管他了，照原本的工作方式用 git。

## 使用

目前在公司因為用 svn 的同事還是佔大多數，程式碼也都是放在 svn server 上，所以常做的就是

```
git svn rebase
git svn dcommit
```

於是我的得分大部分都是從 git-svn 來的，是不是感覺有點悲哀？真希望 Linus 來幫大家[洗腦一下](http://www.youtube.com/watch?v=4XpnKHJAok8)。

總之邊~~玩~~工作就會邊升級，三不五時就有一個獎盃也算是有點提振士氣的效果。

最後如果你想欣賞你全部的獎盃的話，只需要打 `git achievements -p`，就會在你安裝 git-achievements 的目錄產生 `index.html`，用瀏覽器打開就可以看到結果。假使你有照前面介紹的 fork 一份，而且也設定了

```
git config --global achievement.upload "true"
```

那麼每當你拿到新的獎盃，[git-achievements](https://github.com/icefox/git-achievements) 就會自動幫你上傳，接著你就可以在

```
http://<username>.github.com/git-achievements
```

看到你全部的獎盃囉！是不是很有成就感！

你問我說耐不耐玩？看看作者 [icefox](https://github.com/icefox) 自己都[還沒全破](http://icefox.github.com/git-achievements/)，你說呢？一起來用 [Git](http://git-scm.com/) 拿獎盃吧！
