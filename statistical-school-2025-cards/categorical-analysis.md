# 類別資料分析 Categorical Analysis
#mushroom
#intention
#1.看各類別出現的頻率 → 描述統計
#2.看類別與類別之間是否有關 → 列聯表、卡方檢定
#3.建立預測模型 → logistic regression、決策樹等


類別資料分析

複習網址
1. https://scgeeker.github.io/lsj-book-zh_tw/10-Categorical-data-analysis.html


類別
可以用
.count
.yes/no

goal 
1.find the association between different mushrooms

2.How to choose parameters


Notation
1.設定兩種類別的應變數
2.可以將兩種類別的變數繪製成交叉表(列連表)

parameter
1.πij=P[X=i,Y=j]
2.列邊際機率總和=行邊際機率總和=聯合機率總和

Difference of proportion
1.π1=π2>>獨立
2.比大小>>π2-π1>>介於-1~1
3.用相差比較大小時，需注意，如果兩個數值極微小，差值也小，但比率不見得小
Ex:
  0.0007-0.0014=-0.0007
  0.0007/0.0014=1/2
  *因此較少在實際應用，改用OR(勝算比)

Odds ratio(OR,勝算比)
1.Ω=π/(1-π)
2.
  OR is defined as
  θ=Ω1/Ω2


除了用Difference of proportion & Odds ratio推論數據間的關聯性之外，也可以用皮爾森卡方檢定

皮爾森卡方檢定
H0:數據間有關係
H1:數據間沒有關係

1.Under H0
  E[nij]=μij
  μ_hat=n*pi+*p+j,i=1,....,I,j=1,....,J
where pi+=

  df=(I-1)*(J-1)

2.
P-value=P[X^2 >= X0^2]


Predictive power-Classification tables(預測能力分類表)
1.
Sensitivity = P[y_hat = 1|y=1]
Specificity = P[y_hat = 0|y=0]
Accurcy= P[y_hat = 1|y=1] or P[y_hat = 0|y=0](Sum)

2.Set a π0 is srbitrary (we set π0=0.5 in uausal )
  PS:π0 can be set 0.4、0.6、.....

3. y=1 if π>π0
   y=0 if π<π0



羅吉斯的分類好處是，算出來的係數 is positive，資料則有正相關，反之，亦同 











