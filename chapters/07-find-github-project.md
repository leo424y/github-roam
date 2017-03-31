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
