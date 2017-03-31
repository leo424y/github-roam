
#前言

我的GitHub主頁上寫著加入的時間——``Joined on Nov 8, 2010``，那時才大一，在那之後的那長日子裡我都沒有過到。也許是因為我學的不是計算機，到了今天——``2015.3.9``，我也發現這其實是程式設計師的社交網站。

過去，曾經有很長的一些時間我試過在GitHub上連擊，也試著去了解別人是如何用好這個工具的。當然粉絲在GitHub上也是很重要的。

在這裡，我會試著將我在GitHub上學到的東西一一分享出來。

##我與GitHub的故事

在我大四找工作的時候，試圖去尋找一份硬體、物聯網相關的工作(ps: 專業是電子資訊工程)。儘管簡歷上寫得滿滿的各種經歷、經驗，然而並沒有卵用。跑了幾場校園招聘會後，十份簡歷(ps: 事先已經有心裡準備)一個也沒有投出去——因為學校直接被拒。我對霸面什麼的一點興趣都沒有，千里馬需要伯樂。後來，我加入了Martin Flower所在的公司，當然這是後話了。

這是一個殘酷的世界，在學生時代，如果你長得不帥不高的話，那麼多數的附加技能都是白搭(ps: 通常富的是看不到這篇文章的)。在工作時期，如果你上家沒有名氣，那麼將會影響你下一份工作的待遇。而，很多東西卻會改變這些，GitHub就是其中一個。

註冊GitHub的時候大概是大一的時候，我熟悉的時候已經是大四了，現在已經畢業一年了。在過去的近兩年裡，我試著以幾個維度在GitHub上建立項目:

1. 快速上手框架來實戰，即demo
2. 重構別人的程式碼
3. 建立自己可用的框架
4. 快速構建大型應用
5. 構建通用的框架

###GitHub與收穫

