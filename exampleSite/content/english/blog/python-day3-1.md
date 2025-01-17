+++
author = "Alpha"
date = 2021-09-14T16:00:00Z
description = "from台大資訊系統訓練班"
image = "/images/常見的統計實務應用.jpg"
image_webp = "/images/常見的統計實務應用.jpg"
title = "【量化金融人】Python財務計算Day3"

+++
#### 數學工具介紹

#### Numpy

向量化、矩陣操作 vector matrix

減少寫迴圈的機會，且運算速度較快

`np.linspace(0, 10, 11)`  #從0出發到10 切成11等分

內積、反矩陣

`linalg`

應用：效率前緣的投資組合內N檔資產裡的權重

線性代數推薦影片：[**3blue1brown**](https://www.youtube.com/playlist?list=PLZHQObOWTQDPD3MizzM2xVFitgF8hE_ab)

#### Scipy

內差 最佳化 統計檢定 檢定量 積分

內差：當資料較少時，需要估計中間的值。又分為線性內差或是較平滑的內差`cubic spline`

例如：美國公債殖利率的頻率較少，可透過內差建模用在利率模型

最佳化應用：投資組合最佳化return、risk(成本最小、效用最大)，

考量到每多一單位的風險他的報酬。

微分透過gradient descent找出全域最佳解Global minimum

#### 統計檢定解讀

    Step1. 看p-value是否顯著
    Step2. 看coefficience準不準、stander error不要太大
    Step3. 看殘差、模型配置的好不好 
    	   可由Durbin Watson看樣本之間是否有相關性、R-squared

p-value > alpha  無顯著差異，無法拒絕H0

p-value < alpha 此統計量有顯著差異，拒絕H0