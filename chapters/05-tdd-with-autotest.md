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
