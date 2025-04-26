# Predicting High-Traffic Recipes
**Supporting Smarter Homepage Curation with Data**

## 1. Introduction
Tasty Bytes, founded during the COVID pandemic in 2020, aims to inspire users by helping them discover creative recipes. Homepage curation is critical: selecting a popular recipe can increase overall website traffic by up to 40%.  
This project predicts which recipes will be popular to assist the team in optimizing homepage selections, maximizing traffic, and boosting subscriptions.

**Goal:**  
Predict if a recipe will be "high-traffic" 80% of the time, minimizing the chance of featuring unpopular recipes.

## 2. Data Overview

**Dataset:**  
- 947 rows, 8 columns
- Variables: nutritional information (calories, carbs, sugar, protein), servings, category, and traffic labels.

**Data Validation & Cleaning:**
- Extracted numeric servings from mixed text entries.
- Imputed missing nutritional values with column medians.
- Outlier capping at the 99th percentile for nutrition features.
- Corrected inconsistent category labels.
- Transformed `high_traffic` into a binary target variable (1 = High, 0 = Other).

## 3. Exploratory Analysis

**Key Findings:**
- **Target Distribution:** Slight imbalance; more high-traffic recipes.
- **Nutrition Variables:** Right-skewed distributions; handled via `log1p` transformation.
- **Category Analysis:** Strong predictor; some categories like Vegetables and POrk have >70% high-traffic.
- **Correlation:** Weak direct correlations between nutrition and traffic labels; suggests non-linear models may perform better.

**Visualizations:**
- Distributions of nutritional features
- Nutritional comparison by traffic level
- Servings by traffic level
- High-traffic proportion by category

## 4. Modeling

**Problem Type:**  
Binary classification — predict whether a recipe will be high-traffic (1) or not (0).

**Feature Engineering:**
- Used log-transformed nutritional features.
- One-hot encoded categories (drop-first approach).

**Models Trained:**
- **Logistic Regression:** Interpretable baseline.
- **Decision Tree Classifier:** Captures non-linear relationships.

**Model Evaluation:**

| Metric               | Logistic Regression | Decision Tree |
|---------------------- |--------------------- |---------------|
| Precision             | 85.2%                 | 98.6%         |
| Recall                | 66.5%                 | 41.0%         |
| F1 Score              | 75.0%                 | 58.0%         |
| Accuracy              | 72.6%                 | 63.9%         |

**Model Comparison:**
- **Logistic Regression:** More balanced; higher recall.
- **Decision Tree:** Exceptional precision (98.6%), ideal for the business goal.

## 5. Business Impact Metric

**Precision@High:**  
- Measures how often predicted high-traffic recipes are truly successful.
- Since homepage errors are costly, **precision is prioritized** over recall.

## 6. Final Recommendations

- **Deploy Decision Tree Model:**  
  Provides nearly perfect precision, surpassing the 80% business target.

- **Set Up Weekly Monitoring:**  
  Build a precision dashboard. If precision falls below 75%, retrain the model.

- **Expand Feature Set:**  
  Future improvements could include:
  - User Ratings
  - Prep Time
  - Seasonality Tags
  - Ingredient attributes (vegan, gluten-free)

- **Improve Recall in Future Iterations:**  
  Once precision is stable, optimize for recall using Random Forests, threshold tuning, or advanced ensemble models.

## 7. Tools and Technologies

| Tool            | Purpose                         |
|----------------- |----------------------------------|
| Python           | Data Cleaning, EDA, Modeling     |
| Pandas           | Data Manipulation                |
| NumPy            | Numerical Operations             |
| Scikit-learn     | Modeling and Evaluation          |
| Seaborn, Matplotlib | Data Visualization           |

## 8. Files

| File                               | Description                               |
|------------------------------------|-------------------------------------------|
| `recipe_site_traffic_2212.csv`     | Original dataset                         |
| `recipe_prediction.ipynb`          | Full data cleaning, EDA, modeling code    |
| `High_Traffic_Recipes_Presentation.pdf` | Presentation for product manager    |                  

## 9. Future Work

- Deploy model into production.
- Automate data ingestion and retraining.
- Expand recipe metadata to refine predictions.
- Implement A/B testing for homepage recipe selections.

