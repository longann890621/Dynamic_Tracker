# Dynamic_Tracker
這是一個使用Python程式語言控制滑台機構，來追蹤汽車商標的程式碼範例，使用的滑台機構是是駿河精機股份有限公司的滑台，名為：XY軸直線滾珠:KYL06200。
首要的工作是要將滑台的座標與攝影機所照射到領空中的座標做一個匹配，由於領空是一個非線性的環境，因此使用機器學習的方式來訓練一個定位模型。

再來導入已訓練好的YOLOv7權重檔以及網路架構，接著導入點位模型檔，將上述這些網路作為後續需要的使用。接下來啟動攝影機開始捕捉畫面，這裡設定為每5個幀進行一次畫面檢測。
其中程式碼將捕捉到的影像轉換為YOLOv7框架所需要的輸入尺寸，最終進行畫面的檢測，看是否有欲辨識之物體。接下來程式系統根據預測的結果，來作為移動距離的依據。

在這個系統內，給定了兩個停止條件。分別為：超過一定的時間為捕捉到欲觀察的物體，或超過一定的時間判定欲移動的位置超過機構限制，則停止城市的運作。

最終將硬體機構及追蹤網路串接起來，完成最終的動態追蹤系統。
