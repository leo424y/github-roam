#Git基本知識與GitHub使用

##Git

從一般開發者的角度來看，git有以下功能：

1. 從伺服器上克隆資料庫（包括程式碼和版本資訊）到單機上。
2. 在自己的機器上建立分支，修改程式碼。
3. 在單機上自己建立的分支上提交程式碼。
4. 在單機上合併分支。
5. 新建一個分支，把伺服器上最新版的程式碼fetch下來，然後跟自己的主分支合併。
6. 生成補丁（patch），把補丁傳送給主開發者。
7. 看主開發者的反饋，如果主開發者發現兩個一般開發者之間有衝突（他們之間可以合作解決的衝突），就會要求他們先解決衝突，然後再由其中一個人提交。如果主開發者可以自己解決，或者沒有衝突，就通過。
8. 一般開發者之間解決衝突的方法，開發者之間可以使用pull 命令解決衝突，解決完衝突之後再向主開發者提交補丁。

從主開發者的角度（假設主開發者不用開發程式碼）看，git有以下功能：

1. 檢視郵件或者通過其它方式檢視一般開發者的提交狀態。
2. 打上補丁，解決衝突（可以自己解決，也可以要求開發者之間解決以後再重新提交，如果是開源項目，還要決定哪些補丁有用，哪些不用）。
3. 向公共伺服器提交結果，然後通知所有開發人員。

###Git初入

如果是第一次使用Git，你需要設定署名和郵箱：

```
$ git config --global user.name "使用者名稱"
$ git config --global user.email "電子郵箱"
```

將程式碼倉庫clone到本地，其實就是將程式碼複製到你的機器裡，並交由Git來管理：

```
$ git clone git@github.com:someone/symfony-docs-chs.git
```

你可以修改複製到本地的程式碼了（symfony-docs-chs項目裡都是rst格式的文件）。當你覺得完成了一定的工作量，想做個階段性的提交：

向這個本地的程式碼倉庫新增當前目錄的所有改動：

```
$ git add .
```

或者只是新增某個檔案：

