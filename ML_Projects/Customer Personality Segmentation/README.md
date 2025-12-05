# 🧑‍🤝‍🧑 Customer Personality Segmentation

This project performs customer segmentation on the **Marketing Campaign** dataset using unsupervised learning.  
The goal is to identify meaningful customer groups based on demographics, purchasing behavior, and engagement patterns to support targeted marketing and business decision-making.

## Problem Statement

Since no target variable is provided, this is an **unsupervised clustering task**.  
Cluster quality is evaluated using:

- Silhouette Score  
- Visual separation (PCA, t-SNE)  
- Business interpretability of segments  

The output is a set of actionable customer segments.


## Dataset Overview

The dataset contains **2,240** customers with attributes such as:

- **Income, Recency, NumStorePurchases, NumDealsPurchases**  
- **Kidhome, Teenhome, Education, Marital Status**  
- **Dt_Customer** (registration date)  
- **Campaign Acceptance Flags**  

Missing `Income` values were imputed and unrealistic outliers removed.


Categorical features were encoded; date features were converted into numeric durations.


## Workflow

### **1. Exploratory Data Analysis (EDA)**
- Inspected distributions and correlations  
- Analyzed cluster tendencies via Income × Purchases plots  
- Detected outliers and missing values  

### **2. Preprocessing**
- Median imputation for `Income`  
- Removal of outlier incomes  
- Date parsing and lifetime features  
- Label / one-hot encoding of categorical features  
- Scaled and unscaled versions of the data for comparison  

### **3. Clustering Methods Tested**
- **KMeans** (scaled & unscaled)  
- **Agglomerative Clustering** (Single, Complete linkage)  
- **DBSCAN**  

### **4. Dimensionality Reduction**
- **PCA (3 components)** for interpretability  
- **t-SNE (2D)** for nonlinear cluster visualization  


## Results & Model Comparison

### **KMeans (Unscaled)**
- **Silhouette:** ~0.54  
- Best KMeans performance  
- Clusters primarily separated by **Income** and activity level  

### **KMeans (Scaled)**
- **Silhouette:** ~0.16  
- Scaling reduces natural cluster structure  
- Income is the dominant driver → unscaled is preferred  

### **Agglomerative Clustering**
| Method | Silhouette | Notes |
|--------|------------|-------|
| **Complete Linkage** | **~0.60** | ✅ Best overall; clear, interpretable clusters |
| Single Linkage | ~0.42 | Poor separation (chaining effect) |

### **DBSCAN**
- Silhouette: ~0.45  
- Not stable for segmentation  
- Best suited for anomaly detection  


## PCA Insights

### **Explained Variance**
- PC1: **31.8%** — income + purchasing activity  
- PC2: **19.7%** — discount usage + customer lifetime  
- PC3: **14.3%** — recency  

**Total:** ~65.8%

Removing `Income` shifts PC1 and changes interpretability, confirming that **Income is the strongest structural feature**.


## t-SNE Segmentation Overview

t-SNE reveals three distinct customer segments:

### **Cluster 0 — Low Income, High Web Activity**
- Frequent web visits  
- Low purchasing power  
- Digital-first shoppers  

### **Cluster 1 — High Income, Offline Buyers**
- Highest store purchases  
- Low web usage  
- Premium, high-value customers  

### **Cluster 2 — Mid Income, Discount-Driven**
- Highest discount usage  
- Active online & offline  
- Strong engagement  


## Business Impact

Identified segments support:

- Targeted, personalized marketing  
- Improved allocation of promotional budgets  
- Better retention strategies for high-value customers  
- Tailored communication for online vs. offline buyers  

Actionable strategies:

- **Cluster 1:** premium offline offers  
- **Cluster 2:** loyalty programs + personalized deals  
- **Cluster 0:** online marketing and discount triggers  


## Tools & Libraries

- Python (Pandas, NumPy)  
- Scikit-learn (KMeans, Agglomerative, DBSCAN, PCA, t-SNE)  
- SciPy (hierarchical clustering)  
- Visualization: Matplotlib, Seaborn, Plotly
  
