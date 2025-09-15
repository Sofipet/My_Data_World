# 🏦 Bank Marketing Campaign Prediction

This project focuses on predicting whether a client will subscribe to a **term deposit** (time deposit) after a direct marketing campaign by a Portuguese bank.  
The problem is a **binary classification task** with the target variable:  
- **y = yes** → the client subscribed  
- **y = no** → the client did not subscribe  

---

## 📂 Dataset Overview

The dataset contains information about bank clients, details from the last marketing campaign, previous interactions, and macroeconomic indicators.  

### 👤 Client Information
- **age** → client’s age (numeric)  
- **job** → type of employment (categorical: *admin., blue-collar, entrepreneur, housemaid, management, retired, self-employed, services, student, technician, unemployed, unknown*)  
- **marital** → marital status (categorical: *divorced, married, single, unknown*)  
  > *Note: divorced includes divorced, widowed, or widower*  
- **education** → education level (categorical: *basic.4y, basic.6y, basic.9y, high.school, illiterate, professional.course, university.degree, unknown*)  
- **default** → has credit in default? (*yes, no, unknown*)  
- **housing** → has housing loan? (*yes, no, unknown*)  
- **loan** → has personal loan? (*yes, no, unknown*)  

### 📞 Last Contact Information
- **contact** → communication type (*cellular, telephone*)  
- **month** → month of last contact (*jan, feb, …, nov, dec*)  
- **day_of_week** → day of the week (*mon, tue, wed, thu, fri*)  
- **duration** → duration of the last contact in seconds (numeric)  

⚠️ **Important note**: `duration` strongly affects the target (e.g., if duration = 0, then y = no). However, this variable is **unknown before the call** and only observed afterward (when the outcome is already determined).  
👉 Therefore, `duration` should only be used for **model comparison**, not in the final predictive model.  

### 📊 Other Campaign Attributes
- **campaign** → number of contacts during the current campaign for this client (numeric, includes last contact)  
- **pdays** → number of days since client was last contacted in a previous campaign (numeric; `999` means client was not previously contacted)  
- **previous** → number of contacts before this campaign (numeric)  
- **poutcome** → outcome of previous campaign (*failure, nonexistent, success*)  

### 🌍 Socio-Economic Indicators
- **emp.var.rate** → employment variation rate (quarterly, numeric)  
- **cons.price.idx** → consumer price index (monthly, numeric)  
- **cons.conf.idx** → consumer confidence index (monthly, numeric)  
- **euribor3m** → 3-month Euribor rate (daily, numeric)  
- **nr.employed** → number of employees (quarterly, numeric)  

### 🎯 Target Variable
- **y** → did the client subscribe to a term deposit? (*yes, no*)  

---

## 🎯 Objective
The goal is to build a machine learning model that predicts whether a client will subscribe to a term deposit, helping the bank:  
- Improve targeting of marketing campaigns  
- Reduce costs by avoiding unpromising calls  
- Increase subscription rates  

---

## 🛠️ Tools & Methods
- **Python**: Pandas, NumPy  
- **Visualization**: Matplotlib, Seaborn  
- **ML Models**: Logistic Regression, Random Forest, XGBoost  
- **Evaluation**: Accuracy, ROC AUC, Precision/Recall, F1-score  
