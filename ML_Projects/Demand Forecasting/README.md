# 🛒 Demand Forecasting for Retail Sales

Forecasting daily sales for **50 items across 10 stores (2013–2017)**.  
Goal: predict future sales using statistical, machine learning, and deep learning models.  
Metric: **MAPE (Mean Absolute Percentage Error)**.

---

## 📊 Exploratory Analysis
- Items and stores show clear **differences in sales levels**.  
- **Seasonality** is visible (yearly peaks), but daily data makes patterns noisy.  
- Weekly/monthly aggregation or log transform improves interpretability.  

---

## ⚖️ Baselines
- **NaiveSeasonal (weekly):** MAPE ≈ 38%  
- **NaiveDrift:** MAPE ≈ 69%  

---

## 📈 Classical Models
- **Exponential Smoothing:** MAPE ≈ 39% — smooth but misses sharp fluctuations.  
- **ARIMA / AutoARIMA:** similar to ES, no significant improvement without explicit seasonality.  

---

## 🤖 Machine Learning
- **XGBoost (lags + calendar features):** MAPE ≈ 27.6% — better fluctuation tracking.  
- **RNN (LSTM):** MAPE ≈ 28.5% — promising, but needs more training.  

---

## 🔮 Prophet
- Best model overall: **MAPE ≈ 23.8% (val), 24.5% (backtest)**.  
- Captures trend + seasonality well, but does not scale (would require 500 models).  

---

## 🚀 Key Insight
- **Prophet gives highest accuracy**, but not scalable.  
- **Global models (XGBoost, RNN)** are more practical for 500 series:  
  - One model for all time series.  
  - Faster training.  
  - Captures shared seasonal patterns.  

---

## 🛠️ Tools
`Pandas` · `NumPy` · `Matplotlib` · `Statsmodels` · `Darts` · `Prophet` · `XGBoost` · `PyTorch`  

