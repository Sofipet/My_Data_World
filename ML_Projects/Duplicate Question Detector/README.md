# ❓ Quora Duplicate Question Detector

An end-to-end NLP project for detecting whether two questions express the same intent, inspired by real-world challenges on Q&A platforms like Quora.

The project combines classic machine learning, transformer models, and production-style deployment.

👉 [GitHub Repo](https://github.com/Sofipet/duplicate-question-api)

👉 [Live Demo (Hugging Face Spaces)](https://huggingface.co/spaces/sofipet451/duplicate-question-detector1)

## Problem
Duplicate questions reduce content quality, increase moderation costs, and hurt search relevance on Q&A platforms.

**Task:** Given two questions, predict the probability that they are duplicates.


## Data
- **Dataset:** Quora Question Pairs (Kaggle)
- ~400k labeled question pairs
- Binary target: `is_duplicate`


## Approach
**Models compared:**
- Baseline (class prior)
- TF-IDF + Logistic Regression
- LightGBM (engineered similarity features)
- Fine-tuned DistilBERT
- Probability-based ensemble (BERT + Logistic Regression)

**Evaluation:**
- Log Loss (primary metric)
- ROC-AUC
- F1-score


## Results (Validation)
| Model | Log Loss | ROC-AUC | F1 |
|------|---------|---------|----|
| TF-IDF + LR | ~0.43 | ~0.87 | ~0.70 |
| LightGBM | ~0.51 | ~0.79 | ~0.62 |
| DistilBERT | ~0.35 | ~0.92 | ~0.79 |
| **Ensemble (BERT + LR)** | **~0.34** | **~0.93** | **~0.80** |


## Deployment
- REST API built with **FastAPI**
- Containerized with **Docker**
- Deployed on **Hugging Face Spaces**
- Includes a minimal web UI and JSON API


## Key Takeaway
Transformer models significantly improve semantic understanding, while lightweight ensembles can further improve calibration and robustness with minimal complexity.

