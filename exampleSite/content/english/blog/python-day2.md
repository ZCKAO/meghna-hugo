+++
author = ""
date = ""
description = ""
draft = true
image = ""
image_webp = ""
title = "【金融人】Python財務計算Day2"

+++
#### 資料擷取

ffn套件 只要在Yahoo Finance上的資料都可以抓EX 台股 美股 期貨、比特幣...

#### 資料視覺化

利用圖表觀察嘗試找策略

porfolio.pct_change() 算報酬率 會希望向右邊偏 通常期望值才會是正的

return rate通常是對稱分佈，若能向右邊偏 就是賺錢的Know how

交易頻率愈高愈容易發生厚尾的效應 ，也就是出現outlier的機率愈高，交易頻率越低 越容易呈現標準常態分配

#### 訊號

portfolio.calc_stats()可算出所有會關心的統計量

訊號：短線由下往上穿越長線做多：當短線(2)<長線(2) & 短線(1)>長線(1)

註：shift是平移幾天的訊號，預計在(0)才會做交易

asset\["sma5"\].shift(2) < asset\["sma10"\].shift(2)) & (asset\["sma5"\].shift(1) > asset\["sma10"\].shift(1)

今天的收盤價不一定買得到，看得到不一定吃得到，可以用今天的收盤價來建立部位，所以用隔天的價格(open/close)建立部位的成本

#### 回測

看出績效較差的部分在哪裡、和最大回檔Max drawdown，或是比較跟buy and hold誰的return比較好，想辦法打敗buy and hold，若績效較不好可以換資產(多資產)或調整參數或是加空單策略(多空不會同時進行，除非日內交易)、檢查程式是否有錯、邏輯上的錯誤