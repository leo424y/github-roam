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
