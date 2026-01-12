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
The performance was evaluated on a held-out 2-week test window for two participants, **Rae** and **Sophia**. The Hybrid model consistently achieved the lowest error metrics by combining smooth seasonal trends with sharp, event-driven corrections.

### **Participant 1: Rae**
| Model | MAE (min) | RMSE (min) |
| :--- | :--- | :--- |
| Seasonal Naive | 330.07 | 367.96 |
| Prophet (Standard) | 197.83 | 247.37 |
| SARIMA | 262.52 | 320.40 |
| Augmented Prophet | 175.51 | 202.86 |
| Weighted TV-GLM | 138.77 | 179.68 |
| **Hybrid Prophet-GLM** | **109.57** | **143.33** |

### **Participant 2: Sophia**
| Model | MAE (min) | RMSE (min) |
| :--- | :--- | :--- |
| Seasonal Naive | 414.00 | 467.24 |
| Prophet (Standard) | 271.96 | 309.32 |
| SARIMA | 323.08 | 389.65 |
| Augmented Prophet | 147.50 | 175.04 |
| Weighted TV-GLM | 92.62 | 141.39 |
| **Hybrid Prophet-GLM** | **87.49** | **128.62** |

*Note: Rae's mean daily usage was 678 minutes, and Sophia's was 710 minutes. An MAE of ~100 minutes represents a modest ~15% relative error in personal behavioral forecasting.*

## 📂 Project Structure
* `data/`: Contains the screen-time datasets for participants (Rae & Sophia).
* `codes/`: Modular Python implementation of the Hybrid Prophet-GLM framework.
* `CS680_Final_Report.pdf`: The full technical report detailing the mathematical derivation and experimental results.

## 💡 Public Sector & Business Impact
This methodology can be directly applied to **Public Sector** challenges such as:
* **Resource Demand Forecasting:** Predicting sudden spikes in government service usage during policy changes or deadlines.
* **Public Health Monitoring:** Analyzing behavioral shifts in longitudinal wellness data to provide personalized interventions.
