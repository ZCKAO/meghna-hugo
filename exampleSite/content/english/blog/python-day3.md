+++
author = "Alpha"
date = 2021-09-14T16:00:00Z
description = "from台大資訊系統訓練班"
image = ""
image_webp = ""
title = "【量化金融人】Python財務計算Day2-1"

+++
> ##### **我們想讓你知道的事：常見的pandas應用以及初學者所使用的回測平台**

**本文重點：**

    Step1. 先抓取資料
    Step2. 做回測

#### 台灣上市櫃公司資料爬蟲 開高低收、成交量

爬蟲的資料來源若不乾淨會影響ML做出來的結果

1\.首先先建之後資料要儲存的資料夾

2\.利用request將server回傳table

3\.資料清洗並寫入

4\.從原來的rawdata變成table，資料定義

若資料龐大 可利用 黑名單與白名單比對 過濾出自己的stock list

EX上市公司財報月營收、三法人買賣日報表、季財報

#### Pandas常見應用

`df.sort_values`  #資料排序

`pd.to_datetime`  #將資料轉換為時間格式

`df.set_index`  #指定某一行為index

`df.info()`  #看統計資料

`df.shape`  #計算維度

`df.count()`  #算有幾個raw

`df.index`  #查看索引

`df.columns`  #看column header有哪些名字

`df.describe()`  #敘述統計 例如平均值 標準差

`rolling`  #算出均線

`df["BIAS"] = (df["Close"] - df["SMA5"]) / df["SMA5"] * 100`

\#計算乖離率：現在價格離N日均線的比例超過X%時為進出場點

均值回歸：若乖離率過大，可能會收斂回均線

`loc` #取出整行或整列的資料

`pct_change() * 100`  #算出return rate

畫出股票的價與量圖

取得yahoo Finance資料可以利用此套件：ffn

* [https://pmorissette.github.io/ffn/](https://pmorissette.github.io/ffn/ "https://pmorissette.github.io/ffn/")

World Bank總經資料api

* [https://data.worldbank.org/indicator/NY.GDP.PCAP.KD.ZG](https://data.worldbank.org/indicator/NY.GDP.PCAP.KD.ZG "https://data.worldbank.org/indicator/NY.GDP.PCAP.KD.ZG")

#### 使用回測平台相關套件

缺點：需遵循別人的邏輯來將自己的策略套用在他人的平台上，較有限制性且等同於能讓對方看到你的策略。

較建議自己利用迴圈改寫，發展出自己的框架

[**Backtrader**](https://www.backtrader.com/ "Backtrader")

[**Quantopian**](https://github.com/quantopian)

實際上要做研究的話，調整後收盤價才是考慮的部分，因為除權息的部分要列入，否則會低估或是高估策略的表現

Object物件：創造一個東西打包成讓別人可以重複使用的。

主要由兩個部分組成：

1\.date  EX：YYYY/MM/DD、資料

2\.action EX：計算出duration(days)、策略