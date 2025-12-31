# Email Spam Detection using Machine Learning

This repository contains an end-to-end machine learning project that classifies
emails as **Spam** or **Not Spam (Ham)**. The project demonstrates a complete
workflow including data preprocessing, exploratory data analysis, feature
engineering, model training, evaluation, and comparison.

---

## 📌 Project Overview

The goal of this task is to build and evaluate different machine learning models
for spam email detection using textual data. Special emphasis is placed on proper
feature engineering and evaluation metrics due to class imbalance.

---

## 🗂 Dataset

- Each email consists of:
  - `title`: Email subject
  - `text`: Email body
  - `type`: Label (`spam` or `not spam`)

- The dataset is downloaded programmatically (Kaggle/Drive/Colab) to ensure
  reproducibility across environments.

---

## 🔧 Feature Engineering

- Text cleaning (lowercasing, removing URLs, numbers, punctuation)
- **TF-IDF vectorization** with unigrams and bigrams
- Experimental meta-features (email length)
- **Sentence embeddings (transformer-based)** as an advanced approach

---

## 🤖 Models Implemented

1. **Logistic Regression (TF-IDF)**  
   - Serves as a classical baseline model

2. **Logistic Regression (TF-IDF + Email Length)**  
   - Evaluates the impact of simple meta-features

3. **Feed-Forward Neural Network (MLPClassifier)**  
   - Trained on TF-IDF features
   - Achieved the best spam detection performance

4. **Logistic Regression with Sentence Embeddings (Bonus)**  
   - Uses transformer-based semantic representations

---

## 📊 Evaluation Metrics

Due to class imbalance, models are evaluated using:
- Precision
- Recall
- F1-score
- Confusion Matrix

Spam recall is treated as a key metric to assess model effectiveness.

---

## ✅ Key Results

- Logistic Regression performed well on non-spam emails but missed many spam cases.
- Adding email length degraded performance and was discarded.
- **TF-IDF + Neural Network achieved the best balance**, detecting 60% of spam emails
  with strong precision.
- Sentence embeddings provided stable results but did not outperform TF-IDF on this
  small, keyword-driven dataset.

---

## 🚀 How to Run

1. Clone the repository:
   ```bash
   git clone https://github.com/<your-username>/email-spam-detection-ml.git
