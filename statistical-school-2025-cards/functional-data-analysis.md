# 函數型資料分析 Functional Data Analysis
一、FDA 核心觀念 函數型資料：每一筆資料是整條曲線（如溫度、身高等），非單一數值 關鍵假設：平滑性（smoothness） 模型形式：資料是來自無限維空間的隨機函數

二、應用領域 & 範例 生長曲線：如女孩身高隨年齡變化 氣象資料：每日氣溫與降雨 書寫筆劃運動軌跡：20 次手寫 "fda" 交通流量資料：240 天之交通流量軌跡 基因表現資料：基因隨時間的表現曲線

三、資料處理步驟

表示資料（Representing Functional Data） 基底展開（Basis Expansion）： Fourier：週期性資料 B-spline：非週期性資料 Local Polynomial：局部平滑 平滑方法： 最小平方法（Least Squares） 加入平滑懲罰項（Roughness Penalty, e.g., GCV）

探索性資料分析（EDA） 函數的平均與變異數：mean.fd(), var.fd() 共變異數與相關函數 Functional PCA：提取主要變異方向 使用 Karhunen–Loève 展開 可視化主成分與分數（scores）

四、R語言與fda套件應用 常用物件 basis：基底系統定義 fd：儲存函數資料 fdPar：包含懲罰項與平滑參數 bifd：雙變數函數

常用函數 create.bspline.basis(), create.fourier.basis() smooth.basis(): 平滑資料 eval.fd(), plot.fd(): 評估與繪圖 pca.fd(), varmx.pca.fd(): 主成分分析與旋轉

六、Functional Linear Models（函數型線性模型） 模型類型 函數型自變數 → 標量因變數（e.g., 溫度曲線 → 作物產量） 標量自變數 → 函數型因變數（e.g., 性別 → 生長曲線） 函數型自變數 → 函數型因變數（e.g., 力量 → 速度）

R 套件實作 fRegress()：估計模型 fRegress.stderr()：取得標準誤 fRegress.CV()：交叉驗證 plotbeta()：繪製係數與信賴區間
