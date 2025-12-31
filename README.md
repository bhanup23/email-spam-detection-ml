# Email Spam Detection using Machine Learning

This repository contains a complete machine learning workflow to classify emails as **Spam** or **Not Spam (Ham)**. It includes data preprocessing, exploratory analysis, feature engineering, model training, evaluation, and comparisons between multiple approaches.

---

## 📌 Project Overview

The goal is to build a spam detection system that works well on a labeled dataset of email subject lines and body text. Due to class imbalance, models were evaluated using precision, recall, and F1-score with a focus on correctly detecting spam.

---

## 📂 Dataset

The dataset used in this project contains:
- `title`: Email subject
- `text`: Email body
- `type`: Label (`spam`, `not spam`)
- `label`: Numeric encoding (`spam` → 1, `not spam` → 0)

The dataset is loaded from the Kaggle dataset or manually uploaded via Colab.

---

## 🔍 Exploratory Data Analysis (EDA)

During analysis:
- Spam emails tend to be longer, but length alone was not sufficient.
- Simple count-based features like URL count, number count, uppercase ratio did not separate classes well.
- Raw word frequencies were dominated by common words, motivating TF-IDF.

---

## 🛠 Feature Engineering

- **TF-IDF Vectorization**: Unigrams + bigrams, stopwords removed.
- **Email length**: Evaluated but not useful.
- **Sentence embeddings** (transformer-based): Explored as a bonus.

---

## 🤖 Models Implemented

1. **Logistic Regression (TF-IDF)** – Baseline model.
2. **Logistic Regression (TF-IDF + email length)** – Meta-feature experiment.
3. **Neural Network (MLP + TF-IDF)** – Best performing approach.
4. **Logistic Regression with Sentence Embeddings (Bonus)**.

---

## 📊 Evaluation Metrics

Models were evaluated using:
- **Precision**
- **Recall**
- **F1-score**
- **Confusion Matrix**

Priority was given to **spam recall**.

---

## 📈 Results Summary

| Model | Spam Precision | Spam Recall | F1-Score |
|-------|----------------|-------------|----------|
| Logistic Regression (TF-IDF) | 0.50 | 0.20 | 0.29 |
| Logistic Regression (TF-IDF + length) | 0.00 | 0.00 | 0.00 |
| Neural Network (MLP + TF-IDF) | **0.75** | **0.60** | **0.67** |
| Logistic Regression (Sentence Embeddings) | 0.60 | 0.60 | 0.60 |

The **MLP + TF-IDF** model was the best performing model for spam detection.

---

## 🚀 How to Run

1. Clone the repository:
```bash
git clone https://github.com/bhanup23/email-spam-detection-ml.git
cd email-spam-detection-ml
```

2. Install dependencies:
```bash
pip install -r requirements.txt
```

3. Run the notebook:
```bash
jupyter notebook
```

---
