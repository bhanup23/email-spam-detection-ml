# Email Spam Detection using Machine Learning

This repository contains a complete machine learning solution to classify emails as **Spam** or **Not Spam (Ham)**. It includes data preprocessing, exploratory analysis, feature engineering, model training, evaluation, and comparison of multiple approaches.

---

## 📌 Project Overview

The task was to build a robust classifier to detect spam emails effectively. The dataset includes email subject lines and body text, labeled as spam or not spam. Due to class imbalance, evaluation focuses on precision, recall, and F1-score rather than accuracy alone.

---

## 📂 Dataset

- **title**: Email subject
- **text**: Email body content
- **type**: Label indicating spam or not spam

The dataset can be downloaded using the Kaggle API or uploaded directly into the notebook.

---

## 🔍 Exploratory Data Analysis (EDA)

Key trends discovered:
- Spam emails tend to be longer (but not exclusively)
- Simple count-based features like URL count or uppercase ratio did not strongly separate classes
- Vocabulary analysis showed that common stopwords dominate raw frequency counts

These insights motivated the choice of TF-IDF for text representation.

---

## 🛠 Feature Engineering

1. **Text cleaning and preprocessing**
2. **TF-IDF Vectorization**
   - Unigrams and bigrams
   - Stopword removal
3. **Email length** (evaluated but shown to be not helpful)
4. **Sentence embeddings** (advanced/bonus)

---

## 🤖 Models Implemented

### ✅ 1. Logistic Regression (Baseline)
Trained using TF-IDF features — strong baseline but low recall on spam.

### ❌ 2. Logistic Regression + Email Length
Adding email length did not improve performance and was discarded.

### ⭐ 3. Neural Network (MLP Classifier)
Feed-forward network trained on TF-IDF features — achieved the best balance of precision and recall.

### 🔁 4. Sentence Embeddings (Bonus)
Transformer embeddings evaluated with Logistic Regression — stable but did not outperform the TF-IDF + neural network model.

---

## 📊 Evaluation Results

| Model | Spam Precision | Spam Recall | F1-Score |
|-------|----------------|-------------|----------|
| Logistic Regression (TF-IDF) | 0.50 | 0.20 | 0.29 |
| Logistic Regression (TF-IDF + length) | 0.00 | 0.00 | 0.00 |
| Neural Network (MLP + TF-IDF) | **0.75** | **0.60** | **0.67** |
| Logistic Regression (Sentence Embeddings) | 0.60 | 0.60 | 0.60 |

---

## 📈 Insights

- **TF-IDF features** are effective at capturing keyword/phrase-level signals that differentiate spam from not spam.
- **Neural network (MLP)** further improves performance by capturing non-linear relationships.
- **Sentence embeddings** provide semantic features but may require larger data to outperform TF-IDF.

---

## 🧪 How to Run

1. Clone the repository:
   ```bash
   git clone https://github.com/bhanup23/email-spam-detection-ml.git
