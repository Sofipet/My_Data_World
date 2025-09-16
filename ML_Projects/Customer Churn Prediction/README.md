# 🏦 Customer Churn Prediction

This project is inspired by a Kaggle competition focused on predicting customer churn — determining whether a client will continue using their bank account or close it.


## Problem Statement
The task is framed as a **binary classification problem**:

- `1` → Customer exited (churned)  
- `0` → Customer stayed  

The evaluation metric is **ROC AUC**. The primary objective is to build a machine learning model that maximizes this score.


## Dataset
The dataset contains three files:

- `train.csv` — training data with labels (Exited)  
- `test.csv` — test data without labels  
- `sample_submission.csv` — template for Kaggle submission  

### Features
- **ID** → unique row identifier  
- **CustomerId** → client identifier (contains duplicates; dropped during preprocessing)  
- **Surname** → client surname (non-predictive; dropped)  
- **CreditScore** → credit score of the customer  
- **Geography** → country of residence (France, Spain, Germany)  
- **Gender** → male or female  
- **Age** → customer’s age  
- **Tenure** → number of years with the bank  
- **Balance** → account balance  
- **NumOfProducts** → number of bank products (e.g., savings, credit card)  
- **HasCrCard** → has a credit card (1 = yes, 0 = no)  
- **IsActiveMember** → active membership status (1 = yes, 0 = no)  
- **EstimatedSalary** → estimated annual salary  
- **Exited** → target variable (1 = churned, 0 = stayed)  


## Project Workflow
1. **Exploratory Data Analysis (EDA)** — studied distributions, correlations, and class imbalance.  
2. **Preprocessing** — handled missing values, encoded categorical variables, scaled numerical features.  
3. **Modeling** — trained and compared several models:  
   - Logistic Regression  
   - Decision Tree  
   - k-Nearest Neighbors (KNN)  
   - XGBoost  
   - LightGBM  
4. **Evaluation** — used ROC AUC on validation sets and cross-validation.  
5. **Submission** — generated predictions on the test set in Kaggle format.  


## Results & Model Comparison

| Model                  | ROC AUC (Train) | ROC AUC (Validation) | Notes |
|-------------------------|-----------------|-----------------------|-------|
| Logistic Regression     | 0.88            | 0.88                  | Solid baseline; simple and interpretable, but limited in capturing nonlinear relationships |
| Decision Tree           | 0.92            | 0.91                  | Easy to interpret; tends to overfit slightly, less stable on small data |
| KNN (GridSearchCV)      | 0.93            | 0.91                  | Improved with tuning; still sensitive to scaling and local noise, moderate generalization |
| LightGBM                | 0.96            | 0.93                  | Captures nonlinearities well; some signs of overfitting, higher variance |
| **XGBoost (Hyperopt)**  | **0.95**        | **0.94**              | ✅ Best model; robust, well-regularized, achieves best balance between bias and variance |



## Kaggle Submission Result

Here is the leaderboard public score for the best model (**XGBoost with Hyperopt tuning**):

<img width="1624" height="822" alt="image45" src="https://github.com/user-attachments/assets/ab4f1af0-349b-42d3-a349-3f042ad5cb91" />


## Business Impact
A reliable churn prediction model enables banks to:

- Detect customers at risk of leaving  
- Take targeted retention actions  
- Increase customer satisfaction and reduce revenue loss  


## Tools & Libraries
- **Python**: Pandas, NumPy  
- **Visualization**: Matplotlib, Seaborn  
- **Machine Learning**: Scikit-learn, XGBoost, LightGBM  
- **Model Evaluation**: ROC AUC, Stratified Cross-validation  
