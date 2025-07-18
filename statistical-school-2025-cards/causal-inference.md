# 因果推論 Causal Inference
# Causal Inference 筆記

## 1. 基礎概念
- **為什麼需要因果推論？**
  - 與相關性的區別
- **Counterfactual（反事實框架）**
  - 例子與數學定義
- **因果圖（Causal Diagram, DAG）**
  - 節點、邊、路徑概念
- **Confounder / Mediator / Collider**
  - 定義與差異

---

## 2. 因果推論的主要假設
- Ignorability（可忽略性）
- Positivity（可行性/覆蓋性）
- Stable Unit Treatment Value Assumption (SUTVA)
- Exchangeability

---

## 3. 因果效應定義
- Average Treatment Effect (ATE)
- Average Treatment Effect on the Treated (ATT)
- Conditional Average Treatment Effect (CATE)
- Marginal Treatment Effect (MTE)

---

## 4. 常用方法
### 4.1 傳統方法
- Regression Adjustment（回歸調整）
- Stratification（分層分析）
- Standardization（標準化）

### 4.2 傳統觀察性方法
- Matching（匹配法）
  - Propensity Score Matching (PSM)
  - Mahalanobis Distance Matching
- Weighting（Inverse Probability Weighting, IPW）
- Doubly Robust Estimation（雙穩健估計）

### 4.3 進階方法
- Instrumental Variables (IV)
- Difference-in-Differences (DiD)
- Regression Discontinuity Design (RDD)
- Synthetic Control

### 4.4 圖模型與 do-calculus
- Pearl’s do-operator
- Back-door & Front-door Criteria

### 4.5 Modern Causal ML
- Causal Forest
- Targeted Maximum Likelihood Estimation (TMLE)
- Bayesian Causal Inference

---

## 5. 因果識別與檢驗
- DAG 與識別條件（backdoor / frontdoor）
- Sensitivity Analysis（敏感度分析）
- Placebo Test
- Falsification Test

---

## 6. 應用案例
- 醫療研究（治療 vs. 對照）
- 公共政策分析（政策介入）
- 商業 A/B 測試
- 社會科學數據

---

## 7. 工具與程式實作
- R: `MatchIt`, `causalTree`, `causalForest`, `dagitty`
- Python: `DoWhy`, `EconML`, `CausalML`
- **實作流程範例：**
  1. DAG 建模  
  2. 資料準備（confounder 處理）  
  3. 方法選擇  
  4. ATE 估計與檢驗  

---

## 8. 延伸閱讀與經典書籍
- Judea Pearl: *Causality*
- Hernán & Robins: *Causal Inference: What If*
- Imbens & Rubin: *Causal Inference for Statistics, Social, and Biomedical Sciences*
- Scott Cunningham: *Causal Inference: The Mixtape*
