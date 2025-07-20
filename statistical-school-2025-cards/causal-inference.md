

# 因果推論-Part I 反事實結果與可互換性

## 1. 潛在結果表示（Potential Outcomes）
- 描述個體在不同處理狀況下可能的結果 \(Y(s=0), Y(s=1)\)。
- 有助於理解因果效應的實質。

**例子：**  
假設 Ian 和 Jim 是兩個人：  
- Ian：如果抽菸 \(Y(s=1)=1\)（會得肺癌），如果不抽菸 \(Y(s=0)=0\)（不會得肺癌）。  
- Jim：如果抽菸 \(Y(s=1)=0\)（不會得肺癌），如果不抽菸 \(Y(s=0)=0\)（不會得肺癌）。

---

## 2. 因果關係（Causation）與關聯（Association）
- **關聯**：觀察到的平均差異 E[Y|S=1] - E[Y|S=0]，不一定等於因果效應。
- **因果**：指處理 \(S\) 對結果 \(Y\) 的真實影響。

**例子：**  
在資料中：  
- 抽菸者有 40% 得肺癌（E[Y|S=1]=0.40）。  
- 不抽菸者有 10% 得肺癌（E[Y|S=0]=0.10）。  
- 關聯為 0.40 - 0.10 = 0.30，但這是否完全由抽菸造成仍需檢驗。

---

## 3. 交換性（Exchangeability）
- 假設潛在結果在不同處理組之間是可互換的。
- 治療組與控制組在潛在結果上具有平衡性。
- **隨機化（Randomization）** 通常用於保證交換性。

**例子：**  
如果抽菸組與不抽菸組在人種、飲食、遺傳等方面相同，  
則可以認為潛在結果是可交換的。  
假設 Ian 和 Jim 被隨機分派抽菸與否，Ian 抽菸的結果與 Jim 不抽菸的結果可以直接比較。
也就是說，抽菸組與不抽菸組在「假設不抽菸」的世界下，得到肺癌的風險是一樣的。


---

## 4. 因果一致性（Causal Consistency）
- 當個體接受實際處理時，觀察結果 \(Y\) 等於潛在結果 \(Y(s)\) 中對應的值。

**例子：**  
- Ian 實際抽菸（S=1），因此 Y=1 等於 \(Y(s=1)\)。  
- Jim 實際不抽菸（S=0），因此 Y=0 等於 \(Y(s=0)\)。

---

## 5. 因果效應測量
- **個體因果效應**：\(Y(s=1) - Y(s=0)\)。  
- **平均因果效應（ACE）**：  
  \[
  ACE = E[Y(s=1)] - E[Y(s=0)]
  \]

**例子：**  
- 對 Ian 而言：\(Y(s=1)-Y(s=0)=1-0=1\)。  
- 假設 E[Y(s=1)]=0.40、E[Y(s=0)]=0.10，  
  則 ACE = 0.40 - 0.10 = 0.30。

---

## 6. 條件交換性（Conditional Exchangeability）
- 當控制協變數 \(L\)（如基因、年齡）後，有 \(Y(s) \perp S \mid L\)。  
- 條件下的關聯可以更接近真實的因果效應。

**例子：**  
考慮基因或年齡等混雜因子，控制這些因素後，  
可比較相同條件下抽菸與不抽菸的結果。

---

## 7. 總結
- 當 **（條件）交換性 + 一致性** 成立時，  
  \[
  E[Y(s=1)] - E[Y(s=0)] = E[Y|S=1] - E[Y|S=0]
  \]
  即關聯 = 因果效應。  
- 重點是判斷何時觀察到的關聯能真實反映因果關係。

  
# 因果推論 - Part II：因果中介與例子

