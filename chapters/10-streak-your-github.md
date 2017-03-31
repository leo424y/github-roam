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
