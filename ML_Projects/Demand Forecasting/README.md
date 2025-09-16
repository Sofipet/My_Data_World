# 🛒 Demand Forecasting for Retail Sales

Forecasting daily sales for **50 items across 10 stores (2013–2017)**.  
Goal: predict future sales using machine learning models.  
Metric: **MAPE (Mean Absolute Percentage Error)**.


## Exploratory Analysis
- Items and stores show clear **differences in sales levels**.  
- **Seasonality** is visible (yearly peaks), but daily data makes patterns noisy.  
- Weekly/monthly aggregation or log transform improves interpretability.  


## Baselines
- **NaiveSeasonal (weekly):** MAPE ≈ 38%  
- **NaiveDrift:** MAPE ≈ 69%  


## Models
- **Exponential Smoothing:** MAPE ≈ 39% — smooth but misses sharp fluctuations.  
- **ARIMA / AutoARIMA:** similar to ES, no significant improvement without explicit seasonality.  
- **XGBoost (lags + calendar features):** MAPE ≈ 27.6% — better fluctuation tracking.  
- **RNN (LSTM):** MAPE ≈ 28.5% — promising, but needs more training.  
- **Prophet:** best model overall; captures trend + seasonality well, but does not scale (would require 500 models).  

**MAPE ≈ 23.8% (val)**
<img width="1594" height="470" alt="image" src="https://github.com/user-attachments/assets/8c3e5d96-a098-4c23-9377-ace55f81337b" />

**MAPE ≈ 24.5% (backtest)**
<img width="1594" height="470" alt="image" src="https://github.com/user-attachments/assets/2f242a6a-ef0e-4160-bfce-9b4c5ac396df" />



## Key Insight
- **Prophet gives highest accuracy**, but not scalable.  
- **Global models (XGBoost, RNN)** are more practical for 500 series:  
  - One model for all time series.  
  - Faster training.  
  - Captures shared seasonal patterns.

## 💡 Business Impact
Accurate sales forecasting enables retailers to:  
- **Optimize inventory management** → reduce overstock and stockouts.  
- **Increase revenue** → meet demand peaks without missing sales opportunities.  
- **Improve logistics planning** → allocate resources (warehouses, deliveries) more efficiently.  
- **Enhance customer satisfaction** → products available at the right time and place.  
- **Support strategic decisions** → pricing, promotions, and supply chain planning.  

By reducing MAPE from ~38% (naive baseline) to ~24% (advanced models), the company gains a **~37% improvement in forecast accuracy**, directly impacting profitability and operational efficiency.


## Tools
`Pandas` · `NumPy` · `Matplotlib` · `Statsmodels` · `Darts` 
