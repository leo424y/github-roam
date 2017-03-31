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
