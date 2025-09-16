# 🛒 Retail Demand Forecasting 

This project focuses on forecasting **daily sales for one store–item pair** (Store 1, Item 1, 2013–2017).  
The objective was to predict future demand and improve inventory decisions.  
Evaluation metric: **MAPE (Mean Absolute Percentage Error)**.


## Key Findings
- Sales show **seasonality** (yearly and weekly patterns) with occasional spikes.  
- Naive methods provided weak baselines (MAPE 38–69%).  
- Advanced models significantly improved forecast accuracy.  


## Model Performance

| Model                  | MAPE (Validation) | Comments |
|-------------------------|-------------------|----------|
| Naive Drift             | ~69%              | Weak baseline |
| Naive Seasonal (weekly) | ~38%              | Captures cycles only |
| Exponential Smoothing   | ~39%              | Smooth, misses peaks |
| ARIMA / AutoARIMA       | ~39%              | Struggles with daily data |
| XGBoost (lags + cal.)   | ~27.6%            | Handles spikes, short-term effects |
| RNN (LSTM)              | ~28.5%            | Promising, needs larger dataset |
| **Prophet**             | **~23.8%**        | ✅ Best result, robust seasonality & trend |

**Validation example (MAPE ≈ 23.8%)**  
<img width="1594" height="470" alt="val-forecast" src="https://github.com/user-attachments/assets/8c3e5d96-a098-4c23-9377-ace55f81337b" />

**Backtest example (MAPE ≈ 24.5%)**  
<img width="1594" height="470" alt="backtest-forecast" src="https://github.com/user-attachments/assets/2f242a6a-ef0e-4160-bfce-9b4c5ac396df" />


## Business Value
Accurate forecasts at this level are critical for retail operations:

- **Better stock management** → avoid overstock & shortages  
- **Higher profitability** → reduce waste and lost sales  
- **Improved customer experience** → ensure product availability  
- **Decision support** → guide promotions, procurement, and pricing  

Compared to a seasonal baseline (38% MAPE), Prophet reduced forecast error to **23.8%**, a **37% improvement** in accuracy.


## Next Steps
- Scale this pipeline to **all store–item combinations** (500+ time series).  
- Explore **global models** (XGBoost, RNNs) for faster training across multiple series.  
- Integrate forecasts into **supply chain planning systems** for automated reordering.
