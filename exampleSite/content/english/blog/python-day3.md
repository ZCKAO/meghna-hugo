+++
author = "Alpha"
date = 2021-09-14T16:00:00Z
description = "from台大資訊系統訓練班"
image = ""
image_webp = ""
title = "【金融人】Python財務計算Day2-1"

+++
#### 台灣上市櫃公司資料爬蟲 開高低收、成交量

爬蟲的資料來源若不乾淨會影響ML做出來的結果

1\.首先先建之後資料要儲存的資料夾

2\.利用request將server回傳table

3\.資料清洗並寫入

4\.從原來的rawdata變成table，資料定義

若資料龐大 可利用 黑名單與白名單比對 過濾出自己的stock list

EX上市公司財報月營收

#### Pandas應用 

`df.sort_values`  #資料排序

`pd.to_datetime  #將資料轉換為時間格式`

df.set_index指定某一行為index

df.info() 看統計資料

df.shape 計算維度

df.count() 算有幾個raw

df.index

df.columns 看column header有哪些名字

df.describe() 敘述統計 例如平均值 標準差

'code'   
\`code\`

' 利用rolling算出均線 ' 