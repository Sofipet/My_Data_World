# 🏦 Customer Churn Prediction 

This project is inspired by a Kaggle competition focused on **predicting customer churn** — determining whether a client will continue using their bank account or close it.  

The task is framed as a **binary classification problem**:  
- **1** → Customer exited (churned)  
- **0** → Customer stayed  

The evaluation metric is **ROC AUC** (Area Under the Receiver Operating Characteristic Curve).  
The primary objective is to build a machine learning model that maximizes this score.

---

## 📂 Dataset
The dataset contains three files:

- `train.csv` — training data with labels (`Exited`)  
- `test.csv` — test data without labels  
- `sample_submission.csv` — template for Kaggle submission  

---

## 🔑 Features
The dataset describes each client with the following attributes:

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

---

## 🎯 Project Workflow
1. **Exploratory Data Analysis (EDA)** — understand data distribution, correlations, and potential data quality issues.  
2. **Preprocessing** — handle missing values, encode categorical variables, and scale numerical features.  
3. **Modeling** — train and compare several models: Logistic Regression, Random Forest, XGBoost, and LightGBM.  
4. **Evaluation** — assess models using **ROC AUC** on validation data.  
5. **Submission** — generate predictions on the test set in Kaggle format.  

---

## 🛠️ Tools & Libraries
- **Python**: Pandas, NumPy  
- **Visualization**: Matplotlib, Seaborn  
- **Machine Learning**: Scikit-learn, XGBoost, LightGBM  
- **Model Evaluation**: ROC AUC, Stratified Cross-validation  

---

## 📌 Results & Insights
- Logistic Regression established a strong baseline after preprocessing and scaling.  
- Tree-based models (Random Forest, XGBoost, LightGBM) captured nonlinearities and interactions, improving performance further.  
- The final model achieved a **ROC AUC significantly above baseline**, demonstrating the ability to identify at-risk customers.  

---

## 💡 Business Impact
A reliable churn prediction model enables banks to:  
- Detect customers at risk of leaving  
- Take targeted retention actions  
- Increase customer satisfaction and reduce revenue loss  
