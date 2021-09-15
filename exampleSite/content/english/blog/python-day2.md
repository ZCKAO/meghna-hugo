+++
author = "Alpha"
date = 2021-09-13T16:00:00Z
description = "from台大資訊系統訓練班"
image = "/images/量化研究員應具備的 基本能力.jpg"
image_webp = "/images/量化研究員應具備的 基本能力.jpg"
title = "【量化金融人】Python財務計算Day2"

+++
> 我們想讓你知道的是：量化研究員應具備資料擷取、資料視覺化、策略發想、回測

### 資料擷取

利用 [**ffn **](https://pmorissette.github.io/ffn/ "ffn")套件：只要在Yahoo Finance上的資料都可以抓，EX：台股、美股、期貨、比特幣...

### 資料視覺化

利用圖表觀察嘗試找策略

`porfolio.pct_change()`  #算報酬率，會希望向右邊偏，通常這樣期望值才會是正的

`return rate`  #通常是對稱分佈，若能向右邊偏，就是賺錢的Know how

* 交易頻率愈高愈容易發生厚尾的效應 ，也就是出現outlier的機率愈高，而交易頻率越低，越容易呈現標準常態分配

### 訊號

`portfolio.calc_stats()`  #可算出所有會關心的統計量

***

訊號：短線由下往上穿越長線做多：當短線(2)<長線(2) & 短線(1)>長線(1)

註：shift是平移幾天的訊號，預計在(0)才會做交易

`asset["sma5"].shift(2) < asset["sma10"].shift(2)) & (asset["sma5"].shift(1) > asset["sma10"].shift(1)`

今天的收盤價不一定買得到，看得到不一定吃得到，可以用今天的收盤價來建立部位，所以用隔天的價格(open/close)建立部位的成本

### 策略發想、回測

看出績效較差的部分在哪裡、和最大回檔Max drawdown，或是比較跟buy and hold誰的return比較好，想辦法打敗buy and hold，若績效較不好可以換資產(多資產)或調整參數或是加空單策略(多空不會同時進行，除非日內交易)、檢查程式端打錯或是邏輯上的錯誤

調整策略：例如乖離率 booling bands

DD是指在沒有過前高的情況下之**最大回檔深度**

計算方式：`asset["PV"].cummax().cummin()`

![](/images/2021-09-15-4-32-01.png)