# Electricity-Demand-forecasting


# ⚡ Electricity Demand Forecasting Using Machine Learning & Hybrid Models

**Author:** Jaya Sai Sunny Yarramsetti    
**MSc in Data Analytics — Technological University of the Shannon, Limerick**  
  
**Date:** August 2025  

---

## 📘 Project Overview

Accurate forecasting of electricity demand is essential for **grid stability, renewable integration, and sustainable energy planning**.  
This project develops **short-term load forecasting models** for **England and Wales (2024)** using **half-hourly electricity demand data** from the **National Grid Electricity System Operator (ESO)** and **Balancing Mechanism Reporting Service (BMRS)**.

By combining traditional time-series models (ARIMA) with advanced **machine learning** and **deep learning** techniques (Random Forest, XGBoost, LSTM, and Hybrid CNN-LSTM models), the project aims to enhance forecasting accuracy and support smarter energy management.

---

## 🎯 Aim

To develop a **robust and accurate short-term electricity demand forecasting model** that captures temporal patterns, renewable contributions, and interconnector dynamics for **England and Wales (2024)**.

---

## 🧩 Objectives

- Collect and clean high-resolution half-hourly demand data (2024).  
- Perform **Exploratory Data Analysis (EDA)** to identify daily, weekly, and seasonal trends.  
- Engineer features such as lag values, rolling averages, holidays, and renewable generation.  
- Evaluate and compare multiple forecasting models: **ARIMA**, **Random Forest**, **XGBoost**, **LSTM**.  
- Assess model performance using **RMSE**, **MAE**, and **MAPE**.  
- Use **SHAP values** to interpret model explainability and feature importance.

---

## 📊 Dataset Description

**Source:**  
- [National Grid ESO](https://www.nationalgrideso.com)  
- [Balancing Mechanism Reporting Service (BMRS)](https://bmreports.com)

**Frequency:** Half-hourly records — 17,520 data points for 2024  
**Target Variable:** `ENGLAND_WALES_DEMAND (MW)`

**Selected Features:**
| Category | Variables |
|-----------|------------|
| Temporal | Date, Time, Month, Day of Week, Holiday Flag |
| Demand | ND, TSD, ENGLAND_WALES_DEMAND |
| Renewable | EMBEDDED_WIND_GENERATION, EMBEDDED_SOLAR_GENERATION |
| Interconnectors | IFA_FLOW, NEMO_FLOW, BRITNED_FLOW, MOYLE_FLOW, NSL_FLOW, ELECLINK_FLOW |
| Storage | NON_BM_STOR, PUMP_STORAGE_PUMPING |

---

## 🧠 Methodology

1. **Data Cleaning:**  
   Verified timestamps, handled missing data, converted formats.

2. **Exploratory Data Analysis (EDA):**  
   - Line plots, boxplots, and heatmaps to detect seasonal patterns.  
   - Correlation analysis between demand, temperature, renewables, and flows.

3. **Feature Engineering:**  
   - Lagged demand values (t−1, t−24, t−48).  
   - Rolling averages (3h, 6h, 12h).  
   - Holiday indicators and cyclical time encodings (sine/cosine).

4. **Model Development:**  
   - Baseline: **ARIMA**  
   - Tree-based: **Random Forest**, **XGBoost**  
   - Deep Learning: **LSTM**, **Hybrid CNN–LSTM with Attention**

5. **Evaluation Metrics:**  
   RMSE, MAE, and MAPE were used to compare accuracy.

6. **Explainability:**  
   Used **SHAP** (SHapley Additive Explanations) to interpret the influence of each feature.

---

## 🚀 Results Summary

| Model | RMSE (MW) | MAPE (%) | Key Observation |
|--------|------------|-----------|----------------|
| ARIMA | 3,200 | 7.8 | Captures daily cycles only |
| Random Forest | 2,050 | 4.9 | Handles nonlinearities well |
| XGBoost | 1,780 | 4.1 | Excellent gradient boosting accuracy |
| **LSTM** | **1,540** | **3.6** | Best overall performance |

**Best Model:** LSTM — 50% lower RMSE than ARIMA.  
It accurately captured complex nonlinear and temporal dependencies.

---

## 🔍 Key Findings

- Clear **daily and weekly demand cycles** with peaks around **07:00–09:00** and **18:00–21:00**.  
- **Temperature** strongly influenced demand (r = −0.72).  
- **Holiday effects** reduced demand by up to **20%** on working days.  
- **LSTM** was most effective for short-term load forecasting.  
- **Feature importance  :** Temperature, Day of Week, Holiday Flag, Lag Demand, and Wind/Solar Generation.

---

## 🧩 Tools & Libraries

- **Programming:** Python  
- **Libraries:** pandas, numpy, scikit-learn, xgboost, tensorflow, keras, shap, matplotlib, seaborn  
- **Environment:**   Jupyter Notebook  

---


