# Hybrid Statistical Forecasting of Daily Screen Time

## 📌 Project Overview
Predicting human behavior (like screen time) is challenging due to small sample sizes, strong weekly seasonality, and abrupt shifts caused by external events (e.g., academic deadlines). 

This project, developed as part of the **MDSAI program at the University of Waterloo**, proposes a novel **Sequential Hybrid Prophet-GLM** approach. It leverages the strengths of additive seasonal decomposition and structured residual correction to outperform standard baselines like SARIMA and standard Prophet.

## 🚀 Key Achievements
* **Reduced Prediction Error:** The Hybrid Prophet-GLM model achieved the lowest **MAE** and **RMSE** across all participants.
* **Structural Break Handling:** Successfully modeled "cramming behavior" and academic deadlines using **Total-Variation (TV) Regularization**.
* **Advanced Feature Engineering:** Integrated Fourier seasonality, academic event indicators, and assignment urgency metrics as exogenous regressors.

## 🛠️ Technical Methodology
The framework consists of three progressively expressive modules:
1. **TV-Regularized GLM:** A Poisson GLM utilizing Fused Lasso (Total-Variation) penalty to capture piecewise-constant shifts in behavioral baselines.
2. **Enhanced Prophet:** Augmented the standard Facebook Prophet procedure with customized exogenous regressors.
3. **Sequential Hybrid Model:** - **Backbone:** Prophet captures long-term non-linear seasonal trends.
   - **Residual Correction:** The TV-GLM learns structured corrections from Prophet's residuals to handle event-driven structural breaks.

## 📊 Results Summary
| Model | MAE | RMSE |
| :--- | :--- | :--- |
| Seasonal Naive | 134.72 | 163.78 |
| SARIMA | 123.36 | 162.72 |
| Prophet (Standard) | 120.35 | 155.67 |
| **Hybrid Prophet-GLM** | **110.12** | **145.34** |
*(Values represent the average across test participants)*

## 📂 Project Structure
* `notebooks/`: Exploratory Data Analysis (EDA) and model experimentation.
* `src/`: Implementation of the TV-GLM solver and Hybrid framework.
* `report/`: Full technical report (CS680 Final Report).

## 💡 Public Sector & Business Impact
This methodology can be directly applied to **Public Sector** challenges such as:
* **Resource Demand Forecasting:** Predicting sudden spikes in government service usage during policy changes or deadlines.
* **Public Health Monitoring:** Analyzing behavioral shifts in longitudinal wellness data to provide personalized interventions.
