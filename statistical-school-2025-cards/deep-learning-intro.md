# 深度學習導論 Deep Learning Intro

## 上課心得
本次深度學習導論為顏佐榕教授指導，讓我們用嚴謹和深入的視角初步認識深度學習的作用。
其中最為印象的是 Image Traslation 和 Point Cloud Reconstruction，

DDIM使用了動態的方式來採樣；而DDPM是遵照著馬可夫鏈，使用固定的變異數來採樣。
DDIM可以跳過一些擴散時間進行採樣；但DDPM必須遵照時間一個一個採樣。這代表DDIM可以預測可能10個擴散時間後的結果，這就代表比起一次1個擴散時間的DDPM，DDIM的速度就被增加了10倍！

# Data Annotation
-Label Studio ( A tool designed to assist in accurate data labeling and result verification. )/n
-LLM labeling ( It is more appropriate for a language model to provide positive/neutral/negative responses to the data, rather than outputting a numerical score.)
