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
