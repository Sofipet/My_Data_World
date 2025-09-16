# 🏦 Bank Marketing Campaign Prediction  

This project is based on the **Bank Marketing Dataset** from the UCI Machine Learning Repository.  
The goal is to predict whether a bank client will **subscribe to a term deposit (y = yes/no)** after a direct marketing campaign.  


## Dataset Overview  

The dataset contains **41,188 records and 21 features** describing:  

- **Client Information**  
  - `age` (numeric)  
  - `job` (admin., blue-collar, management, retired, student, etc.)  
  - `marital` (divorced, married, single, unknown)  
  - `education` (basic, high school, professional, university, unknown)  
  - `default`, `housing`, `loan` (yes/no/unknown)  

- **Last Contact**  
  - `contact` (cellular, telephone)  
  - `month` (jan–dec), `day_of_week` (mon–fri)  
  - `duration` (numeric, seconds)  
    ⚠️ Strongly correlated with outcome but not available before the call → used for model comparison only.  

- **Campaign Details**  
  - `campaign` (# of contacts in this campaign)  
  - `pdays` (days since last contact; 999 = never contacted)  
  - `previous` (# of previous contacts)  
  - `poutcome` (outcome of previous campaign: success/failure/none)  

- **Macroeconomic Indicators**  
  - `emp.var.rate` (employment variation rate)  
  - `cons.price.idx` (consumer price index)  
  - `cons.conf.idx` (consumer confidence index)  
  - `euribor3m` (3-month Euribor rate)  
  - `nr.employed` (number of employees)  

- **Target**  
  - `y = yes` → client subscribed  
  - `y = no` → client did not subscribe  


## Challenges  

- Strong **class imbalance** (~11% subscribed).  
- High **multicollinearity** among macroeconomic variables.  
- Many **categorical features** with low-frequency categories.  


## Approach  

### Preprocessing  
- One-hot encoding for categorical features  
- Scaling for numeric features (Logistic Regression, kNN)  
- Feature engineering:  
  - `campaign_log`  
  - `no_prev_contact` flag  
  - `age_cats` (age categories)  

### Handling Imbalance  
- `class_weight='balanced'`  
- Threshold tuning for decision boundary  

### Models  
- Logistic Regression  
- kNN  
- Decision Tree  
- XGBoost (tuned via **RandomizedSearchCV** and **Hyperopt**)  

### Evaluation  
- **Primary metric:** ROC-AUC (robust under imbalance)  
- Additional metrics: Precision, Recall, F1  


## Results  

| Model                  | Key Hyperparameters                               | ROC-AUC (train) | ROC-AUC (val) | Notes                                                                 |
|-------------------------|---------------------------------------------------|-----------------|---------------|----------------------------------------------------------------------|
| Logistic Regression     | L2, class_weight=balanced                         | 0.935           | 0.943         | Strong baseline, high recall, but many false positives                |
| kNN                    | n_neighbors=15                                    | 0.948           | 0.924         | Sensitive to scaling & k, weaker generalization                       |
| Decision Tree          | max_depth=6, min_samples_leaf=50, balanced         | 0.945           | 0.945         | Interpretable, but less stable                                        |
| XGBoost (RandomizedCV) | n_estimators=332, lr=0.01, max_depth=7, subsample=0.72 | 0.964           | 0.955         | Best model, stable performance                                        |
| XGBoost (Hyperopt)     | n_estimators=225, lr=0.013, max_depth=9, subsample=0.67 | 0.974           | 0.954         | Similar performance, more complex search                              |  


## Insights  

- **Best model:** XGBoost (ROC-AUC ≈ 0.95).  
- Logistic Regression works as a **solid interpretable baseline**.  
- kNN underperforms due to high dimensionality.  
- SHAP analysis confirmed the importance of:  
  - Macroeconomic indicators (`emp.var.rate`, `nr.employed`)  
  - `duration` (though not usable in production)  
  - Seasonality (month, especially May campaigns)  
- Errors often concentrated in **May campaigns** and certain macro contexts.  


## Next Steps  

- Optimize **decision threshold** for Precision/Recall trade-off.  
- Experiment with **SMOTE** or undersampling for imbalance.  
- Test **stacking/ensembling** (LogReg + Trees + Boosting).  
