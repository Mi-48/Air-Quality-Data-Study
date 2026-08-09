# Air Quality Data Study — Islamabad, Pakistan (2019–2023)

A data analysis project exploring air pollution trends and predictors of PM2.5 concentration in Islamabad over 3.5 years, using Python-based EDA, correlation analysis, and machine learning regression models.

---

## Overview

Air quality in urban Pakistan is a growing public health concern. This study uses official EPA monitoring data to track concentrations of PM2.5, NO₂, and SO₂ across Islamabad from June 2019 to March 2023 — examining seasonal trends, environmental drivers, and building predictive models for PM2.5 levels.

---

## Objectives

- Track monthly and seasonal trends in PM2.5, NO₂, and SO₂ concentrations over 3.5 years
- Quantify the effect of temperature and humidity on PM2.5 levels
- Measure correlations between pollutants (NO₂, SO₂) and PM2.5
- Train and compare Linear Regression and Random Forest models to predict PM2.5 concentration

---

## Dataset

| Property | Detail |
|---|---|
| **Source** | Pakistan Environmental Protection Agency (EPA) via [Kaggle](https://www.kaggle.com/datasets/diraf0/islamabad-pakistan-air-quality-data) |
| **Period** | June 2019 – March 2023 |
| **Variables** | PM2.5, NO₂, SO₂ (µg/cm³), Temperature (°C), Humidity (%) |
| **License** | Public Domain |

---

## Tools & Libraries

- **Python** — Pandas, NumPy, Matplotlib, SciPy, Scikit-learn
- **Jupyter Notebook**

---

## Methodology

### 1. Exploratory Data Analysis
- Day-wise scatter plots per year for PM2.5, NO₂, and SO₂ with WHO/EPA health threshold reference lines
- Average monthly trend lines compared across all years (2019–2023)
- Seasonal pattern identification across winter and summer months

### 2. Correlation & Regression Analysis
Linear regression fitting and Pearson correlation were computed between PM2.5 and each predictor:

| Predictor | Correlation with PM2.5 | Direction |
|---|---|---|
| Temperature | Strong | Negative |
| Humidity | Weak | Positive |
| NO₂ | Moderate | Positive |
| SO₂ | Moderate | Positive |

### 3. Predictive Modelling
Both models were trained on 70% of the combined dataset and tested on the remaining 30%, using Temperature, Humidity, NO₂, and SO₂ as features to predict PM2.5.

| Model | R² Score | Notes |
|---|---|---|
| Linear Regression | 0.34 | Moderate explanatory power |
| Random Forest | 0.52 | +18% improvement over linear model |

---

## Key Findings

1. **PM2.5 levels were within acceptable range on average**, but consistently exceeded safe thresholds during winter months across all years.
2. **2020 recorded the highest PM2.5 spike**, with a notable decline in subsequent years.
3. **Temperature is the strongest predictor of PM2.5** — lower temperatures correlate with significantly higher PM2.5 concentrations, consistent with reduced atmospheric dispersion in winter.
4. **NO₂ and SO₂ showed moderate positive correlations** with PM2.5, suggesting shared emission sources (fossil fuel combustion, vehicle exhaust).
5. **Humidity showed only a weak positive relationship** with PM2.5.
6. **Random Forest outperformed Linear Regression by 18%** (R²: 0.52 vs 0.34), indicating non-linear interactions between predictors — for example, humidity may increase PM2.5 at low temperatures but decrease it at high temperatures, a pattern linear models cannot capture.
7. **Model limitations**: variables such as wind speed, atmospheric pressure, and rainfall were not included and likely account for the remaining unexplained variance.

---

## Limitations & Future Work

- Wind speed, atmospheric pressure, and rainfall were not available in this dataset and are known PM2.5 drivers
- A longer time series and additional monitoring stations across Islamabad would improve model generalisability