```
$ git add -p
````

我們可以輸入

```
$git status
```

來看現在的狀態，如下圖是新增之前的：

![Before add](./img/before-add.png)

下面是新增之後 的

![After add](./img/after-add.png)

可以看到狀態的變化是從黃色到綠色，即unstage到add。


##GitHub

Wiki百科上是這麼說的

> GitHub 是一個共享虛擬主機服務，用於存放使用Git版本控制的軟體程式碼和內容項目。它由GitHub公司（曾稱Logical Awesome）的開發者Chris Wanstrath、PJ Hyett和Tom Preston-Werner
使用Ruby on Rails編寫而成。

當然讓我們看看官方的介紹:

> GitHub is the best place to share code with friends, co-workers, classmates, and complete strangers. Over eight million people use GitHub to build amazing things together.


它還是什麼?

- 網站
- 免費部落格
- 管理配置檔案
- 收集資料
- 簡歷
- 管理程式碼片段
- 託管程式設計環境
- 寫作

等等。看上去像是大餐，但是你還需要了解點什麼?

###版本管理與軟體部署

jQuery[^jQuery]在釋出版本``2.1.3``，一共有152個commit。我們可以看到如下的提交資訊:

 - Ajax: Always use script injection in globalEval …	 bbdfbb4
 - Effects: Reintroduce use of requestAnimationFrame …	 72119e0
 - Effects: Improve raf logic …	 708764f
 - Build: Move test to appropriate module	 fbdbb6f
 - Build: Update commitplease dev dependency
 - ...

###GitHub與Git

> Git是一個分散式的版本控制系統，最初由Linus Torvalds編寫，用作Linux核心程式碼的管理。在推出後，Git在其它項目中也取得了很大成功，尤其是在Ruby社羣中。目前，包括Rubinius、Merb和Bitcoin在內的很多知名項目都使用了Git。Git同樣可以被諸如Capistrano和Vlad the Deployer這樣的部署工具所使用。

> GitHub可以託管各種git庫，並提供一個web介面，但與其它像 SourceForge或Google Code這樣的服務不同，GitHub的獨特賣點在於從另外一個項目進行分支的簡易性。為一個項目貢獻程式碼非常簡單：首先點選項目站點的“fork”的按鈕，然後將程式碼檢出並將修改加入到剛才分出的程式碼庫中，最後通過內建的“pull request”機制向項目負責人申請程式碼合併。已經有人將GitHub稱為程式碼玩家的MySpace。

###在GitHub建立項目

接著,我們試試在上面建立一個項目:

![GitHub Roam](./img/github-roam-create.jpg)

就會有下面的提醒:

![GitHub Roam](./img/project-init.jpg)

它提供多種方式的建立方法:

> …or create a new repository on the command line

```
echo "# github-roam" >> README.md
git init
git add README.md
git commit -m "first commit"
git remote add origin git@github.com:phodal/github-roam.git
git push -u origin master
```

> …or push an existing repository from the command line

```
git remote add origin git@github.com:phodal/github-roam.git
git push -u origin master
```

如果你完成了上面的步驟之後,那麼我想你想知道你需要怎樣的項目。

##GitHub流行項目分析

之前曾經分析過一些GitHub的使用者行為，現在我們先來說說GitHub上的Star吧。(截止: 2015年3月9日23時。)

使用者  | 項目名    | Language | Star | Url
-----|---------- |----------|------|----
twbs | Bootstrap | CSS      | 78490 | [https://github.com/twbs/bootstrap](https://github.com/twbs/bootstrap)
vhf |free-programming books | - | 37240 | [https://github.com/vhf/free-programming-books](https://github.com/vhf/free-programming-books)
angular | angular.js | JavaScript | 36,061 | [https://github.com/angular/angular.js](https://github.com/angular/angular.js)
mbostock | d3 | JavaScript | 35,257 | [https://github.com/mbostock/d3](https://github.com/mbostock/d3)
joyent | node | JavaScript | 35,077 | [https://github.com/joyent/node](https://github.com/joyent/node)

上面列出來的是前5的，看看大於1萬個stars的項目的分佈，一共有82個:

語言 | 項目數
-----|-----
JavaScript | 37
Ruby | 6
CSS | 6
Python | 4
HTML | 3
C++ | 3
VimL | 2
Shell | 2
Go | 2
C | 2

類型分佈:


 - 庫和框架: 如``jQuery``
 - 系統: 如``Linux``、``hhvm``、``docker``
 - 配置集: 如``dotfiles``
 - 輔助工具: 如``oh-my-zsh``
 - 工具: 如``Homewbrew``和``Bower``
 - 資料收集: 如``free programming books``，``You-Dont-Know-JS``，``Font-Awesome``
 - 其他:簡歷如``Resume``

##Pull Request

除了建立項目之外，我們也可以建立Pull Request來做貢獻。

###我的第一個PR

我的第一個PR是給一個小的Node的CoAP相關的庫的Pull Request。原因比較簡單，是因為它的README.md寫錯了，導致我無法辦法進行下一步。

		 const dgram       = require('dgram')
		-    , coapPacket  = require('coap-packet')
		+    , package     = require('coap-packet')

很簡單，卻又很有用的步驟，另外一個也是：

```
 else
   cat << END
 $0: error: module ngx_pagespeed requires the pagespeed optimization library.
-Look in obj/autoconf.err for more details.
+Look in objs/autoconf.err for more details.
 END
   exit 1
 fi
```

###CLA

CLA即Contributor License Agreement，在為一些大的組織、機構提交Pull Request的時候，可能需要簽署這個協議。他們會在你的Pull Request裡問你，只有你到他們的網站去註冊並同意協議才會接受你的PR。

以下是我為Google提交的一個PR

![Google CLA](./img/google-cla.png)

以及Eclipse的一個PR

![Eclipse CLA](./img/eclipse-cla.png)

他們都要求我簽署CLA。

 <hr>
