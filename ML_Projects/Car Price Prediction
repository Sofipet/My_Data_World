# 🚗 Car Price Prediction (ML Project)

This project focuses on building a **machine learning solution** to predict car prices in India using the **Cars dataset**.  
The goal was to explore the relationships between car characteristics and their price, preprocess the data, build regression models, and evaluate their performance.  

---

## 📂 Dataset Overview

The dataset (`cars.csv`) contains information about cars and their attributes:

### Numerical Features
- **Year** – Year of manufacture  
- **Kilometers_Driven** – Total distance driven  
- **Mileage** – Fuel efficiency (km/l)  
- **Engine** – Engine size (CC)  
- **Power** – Maximum horsepower (bhp)  
- **Seats** – Number of seats  
- **Car_ID** – Unique identifier  
- **Price** – 💰 Target variable (car price in INR)  

### Categorical Features
- **Brand** (11 unique: Toyota, Honda, Ford, … Mercedes)  
- **Model** (58 unique: Civic, Mustang, Swift, … EcoSport)  
- **Fuel_Type** (Petrol, Diesel)  
- **Transmission** (Manual, Automatic)  
- **Owner_Type** (First, Second, Third → ordinal)

---

## ⚙️ Preprocessing

- **Binary encoding** for *Fuel_Type* and *Transmission* (most frequent = 1).  
- **One-Hot Encoding** for *Brand*.  
- **Ordinal Encoding** for *Owner_Type* (`First < Second < Third`).  
- **Train-test split**: 80% training, 20% test.  

---

## 📊 Correlation Analysis

Heatmap showed strongest correlations with **Price**:

- **Power** (0.85)  
- **Engine** (0.71)  
- **Transmission type** (0.68)  
- **Mileage** (0.64)  

👉 Interpretation: More powerful cars with larger engines and automatic transmissions tend to be more expensive. Higher mileage (fuel efficiency) also increases price.

---

## 🏗️ Model Training

We used **Linear Regression** as the baseline model.

- **RMSE Train**: 210,343  
- **RMSE Test**: 259,601  

Scatter plots show predictions closely follow the diagonal line, meaning good performance, though higher-priced cars show more variance due to limited data.

---

## 🔍 Feature Importance

### Positive Influences on Price
- **Power**: strongest factor (higher power → higher price).  
- **Brand**: premium brands (Mercedes, BMW, Audi) strongly increase price.  
- **Transmission**: automatic cars cost more.  

### Negative Influences
- **Fuel type**: Diesel cars tend to be cheaper.  
- **Economy brands** (Hyundai, Mahindra, Maruti) lower prices.  
- **Kilometers driven & lower mileage** reduce price.  

---

## 📑 Statistical Significance

Using **OLS regression**:

- **Statistically significant features (p < 0.05)**:  
  *Mileage, Power, Fuel_Type, Transmission, Audi, BMW, Mercedes, Ford, Hyundai, Mahindra, Maruti, Volkswagen*  

- After keeping only significant features,  
  - **R² = 0.951**, **Adj. R² = 0.943**  
  - Minimal drop from full model → simpler yet effective.  

- With relaxed threshold (**p < 0.25**):  
  - **R² = 0.958**, **Adj. R² = 0.948**  
  - Close to full model but with fewer predictors → good **balance between simplicity & performance**.

---

## ✅ Key Insights

- **Power** is the most important predictor of car price.  
- **Premium brands** substantially increase value.  
- **Automatic transmission** adds price premium.  
- **Fuel type (Diesel), higher kilometers, lower mileage** reduce value.  
- Simplified models with fewer predictors maintain nearly the same predictive power as full models.  

---

## 📌 Conclusion

This project demonstrates the full ML workflow:
1. Data preprocessing (encoding categorical features, scaling).  
2. Correlation and feature importance analysis.  
3. Model building with **Linear Regression**.  
4. Statistical testing for feature selection.  
5. Trade-off analysis between model complexity and interpretability.  

👉 **Best practical model**: using predictors with **p < 0.25**, which balances interpretability and predictive accuracy.  
