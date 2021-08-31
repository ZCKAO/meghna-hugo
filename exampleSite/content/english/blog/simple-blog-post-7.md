---
title: "【陪你讀論文】Monte Carlo Method"
date: 2021-08-30T00:00:00+08:00
image_webp: ''
image: ''
author: Alpha Kao
description: hi
draft: true

---
> **我們想讓你知道的是：**蒙地卡羅是一種隨機生成樣本的方法來估算真實值，利用上萬次的模擬出真實的樣子

##### 本文重點：

1. 模擬次數越多，出來的結果會愈接近真實值
2. 利用蒙地卡羅生成的未來隨機股價走勢圖，若與真實的開發策略走勢相距越遠表示發生over-fitting的機率越小。

pip install pandas_datareader

pip install --upgrade pandas