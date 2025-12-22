# Machine Learning Projects

Welcome to the **ML Projects** repository! This collection highlights machine learning solutions I’ve built, covering end-to-end workflows: from preprocessing and feature engineering to modeling, evaluation, and business interpretation.


## Tools & Libraries
- **Python**: Pandas, NumPy, Scikit-learn, XGBoost, LightGBM, Statsmodels
- **Natural Language Processing (NLP)**: NLTK, Regex, Bag-of-Words, TF-IDF, N-grams, BERT  
- **Web Scraping & Automation**: Selenium, BeautifulSoup, Requests  
- **Deep Learning**: PyTorch  
- **Unsupervised Learning**: PCA, t-SNE, KMeans, Agglomerative Clustering, DBSCAN (Scikit-learn), SciPy  
- **Visualization**: Matplotlib, Seaborn, Plotly  
- **Time Series**: Statsmodels, Prophet, Darts  
- **Model Explainability**: SHAP
- **Model Deployment & Apps**: Streamlit, Joblib, FastAPI, Docker, Hugging Face Spaces
- **Experimentation**: GridSearchCV, RandomizedSearchCV, Hyperopt  


## Contents

- [❓ Quora Duplicate Question Detector](https://github.com/Sofipet/My_Data_World/tree/main/ML_Projects/Duplicate%20Question%20Detector):  
  End-to-end NLP project for detecting duplicate questions. Compared classic ML models with a fine-tuned DistilBERT transformer. Best results achieved with a **BERT–LogReg ensemble (log loss ≈ 0.34)**. Deployed as a REST API using FastAPI and Docker, with a lightweight web interface hosted on Hugging Face Spaces.

- [🏦 Bank Marketing Campaign Prediction](https://github.com/Sofipet/My_Data_World/tree/main/ML_Projects/Bank%20Marketing%20Campaign%20Prediction):  
  Predicted whether a client subscribes to a term deposit using UCI Bank Marketing data. Explored Logistic Regression, Decision Trees, kNN, and XGBoost. Best result: **XGBoost (AUROC ≈ 0.95)**, with macroeconomic indicators and campaign history as key drivers.

- [🏦 Customer Churn Prediction](https://github.com/Sofipet/My_Data_World/tree/main/ML_Projects/Customer%20Churn%20Prediction):   
  Kaggle competition predicting bank customer churn. Compared Logistic Regression, Decision Tree, kNN, LightGBM, and XGBoost. Best result: **XGBoost (AUROC ≈ 0.94)**. Provided insights for targeted retention strategies.

- [⛅ Streamlit Weather App](https://github.com/Sofipet/My_Data_World/tree/main/ML_Projects/Streamlit%20Weather%20App):  
  Interactive Streamlit application predicting rainfall in Australia using a trained Random Forest model. Includes user input features, dynamic UI elements, weather-dependent backgrounds, and an integrated geolocation map. The app is fully deployable via Streamlit Cloud and uses a saved `.joblib` model for fast inference.

- [🤖 LLM & Agent-Based Automation](https://github.com/Sofipet/My_Data_World/tree/main/ML_Projects/Prompts%20%26%20Agents%20in%20Langchain):  
  Explored Large Language Models (OpenAI, Mistral) and LangChain agents. Compared prompt responses, automated literature search with DuckDuckGo, and built a business forecasting assistant combining LLM reasoning with external data.

- [🛒 Retail Demand Forecasting](https://github.com/Sofipet/My_Data_World/tree/main/ML_Projects/Demand%20Forecasting):  
  Forecasted daily sales for one store–item pair (2013–2017). Benchmarked classical and ML methods. **Prophet achieved best accuracy (MAPE ≈ 23.8%)**, while XGBoost and RNNs showed scalable potential for larger datasets.

- [📝 Tweet Sentiment Classification](https://github.com/Sofipet/My_Data_World/tree/main/ML_Projects/Tweet%20Sentiment%20Classification):  
  Built a complete NLP pipeline to classify tweets into negative, neutral, and positive sentiment. Performed preprocessing, vectorization (Bag-of-Words and TF-IDF), and trained models including Logistic Regression, Random Forest, and XGBoost. Conducted confusion-matrix error analysis and feature-importance interpretation to understand emotional language patterns.

- [🔍 Data Science Job Market Analysis (DOU.ua)](https://github.com/Sofipet/My_Data_World/tree/main/ML_Projects/Skill%20Extraction%20Workflow):  
  Scraped 50+ Data Science vacancies using Selenium and BeautifulSoup. Extracted skills and responsibilities with GPT (OpenAI API) and analyzed market demand using NLP techniques (N-grams, WordCloud, regex preprocessing). Identified the most common required skills and trends such as LLM adoption and neural network demand.

- [✈️ LSTM Time Series Forecasting](https://github.com/Sofipet/My_Data_World/tree/main/ML_Projects/LSTM%20Time%20Series%20Forecasting):  
  Implemented an LSTM model in PyTorch to forecast monthly airline passengers. Covered supervised windowing, model architecture, RMSE evaluation, loss curves, and prediction visualization. Compared hidden sizes and analyzed model limitations with short lookback windows.

- [🧑‍🤝‍🧑 Customer Personality Segmentation](https://github.com/Sofipet/My_Data_World/tree/main/ML_Projects/Customer%20Personality%20Segmentation):  
  Performed unsupervised segmentation on a marketing dataset using KMeans, Agglomerative Clustering, DBSCAN, PCA, and t-SNE. Identified three distinct customer groups based on income, purchasing behavior, and engagement patterns.

- [🚗 Car Price Prediction](https://github.com/Sofipet/My_Data_World/tree/main/ML_Projects/Car%20Price%20Prediction):  
  Built regression models to estimate used car prices in India. Applied feature encoding, correlation analysis, and OLS regression. **Horsepower, brand, and transmission** emerged as main predictors. Simplified model achieved high accuracy with fewer features.
