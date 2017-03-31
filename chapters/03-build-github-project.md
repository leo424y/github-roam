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
