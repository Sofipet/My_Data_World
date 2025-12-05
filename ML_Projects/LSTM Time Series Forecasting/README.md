# ✈️ LSTM Time Series Forecasting: Airline Passengers

This project demonstrates how to build, train, and evaluate an LSTM neural network in **PyTorch** to forecast monthly international airline passengers (the classic **AirPassengers** dataset). The goal is to predict the next month's passenger count using previous observations.


## Project Summary

The notebook walks through the full workflow:

- Preparing and splitting a real-world time series dataset  
- Constructing supervised learning windows for LSTM (`lookback = 1`)  
- Implementing a custom LSTM model in PyTorch  
- Training with Adam and MSE loss  
- Monitoring training loss and RMSE  
- Visualizing predictions vs. actual data  
- Comparing models with hidden sizes 50 and 100  

This project highlights the strengths and limitations of simple LSTM architectures in capturing **trend** and **seasonality**.



## Dataset

**AirPassengers (1949–1960)**  
144 monthly observations of international airline passengers (in thousands).

Source:  
https://raw.githubusercontent.com/jbrownlee/Datasets/master/airline-passengers.csv


## Training Results

### ✔ Training Loss  
The loss decreases smoothly and stabilizes, indicating correct training behavior.

### ✔ RMSE Performance

| Model | Train RMSE | Test RMSE |
|-------|------------|------------|
| **LSTM (hidden=50)** | ~23.4 | ~99.2 |
| **LSTM (hidden=100)** | ~23.7 | ~103.0 |

Although the model fits the training set well, the test RMSE remains high — showing **limited generalization** due to the short input sequence.



## Prediction Behavior

The model’s predictions show:

### **Learned**
- Upward long-term trend  
- Partial seasonal structure  
- Some local fluctuation patterns  

### **Not Learned**
- Full seasonal amplitude  
- Peak and trough magnitudes  
- Sharp seasonal transitions  

Predictions on the test set appear **overly smoothed**, with the model consistently underestimating peaks.



## Key Insights

- A lookback window of **1** time step is insufficient for learning **12-month seasonality**.
- Increasing hidden size alone does not significantly improve forecasting quality.
- To better capture seasonal dynamics, the model should use a larger window (e.g., **12 or 24** steps).


## Technologies Used

- **PyTorch**
- **NumPy**
- **Pandas**
- **Matplotlib**

