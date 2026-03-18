# 🎬 Movie Review Sentiment Classification

A deep learning project that classifies movie reviews as **positive** or **negative** using a Bidirectional LSTM model trained on ~50,000 IMDb-style reviews.

---

## 📌 Overview

This project builds an end-to-end NLP pipeline to perform binary sentiment analysis on movie reviews. It covers data cleaning, text preprocessing, sequence modeling with an embedding layer and Bidirectional LSTM, and evaluation using standard classification metrics.

---

## 📂 Dataset

- **File:** `movie_data.csv`
- **Size:** ~49,969 rows (418 duplicates removed → 49,551 unique reviews)
- **Columns:**
  - `review` — Raw text of the movie review
  - `sentiment` — Binary label (`1` = Positive, `0` = Negative)
- **Class distribution:** Approximately balanced (~24,866 positive / ~24,685 negative)

---

## 🔧 Pipeline

### 1. Data Cleaning & EDA
- Inspected shape, dtypes, and null values
- Removed 418 duplicate reviews

### 2. Text Preprocessing
- Stripped HTML tags using `BeautifulSoup`
- Removed non-alphabetical characters with regex
- Lowercased and tokenized text
- Removed English stopwords (`nltk`)
- Applied verb lemmatization (`WordNetLemmatizer`)
- Used multiprocessing (`Pool`) for fast parallel preprocessing

### 3. Tokenization & Sequence Encoding
- Tokenized with `Keras Tokenizer` (vocabulary size: 20,000 + OOV token)
- Padded/truncated sequences to a fixed length of **200 tokens**

### 4. Train/Test Split
- 80% training / 20% test (`random_state=42`)

### 5. Model Architecture

```
Input (200,)
  └─ Embedding(20001, 128)
      └─ SpatialDropout1D(0.3)
          └─ Bidirectional LSTM(64)
              └─ Dropout(0.3)
                  └─ Dense(32, ReLU)
                      └─ Dense(1, Sigmoid)
```

- **Loss:** Binary Crossentropy
- **Optimizer:** Adam (`lr=0.001`, `clipnorm=1.0`)
- **Callbacks:** EarlyStopping (patience=3), ReduceLROnPlateau (patience=2)
- **Epochs:** Up to 15 (early stopping applied)
- **Batch size:** 128

### 6. Evaluation
- Accuracy score
- Confusion matrix (heatmap)
- Classification report (precision, recall, F1-score)

---

## 📊 Results

| Metric        | Class 0 (Negative) | Class 1 (Positive) | Overall |
|---------------|--------------------|--------------------|---------|
| Precision     | 0.90               | 0.87               | 0.89    |
| Recall        | 0.87               | 0.90               | 0.89    |
| F1-Score      | 0.88               | 0.89               | 0.89    |
| **Accuracy**  |                    |                    | **89%** |

---

## 🛠️ Tech Stack

| Category        | Tools / Libraries                          |
|-----------------|--------------------------------------------|
| Language        | Python 3                                   |
| Data Handling   | Pandas, NumPy                              |
| Visualization   | Matplotlib, Seaborn                        |
| NLP             | NLTK, BeautifulSoup                        |
| Deep Learning   | TensorFlow / Keras                         |
| ML Utilities    | scikit-learn                               |
| Runtime         | Google Colab (T4 GPU)                      |

---


