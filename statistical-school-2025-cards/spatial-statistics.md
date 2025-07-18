# 空間統計 Spatial Statistics


What Is Spatial Statistics?
- Data are observed or collected at spatial locations – Spatial data
- Spatial statistics is concerned with analysis of spatial data in which the set of spatial locations are taken into account
- Data and/or locations are modeled as random, and inferences are made about these models or about additional unobserved quantities
- Spatial locations are used in a spatial analysis to model statistical dependence

---

$Y_i \mid Y_{-i} \sim \mathcal{N}\left(\sum_{j \neq i} c_{ij} Y_j, \, \tau^2\right)$

$\mathbf{Y} \sim \mathcal{N}\left(\mathbf{0}, \, (\mathbf{I} - \rho \mathbf{W})^{-1} \tau^2 \right)$

$\mathbf{Y} = \rho \mathbf{W} \mathbf{Y} + \mathbf{X}\boldsymbol{\beta} + \boldsymbol{\epsilon}$

$\boldsymbol{\epsilon} \sim \mathcal{N}(\mathbf{0}, \sigma^2 \mathbf{I})$

$\mathbf{Y} \sim \mathcal{N}\left((\mathbf{I} - \rho \mathbf{W})^{-1} \mathbf{X}\boldsymbol{\beta}, \, \sigma^2 (\mathbf{I} - \rho \mathbf{W})^{-1} (\mathbf{I} - \rho \mathbf{W}^\top)^{-1} \right)$

Spatial correlation decreases with distance, which affects statistical inference. This phenomenon is commonly observed in fields such as forestry, astronomy, epidemiology, and geology.
After merging spatial data blocks, smoothing techniques should be applied to maintain continuity.
Time series regression is used to estimate correlations or model dynamic changes over time.
In regression models, maximum likelihood estimation (MLE) is used to estimate parameters.
In spatial autoregressive (SAR) models, a lower AIC value indicates a better fit.
For conditional autoregressive (CAR) models, the weight matrix w ij is binary (0 or 1) with zeros on the diagonal.
To understand the spatial structure of variables, appropriate weighting and techniques such as the internal difference method can be applied.


