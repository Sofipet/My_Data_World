# 📝 Tweet Sentiment Classification 

This project performs sentiment classification on Twitter messages using classical machine-learning methods and text-vectorization techniques. The workflow includes exploratory data analysis, text preprocessing, feature extraction (Bag-of-Words and TF-IDF), model training, evaluation, error analysis, and interpretation of feature importance.


## Dataset
Each record contains:

- **textID** — unique identifier  
- **text** — full tweet text  
- **selected_text** — span of text expressing sentiment  
- **sentiment** — target label: *negative*, *neutral*, *positive*  

Total samples: **27,480 tweets**.



## Exploratory Data Analysis 

### ✔ Class distribution
Tweets are slightly imbalanced:
- **neutral** — 11,117  
- **positive** — 8,582  
- **negative** — 7,781  

The classifier tends to predict **neutral** more often.

### ✔ Tweet length analysis
- Avg. length ≈ **68 characters**
- 50% of tweets shorter than **64** chars  
- 75% shorter than **97** chars  

No need for long-sequence models (e.g., LSTMs).


## Text Preprocessing

Steps applied:

- lowercasing  
- removing punctuation and non-alphabetic characters  
- tokenization  
- stopword removal  
- stemming (SnowballStemmer)  

Result is stored in `clean_text`.



## Bag-of-Words Vectorization 

- Full vocabulary: **22,746 unique terms**
- Most words appear only **1–2 times** → noisy, low signal  
- Corpus coverage analysis shows:
  - **Top 5,000 words** achieve best signal-to-noise ratio  

Final representation: **5000-feature CountVectorizer**

### ✔ Models trained:
- Logistic Regression  
- Decision Tree  
- Random Forest  
- XGBoost  

Best BoW model: **XGBoost (Accuracy ≈ 0.694)**  
Neutral & positive classified best; negative often confused with neutral.



## Word-Importance Analysis

### ✔ Logistic Regression coefficients
- **negative**: sad, suck, bore, hate, fail  
- **positive**: great, amaz, enjoy, thank, love  
- **neutral**: context-free tokens (e.g., how, indoor, jst)

The model correctly captures emotional vocabulary.

### ✔ XGBoost feature importance
Top features include sentiment-heavy tokens (e.g., *sad*, *love*, *miss*).



## TF-IDF Vectorization

- TF-IDF reduces influence of frequent generic words
- Strengthens meaningful sentiment tokens
- Still using **5000 features**

### ✔ Models trained again:
- Logistic Regression  
- Decision Tree  
- Random Forest  
- XGBoost  

Best TF-IDF model: **Random Forest (Accuracy ≈ 0.70)**  
Shows improved generalization and fewer neutral/negative confusions.

**TF-IDF outperforms BoW** and is recommended as the final feature representation.



## Error Analysis

Confusion matrix shows:

- **Most errors occur between:**
  - negative ↔ neutral (482 cases)
  - positive ↔ neutral (388 cases)

Reason:  
Tweets with weak emotional cues are difficult even for humans.



## Possible Improvements

- Use **bigrams/trigrams** in TF-IDF  
- Replace stemming with **lemmatization**  
- Use advanced embeddings:
  - Word2Vec / GloVe  
  - Transformers (BERT, DistilBERT)  
- Apply class-balancing techniques  
- Hyperparameter optimization with Bayesian search  


## Tools & Libraries

- **Python**: Pandas, NumPy, re, NLTK  
- **Vectorization**: CountVectorizer, TfidfVectorizer  
- **Models**: Logistic Regression, Decision Tree, Random Forest, XGBoost  
- **Evaluation**: accuracy, precision, recall, F1, confusion matrix  
- **Visualization**: Matplotlib, Seaborn  