先說說**與技能無關的收穫**吧，畢業設計做的是一個《[最小物聯網系統](https://github.com/phodal/iot)》，考慮到我們專業老師沒有這方面知識，答辯時會帶來問題，儘量往這方面靠攏。當我畢業後，這個項目已經有過百個star了，這樣易上手的東西還是比較受歡迎的(ps: 不過這種硬體相關的項目通常受限於GitHub上硬體開發工程師比較少的困擾)。

畢業後一個月收到PACKT出版社的郵件(ps: 他們是在github上找到我的)，內容是關於Review一本[物聯網](iot)書籍，即在《[從Review到翻譯IT書籍](http://www.phodal.com/blog/review-it-books-with-translate-book/)》中提到的《Learning Internet of Things》。作為一個四級沒過的"物聯網專家"，去審閱一本英文的物聯網書籍。。。

當然，後來是審閱完了，書上有我的英文簡介。

![Phodal Huang Introduction](./img/phodal-intro.jpg)

一個月前，收到MANNING出版社的郵件(ps: 也是在github上)，關於Review一本[物聯網](iot)書籍的目錄，並提出建議。

也因此帶來了其他更多的東西，當然不是這裡的主題。在這裡，我們就不討論各種騷擾郵件，或者中文合作。從沒有想象過，我也可以在英語世界有一片小天地。

這些告訴我們，GitHub上找一個你擅長的主題，那麼會有很多人找上你的。

###GitHub與成長

過去寫過一篇《[如何通過github提升自己](http://www.phodal.com/blog/use-github-grow-self/)》的文章，現在只想說三點:

1. 測試
2. 更多的測試
3. 更多的、更多的、更多的測試

沒有測試的項目是很扯淡的，除非你的項目只有一個函數，然後那個函數返回``Hello,World``。

如果你的項目程式碼有上千行，如果你能保證測試覆蓋率可以達到95%以的話，那麼我想你的項目不會有太複雜的函數。假使有這樣的函數，那麼他也是被測試覆蓋住的。

如果你在用心做這個項目，那麼你看到程式碼寫得不好也會試著改進，即重構。當有了一些，你的技能會不斷提升。你開始會試著接觸更多的東西，如stub，如mock，如fakeserver。

有一天，你會發現你離不開測試。

然後就會相信: **那些沒有寫測試的項目都是在耍流氓**

##為什麼你應該深入GitHub

上面我們說的都是我們可以收穫到的東西，我們開始嘗試就意味著我們知道它可能給我們帶來好處。上面已經提到很多可以提升自己的例子了，這裡再說說其他的。

###方便工作

我們可以從中獲取到不同的知識、內容、資訊。每個人都可以從別人的程式碼中學習，當我們需要構建一個庫的時候我們可以在上面尋找不同的庫和程式碼來實現我們的功能。如當我在實現一個庫的時候，我會在GitHub上到相應的元件:

- Promise 支援
- Class類(ps:沒有一個好的類使用的方式)
- Template 一個簡單的模板引擎
- Router 用來控制頁面的路由
- Ajax 基本的Ajax Get/Post請求

###獲得一份工作

越來越多的人因為GitHub獲得工作，因為他們的做的東西正好符合一些公司的要求。那麼，這些公司在尋找程式碼的時候，就會試著邀請他們。

因而，在GitHub尋找合適的候選人，已經是一種趨勢。

###擴大交際

如果我們想創造出更好、強大地框架時，那麼認識更多的人可能會帶來更多的幫助。有時候會同上面那一點一樣的效果

---

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

#構建GitHub項目

##如何用好GitHub

如何用好GitHub,並實踐一些敏捷軟體開發是一個很有意思的事情.我們可以在上面做很多事情,從測試到CI,再到自動部署.

###敏捷軟體開發

顯然我是在扯淡，這和敏捷軟體開發沒有什麼關係。不過我也不知道瀑布流是怎樣的。說說我所知道的一個項目的組成吧:

 - 看板式管理應用程式(如trello，簡單地說就是管理軟體功能)
 - CI(持續整合)
 - 測試覆蓋率
 - 程式碼質量(code smell)

對於一個不是遠端的團隊(如只有一個人的項目) 來說，Trello、Jenkin、Jira不是必需的:

> 你存在，我深深的腦海裡

當只有一個人的時候，你只需要明確知道自己想要什麼就夠了。我們還需要的是CI、測試，以來提升程式碼的質量。

###測試

通常我們都會找Document，如果沒有的話，你會找什麼?看原始碼，還是看測試?

```javascript
it("specifying response when you need it", function (done) {
	var doneFn = jasmine.createSpy("success");

	lettuce.get('/some/cool/url', function (result) {
		expect(result).toEqual("awesome response");
		done();
	});

	expect(jasmine.Ajax.requests.mostRecent().url).toBe('/some/cool/url');
	expect(doneFn).not.toHaveBeenCalled();

	jasmine.Ajax.requests.mostRecent().respondWith({
		"status": 200,
		"contentType": 'text/plain',
		"responseText": 'awesome response'
	});
});
```

程式碼來源: [https://github.com/phodal/lettuce](https://github.com/phodal/lettuce)

上面的測試用例，清清楚楚地寫明瞭用法，雖然寫得有點扯。

等等，測試是用來幹什麼的。那麼，先說說我為什麼會想去寫測試吧:

 - 我不希望每次做完一個個新功能的時候，再手動地去測試一個個功能。(自動化測試)
 - 我不希望在重構的時候發現破壞了原來的功能，而我還一無所知。
 - 我不敢push程式碼，因為我沒有把握。

雖然，我不是TDD的死忠，測試的目的是保證功能正常，TDD沒法讓我們寫出質量更高的程式碼。但是有時TDD是不錯的，可以讓我們寫出邏輯更簡單地程式碼。

也許你已經知道了``Selenium``、``Jasmine``、``Cucumber``等等的框架，看到過類似於下面的測試

```
 Ajax
   ✓ specifying response when you need it
   ✓ specifying html when you need it
   ✓ should be post to some where
 Class
   ✓ respects instanceof
   ✓ inherits methods (also super)
   ✓ extend methods
 Effect
   ✓ should be able fadein elements
   ✓ should be able fadeout elements
```

程式碼來源: [https://github.com/phodal/lettuce](https://github.com/phodal/lettuce)

看上去似乎每個測試都很小，不過補完每一個測試之後我們就得到了測試覆蓋率

File | Statements | Branches | Functions | Lines
-----|------------|----------|-----------|------
lettuce.js	| 98.58% (209 / 212)| 82.98%(78 / 94) | 100.00% (54 / 54) | 98.58% (209 / 212)

本地測試都通過了，於是我們新增了``Travis-CI``來跑我們的測試

###CI

雖然node.js不算是一門語言，但是因為我們用的node，下面的是一個簡單的``.travis.yml``示例:

```yml
language: node_js
node_js:
	- "0.10"

notifications:
	email: false

before_install: npm install -g grunt-cli
install: npm install
after_success: CODECLIMATE_REPO_TOKEN=321480822fc37deb0de70a11931b4cb6a2a3cc411680e8f4569936ac8ffbb0ab codeclimate < coverage/lcov.info
```

程式碼來源: [https://github.com/phodal/lettuce](https://github.com/phodal/lettuce)

我們把這些整合到``README.md``之後，就有了之前那張圖。

CI對於一個開發者在不同城市開發同一項目上來說是很重要的，這意味著當你新增的部分功能有測試覆蓋的時候，項目程式碼會更加強壯。

###程式碼質量

像``jslint``這類的工具，只能保證程式碼在語法上是正確的，但是不能保證你寫了一堆bad smell的程式碼。

 - 重複程式碼
 - 過長的函數
 - 等等

``Code Climate``是一個與github整合的工具，我們不僅僅可以看到測試覆蓋率，還有程式碼質量。

先看看上面的ajax類:

```javascript
Lettuce.get = function (url, callback) {
	Lettuce.send(url, 'GET', callback);
};

Lettuce.send = function (url, method, callback, data) {
	data = data || null;
	var request = new XMLHttpRequest();
	if (callback instanceof Function) {
		request.onreadystatechange = function () {
			if (request.readyState === 4 && (request.status === 200 || request.status === 0)) {
				callback(request.responseText);
			}
		};
	}
	request.open(method, url, true);
	if (data instanceof Object) {
		data = JSON.stringify(data);
		request.setRequestHeader('Content-Type', 'application/json');
	}
	request.setRequestHeader('X-Requested-With', 'XMLHttpRequest');
	request.send(data);
};
```

程式碼來源: [https://github.com/phodal/lettuce](https://github.com/phodal/lettuce)

在[Code Climate](https://codeclimate.com/github/phodal/lettuce/src/ajax.js)在出現了一堆問題

 - Missing "use strict" statement. (Line 2)
 - Missing "use strict" statement. (Line 14)
 - 'Lettuce' is not defined. (Line 5)

而這些都是小問題啦，有時可能會有

 - Similar code found in two :expression_statement nodes (mass = 86)

這就意味著我們可以對上面的程式碼進行重構，他們是重複的程式碼。

##模組分離與測試

在之前說到

> 奮鬥了近半個月後，將fork的程式碼讀懂、重構、升級版本、調整，新增新功能、新增測試、新增CI、新增分享之後，終於almost finish。

今天就來說說是怎樣做的。

以之前造的[Lettuce](https://github.com/phodal/lettuce)為例，裡面有:

 - 程式碼質量(Code Climate)
 - CI狀態(Travis CI)
 - 測試覆蓋率(96%)
 - 自動化測試(npm test)
 - 文件

按照[Web Developer路線圖](https://github.com/phodal/awesome-developer)來說，我們還需要有:

 - 版本管理
 - 自動部署

等等。

###程式碼模組化

在SkillTree的源碼裡，大致分為三部分:

 - namespace函數: 顧名思義
 - Calculator也就是TalentTree，主要負責解析、生成url，頭像，依賴等等
 - Skill 主要是tips部分。

而這一些都在一個js裡，對於一個庫來說，是一件好事，但是對於一個項目來說，並非如此。

依賴的庫有

 - jQuery
 - Knockout

好在Knockout可以用Require.js進行管理，於是，使用了``Require.js``進行管理:

```html
<script type="text/javascript" data-main="app/scripts/main.js" src="app/lib/require.js"></script>
```

``main.js``配置如下:

```javascript
require.config({
  baseUrl: 'app',
  paths:{
    jquery: 'lib/jquery',
    json: 'lib/json',
    text: 'lib/text'
  }
});

require(['scripts/ko-bindings']);

require(['lib/knockout', 'scripts/TalentTree', 'json!data/web.json'], function(ko, TalentTree, TalentData) {
  'use strict';
  var vm = new TalentTree(TalentData);
  ko.applyBindings(vm);
});
```

text、json外掛主要是用於處理web.json，即用json來處理技能，於是不同的類到了不同的js檔案。

	.
	|____Book.js
	|____Doc.js
	|____ko-bindings.js
	|____Link.js
	|____main.js
	|____Skill.js
	|____TalentTree.js
	|____Utils.js

加上了後來的推薦閱讀書籍等等。而Book和Link都是繼承自Doc。

```javascript
define(['scripts/Doc'], function(Doc) {
  'use strict';
  function Book(_e) {
    Doc.apply(this, arguments);
  }
  Book.prototype = new Doc();

  return Book;
});
```

而這裡便是後面對其進行重構的內容。Doc類則是Skillock中類的一個縮影

```javascript
define([], function() {
  'use strict';
  var Doc = function (_e) {
    var e = _e || {};
    var self = this;

    self.label = e.label || (e.url || 'Learn more');
    self.url = e.url || 'javascript:void(0)';
  };

  return Doc;
});
```

或者說這是一個AMD的Class應該有的樣子。考慮到this的隱性繫結，作者用了self=this來避免這個問題。最後Return了這個物件，我們在呼叫的就需要new一個。大部分在程式碼中返回的都是物件，除了在Utils類裡面返回的是函數:

```javascript
return {
    getSkillsByHash: getSkillsByHash,
    getSkillById: getSkillById,
    prettyJoin: prettyJoin
};
```

當然函數也是一個物件。

###自動化測試

一直習慣用Travis CI，於是也繼續用Travis Ci，``.travis.yml``配置如下所示:

```yml
language: node_js
node_js:
  - "0.10"

notifications:
  email: false

branches:
  only:
    - gh-pages
```

使用gh-pages的原因是，我們一push程式碼的時候，就可以自動測試、部署等等，好處一堆堆的。

接著我們需要在``package.json``裡面新增指令碼

```javascript
"scripts": {
    "test": "mocha"
  }
```

這樣當我們push程式碼的時候便會自動跑所有的測試。因為mocha的主要配置是用``mocha.opts``，所以我們還需要配置一下``mocha.opts``

	--reporter spec
	--ui bdd
	--growl
	--colors
	test/spec

最後的``test/spec``是指定測試的目錄。

###Jshint

> JSLint定義了一組編碼約定，這比ECMA定義的語言更為嚴格。這些編碼約定汲取了多年來的豐富編碼經驗，並以一條年代久遠的程式設計原則 作為宗旨：能做並不意味著應該做。JSLint會對它認為有的編碼實踐加標誌，另外還會指出哪些是明顯的錯誤，從而促使你養成好的 JavaScript編碼習慣。

當我們的js寫得不合理的時候，這時測試就無法通過:

	line 5   col 25   A function Object() { [native code] } name should start with an uppercase letter.
	line 21  col 62   Strings must use singlequote.

這是一種驅動寫出更規範js的方法。


###Mocha

> Mocha 是一個優秀的JS測試框架，支援TDD/BDD，結合 should.js/expect/chai/better-assert，能輕鬆構建各種風格的測試用例。

最後的效果如下所示:

    Book,Link
      Book Test
        ✓ should return book label & url
      Link Test
        ✓ should return link label & url

###測試示例

簡單地看一下Book的測試:

```javascript
/* global describe, it */

var requirejs = require("requirejs");
var assert = require("assert");
var should = require("should");
requirejs.config({
  baseUrl: 'app/',
  nodeRequire: require
});

describe('Book,Link', function () {
  var Book, Link;
  before(function (done) {
    requirejs(['scripts/Book'、], function (Book_Class) {
      Book = Book_Class;
      done();
    });
  });

  describe('Book Test', function () {
    it('should return book label & url', function () {
      var book_name = 'Head First HTML與CSS';
      var url = 'http://www.phodal.com';
      var books = {
        label: book_name,
        url: url
      };

      var _book = new Book(books);
      _book.label.should.equal(book_name);
      _book.url.should.equal(url);
    });
  });
});
```

因為我們用``require.js``來管理瀏覽器端，在後臺寫測試來測試的時候，我們也需要用他來管理我們的依賴，這也就是為什麼這個測試這麼長的原因，多數情況下一個測試類似於這樣子的。(用Jasmine似乎會是一個更好的主意，但是用習慣Jasmine了)

```javascript
describe('Book Test', function () {
it('should return book label & url', function () {
  var book_name = 'Head First HTML與CSS';
  var url = 'http://www.phodal.com';
  var books = {
    label: book_name,
    url: url
  };

  var _book = new Book(books);
  _book.label.should.equal(book_name);
  _book.url.should.equal(url);
});
});
```

最後的斷言，也算是測試的核心，保證測試是有用的。

##程式碼質量與重構

 - 當你寫了一大堆程式碼,你沒有意識到裡面有一大堆重複。
 - 當你寫了一大堆測試,卻不知道覆蓋率有多少。

這就是個問題了，於是偶然間看到了一個叫code climate的網站。

###Code Climate

> Code Climate consolidates the results from a suite of static analysis tools into a single, real-time report, giving your team the information it needs to identify hotspots, evaluate new approaches, and improve code quality.

Code Climate整合一組靜態分析工具的結果到一個單一的，實時的報告，讓您的團隊需要識別熱點，探討新的方法，提高程式碼質量的資訊。

簡單地來說:

- 對我們的程式碼評分
- 找出程式碼中的壞味道

於是，我們先來了個例子

Rating	| Name |	Complexity |	Duplication	| Churn |	C/M	| Coverage |	Smells
--------|------|--------------|-------------|----------|---------|---------------------
A |	lib/coap/coap_request_handler.js |	24 |	0 |	6 |	2.6 |	46.4% |	0
A |	lib/coap/coap_result_helper.js |	14	| 0	| 2 |	3.4 |	80.0% |	0
A	| lib/coap/coap_server.js |	16 |	0 |	5 |	5.2 |	44.0% |	0
A	| lib/database/db_factory.js |	8 |	0 |	3 |	3.8 |	92.3% |	0
A |	lib/database/iot_db.js |	7 |	0 |	6 |	1.0 |	58.8% |	0
A |	lib/database/mongodb_helper.js |	63 | 0 |	11 |	4.5	 | 35.0%	| 0
C |	lib/database/sqlite_helper.js |	32 |	86 |	10 |	4.5 |	35.0% |	2
B |	lib/rest/rest_helper.js	 | 19	| 62 |	3 |	4.7	| 37.5% |	2
A |	lib/rest/rest_server.js |	17 |	0 |	2 |	8.6	| 88.9% |	0
A |	lib/url_handler.js |	9 |	0	| 5 |	2.2	| 94.1% |	0

分享得到的最後的結果是:

![Coverage][1]

###程式碼的壞味道

於是我們就開啟``lib/database/sqlite_helper.js``，因為其中有兩個壞味道

Similar code found in two :expression_statement nodes (mass = 86)

在程式碼的 ``lib/database/sqlite_helper.js:58…61 < >``

```javascript
    SQLiteHelper.prototype.deleteData = function (url, callback) {
        'use strict';
        var sql_command = "DELETE FROM  " + config.table_name + "  where " + URLHandler.getKeyFromURL(url) + "=" + URLHandler.getValueFromURL(url);
        SQLiteHelper.prototype.basic(sql_command, callback);
```

lib/database/sqlite_helper.js:64…67 < >

與

```javascript
SQLiteHelper.prototype.getData = function (url, callback) {
    'use strict';
    var sql_command = "SELECT * FROM  " + config.table_name + "  where " + URLHandler.getKeyFromURL(url) + "=" + URLHandler.getValueFromURL(url);
    SQLiteHelper.prototype.basic(sql_command, callback);
```

只是這是之前修改過的重複。。

原來的程式碼是這樣的

```javascript
SQLiteHelper.prototype.postData = function (block, callback) {
    'use strict';
    var db = new sqlite3.Database(config.db_name);
    var str = this.parseData(config.keys);
    var string = this.parseData(block);

    var sql_command = "insert or replace into " + config.table_name + " (" + str + ") VALUES (" + string + ");";
    db.all(sql_command, function (err) {
        SQLiteHelper.prototype.errorHandler(err);
        db.close();
        callback();
    });
};

SQLiteHelper.prototype.deleteData = function (url, callback) {
    'use strict';
    var db = new sqlite3.Database(config.db_name);
    var sql_command = "DELETE FROM  " + config.table_name + "  where " + URLHandler.getKeyFromURL(url) + "=" + URLHandler.getValueFromURL(url);
    db.all(sql_command, function (err) {
        SQLiteHelper.prototype.errorHandler(err);
        db.close();
        callback();
    });
};

SQLiteHelper.prototype.getData = function (url, callback) {
    'use strict';
    var db = new sqlite3.Database(config.db_name);
    var sql_command = "SELECT * FROM  " + config.table_name + "  where " + URLHandler.getKeyFromURL(url) + "=" + URLHandler.getValueFromURL(url);
    db.all(sql_command, function (err, rows) {
        SQLiteHelper.prototype.errorHandler(err);
        db.close();
        callback(JSON.stringify(rows));
    });
};
```
說的也是大量的重複，重構完的程式碼

```javascript
SQLiteHelper.prototype.basic = function(sql, db_callback){
    'use strict';
    var db = new sqlite3.Database(config.db_name);
    db.all(sql, function (err, rows) {
        SQLiteHelper.prototype.errorHandler(err);
        db.close();
        db_callback(JSON.stringify(rows));
    });

};

SQLiteHelper.prototype.postData = function (block, callback) {
    'use strict';
    var str = this.parseData(config.keys);
    var string = this.parseData(block);

    var sql_command = "insert or replace into " + config.table_name + " (" + str + ") VALUES (" + string + ");";
    SQLiteHelper.prototype.basic(sql_command, callback);
};

SQLiteHelper.prototype.deleteData = function (url, callback) {
    'use strict';
    var sql_command = "DELETE FROM  " + config.table_name + "  where " + URLHandler.getKeyFromURL(url) + "=" + URLHandler.getValueFromURL(url);
    SQLiteHelper.prototype.basic(sql_command, callback);
};

SQLiteHelper.prototype.getData = function (url, callback) {
    'use strict';
    var sql_command = "SELECT * FROM  " + config.table_name + "  where " + URLHandler.getKeyFromURL(url) + "=" + URLHandler.getValueFromURL(url);
    SQLiteHelper.prototype.basic(sql_command, callback);
};
```

重構完後的程式碼比原來還長，這似乎是個問題~~

 ---

#建立項目文件

我們需要為我們的項目建立一個文件，通常我們可以將核心程式碼以外的東西都稱為文件：

1. README
2. 文件
3. 示例
4. 測試

通常這個會在項目的最上方會有一個項目的簡介，如下圖所示：

![GitHub Project Introduction](./img/github-intro.png)

##README

README通常會顯示在GitHub項目的下面，如下圖所示：

![GitHub README](./img/readme-example.png)

通常一個好的README會讓你立馬對項目產生興趣。

如下面的內容是React項目的簡介：

![React README](./img/react-intro.png)

下面的內容寫清楚了他們的用途：

* **Just the UI:** Lots of people use React as the V in MVC. Since React makes no assumptions about the rest of your technology stack, it's easy to try it out on a small feature in an existing project.
* **Virtual DOM:** React abstracts away the DOM from you, giving a simpler programming model and better performance. React can also render on the server using Node, and it can power native apps using [React Native](https://facebook.github.io/react-native/).
* **Data flow:** React implements one-way reactive data flow which reduces boilerplate and is easier to reason about than traditional data binding.

通常在這個README裡，還會有：

* 針對人群
* 安裝指南
* 示例
* 執行的平臺
* 如何參與貢獻
* 協議

##線上文件

很多開源項目都會有自己的網站，並在上面有一個文件，而有的則會放在[https://readthedocs.org/](https://readthedocs.org/)。

> Read the Docs 託管文件，讓文件可以被全文搜尋和更易查詢。您可以匯入您使用任何常用的版本控制系統管理的文件，包括 Mercurial、Git、Subversion 和 Bazaar。 我們支援 webhooks，因此可以在您提交程式碼時自動構建文件。並且同樣也支援版本功能，因此您可以構建來自您程式碼倉庫中某個標籤或分支的文件。檢視完整的功能列表 。

在一個開源項目中，良好和專業的文件是相當重要的，有時他可能會比軟體還會重要。因為如果一個開源項目好用的話，多數人可能不會去檢視軟體的程式碼。這就意味著，多數時候他在和你的文件打交道。文件一般會有：API 文件、 配置文件、幫助文件、使用者手冊、教程等等

寫文件的軟體有很多，如Markdown、Doxygen、Docbook等等。

##可用示例

一個簡單上手的示例非常重要，特別是通常我們是在為著某個目的而去使用一個開源項目的是時候，我們希望能馬上使用到我們的項目中。

你希望看到的是，你開啟瀏覽器，輸入下面的程式碼，然後**It Works**:

```
var HelloMessage = React.createClass({
  render: function() {
    return <div>Hello {this.props.name}</div>;
  }
});

React.render(
  <HelloMessage name="John" />,
  document.getElementById('container')
);
```

而不是需要繁瑣的步驟才能進行下一步。

---

#測試

##TDD

雖然接觸的TDD時間不算短，然而真正在實踐TDD上的時候少之又少。除去怎麼教人TDD，就是與人結對程式設計時的switch，或許是受限於當前的開發流程。

偶然間在開發一個物聯網相關的開源項目——[Lan](https://github.com/phodal/lan)的時候，重拾了這個過程。不得不說提到的一點是，在我們的開發流程中**測試是由相關功能開發人員寫的**，有時候測試是一種很具挑戰性的工作。久而久之，為自己的開源項目寫測試變成一種自然而然的事。有時沒有測試，反而變得**沒有安全感**。

###一次測試驅動開發

之前正在重寫一個[物聯網](http://www.phodal.com/iot)的服務端，主要便是結合CoAP、MQTT、HTTP等協議構成一個物聯網的雲服務。現在，主要的任務是集中於協議與授權。由於，不同協議間的授權是不一樣的，最開始的時候我先寫了一個http put授權的功能，而在起先的時候是如何測試的呢?

    curl --user root:root -X PUT -d '{ "dream": 1 }' -H "Content-Type: application/json" http://localhost:8899/topics/test

我只要順利在request中看有無``req.headers.authorization``，我便可以繼續往下，接著給個判斷。畢竟，我們對HTTP協議還是蠻清楚的。

```javascript
if (!req.headers.authorization) {
  res.statusCode = 401;
  res.setHeader('WWW-Authenticate', 'Basic realm="Secure Area"');
  return res.end('Unauthorized');
}
```

可是除了HTTP協議，還有MQTT和CoAP。對於MQTT協議來說，那還算好，畢竟自帶授權，如:

```bash
mosquitto_pub -u root -P root -h localhost -d -t lettuce -m "Hello, MQTT. This is my first message."
```

便可以讓我們簡單地完成這個功能，然而有的協議是沒有這樣的功能如CoAP協議中是用Option來進行授權的。現在的工具如libcoap只能有如下的簡單功能

```bash
coap-client -m get coap://127.0.0.1:5683/topics/zero -T
```

於是，先寫了個測試指令碼來驗證功能。

```javascript
var coap     = require('coap');
var request  = coap.request;
var req = request({hostname: 'localhost',port:5683,pathname: '',method: 'POST'});

...

req.setHeader("Accept", "application/json");
req.setOption('Block2',  [new Buffer('phodal'), new Buffer('phodal')]);

...

req.end();
```

寫完測試指令碼後發現不對了，這個不應該是測試的程式碼嗎? 於是將其放到了spec中，接著發現了上面的全部功能的實現過程為什麼不用TDD實現呢？

###說說TDD

測試驅動開發是一個很"古老"的程式開發方法，然而由於國內的開發流程的問題——即開發人員負責功能的測試，導致這麼好的一項技術沒有在國內推廣。

測試驅動開發的主要過程是:

1. 先寫功能的測試
2. 實現功能程式碼
3. 提交程式碼(commit -> 保證功能正常)
4. 重構功能程式碼

而對於這樣的一個物聯網項目來說，我已經有了幾個有利的前提:

1. 已經有了原型
2. 框架設計

###TDD思考

通常在我的理解下，TDD是可有可無的。既然我知道了我要實現的大部分功能，而且我也知道如何實現。與此同時，對Code Smell也保持著警惕、要保證功能被測試覆蓋。那麼，總的來說TDD帶來的價值並不大。

然而，在當前這種情況下，我知道我想要的功能，但是我並不理解其深層次的功能。我需要花費大量的時候來理解，它為什麼是這樣的，需要先有一些指令碼來知道它是怎麼工作的。TDD變顯得很有價值，換句話來說，在現有的情況下，TDD對於我們不瞭解的一些事情，可以驅動出更多的開發。畢竟在我們完成測試指令碼之後，我們也會發現這些測試指令碼成為了程式碼的一部分。

在這種理想的情況下，我們為什麼不TDD呢?


##功能測試

###輕量級網站測試TWill

> twill was initially designed for testing Web sites, although since then people have also figured out that it's good for browsing unsuspecting Web sites.

之所以說輕量的原因是他是拿命令列測試的，還有DSL，還有Python。

除此之外，還可以拿它做壓力測試，這種壓力測試和一般的不一樣。可以模擬整個過程，比如同時有多少人登陸你的網站。

不過，它有一個限制是沒有JavaScript。

看了一下源碼，大概原理就是用``requests``下載html，接著用``lxml``解析html，比較有意思的是內嵌了一個``DSL``。

這是一個Python的庫。

     pip install twill

###Twill 登陸測試

1.啟動我們的應用。

2.進入twill shell

    twill-sh
     -= Welcome to twill! =-
    current page:  *empty page*

3.開啟網頁

    >> go http://127.0.0.1:5000/login
    ==> at http://127.0.0.1:5000/login
    current page: http://127.0.0.1:5000/login

4.顯示錶單

    	>> showforms

	Form #1
	## ## __Name__________________ __Type___ __ID________ __Value__________________
	1     csrf_token               hidden    csrf_token   1423387196##5005bdf3496e09b8e2fbf450 ...
	2     email                    email     email        None
	3     password                 password  password     None
	4     login                    submit    (None)       登入

	current page: http://127.0.0.1:5000/login

5.填充表單

    formclear 1
    fv 1 email test@tes.com
    fv 1 password test

6.修改action

    formaction 1 http://127.0.0.1:5000/login

7.提交表單

    >> submit
    Note: submit is using submit button: name="login", value="登入"
    current page: http://127.0.0.1:5000/

發現重定向到首頁了。

###Twill 測試指令碼

當然我們也可以用指令碼直接來測試``login.twill``:

	go http://127.0.0.1:5000/login

	showforms
	formclear 1
	fv 1 email test@tes.com
	fv 1 password test
	formaction 1 http://127.0.0.1:5000/login
	submit

	go http://127.0.0.1:5000/logout

執行

     twill-sh login.twill

結果

	>> EXECUTING FILE login.twill
	AT LINE: login.twill:0
	==> at http://127.0.0.1:5000/login
	AT LINE: login.twill:2

	Form #1
	## ## __Name__________________ __Type___ __ID________ __Value__________________
	1     csrf_token               hidden    csrf_token   1423387345##7a000b612fef39aceab5ca54 ...
	2     email                    email     email        None
	3     password                 password  password     None
	4     login                    submit    (None)       登入

	AT LINE: login.twill:3
	AT LINE: login.twill:4
	AT LINE: login.twill:5
	AT LINE: login.twill:6
	Setting action for form  (<Element form at 0x10e7cbb50>,) to  ('http://127.0.0.1:5000/login',)
	AT LINE: login.twill:7
	Note: submit is using submit button: name="login", value="登入"

	AT LINE: login.twill:9
	==> at http://127.0.0.1:5000/login
	--
	1 of 1 files SUCCEEDED.

一個成功的測試誕生了。

##Fake Server

實踐了一下怎麼用sinon去fake server，還沒用respondWith，於是寫一下。

這裡需要用到sinon框架來測試。

當我們fetch的時候，我們就可以返回我們想要fake的結果。

        var data = {"id":1,"name":"Rice","type":"Good","price":12,"quantity":1,"description":"Made in China"};
	beforeEach(function() {
		this.server = sinon.fakeServer.create();
		this.rices = new Rices();
		this.server.respondWith(
			"GET",
			"http://localhost:8080/all/rice",
			[
				200,
				{"Content-Type": "application/json"},
				JSON.stringify(data)
			]
		);
	});

於是在afterEach的時候，我們需要恢復這個server。

	afterEach(function() {
		this.server.restore();
	});

接著寫一個jasmine測試來測試

	describe("Collection Test", function() {
		it("should get data from the url", function() {
			this.rices.fetch();
			this.server.respond();
			var result = JSON.parse(JSON.stringify(this.rices.models[0]));
			expect(result["id"])
				.toEqual(1);
			expect(result["price"])
				.toEqual(12);
			expect(result)
				.toEqual(data);
		});
	});

---

#重構

或許你應該知道了，重構是怎樣的，你也知道重構能帶來什麼。在我剛開始學重構和設計模式的時候，我需要去找一些好的示例，以便於我更好的學習。有時候不得不創造一些更好的場景，來實現這些功能。

有一天，我發現當我需要我一次又一次地重複講述某些內容，於是我就計劃著把這些應該掌握的技能放到GitHub上，也就有了[Artisan Stack](https://github.com/artisanstack) 計劃。

每個程式設計師都不可避免地是一個Coder，一個沒有掌握好技能的Coder，算不上是手工藝人，但是是手工人。

藝，需要有創造性的方法。

##為什麼重構?

> 為了更好的程式碼。

在經歷了一年多的工作之後，我平時的主要工作就是修Bug。剛開始的時候覺得無聊，後來才發現修Bug需要更好的技術。有時候你可能要面對著一坨一坨的程式碼，有時候你可能要花幾天的時間去閱讀程式碼。而，你重寫那幾十程式碼可能只會花上你不到一天的時間。但是如果你沒辦法理解當時為什麼這麼做，你的修改只會帶來更多的bug。修Bug，更多的是維護程式碼。還是前人總結的那句話對:

> 寫程式碼容易，讀程式碼難。

假設我們寫這些程式碼只要半天，而別人讀起來要一天。為什麼不試著用一天的時候去寫這些程式碼，讓別人花半天或者更少的時間來理解。

如果你的程式碼已經上線，雖然是一坨坨的。但是不要輕易嘗試，``沒有測試的重構``。

從前端開始的原因在於，寫得一坨坨且最不容易測試的程式碼都在前端。

讓我們來看看我們的第一個訓練，相當有挑戰性。

##重構uMarkdown

程式碼及setup請見github: [js-refactor](https://github.com/artisanstack/js-refactor)

###程式碼說明

``uMarkdown``是一個用於將Markdown轉化為HTML的庫。程式碼看上去就像一個很典型的過程程式碼:

```javascript
/* code */
while ((stra = micromarkdown.regexobject.code.exec(str)) !== null) {
  str = str.replace(stra[0], '<code>\n' + micromarkdown.htmlEncode(stra[1]).replace(/\n/gm, '<br/>').replace(/\ /gm, '&nbsp;') + '</code>\n');
}

/* headlines */
while ((stra = micromarkdown.regexobject.headline.exec(str)) !== null) {
  count = stra[1].length;
  str = str.replace(stra[0], '<h' + count + '>' + stra[2] + '</h' + count + '>' + '\n');
}

/* mail */
while ((stra = micromarkdown.regexobject.mail.exec(str)) !== null) {
  str = str.replace(stra[0], '<a href="mailto:' + stra[1] + '">' + stra[1] + '</a>');
}
```

選這個做重構的開始，不僅僅是因為之前在寫[EchoesWorks](https://github.com/phodal/echoesworks)的時候進行了很多的重構。而且它更適合於，``重構到設計模式``的理論。讓我們在重構完之後，給作者進行pull request吧。

Markdown的解析過程，有點類似於``Pipe and Filters``模式(架構模式)。

Filter即我們在程式碼中看到的正規表示式集:

```javascript
regexobject: {
    headline: /^(\#{1,6})([^\#\n]+)$/m,
    code: /\s\`\`\`\n?([^`]+)\`\`\`/g
```

他會匹配對應的Markdown類型，隨後進行替換和處理。而``str```，就是管理口的輸入和輸出。

接著，我們就可以對其進行簡單的重構。

(ps: 推薦用WebStrom來做重構，自帶重構功能)

作為一個示例，我們先提出codeHandler方法，即將上面的

```javascript
/* code */
while ((stra = micromarkdown.regexobject.code.exec(str)) !== null) {
  str = str.replace(stra[0], '<code>\n' + micromarkdown.htmlEncode(stra[1]).replace(/\n/gm, '<br/>').replace(/\ /gm, '&nbsp;') + '</code>\n');
}
```

提取方法成

```javascript
codeFilter: function (str, stra) {
    return str.replace(stra[0], '<code>\n' + micromarkdown.htmlEncode(stra[1]).replace(/\n/gm, '<br/>').replace(/\ /gm, '&nbsp;') + '</code>\n');
  },
```

while語句就成了

```javascript
while ((stra = regexobject.code.exec(str)) !== null) {
    str = this.codeFilter(str, stra);
}
```

然後，執行所有的測試。

```
grunt test
```

同理我們就可以``mail``、``headline``等方法進行重構。接著就會變成類似於下面的程式碼，

```javascript
/* code */
while ((execStr = regExpObject.code.exec(str)) !== null) {
str = codeHandler(str, execStr);
}

/* headlines */
while ((execStr = regExpObject.headline.exec(str)) !== null) {
str = headlineHandler(str, execStr);
}

/* lists */
while ((execStr = regExpObject.lists.exec(str)) !== null) {
str = listHandler(str, execStr);
}

/* tables */
while ((execStr = regExpObject.tables.exec(str)) !== null) {
str = tableHandler(str, execStr, strict);
}
```

然後你也看到了，上面有一堆重複的程式碼，接著讓我們用JavaScript的``奇技浮巧``，即apply方法，把上面的重複程式碼變成。

```javascript
['code', 'headline', 'lists', 'tables', 'links', 'mail', 'url', 'smlinks', 'hr'].forEach(function (type) {
    while ((stra = regexobject[type].exec(str)) !== null) {
        str = that[(type + 'Handler')].apply(that, [stra, str, strict]);
    }
});
```

進行測試，blabla，都是過的。

```javascript
 Markdown
   ✓ should parse h1~h3
   ✓ should parse link
   ✓ should special link
   ✓ should parse font style
   ✓ should parse code
   ✓ should parse ul list
   ✓ should parse ul table
   ✓ should return correctly class name
```

快來試試吧， [https://github.com/artisanstack/js-refactor](https://github.com/artisanstack/js-refactor)

是時候討論這個Refactor利器了，最初看到這個重構的過程是從ThoughtWorks鄭大曄校開始的，只是之前對於Java的另外一個編輯器Eclipse的壞感。。這些在目前已經不是很重要了，試試這個公司裡面應用廣泛的編輯器。

##Intellij Idea重構

開發的流程大致就是這樣子的，測試先行算是推薦的。

    編寫測試->功能程式碼->修改測試->重構

上次在和buddy聊天的時候，才知道測試在功能簡單的時候是後行的，在功能複雜不知道怎麼下手的時候是先行的。


開始之前請原諒我對於Java語言的一些無知，然後，看一下我寫的Main函數：

```java
package com.phodal.learing;

public class Main {

    public static void main(String[] args) {
        int c=new Cal().add(1,2);
        int d=new Cal2().sub(2,1);
        System.out.println("Hello,s");
        System.out.println(c);
        System.out.println(d);
    }
}
```

程式碼寫得還好(自我感覺)，先不管Cal和Cal2兩個類。大部分都能看懂，除了c,d不知道他們表達的是什麼意思，於是。

###Rename

**快捷鍵:Shift+F6**

**作用:重新命名**

 - 把游標丟到int c中的c，按下shift+f6，輸入result_add
 - 把游標移到int d中的d，按下shift+f6，輸入result_sub

於是就有

```java
package com.phodal.learing;

public class Main {

    public static void main(String[] args) {
        int result_add=new Cal().add(1,2);
        int result_sub=new Cal2().sub(2,1);
        System.out.println("Hello,s");
        System.out.println(result_add);
        System.out.println(result_sub);
    }
}
```

###Extract Method

**快捷鍵:alt+command+m**

**作用:擴充套件方法**

- 選中System.out.println(result_add);
- 按下alt+command+m
- 在彈出的視窗中輸入mprint

於是有了

```java
public static void main(String[] args) {
    int result_add=new Cal().add(1,2);
    int result_sub=new Cal2().sub(2,1);
    System.out.println("Hello,s");
    mprint(result_add);
    mprint(result_sub);
}

private static void mprint(int result_sub) {
    System.out.println(result_sub);
}
```

似乎我們不應該這樣對待System.out.println，那麼讓我們內聯回去

###Inline Method

**快捷鍵:alt+command+n**

**作用:內聯方法**

- 選中main中的mprint
- alt+command+n
- 選中Inline all invocations and remove the method(2 occurrences) 點確定

然後我們等於什麼也沒有做了~~:

```java
public static void main(String[] args) {
    int result_add=new Cal().add(1,2);
    int result_sub=new Cal2().sub(2,1);
    System.out.println("Hello,s");
    System.out.println(result_add);
    System.out.println(result_sub);
}
```

似乎這個例子不是很好，但是夠用來說明了。

###Pull Members Up

開始之前讓我們先看看Cal2類:

```java
public class Cal2 extends Cal {

    public int sub(int a,int b){
        return a-b;
    }
}
```

以及Cal2的父類Cal

```java
public class Cal {

    public int add(int a,int b){
        return a+b;
    }

}
```

最後的結果，就是將Cal2類中的sub方法，提到父類:

```java
public class Cal {

    public int add(int a,int b){
        return a+b;
    }

    public int sub(int a,int b){
        return a-b;
    }
}
```

而我們所要做的就是滑鼠右鍵

###重構之以查詢取代臨時變數

快捷鍵

Mac:  木有

Windows/Linux:  木有

或者: ``Shift``+``alt``+``command``+``T`` 再選擇  ``Replace Temp with Query``

滑鼠: **Refactor** | ``Replace Temp with Query``

####重構之前

過多的臨時變數會讓我們寫出更長的函數，函數不應該太多，以便使功能單一。這也是重構的另外的目的所在，只有函數專注於其功能，才會更容易讀懂。

以書中的程式碼為例

```java
import java.lang.System;

public class replaceTemp {
    public void count() {
        double basePrice = _quantity * _itemPrice;
        if (basePrice > 1000) {
            return basePrice * 0.95;
        } else {
            return basePrice * 0.98;
        }
    }
}
```

####重構

選中``basePrice``很愉快地拿滑鼠點上面的重構

![Replace Temp With Query](./img/replace.jpg)

便會返回

```java
import java.lang.System;

public class replaceTemp {
    public void count() {
        if (basePrice() > 1000) {
            return basePrice() * 0.95;
        } else {
            return basePrice() * 0.98;
        }
    }

    private double basePrice() {
        return _quantity * _itemPrice;
    }
}
```

而實際上我們也可以

1. 選中

    _quantity * _itemPrice

2. 對其進行``Extrace Method``

3. 選擇``basePrice``再``Inline Method``

####Intellij IDEA重構

在Intellij IDEA的文件中對此是這樣的例子

```java
public class replaceTemp {

    public void method() {
        String str = "str";
        String aString = returnString().concat(str);
        System.out.println(aString);
    }

}
```

接著我們選中``aString``，再開啟重構選單，或者

``Command``+``Alt``+``Shift``+``T`` 再選中Replace Temp with Query

便會有下面的結果:


```javas
import java.lang.String;

public class replaceTemp {

    public void method() {
        String str = "str";
        System.out.println(aString(str));
    }

    private String aString(String str) {
        return returnString().concat(str);
    }

}
```

---

#如何在GitHub"尋找靈感(fork)"

> 重造輪子是重新創造一個已有的或是已被其他人優化的基本方法。

最近萌發了一個想法寫遊戲引擎，之前想著做一個JavaScript前端框架。看看，這個思路是怎麼來的。

##Lettuce構建過程

> Lettuce是一個簡約的移動開發框架。

故事的出發點是這樣的:``寫了很多程式碼,用的都是框架，最後不知道收穫什麼了``?事實也是如此，當自己做了一些項目之後，發現最後什麼也沒有收穫到。於是，就想著做一個框架。

###需求

有這樣的幾個前提

 - 為什麼我只需要jQuery裡的選擇器、Ajax要引入那麼重的庫呢?
 - 為什麼我只需要一個Template，卻想著用Mustache
 - 為什麼我需要一個Router，卻要用Backbone呢?
 - 為什麼我需要的是一個isObject函數，卻要用到整個Underscore?

我想要的只是一個簡單的功能，而我不想引入一個龐大的庫。換句話說，我只需要不同庫裡面的一小部分功能，而不是一個庫。

實際上想要的是:

> 構建一個庫，裡面從不同的庫裡面抽取出不同的函數。

###計劃

這時候我參考了一本電子書《Build JavaScript FrameWork》，加上一些平時的需求，於是很快的就知道自己需要什麼樣的功能:

 - Promise 支援
 - Class類(ps:沒有一個好的類使用的方式)
 - Template 一個簡單的模板引擎
 - Router 用來控制頁面的路由
 - Ajax 基本的Ajax Get/Post請求

在做一些實際的項目中，還遇到了這樣的一些功能支援:

 - Effect 簡單的一些頁面效果
 - AMD支援

而我們有一個前提是要保持這個庫儘可能的小、同時我們還需要有測試。

###實現第一個需求

簡單說說是如何實現一個簡單的需求。

####生成框架

因為Yeoman可以生成一個簡單的輪廓，所以我們可以用它來生成這個項目的骨架。

 - Gulp
 - Jasmine

####尋找

在GitHub上搜尋了一個看到了下面的幾個結果:

- [https://github.com/then/promise](https://github.com/then/promise)
- [https://github.com/reactphp/promise](https://github.com/reactphp/promise)
- [https://github.com/kriskowal/q](https://github.com/kriskowal/q)
- [https://github.com/petkaantonov/bluebird](https://github.com/petkaantonov/bluebird)
- [https://github.com/cujojs/when](https://github.com/cujojs/when)

但是顯然，他們都太重了。事實上，對於一個庫來說，80%的人只需要其中20%的程式碼。於是，找到了[https://github.com/stackp/promisejs](https://github.com/stackp/promisejs)，看了看用法，這就是我們需要的功能:

```javascript
function late(n) {
    var p = new promise.Promise();
    setTimeout(function() {
        p.done(null, n);
    }, n);
    return p;
}

late(100).then(
    function(err, n) {
        return late(n + 200);
    }
).then(
    function(err, n) {
        return late(n + 300);
    }
).then(
    function(err, n) {
        return late(n + 400);
    }
).then(
    function(err, n) {
        alert(n);
    }
);
```

接著開啟看看Promise物件，有我們需要的功能，但是又有一些功能超出我的需求。接著把自己不需要的需求去掉，這裡函數最後就變成了

```javascript
function Promise() {
    this._callbacks = [];
}

Promise.prototype.then = function(func, context) {
    var p;
    if (this._isdone) {
        p = func.apply(context, this.result);
    } else {
        p = new Promise();
        this._callbacks.push(function () {
            var res = func.apply(context, arguments);
            if (res && typeof res.then === 'function') {
                res.then(p.done, p);
            }
        });
    }
    return p;
};

Promise.prototype.done = function() {
    this.result = arguments;
    this._isdone = true;
    for (var i = 0; i < this._callbacks.length; i++) {
        this._callbacks[i].apply(null, arguments);
    }
    this._callbacks = [];
};

var promise = {
    Promise: Promise
};
```

需要注意的是: ``License``，不同的軟體有不同的License，如MIT、GPL等等。最好能在遵循協議的情況下，使用別人的程式碼。

###實現第二個需求

由於已經有了現有的很多庫，所以就可以直接參照（抄）別人寫的程式碼。

```javascript
Lettuce.get = function (url, callback) {
    Lettuce.send(url, 'GET', callback);
};

Lettuce.load = function (url, callback) {
    Lettuce.send(url, 'GET', callback);
};

Lettuce.post = function (url, data, callback) {
    Lettuce.send(url, 'POST', callback, data);
};

Lettuce.send = function (url, method, callback, data) {
    data = data || null;
    var request = new XMLHttpRequest();
    if (callback instanceof Function) {
        request.onreadystatechange = function () {
            if (request.readyState === 4 && (request.status === 200 || request.status === 0)) {
                callback(request.responseText);
            }
        };
    }
    request.open(method, url, true);
    if (data instanceof Object) {
        data = JSON.stringify(data);
        request.setRequestHeader('Content-Type', 'application/json');
    }
    request.setRequestHeader('X-Requested-With', 'XMLHttpRequest');
    request.send(data);
};
```

---

#GitHub使用者分析

##生成圖表

如何分析使用者的資料是一個有趣的問題，特別是當我們有大量的資料的時候。除了``matlab``，我們還可以用``numpy``+``matplotlib``

資料可以在這邊尋找到

[https://github.com/gmszone/ml](https://github.com/gmszone/ml)

最後效果圖

![2014 01 01](./img/2014-01-01.png)

要解析的json檔案位於``data/2014-01-01-0.json``，大小6.6M，顯然我們可能需要用每次只讀一行的策略，這足以解釋為什麼諸如sublime開啟的時候很慢，而現在我們只需要裡面的json資料中的建立時間。。

==,這個檔案代表什麼？

**2014年1月1日零時到一時，使用者在github上的操作，這裡的使用者指的是很多。。一共有4814條資料，從commit、create到issues都有。**

###資料解析

```python
import json
for line in open(jsonfile):
    line = f.readline()
```

然後再解析json

```python
import dateutil.parser

lin = json.loads(line)
date = dateutil.parser.parse(lin["created_at"])
```

這裡用到了``dateutil``，因為新鮮出爐的資料是string需要轉換為``dateutil``，再到資料放到陣列裡頭。最後有就有了``parse_data``

```python
def parse_data(jsonfile):
    f = open(jsonfile, "r")
    dataarray = []
    datacount = 0

    for line in open(jsonfile):
        line = f.readline()
        lin = json.loads(line)
        date = dateutil.parser.parse(lin["created_at"])
        datacount += 1
        dataarray.append(date.minute)

    minuteswithcount = [(x, dataarray.count(x)) for x in set(dataarray)]
    f.close()
    return minuteswithcount
```

下面這句程式碼就是將上面的解析為

```python
minuteswithcount = [(x, dataarray.count(x)) for x in set(dataarray)]
```

這樣的陣列以便於解析

```python
[(0, 92), (1, 67), (2, 86), (3, 73), (4, 76), (5, 67), (6, 61), (7, 71), (8, 62), (9, 71), (10, 70), (11, 79), (12, 62), (13, 67), (14, 76), (15, 67), (16, 74), (17, 48), (18, 78), (19, 73), (20, 89), (21, 62), (22, 74), (23, 61), (24, 71), (25, 49), (26, 59), (27, 59), (28, 58), (29, 74), (30, 69), (31, 59), (32, 89), (33, 67), (34, 66), (35, 77), (36, 64), (37, 71), (38, 75), (39, 66), (40, 62), (41, 77), (42, 82), (43, 95), (44, 77), (45, 65), (46, 59), (47, 60), (48, 54), (49, 66), (50, 74), (51, 61), (52, 71), (53, 90), (54, 64), (55, 67), (56, 67), (57, 55), (58, 68), (59, 91)]
```

###Matplotlib

開始之前需要安裝``matplotlib

```bash
sudo pip install matplotlib
```
然後引入這個庫

      import matplotlib.pyplot as plt

如上面的那個結果，只需要

<pre><code class="python">
    plt.figure(figsize=(8,4))
    plt.plot(x, y,label = files)
    plt.legend()
    plt.show()
</code></pre>

最後程式碼可見


```python
#!/usr/bin/env python
# -*- coding: utf-8 -*-

import json
import dateutil.parser
import numpy as np
import matplotlib.mlab as mlab
import matplotlib.pyplot as plt


def parse_data(jsonfile):
    f = open(jsonfile, "r")
    dataarray = []
    datacount = 0

    for line in open(jsonfile):
        line = f.readline()
        lin = json.loads(line)
        date = dateutil.parser.parse(lin["created_at"])
        datacount += 1
        dataarray.append(date.minute)

    minuteswithcount = [(x, dataarray.count(x)) for x in set(dataarray)]
    f.close()
    return minuteswithcount


def draw_date(files):
    x = []
    y = []
    mwcs = parse_data(files)
    for mwc in mwcs:
        x.append(mwc[0])
        y.append(mwc[1])

    plt.figure(figsize=(8,4))
    plt.plot(x, y,label = files)
    plt.legend()
    plt.show()

draw_date("data/2014-01-01-0.json")
```

##每週分析

繼上篇之後，我們就可以分析使用者的每週提交情況，以得出使用者的真正的工具效率，每個程式設計師的工作時間可能是不一樣的，如

![Phodal Huang's Report](./img/phodal-results.png)

這是我的每週情況，顯然如果把星期六移到前面的話，隨著工作時間的增長，在github上的使用在下降，作為一個

      a fulltime hacker who works best in the evening (around 8 pm).

不過這個是osrc的分析結果。

###python github 每週情況分析

看一張分析後的結果

![Feb Results](./img/feb-results.png)

結果正好與我的情況相反？似乎圖上是這麼說的，但是資料上是這樣的情況。

	data
	├── 2014-01-01-0.json
	├── 2014-02-01-0.json
	├── 2014-02-02-0.json
	├── 2014-02-03-0.json
	├── 2014-02-04-0.json
	├── 2014-02-05-0.json
	├── 2014-02-06-0.json
	├── 2014-02-07-0.json
	├── 2014-02-08-0.json
	├── 2014-02-09-0.json
	├── 2014-02-10-0.json
	├── 2014-02-11-0.json
	├── 2014-02-12-0.json
	├── 2014-02-13-0.json
	├── 2014-02-14-0.json
	├── 2014-02-15-0.json
	├── 2014-02-16-0.json
	├── 2014-02-17-0.json
	├── 2014-02-18-0.json
	├── 2014-02-19-0.json
	└── 2014-02-20-0.json

我們獲取是每天晚上0點時的情況，至於為什麼是0點，我想這裡的資料量可能會比較少。除去1月1號的情況，就是上面的結果，在只有一週的情況時，總會以為因為在國內那時是假期，但是總覺得不是很靠譜，國內的程式設計師雖然很多，會在github上活躍的可能沒有那麼多，直至列出每一週的資料時。

      6570, 7420, 11274, 12073, 12160, 12378, 12897,
      8474, 7984, 12933, 13504, 13763, 13544, 12940,
      7119, 7346, 13412, 14008, 12555

###Python 資料分析

重寫了一個新的方法用於計算提交數，直至後面才意識到其實我們可以算行數就夠了，但是方法上有點hack

```python
def get_minutes_counts_with_id(jsonfile):
    datacount, dataarray = handle_json(jsonfile)
    minuteswithcount = [(x, dataarray.count(x)) for x in set(dataarray)]
    return minuteswithcount


def handle_json(jsonfile):
    f = open(jsonfile, "r")
    dataarray = []
    datacount = 0

    for line in open(jsonfile):
        line = f.readline()
        lin = json.loads(line)
        date = dateutil.parser.parse(lin["created_at"])
        datacount += 1
        dataarray.append(date.minute)

    f.close()
    return datacount, dataarray


def get_minutes_count_num(jsonfile):
    datacount, dataarray = handle_json(jsonfile)
    return datacount


def get_month_total():
    """

    :rtype : object
    """
    monthdaycount = []
    for i in range(1, 20):
        if i < 10:
            filename = 'data/2014-02-0' + i.__str__() + '-0.json'
        else:
            filename = 'data/2014-02-' + i.__str__() + '-0.json'
        monthdaycount.append(get_minutes_count_num(filename))
    return monthdaycount
```

接著我們需要去遍歷每個結果，後面的後面會發現這個效率真的是太低了，為什麼木有多執行緒？

###Python Matplotlib圖表

讓我們的matplotlib來做這些圖表的工作

```python
if __name__ == '__main__':
    results = pd.get_month_total()
    print results

    plt.figure(figsize=(8, 4))
    plt.plot(results.__getslice__(0, 7), label="first week")
    plt.plot(results.__getslice__(7, 14), label="second week")
    plt.plot(results.__getslice__(14, 21), label="third week")
    plt.legend()
    plt.show()
```

藍色的是第一週，綠色的是第二週，藍色的是第三週就有了上面的結果。

我們還需要優化方法，以及多執行緒的支援。

讓我們分析之前的程式，然後再想辦法做出優化。網上看到一篇文章[http://www.huyng.com/posts/python-performance-analysis/](http://www.huyng.com/posts/python-performance-analysis/)講的就是分析這部分內容的。

##儲存到資料庫中

###SQLite3

我們建立了一個名為``userdata.db``的資料庫檔案，然後建立了一個表，裡面有owner,language,eventtype,name url

```python
def init_db():
    conn = sqlite3.connect('userdata.db')
    c = conn.cursor()
    c.execute('''CREATE TABLE userinfo (owner text, language text, eventtype text, name text, url text)''')
```

接著我們就可以查詢資料，這裡從結果講起。

```python
def get_count(username):
    count = 0
    userinfo = []
    condition = 'select * from userinfo where owener = \'' + str(username) + '\''
    for zero in c.execute(condition):
        count += 1
        userinfo.append(zero)

    return count, userinfo
```

當我查詢``gmszone``的時候，也就是我自己就會有如下的結果

```bash
(u'gmszone', u'ForkEvent', u'RESUME', u'TeX', u'https://github.com/gmszone/RESUME')
(u'gmszone', u'WatchEvent', u'iot-dashboard', u'JavaScript', u'https://github.com/gmszone/iot-dashboard')
(u'gmszone', u'PushEvent', u'wechat-wordpress', u'Ruby', u'https://github.com/gmszone/wechat-wordpress')
(u'gmszone', u'WatchEvent', u'iot', u'JavaScript', u'https://github.com/gmszone/iot')
(u'gmszone', u'CreateEvent', u'iot-doc', u'None', u'https://github.com/gmszone/iot-doc')
(u'gmszone', u'CreateEvent', u'iot-doc', u'None', u'https://github.com/gmszone/iot-doc')
(u'gmszone', u'PushEvent', u'iot-doc', u'TeX', u'https://github.com/gmszone/iot-doc')
(u'gmszone', u'PushEvent', u'iot-doc', u'TeX', u'https://github.com/gmszone/iot-doc')
(u'gmszone', u'PushEvent', u'iot-doc', u'TeX', u'https://github.com/gmszone/iot-doc')
109
````

一共有109個事件，有``Watch``,``Create``,``Push``,``Fork``還有其他的，
項目主要有``iot``,``RESUME``,``iot-dashboard``,``wechat-wordpress``,
接著就是語言了，``Tex``,``Javascript``,``Ruby``,接著就是項目的url了。

值得注意的是。

```bash
-rw-r--r--   1 fdhuang staff 905M Apr 12 14:59 userdata.db
```

這個資料庫檔案有**905M**，不過查詢結果相當讓人滿意，至少相對於原來的結果來說。

Python自帶了對SQLite3的支援，然而我們還需要安裝SQLite3

```bash
brew install sqlite3
```

或者是

```bash
sudo port install sqlite3
```

或者是Ubuntu的

```bash
sudo apt-get install sqlite3
```

openSUSE自然就是

```bash
sudo zypper install sqlite3
```

不過，用yast2也很不錯，不是麼。。

###資料匯入

需要注意的是這裡是需要python2.7，起源於對gzip的上下文管理器的支援問題

```python
def handle_gzip_file(filename):
    userinfo = []
    with gzip.GzipFile(filename) as f:
        events = [line.decode("utf-8", errors="ignore") for line in f]

        for n, line in enumerate(events):
            try:
                event = json.loads(line)
            except:

                continue

            actor = event["actor"]
            attrs = event.get("actor_attributes", {})
            if actor is None or attrs.get("type") != "User":
                continue

            key = actor.lower()

            repo = event.get("repository", {})
            info = str(repo.get("owner")), str(repo.get("language")), str(event["type"]), str(repo.get("name")), str(
                repo.get("url"))
            userinfo.append(info)

    return userinfo

def build_db_with_gzip():
    init_db()
    conn = sqlite3.connect('userdata.db')
    c = conn.cursor()

    year = 2014
    month = 3

    for day in range(1,31):
        date_re = re.compile(r"([0-9]{4})-([0-9]{2})-([0-9]{2})-([0-9]+)\.json.gz")

        fn_template = os.path.join("march",
                                   "{year}-{month:02d}-{day:02d}-{n}.json.gz")
        kwargs = {"year": year, "month": month, "day": day, "n": "*"}
        filenames = glob.glob(fn_template.format(**kwargs))

        for filename in filenames:
            c.executemany('INSERT INTO userinfo VALUES (?,?,?,?,?)', handle_gzip_file(filename))

    conn.commit()
    c.close()
```

``executemany``可以插入多條資料，對於我們的資料來說，一小時的檔案大概有五六千個會符合我們上面的安裝，也就是有``actor``又有``type``才是我們需要記錄的資料，我們只需要統計使用者的那些事件，而非全部的事件。

我們需要去遍歷檔案，然後找到合適的部分，這裡只是要找``2014-03-01``到``2014-03-31``的全部事件，而光這些資料的gz檔案就有1.26G，同上面那些解壓為json檔案顯得不合適，只能用遍歷來處理。

這裡參考了osrc項目中的寫法，或者說直接複製過來。

首先是正規匹配

```python
date_re = re.compile(r"([0-9]{4})-([0-9]{2})-([0-9]{2})-([0-9]+)\.json.gz")
```

不過主要的還是在於``glob.glob``

> glob是python自己帶的一個檔案操作相關模組，用它可以查詢符合自己目的的檔案，就類似於Windows下的檔案搜尋，支援通配符操作。

這裡也就用上了``gzip.GzipFile``又一個不錯的東西。

最後程式碼可以見

[github.com/gmszone/ml](http://github.com/gmszone/ml)

更好的方案？

###Redis

查詢使用者事件總數

```python
import redis
r = redis.StrictRedis(host='localhost', port=6379, db=0)
pipe = pipe = r.pipeline()
pipe.zscore('osrc:user',"gmszone")
pipe.execute()
```

系統返回了``227.0``,試試別人。

```bash
>>> pipe.zscore('osrc:user',"dfm")
<redis.client.StrictPipeline object at 0x104fa7f50>
>>> pipe.execute()
[425.0]
>>>
```

看看主要是在哪一天提交的

```python
>>> pipe.hgetall('osrc:user:gmszone:day')
<redis.client.StrictPipeline object at 0x104fa7f50>
>>> pipe.execute()
[{'1': '51', '0': '41', '3': '17', '2': '34', '5': '28', '4': '22', '6': '34'}]
```

結果大致如下圖所示:

![SMTWTFS](./img/smtwtfs.png)

看看主要的事件是？

    >>> pipe.zrevrange("osrc:user:gmszone:event".format("gmszone"), 0, -1,withscores=True)
    <redis.client.StrictPipeline object at 0x104fa7f50>
    >>> pipe.execute()
    [[('PushEvent', 154.0), ('CreateEvent', 41.0), ('WatchEvent', 18.0), ('GollumEvent', 8.0), ('MemberEvent', 3.0), ('ForkEvent', 2.0), ('ReleaseEvent', 1.0)]]
    >>>

![Main Event](./img/main-events.png)

藍色的就是push事件，黃色的是create等等。

到這裡我們算是知道了OSRC的資料庫部分是如何工作的。

####Redis 查詢

主要程式碼如下所示

```python
def get_vector(user, pipe=None):

    r = redis.StrictRedis(host='localhost', port=6379, db=0)
    no_pipe = False
    if pipe is None:
        pipe = pipe = r.pipeline()
        no_pipe = True

    user = user.lower()
    pipe.zscore(get_format("user"), user)
    pipe.hgetall(get_format("user:{0}:day".format(user)))
    pipe.zrevrange(get_format("user:{0}:event".format(user)), 0, -1,
                   withscores=True)
    pipe.zcard(get_format("user:{0}:contribution".format(user)))
    pipe.zcard(get_format("user:{0}:connection".format(user)))
    pipe.zcard(get_format("user:{0}:repo".format(user)))
    pipe.zcard(get_format("user:{0}:lang".format(user)))
    pipe.zrevrange(get_format("user:{0}:lang".format(user)), 0, -1,
                   withscores=True)

    if no_pipe:
        return pipe.execute()
```

結果在上一篇中顯示出來了，也就是

```
[227.0, {'1': '51', '0': '41', '3': '17', '2': '34', '5': '28', '4': '22', '6': '34'}, [('PushEvent', 154.0), ('CreateEvent', 41.0), ('WatchEvent', 18.0), ('GollumEvent', 8.0), ('MemberEvent', 3.0), ('ForkEvent', 2.0), ('ReleaseEvent', 1.0)], 0, 0, 0, 11, [('CSS', 74.0), ('JavaScript', 60.0), ('Ruby', 12.0), ('TeX', 6.0), ('Python', 6.0), ('Java', 5.0), ('C++', 5.0), ('Assembly', 5.0), ('C', 3.0), ('Emacs Lisp', 2.0), ('Arduino', 2.0)]]
```

有意思的是在這裡生成了和自己相近的人

```
['alesdokshanin', 'hjiawei', 'andrewreedy', 'christj6', '1995eaton']
```

osrc最有意思的一部分莫過於flann，當然說的也是系統後臺的設計的一個很關鍵及有意思的部分。

##鄰近演算法與相似使用者

鄰近演算法是在這個分析過程中一個很有意思的東西。

>鄰近演算法，或者說K最近鄰(kNN，k-NearestNeighbor)分類演算法可以說是整個資料探勘分類技術中最簡單的方法了。所謂K最近鄰，就是k個最近的鄰居的意思，說的是每個樣本都可以用她最接近的k個鄰居來代表。

換句話說，我們需要一些樣本來當作我們的分析資料，這裡東西用到的就是我們之前的。

```
[227.0, {'1': '51', '0': '41', '3': '17', '2': '34', '5': '28', '4': '22', '6': '34'}, [('PushEvent', 154.0), ('CreateEvent', 41.0), ('WatchEvent', 18.0), ('GollumEvent', 8.0), ('MemberEvent', 3.0), ('ForkEvent', 2.0), ('ReleaseEvent', 1.0)], 0, 0, 0, 11, [('CSS', 74.0), ('JavaScript', 60.0), ('Ruby', 12.0), ('TeX', 6.0), ('Python', 6.0), ('Java', 5.0), ('C++', 5.0), ('Assembly', 5.0), ('C', 3.0), ('Emacs Lisp', 2.0), ('Arduino', 2.0)]]
```

在程式碼中是構建了一個points.h5的檔案來分析每個使用者的points，之後再記錄到hdf5檔案中。

```
[ 0.00438596  0.18061674  0.2246696   0.14977974  0.07488987  0.0969163
    0.12334802  0.14977974  0.          0.18061674  0.          0.          0.
    0.00881057  0.          0.          0.03524229  0.          0.
    0.01321586  0.          0.          0.          0.6784141   0.
    0.07929515  0.00440529  1.          1.          1.          0.08333333
    0.26431718  0.02202643  0.05286344  0.02643172  0.          0.01321586
    0.02202643  0.          0.          0.          0.          0.          0.
    0.          0.          0.00881057  0.          0.          0.          0.
    0.          0.          0.          0.          0.          0.          0.
    0.          0.          0.          0.          0.00881057]
```

這裡分析到使用者的大部分行為，再找到與其行為相近的使用者，主要的行為有下面這些:

 - 每星期的情況
 - 事件的類型
 - 貢獻的數量，連線以及語言
 - 最多的語言

osrc中用於解析的程式碼

```python
def parse_vector(results):
    points = np.zeros(nvector)
    total = int(results[0])

    points[0] = 1.0 / (total + 1)

    # Week means.
    for k, v in results[1].iteritems():
        points[1 + int(k)] = float(v) / total

    # Event types.
    n = 8
    for k, v in results[2]:
        points[n + evttypes.index(k)] = float(v) / total

    # Number of contributions, connections and languages.
    n += nevts
    points[n] = 1.0 / (float(results[3]) + 1)
    points[n + 1] = 1.0 / (float(results[4]) + 1)
    points[n + 2] = 1.0 / (float(results[5]) + 1)
    points[n + 3] = 1.0 / (float(results[6]) + 1)

    # Top languages.
    n += 4
    for k, v in results[7]:
        if k in langs:
            points[n + langs.index(k)] = float(v) / total
        else:
            # Unknown language.
            points[-1] = float(v) / total

    return points
```

這樣也就返回我們需要的點數，然後我們可以用``get_points``來獲取這些

```python
def get_points(usernames):
    r = redis.StrictRedis(host='localhost', port=6379, db=0)
    pipe = r.pipeline()

    results = get_vector(usernames)
    points = np.zeros([len(usernames), nvector])
    points = parse_vector(results)
    return points
```

就會得到我們的相應的資料，接著找找和自己鄰近的，看看結果。

```
[ 0.01298701  0.19736842  0.          0.30263158  0.21052632  0.19736842
    0.          0.09210526  0.          0.22368421  0.01315789  0.          0.
    0.          0.          0.          0.01315789  0.          0.
    0.01315789  0.          0.          0.          0.73684211  0.          0.
    0.          1.          1.          1.          0.2         0.42105263
    0.09210526  0.          0.          0.          0.          0.23684211
    0.          0.          0.03947368  0.          0.          0.          0.
    0.          0.          0.          0.          0.          0.          0.
    0.          0.          0.          0.          0.          0.          0.
    0.          0.          0.          0.        ]
```

真看不出來兩者有什麼相似的地方 。。。。

如何以“正確的姿勢”閱讀開源軟體程式碼
===

> 所有讓你直接看最新源碼的文章都是在扯淡，你應該從“某個版本”開始閱讀程式碼。

我們並不建議所有的讀者都直接看最新的程式碼，正確的姿勢應該是：

- clone某個項目的程式碼到本地
- 檢視這個項目的release列表
- 找到一個看得懂的release版本，如1.0或者更早的版本
- 讀懂上一個版本的程式碼
- 向後閱讀大版本的源碼
- 讀最新的源碼

最好的在這個過程中，**可以自己造輪子來實現一遍**。

## 閱讀過程

在我閱讀的前端庫、Python後臺庫的過程中，我們都是以造輪子為目的展開的。所以在最開始的時候，我需要一個可以工作，並且擁有我想要的功能的版本。

![it-works-cms.png](./img/it-works-cms.png)

緊接著，我就可以開始去實踐這個版本中的一些功能，並理解他們是怎麼工作的。再用`git`大法展開之前修改的內容，可以使用IDE自帶的Diff工具：

![pycharm-diff.jpg](./img/pycharm-diff.jpg)

或者類似於`SourceTree`這樣的工具，來檢視修改的內容。

在我們理解了基本的核心功能後，我們就可以向後檢視大、中版本的更新內容了。

開始之前，我們希望大家對版本號管理有一些基本的認識。
## 版本號管理

我最早閱讀的開始軟體是Linux，而下面則是Linux的Release過程：

![linux-history.png](./img/linux-history.png)

表格源自一本書叫《Linux核心0.11(0.95)完全註釋》，簡單地再介紹一下：
- 版本0.00是一個hello,world程式
- 版本0.01包含了可以工作的程式碼
- 版本0.11是基本可以正常的版本

這裡就要扯到《GNU 風格的版本號管理策略》：

1．項目初版本時，版本號可以為 0.1 或 0.1.0, 也可以為 1.0 或 1.0.0，如果你為人很低調，我想你會選擇那個主版本號為 0 的方式；
2．當項目在進行了局部修改或 bug 修正時，主版本號和子版本號都不變，修正版本號加 1；
3. 當項目在原有的基礎上增加了部分功能時，主版本號不變，子版本號加 1，修正版本號復位為 0，因而可以被忽略掉；
4．當項目在進行了重大修改或局部修正累積較多，而導致項目整體發生全局變化時，主版本號加 1；
5．另外，編譯版本號一般是編譯器在編譯過程中自動生成的，我們只定義其格式，並不進行人為控制。

因此，我們可以得到幾個簡單的結論：
- 我們需要閱讀最早的有核心程式碼的版本
- 我們需要閱讀1.0版本的Release
- 往後每一次大的Release我們都需要了解一下

## 示例

以Flask為例：

一、先Clone它。

![clone-flask.png](./img/clone-flask.png)

二、從Release頁面找到它的早期版本：

![flask.png](./img/flask.png)

三、 從上面拿到它的提交號`8605cc3`，然後checkout到這次提交，檢視功能。在這個版本里，一共有六百多行程式碼

![flask-0.1.png](./img/flask-0.1.png)

還是有點長

四、我們可以找到它的最早版本:

![flask-init.png](./img/flask-init.png)

然後檢視它的`flask.py`檔案，只有簡單的三百多行，並且還包含一系列註釋：

![flask-init.png](./img/flask-init.png)

五、接著，再回過頭去閱讀

- 0.1版本
- 。。。
- 最新的0.10.1版本

#GitHub連擊

##100天

我也是蠻拼的，雖然我想的只是在GitHub上連擊100~200天，然而到了今天也算不錯。

![Longest Streak](./img/longest-streak.png)

``在停地造輪子的過程中，也不停地造車子。``

在那篇連續衝擊365天的文章出現之前，我們公司的大大([https://github.com/dreamhead](https://github.com/dreamhead))也曾經在公司內部說過，天天commit什麼的。當然這不是我的動力，在連擊140天之前

- 給過google的``ngx_speed``、``node-coap``等項目建立過pull request
- 也有``free-programming-books``、``free-programming-books-zh_CN``這樣的項目。
- 當然還有一個連擊20天。

對比了一下365天連擊的commit，我發現我在total上整整多了近0.5倍。

![365 Streak](./img/365-streak.jpg)

同時這似乎也意味著，我每天的commit數與之相比多了很多。

在連擊20的時候，有這樣的問題: *為了commit而commit程式碼*，最後就放棄了。

而現在是``為了填坑而commit``，為自己挖了太多的想法。

###40天的提升

當時我需要去印度接受畢業生培訓，大概有5周左右，想著總不能空手而歸。於是在國慶結束後有了第一次commit，當時旅遊歸來，想著自己在不同的地方有不同的照片，於是這個repo的名字是 [onmap](https://github.com/phodal/onmap)——將自己的照片顯示在地圖上的拍攝地點(手機是Lumia 920)。然而，中間因為修改賬號的原因，丟失了commit。

再從印度說起，當時主要維護三個repo:

- 物聯網的CoAP協議
- [一步步設計物聯網系統](https://github.com/phodal/designiot)的電子書
- 一個Node.js + JS的網站

說說最後一個，最後一個是練習的項目。因為當時培訓比較無聊，業餘時間比較多，英語不好，加上聽不懂印度人的話。晚上基本上是在住的地方默默地寫程式碼，所以當時的目標有這麼幾個:

- TDD
- 測試覆蓋率
- 程式碼整潔

這也就是為什麼那個repo有這樣的一行:

![Repo Status](./img/repo-status.png)

做到98%的覆蓋率也算蠻拼的，當然還有Code Climate也達到了4.0，也有了112個commits。因此也帶來了一些提高:

- 提高了程式碼的質量(code climate比jslint更注重重複程式碼等等一些bad smell)。
- 對於Mock、Stub、FakesServer等用法有更好的掌握
- 可以持續地交付軟體(版本管理、自動測試、CI、部署等等)

###100天的挑戰

(ps:從印度回來之後，由於女朋友在泰國實習，有了更多的時間可以看書、寫程式碼)

有意思的是越到中間的一些時間，commits的次數上去了，除了一些簡單的pull request，還有一些新的輪子出現了。

![Problem](./img/problem.jpg)

這是上一星期的commits，這也就意味著，在一星期裡面，我需要在8個repo裡切換。而現在我又有了一個新的idea，這時就發現了一堆的問題:

 - 今天工作在這個repo上，突然發現那個repo上有issue，需要去修復，於是就放下了當前的程式碼。
 - 在不同的repo間切換容易分散精力
 - 很容易就發現有太多的功能可以實現，但是時間是有限的。
 - 沒有足夠的空閒時間，除了週末。
 - 希望去尋找那些有興趣的人，然而卻發現原來沒有那麼多時間去找人。

###140天的希冀

在經歷了100天之後，似乎整個人都輕鬆了，畢竟目標是100~200天。似乎到現在，也不會有什麼特殊的情懷，除了一些希冀。

當然，對於一個開源項目的作者來說，最好有下面的情況:

- 很多人知道了這個項目
- 很多人用它的項目。
- 在某些可以用這個項目快速解決問題的地方提到了這個項目
- 提了bug、issue、問題。
- 提了bug，並解決了。(ps:這是最理想的情況)


##200天的Showcase

今天是我連續泡在GitHub上的第200天，也是蠻高興的，終於到達了:

![GitHub 200 days](./img/github-200-days.png)

故事的背影是: 去年國慶完後要去印度接受畢業生培訓——就是那個神奇的國度。但是在去之前已經在項目待了九個多月，項目上的挑戰越來越少，在印度的時間又算是比較多。便給自己設定了一個長期的goal，即100~200天的longest streak。

或許之前你看到過一篇文章[讓我們連擊](https://github.com/phodal/github-roam/blob/master/chapters/12-streak-your-github.md)，那時已然140天，只是還是渾渾噩噩。到了今天，漸漸有了一個更清晰地思路。

先讓我們來一下ShowCase，然後再然後，下一篇我們再繼續。

###一些項目簡述

上面說到的培訓一開始是用Java寫的一個網站，有自動測試、CI、CD等等。由於是內部組隊培訓，程式碼不能公開等等因素，加之做得無聊。順手，拿Node.js +RESTify 做了Server，Backbone + RequireJS + jQuery 做了前臺的邏輯。於是在那個日子裡，也在維護一些舊的repo，如[iot-coap](https://github.com/phodal/iot-coap)、[iot](https://github.com/phodal/iot)，前者是我拿到WebStorm開源License的Repo，後者則是畢業設計。

對於這樣一個項目也需要有測試、自動化測試、CI等等。CI用的是Travics-CI。總體的技術構架如下:

####技術棧

前臺:

- Backbone
- RequireJS
- Underscore
- Mustache
- Pure CSS

後臺:

- RESTify

測試:

- Jasmine
- Chai
- Sinon
- Mocha
- Jasmine-jQuery

一直寫到五星期的培訓結束， 只是沒有自動部署。想想就覺得可以用github-page的項目多好~~。

過程中還有一些有意思的小項目，如:

###google map solr polygon 搜尋

[google map solr polygon 搜尋](http://www.phodal.com/blog/google-map-width-solr-use-polygon-search/)

![google map solr](./img/solr.png)

程式碼: [https://github.com/phodal/gmap-solr](https://github.com/phodal/gmap-solr)

###技能樹

這個可以從兩部分說起:

####重構Skill Tree

原來的是

- Knockout
- RequireJS
- jQuery
- Gulp

![Skill Tree](./img/skilltree.jpg)

程式碼: [https://github.com/phodal/skillock](https://github.com/phodal/skillock)

####技能樹Sherlock

- D3.js
- Dagre-D3.js
- jquery.tooltipster.js
- jQuery
- Lettuce
- Knockout.js
- Require.js

![Sherlock skill tree](./img/sherlock.png)

程式碼: [https://github.com/phodal/sherlock](https://github.com/phodal/sherlock)

####Django Ionic ElasticSearch 地圖搜尋

![Django Elastic Search](./img/elasticsearch_ionit_map.jpg)

- ElasticSearch
- Django
- Ionic
- OpenLayers 3

程式碼: [https://github.com/phodal/django-elasticsearch](https://github.com/phodal/django-elasticsearch)

####簡歷生成器

![Resume](./img/resume.png)

- React
- jsPDF
- jQuery
- RequireJS
- Showdown

程式碼: [https://github.com/phodal/resume](https://github.com/phodal/resume)


####Nginx 大資料學習

![Nginx Pig](./img/nginx_pig.jpg)

- ElasticSearch
- Hadoop
- Pig

程式碼: [https://github.com/phodal/learning-data/tree/master/nginx](https://github.com/phodal/learning-data/tree/master/nginx)

####其他

雖然技術棧上主要集中在Python、JavaScript，當然還有一些Ruby、Pig、Shell、Java的程式碼，只是我還是習慣用Python和JavaScript。一些用到覺得不錯的框架:

- Ionic: 開始Hybird移動應用。
- Django: Python Web開發利器。
- Flask: Python Web開發小刀。
- RequireJS: 管理js依賴。
- Backbone: Model + View + Router。
- Angluar: ...。
- Knockout: MVV*。
- React: 據說會火。
- Cordova: Hybird應用基礎。

還應該有:

- ElasticSearch
- Solr
- Hadoop
- Pig
- MongoDB
- Redis

##365天

  給你一年的時間，你會怎樣去提高你的水平？？？

![GitHub 365](./img/github-365.jpg)

正值這難得的sick leave（萬惡的空氣），碼文一篇來記念一個過去的366天裡。儘管想的是在今年裡寫一個可持續的開源框架，但是到底這依賴於一個好的idea。在我的[GitHub 孵化器](http://github.com/phodal/ideas) 頁面上似乎也沒有一個特別讓我滿意的想法，雖然上面有各種不樣有意思的ideas。多數都是在過去的一年是完成的，然而有一些也是還沒有做到的。

儘管一直在GitHub上連擊看上去似乎是沒有多大必要的，但是人總得有點追求。如果正是漫無目的，卻又想著提高技術的同時，為什麼不去試試？畢竟技術非常好、不需要太多練習的人只是少數，似乎這樣的人是不存在的。大多數的人都是經過練習之後，才會達到別人口中的“技術好”。

這讓我想起了充斥著各種氣味的知乎上的一些問題，在一些智商被完虐的話題裡，無一不是因為那些人學得比別人早——哪來的天才？所謂的天才，應該是未來的智慧生命一般，一出生什麼都知道。如果並非如此，那只是說明他練習到位了。

練習不到位便意味著，即使你練習的時候是一萬小時的兩倍，那也是無濟於事的。如果你學得比別人晚，在**很長的一段時間裡**(可能直到進棺材)輸給別人是必然的——落後就要捱打。就好像我等畢業於一所二本墊底的學校裡，如果在過去我一直保持著和別人(各種重點)一樣的學習速度，那麼我只能一直是Loser。

需要注意的是，對你來說考上二本很難，並不是因為你比別人笨。教育資源分配不均的問題，在某種程度上導致了新的階級制度的出現。如[我的首頁](https://www.phodal.com/)說的那樣: **THE ONLY FAIR IS NOT FAIR**——唯一公平的是它是不公平的。我們可以做的還有很多——**CREATE & SHARE**。真正的不幸是，因為營養不良導致的教育問題。

於是在想明白了很多事的時候起，便有了Re-Practise這樣的計劃，而365天只是中間的一個產物。

###程式設計的基礎能力

雖說演算法很重要，但是編碼才是基礎能力。演算法與程式設計在某種程度上是不同的領域，演算法程式設計是在程式設計上面的一級。演算法寫得再好，如果別人很難直接拿來複用，在別人眼裡就是shit。想出能work的程式碼一件簡單的事，學會對其重構，使之變得更易讀就是一件有意義的事。

於是，在某一時刻在GitHub上建立了一個組織，叫[Artisan Stack](https://github.com/artisanstack)。當時想的是在GitHub尋找一些JavaScript項目，對其程式碼進行重構。但是到底是影響力不夠哈，參與的人數比較少。

####重構

如果你懂得如何寫出高可讀的程式碼，那麼我想你是不需要這個的，但是這意味著你花了更多的時候在思考上了。當談論重構的時候，讓我想起了TDD(測試驅動開發)。即使不是TDD，那麼如果你寫著測試，那也是可以重構的。(之前寫過一些利用Intellij IDEA重構的文章：[提煉函數](https://www.phodal.com/blog/intellij-idea-refactor-extract-method/)、[以查詢取代臨時變數](https://www.phodal.com/blog/intellij-idea-refactor-replace-temp-with-query/)、[重構與Intellij Idea初探](https://www.phodal.com/blog/thoughtworks-refactor-and-intellij-idea/)、[行內函數](https://www.phodal.com/blog/intellij-idea-refactor-inline-method/))

在各種各樣的文章裡，我們看到過一些相關的內容，最好的參考莫過於《重構》一書。最基礎不過的原則便是函數名，取名字很難，取別人能讀懂的名字更難。其他的便有諸如長函數、過大的類、重複程式碼等等。在我有限的面試別人的經歷裡，這些問題都是最常見的。

####測試

而如果沒有測試，其他都是扯淡。寫好測試很難，寫個測試算是一件容易的事。只是有些容易我們會為了測試而測試。

在我寫[EchoesWorks](https://github.com/echoesworks/echoesworks)和[Lan](https://github.com/phodal/lan)的過程中，我儘量去保證足夠高的測試覆蓋率。

![lan](./img/lan.png)

![EchoesWorks](./img/echoesworks.png)

從測試開始的TDD，會保證方法是可測的。從功能到測試則可以提供工作次效率，但是隻會讓測試成為測試，而不是程式碼的一部分。

測試是程式碼的最後一公里。所以，儘可能的為你的GitHub上的項目新增測試。

####編碼的過程

初到TW時，Pair時候總會有人教我如何開始編碼，這應該也是一項基礎的能力。結合日常，重新演繹一下這個過程：

1. 有一個可衡量、可實現、過程可測的目標
2. Tasking (即對要實現的目標過程進行分解)
3. 一步步實現 (如TDD)
4. 實現目標

放到當前的場景就是：

1. 我想在GitHub上連擊365天。對應於每一個時候段的目標都應該是可以衡量、測試的——即每天都會有Contributions。
2. 分解就是一個痛苦的過程。理想情況下，我們應該會有每天提交，但是這取決於你的repo的數量，如果沒有新的idea出現，那麼這個就變成為了Contributions而Commit。
3. 一步步實現

在我們實際工作中也是如此，接到一個任務，然後分解，一步步完成。不過實現會稍微複雜一些，因為事務總會有搶佔和優先順序的。

###技術與框架設計

在上上一篇部落格中《[After 500: 寫了第500篇部落格，然後呢?](https://www.phodal.com/blog/after-500-blogposts-analytics-after-tech/)》也深刻地討論了下這個問題，技術向來都是後發者優勢。對於技術人員來說，也是如此，後發者佔據很大的優勢。

如果我們只是單純地把我們的關注點僅僅放置於技術上，那麼我們就不具有任何的優勢。而依賴於我們的程式設計經驗，我們可以在特定的時候創造一些框架。而架構的設計本身就是一件有意思的事，大抵是因為程式設計師都喜歡創造。(ps:之前曾經寫過這樣一篇文章，《[對不起，我並不熱愛程式設計，我只喜歡創造](https://www.phodal.com/blog/sorry-i-don't-like-programming/)》)

**創造是一種知識的再掌握過程。**

回顧一下寫echoesworks的過程，一開始我需要的是一個網頁版的PPT，當然這類的東西已經有很多了，如impress.js、bespoke.js等等。分析一下所需要的功能：markdown解析器、鍵盤事件處理、Ajax、進度條顯示、圖片處理、Slide。我們可以在GitHub上找到各式各樣的模組，我們所要做的就是將之結合在一樣。在那之前，我試著用類似的原理寫（組合）了[Lettuce](https://github.com/phodal/lettuce)。

組合相比於創造過程是一個更有挑戰性的過程，我們需要在這過程去設計膠水來粘合這些程式碼，並在最終可以讓他工作。這好比是我們在平時接觸到的任務劃分，每個人負責相應的模組，最後整合。

想似的我在寫[lan](https://github.com/phodal/lan)的時候，也是類似的，但是不同的是我已經設計了一個清晰的架構圖。

![Lan IoT](./img/lan-iot.jpg)

而在我們實現的編碼過程也是如此，使用不同的框架，並且讓他們能工作。如早期玩的[moqi.mobi](https://github.com/echoesworks/moqi.mobi)，基於Backbone、RequireJS、Underscore、Mustache、Pure CSS。在隨後的時間裡，用React替換了View層，就有了[backbone-react](https://github.com/phodal/backbone-react)的練習。

技術同人一樣，需要不斷地往高一級前進。我們只需要不斷地Re-Practise。

###領域與練習

說業務好像不太適合程式設計師的口味，那就領域吧。不同行業的人，如百度、阿里、騰訊，他們的領域核心是不一樣的。

而領域本身也是相似的，這可以解釋為什麼網際網路公司都喜歡互相挖人，而一般都不會去華為、中興等非網際網路領域挖人。出了這個領域，你可能連個畢業生都不如。領域、業務同技術一樣是不斷強化知識的一個過程。Ritchie先實現了BCPL語言，而後設計了C語言，而BCPL語言一開始是基於CPL語言。

領域本身也在不斷進化。

這也是下一個值得提高的地方。

###其他

是時候寫這個小結了。從不會寫程式碼，到寫程式碼是從0到1的過程，但是要從1到60都不是一件容易的事。無論是刷GitHub也好(不要是自動提交)，或者是換工作也好，我們都在不斷地練習。

而練習是要分成不同的幾個步驟，不僅僅侷限於技術：

1. 編碼
2. 架構
3. 設計
4. 。。。

---

##500天

儘管之前已經有100天、200天、365天的文章，但是這不是一篇象徵性的500天的文章。對這樣的一個事物，每個人都會有不同聽看法。有的會說這是一件好事，有的則不是。但是別人的看法終究不重要，因為了解你自己的只有你自己。別人都只是以他們的角度來提出觀點。

在這500天裡，我發現兩點有意思的事，也是總結的時候才意識到的：

1. 程式設計的情緒週期
2. 有意圖的練習

那麼，當我們不斷地練習的時候，我們就可以寫出更好的程式碼。

我想你也聽過一萬小時天才理論的說法：要成為某個領域的專家，需要10000小時。而在這其中每重要的一點是有意圖的練習——而不是一直重複性地用不同的語言去寫一個相同的演算法。如果我們有一天8小時的工作時間  + 2 小時的提高時間，那麼我們還是需要1000天才能實現一萬小時。

###500天與10000小時

當然如果你連做夢也在寫程式碼的話，那麼我想500天就夠了，哈哈~~。

![Gtihub 500](./img/github-500.jpg)

雖然不是連擊次數最多的，但是根據[Most active GitHub users ](http://git.io/top)的結果來說，好似是大陸提交數最多的人，沒有之一。再考慮到提交都是有意義的——不是機器刷出來的，不是有意識的去刷，我覺得還是有很大成就感的。

而要實現500天連擊很重要的兩點是：時間和idea。但是我覺得idea並不是非常重要的，我們可以造輪子，這一點就是在早期我做得最多的一件事，不斷地造輪子——如《[造輪子與從Github生成輪子](https://www.phodal.com/blog/create-framework-from-github/)》一文中所說。除此，你還可以用《[GitHub去管理你的idea](https://www.phodal.com/blog/use-github-manage-idea/)》，每當你想到一個Idea以及完成一個idea的時間你就會多一次提交。

時間則是一件很諷刺的事，因為人們要加班。加班的原因，要麼是因為工作的內容很有意思，要麼是因為錢。如果不是因為錢的話，為什麼不去換個工作呢？比如我司。看似兩者間存在很多的對立，但是我總在想技術的提升可以在後期解決收入的問題，而不需要靠加班來解決這個問題。人總是要活著的，錢是必需的，但是程式設計師的收入都不低。

###程式設計的情緒週期

接著，我觀察到了一些有意思的現象——程式設計的情緒週期也很明顯。

> 所謂“情緒週期”，是指一個人的情緒高潮和低潮的交替過程所經歷的時間。

如下圖所示的就是情緒週期：

![情緒週期](./img/qingxu.jpg)

簡單地來說，就是**有一個時間段寫程式碼的感覺超級爽，有一個時間段不想寫程式碼**，但是如果換一個說法就是：**有一個時間段看書、寫文件的感覺很爽，有一時間段不想看書、寫文件的感覺**。這也就是為什麼在我的GitHub首頁上的綠色各種花。不過因為《物聯網週報》的原因，我會定期地更新一個相關的開源項目。

但是總來說，我習慣在一些時間造一些輪子、建立文件，這就是為什麼我的GitHub會有一些開源電子書的緣故。

###有意圖的練習

程式設計需要很長的學習時間，也需要很長的練習時間。儘管我是從小學程式設計，自認為天賦不錯，但是突破了上個門檻還是花費了三四年的時間。其中的很大一部分原因是，沒有找對一個合適的方向。而在這期間也沒有好好的練習，隨後的日子裡我意識到我會遇到下一個門檻，便開始試圖有意識的練習。

在我開始工作的時候，我寫了一篇名為《[重新思考工作](https://www.phodal.com/blog/rethink-about-the-work/)》的文章。在文章中我提到了幾點練習的點：

 - 加強碼程式碼的準確性
 - 寫出更整潔的程式碼
 - 英語口語 （外企）
 - 針對性的加強語言技能

在一些日子的練習後，我發現這還是太無聊了。天生就喜歡一些有意思的東西，有趣才更有激情吧~~。不過，像下圖的打字練習還是挺有意思的：

![打字練習](./img/huovd.png)

還是能打出了一堆錯誤的字元。但是對比了一下大多數人的人，還算不錯，至少是盲打。但是，還是存在著很大的提升空間。

隨後，我開始一些錯誤的練習，如對設計模式和架構的練習。試圖去練習一些在生產上用不到的設計模式，以及一些架構模式。而這時就意味著，需要生搬一些設計模式。最後，我開始以項目為目的的練習，這就是為什麼我的GitHub上的提交數會有如此多的原因。

###預見性練習

還有一種練習比較有意思，算是以工作為導向的練習。當我們預見到我們的項目需要某一些技術，我們可能在未來採用某些技術的時候，我們就需要開始預見性的練習這些技術。

好的一點是：這些項目可能在未來很受初學者歡迎。

###小結

每個人都有自己的方向，都有一個不錯的發展路線，分享和創造都是不錯的路。

THE ONLY FAIR IS NOT FAIR . ENJOY CREATE & SHARE.

## 365*2-7天裡

剛畢業的時候，有一段時間我一直困惑於如何去提高編碼能力——因為項目上做的東西多數時候和自己想要的是不一樣的，我便想著自己去找一些有意思的東西做著玩，在這個過程中邊練習技能。

> 如果你知道自己程式碼能力不夠，為什麼不花兩年時間去提高這方面的能力呢？

### 編碼的練習

編碼是一件值得練習的事，你從書中、網際網路上看到的那一個個的程式設計大牛無一不是從一點點的小技能積累起來的。從小接觸可以讓你有一個好的開始，一段好好的練習也會幫助你更好的前進。

記得我在最開始練習的時候，我分幾個不同的階段去練習:

 - 按照《重構：改善即有程式碼的設計》一書邊尋找一些 bad smell 的程式碼，一邊想方設法去讓程式碼變得優雅。
 - 按照《設計模式》以及《重構與模式》來將程式碼重構成某種設計模式。
 - 按照《面向模式的軟體架構》去設計一些軟體架構。

而這些並不是一種容易的事，很多時候有一些模式，我們都很難有一個好的實踐。只是這些東西都不是一些可以生搬硬套的，我們更需要的是知道有這些東西的存在，以便於在某一天，我們可以從我們的倉庫裡將這些知識取出來。

![10000 hours](./img/10000.png)

我們的刻意練習加上我們的持之以恆總是會取得長足的進步。不過在我們練習之前，你需要有一個目標。這個目標可以是一個 Idea、一個設計模式、一個模仿等等，這些內容都可以以 Issue 的好好管理著。

在最開始我們下定目標的幾天裡，我們可以很容易做到這樣的事。同樣的，我們也可以很容易達到 21 天。只是，我們很容易在 21 天后失去一些目標。所以在練習開始之前，你需要建立一個幫助你提高技術的列表，然後一點點加以提高。比如說：

1. 嘗試使用 React + Redux + Koa 2、或者Angular 2 + TypeScript，這樣我們就能憑此來學習新的技術。
2. 嘗試使用 CQRS 架構來設計 CMS，這樣我們就可以練習在架構方面的能力。

在我們想到一點我們可以練習的技術的時候，這就是一個可以變成 Issue 管理的內容，我們就可以針對性的提高。

通常在這種情況下，我們知道自己不知道什麼東西，當我們處於不知道自己不知道、不知道自己知道時，那我們就需要網上的各種技能圖譜——如StuQ的技能圖譜。

![skilmap](./img/skillmap.png)

然後瞭解圖譜上的一個個的內容，儘可能依照此構建自己的體系——以讓自己走向知道自己不知道的地步，然後我們才依此來展開練習。

建議試試我們家的Growth哈，地址：http://growth.ren。

文章的剩下部分就讓我分享一下：在這723天裡，我創造出了哪些有意思的東西（ps：讓我裝逼一下）——其實我不僅僅只是 Markdown 寫得好

#### 2014年

時間：2014.10.08-2014.12.30

![2014.png](./img/2014.png)

在這一段時間裡，我建立的項目大部分都是一些物聯網項目：

 - [iot-coap](https://github.com/phodal/iot-coap) 一個基於CoAP協議的物聯網
 - [designiot](https://github.com/phodal/designiot) 即電子書《教你設計物聯網系統》
 - [iot-document](https://github.com/phodal/awesome-iot-document) 收集一些物聯網相關的資料，和Awesome不是一個性質
 - [iot](https://github.com/phodal/iot) 基於PHP框架Laravel的物聯網
 - iot-android 一個與iot項目相配套的Android程式
 - 等等

正是這幾個IoT項目，讓Packt出版社找到了我，才有了後來和國內外出版社打交道的故事。也開始了技術審閱、翻譯、寫書的各種故事，想想就覺得這個開頭真的很好。

期間還建立了一個很有意思的Chrome外掛，叫onebuttonapp——沒錯，就是模仿Amazon的一鍵下單寫的。這個外掛的目的就是難證當時在項目上用的Backbone、Require.js的這一套可以在外掛上好好玩。

OnMap項目是為了讓我用Nokia Lumia 920拍照的照片，可以在地圖上顯示而建立的項目。

當然還有其他的一些小項目啦。

#### 2015年

![2015.png](./img/2015.png)

整個區間就是刷各種前端的技術棧，建立了各種有意思的項目：

 - [Lettuce框架](https://github.com/phodal/lettuce)，一個基於簡單的SPA框架
 - [echoesworks](https://github.com/phodal/echoesworks)，一個支援字幕、Markdown、動畫的Slide框架
 - [diaonan](https://github.com/phodal/diaonan)，一個支援CoAP、MQTT、HTTP的物聯網項目
 - [developer](https://github.com/phodal/developer)，收集各種 Web Developer 成長路線，以及讀書圖譜


期間還建立了幾個混合應用項目：

  - [learning-ionic](https://github.com/phodal/learning-ionic)，程式語言答人，各種hello,world的小應用
  - [ionic-elasticsearch](https://github.com/phodal/ionic-elasticsearch), Django ElasticSearch Ionic 打造 GIS 移動應用
  - [designiot-app](https://github.com/phodal/designiot-app)，教你設計物聯網APP版

更多內容可以見我的Idea列表：[https://github.com/phodal/ideas](https://github.com/phodal/ideas)，我實在是不想寫了。

#### 2016年

![2016.png](./img/2016.png)

我們有了Growth系列的電子書、APP，還有Mole，幾個極具代表性的項目就夠了。

 - [Growth](https://github.com/phodal/growth)，一款專注於Web開發者成長的應用，涵蓋Web開發的流程及技術棧，Web開發的學習路線、成長衡量等各方面。
 - [Growth: 全棧增長工程師指南](https://github.com/phodal/growth-ebook)，一本關於如何成為全棧增長工程師的指南
 - [Growth: 全棧增長工程師實戰](https://github.com/phodal/growth-in-action)，在Growth中我們介紹的只是一系列的實踐，而Growth實戰則會帶領讀者去履行這些實踐

### See you Again

停止這次連擊，只是為了有一個更好的開始。

如果你也想提高自己，不妨從建立你的 ideas 項目開始，如我的[Ideas](https://github.com/phodal/ideas)項目一樣，上面已經有了大量的 Idea。然後，我們還可以依據這一個個的項目，建立出一本電子書，即 [ideabook](https://github.com/phodal/ideabook)。


GitHub 里程碑
===

寫在GitHub 的第 19999 個 star 時
---

>  Star 雖好，可不要貪杯哦。
> 兩年前在做 Annual Review 訂下一年的目標時，想著寫一個開源框架。去年訂下今年的目標時，仍然繼續著這樣的想法。今年又要制定下一年的目標，2333~~。

不久前，在 GitHub Ranking 上看到自己的 star 數（star 不是設計用於做“點贊”的，而是用來收藏的）時，發現已經快 20000 了。然後把自己的項目過了一遍，發現沒有一個比較好的**代表性框架，**要麼是應用，要麼是電子書。

前 8 個項目裡，除了 Growth 應用以外，其他的都是電子書內容——六本電子書加起來的 star 數有 **10619**，果然是騙 star 的。我只能盡力地去想想：為什麼事情會變成這樣了？

### 從建立開源框架說起

建立開源框架和建立建立開源項目是不一樣的，前者你服務於開發者，後者你服務於使用者。

兩年前在做 Annual Review 的時候，想著未來的一年裡可以做一個開源框架試試。那時剛畢業不久，對開源世界的各種遊戲規則不是很瞭解：**開源並不是將程式碼提交上去，然後就會一下子火起來**。雖然我們可以在短期內賺上一些眼球，但是真正要將它採用到項目上的人不多。

當時，我遇到的最主要的問題是：**想參與到項目的人並沒有遇到足夠的能力**。你還需要花費大量的時間去教他們，鼓勵 GitHub 新手並不是一件容易的事。有時我需要在接受他的 PR 後，再修改他的程式碼。並且人們提交 PR 可能是出於不同的原因。

然後，知道了開源世界還有一個遊戲規則是：**誰的影響力大，誰就能產生更廣泛的影響**。如 Virtual Dom 並不是 Facebook 首創的，但是卻因為 FB 火的； 松本行弘在寫下 mruby 的 README 時（印象中是這個項目），star 數就已經過 1k 了。這種例子數不勝數，要麼是在推廣上花了力氣，要麼個人、公司有著更大的影響力。

一年前，稍微改變了下策略：暫時以**培養人為主**，同時想著做一個合適的開源框架——只是在今年看來，前端領域已經沒有合適的地方可以造輪子了。

在 GitHub 上有一個很常見的問題是，**大多部分項目的維護者就是發起人**——如果這個發起人發生意外了，那麼這個項目怎麼辦。如果這是一個很火的項目，它就存在著巨大的風險；同時這可能也說明了，缺乏一套合理的機制。

你的開源項目不僅僅需要一個使用文件，還需要一個相關設計思想的文件、路線圖、未來計劃等等。

去年年底寫總結的時候，想到可以 RePractise 文章為基礎來培養人，於是就有了 Growth 的三個項目：

 - 應用：[Growth](https://github.com/phodal/growth)
 - 電子書：《[Growth：全棧增長工程師指南](https://github.com/phodal/growth-ebook)》
 - 電子書：《[Growth：全棧增長工程師實戰](https://github.com/phodal/growth-in-action)》

如今 Growth 已經有了過萬的使用者，每天活躍的使用者數也接近 300 了。第一步看上去很成功，但是下一步怎麼走呢？

### 下一個開源項目

後來我開始在思索一個問題，建立一個開源框架是必須的嗎？

在編寫 Growth 電子書的時候，我發現一個好的軟體工程實踐遠遠比一個易上手的框架重要多了。框架本身是易變的東西，過去你在用 Backbone，現在你在用 React.js；過去你在用 Angular.js，現在你在用 Vue。會不會使用某個框架，並不是區分你是不是一個有經驗的開發者的標準。

一直將焦點關注於**學習不同的框架的使用**是有問題的，一個在校生可以輕鬆地比你瞭解某個框架的原理——你白天在工作，而他整天在學習。這時你很容易就失去競爭力了，你需要從框架之外瞭解更深層次的東西。**一個好的框架並不能讓你寫出一段好的程式碼**。

> 如果中國人的思想不覺悟，即使治好了他們的病，也只是做毫無意義。

這算是我為自己在 GitHub 下的 Markdown 的自辯吧——誰讓我一直有寫作的衝動呢。

不過我仍然還有一些想法，只是還沒有抽出足夠的時間去思考這樣的事。

**GNU/Linux 的桌面**。這是幾年前的一個想法了，當時 GNU/Linux 的那些作業系統上都沒有一個好玩的桌面，不過感覺這個坑太深了，就沒有進行了。

**家居智慧中心**。我仍然對於大學學的知識有點念念不忘，雖然已經寫了一本書，但是硬體還是相當的刺激。唯一的問題是：連房子都沒有，怎麼做智慧家居。

**圖形框架**。這是我之前在做一個圖形介面的時候，發生沒有一個合適的框架可以滿足我的要求。然後我就在想，還是自己做一個吧。

不過，最好的開源項目就是自己平時用的。於是，我開始將寫各種工作來提自己使用——如現在在用的這篇微信編輯工具：[mdpub](https://github.com/phodal/mdpub)。

最後，我做了一個簡單的 HTML 5 動畫來記錄這一時刻，作為這一個里程碑的記念：

[https://phodal.github.io/20k/](https://phodal.github.io/20k/)