## 1. 基本概念
- **中介分析（Mediation Analysis）** 用於研究「處理 ![公式](https://latex.codecogs.com/svg.latex?S) → 中介變數 ![公式](https://latex.codecogs.com/svg.latex?M) → 結果 ![公式](https://latex.codecogs.com/svg.latex?Y)」的因果機制。
- **總效應 (Total Effect, TE)** 可拆解為：
  - **自然直接效應 (Natural Direct Effect, NDE)**
  - **自然間接效應 (Natural Indirect Effect, NIE)**

![公式](https://latex.codecogs.com/svg.latex?TE%20=%20NDE%20+%20NIE)

**例子：**  
假設我們想研究「是否運動 (S) → 體重 (M) → 血壓 (Y)」。運動可能直接降低血壓 (NDE)，也可能通過減少體重間接降低血壓 (NIE)。

---

## 2. 潛在結果與反事實（Counterfactuals）
- 潛在結果記為 ![公式](https://latex.codecogs.com/svg.latex?Y(s,m))：表示處理設定為 ![公式](https://latex.codecogs.com/svg.latex?s)，中介變數設定為 ![公式](https://latex.codecogs.com/svg.latex?m) 時的結果。
- 反事實分析步驟（以「基因型 ![公式](https://latex.codecogs.com/svg.latex?S) → 喝酒 ![公式](https://latex.codecogs.com/svg.latex?M) → 肝癌 ![公式](https://latex.codecogs.com/svg.latex?Y)」為例）：
  1. 假設介入設定 SNP = ![公式](https://latex.codecogs.com/svg.latex?s_0)。
  2. 觀察 ![公式](https://latex.codecogs.com/svg.latex?M(s_0))：喝酒行為的反事實值。
  3. 再設定 SNP = ![公式](https://latex.codecogs.com/svg.latex?s_1)，並固定 ![公式](https://latex.codecogs.com/svg.latex?M) 為 ![公式](https://latex.codecogs.com/svg.latex?M(s_0))，觀察 ![公式](https://latex.codecogs.com/svg.latex?Y(s_1,%20M(s_0)))。

**例子：**  
假設一名基因型為 `s_1` 的人，在實際情況下他可能多喝酒而增加肝癌風險。如果我們能把他的喝酒習慣固定為基因型 `s_0` 的人那樣，我們就能觀察「假如他不喝酒，肝癌風險是否仍會高」。

---

## 3. 自然效應定義
- **自然間接效應 (NIE)**：
![公式](https://latex.codecogs.com/svg.latex?NIE%20=%20E[Y(s_1,%20M(s_1))]%20-%20E[Y(s_1,%20M(s_0))])
  表示處理 ![公式](https://latex.codecogs.com/svg.latex?S) 影響 ![公式](https://latex.codecogs.com/svg.latex?Y) 的那部分，**經由中介變數 ![公式](https://latex.codecogs.com/svg.latex?M) 傳遞**。

- **自然直接效應 (NDE)**：
![公式](https://latex.codecogs.com/svg.latex?NDE%20=%20E[Y(s_1,%20M(s_0))]%20-%20E[Y(s_0,%20M(s_0))])
  表示處理 ![公式](https://latex.codecogs.com/svg.latex?S) 對 ![公式](https://latex.codecogs.com/svg.latex?Y) 的影響，**不經由中介變數 ![公式](https://latex.codecogs.com/svg.latex?M)**。

**例子：**  
假設運動直接降低血壓 5 mmHg（NDE），同時運動減少體重，而減重又讓血壓下降 3 mmHg（NIE），那麼總效應 TE = 5 + 3 = 8 mmHg。

---

## 4. 假設條件
為了識別 (identifiability) ![公式](https://latex.codecogs.com/svg.latex?NDE) 和 ![公式](https://latex.codecogs.com/svg.latex?NIE)，需要：
1. **A1：** ![公式](https://latex.codecogs.com/svg.latex?Y(s,m)%20\perp%20S%20|%20X) （處理對結果無未觀察混雜）
2. **A2：** ![公式](https://latex.codecogs.com/svg.latex?Y(s,m)%20\perp%20M%20|%20S,%20X) （中介對結果無未觀察混雜）
3. **A3：** ![公式](https://latex.codecogs.com/svg.latex?M(s)%20\perp%20S%20|%20X) （處理對中介無未觀察混雜）
4. **A4：** ![公式](https://latex.codecogs.com/svg.latex?Y(s,m)%20\perp%20M(s^*)%20|%20X) （處理不影響 ![公式](https://latex.codecogs.com/svg.latex?M) 與 ![公式](https://latex.codecogs.com/svg.latex?Y) 之間的關係）

**例子：**  
在研究運動對血壓的影響時，我們要確保沒有其他未測量的因素（如遺傳、飲食）同時影響運動和血壓，否則無法準確分解 NDE 和 NIE。

---

## 5. 迴歸模型表示
- **中介模型：**
![公式](https://latex.codecogs.com/svg.latex?M_i%20=%20\alpha_0%20+%20\alpha_S%20S_i%20+%20\epsilon_{M,i})

- **結果模型：**
![公式](https://latex.codecogs.com/svg.latex?Y_i%20=%20\beta_0%20+%20\beta_S%20S_i%20+%20\beta_M%20M_i%20+%20\epsilon_{Y,i})

- 則：
![公式](https://latex.codecogs.com/svg.latex?NDE%20=%20\beta_S%20(s_1%20-%20s_0))
![公式](https://latex.codecogs.com/svg.latex?NIE%20=%20\alpha_S%20\beta_M%20(s_1%20-%20s_0))

**例子：**  
假設迴歸結果顯示運動對體重的影響係數 ![公式](https://latex.codecogs.com/svg.latex?\alpha_S=-2)，而體重對血壓的影響係數 ![公式](https://latex.codecogs.com/svg.latex?\beta_M=1.5)，那麼間接效應 NIE = -2 × 1.5 = -3 mmHg。

---

## 6. 範例
- **基因 → 喝酒 → 肝癌：**
  - Direct effect: ![公式](https://latex.codecogs.com/svg.latex?1.38%20(0.98,%201.95),%20p%20=%200.07)  
  - Indirect effect: ![公式](https://latex.codecogs.com/svg.latex?0.70%20(0.61,%200.82),%20p%20<%200.001)  
  - Total effect: ![公式](https://latex.codecogs.com/svg.latex?1.02%20(0.84,%201.25),%20p%20=%200.83)

- **PM2.5 → 肝功能 → 肝癌：**
  - Direct effect: ![公式](https://latex.codecogs.com/svg.latex?1.28%20(0.88,%201.92),%20p%20=%200.14)  
  - Indirect effect: ![公式](https://latex.codecogs.com/svg.latex?1.21%20(1.06,%201.41),%20p%20=%200.005)  
  - Total effect: ![公式](https://latex.codecogs.com/svg.latex?1.23%20(1.02,%201.48),%20p%20=%200.03)

**例子：**  
對於 PM2.5 → 肝癌，結果顯示間接效應顯著，說明 PM2.5 是透過改變肝功能影響肝癌的主要因素。

---

## 7. 總結
- 因果中介分析是在反事實框架下定義的。
- 總效應可以分解為自然直接與自然間接效應。
- 識別需要交換性（無未測量混雜）假設。
- 常用於探索因果機制，亦可為政策制定提供依據。

**例子：**  
若政策制定者要降低血壓，可以直接推廣運動（對應直接效應），或針對減重方案設計政策（對應間接效應）。
