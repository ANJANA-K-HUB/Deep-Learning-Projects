# 🧠 Deep Learning Projects

A collection of deep learning projects spanning computer vision and natural language processing — built with TensorFlow / Keras and scikit-learn.

![Python](https://img.shields.io/badge/Python-3.10%2B-blue)
![TensorFlow](https://img.shields.io/badge/TensorFlow-2.x-orange)
![License](https://img.shields.io/badge/License-MIT-green)
![Projects](https://img.shields.io/badge/Projects-5-purple)

---

## 📁 Projects

| # | Project | Type | Task | Key Model |
|---|---------|------|------|-----------|
| 1 | [🌿 Cotton Plant Disease Classification](#-cotton-plant-disease-classification) | Computer Vision | Multi-class Classification | CNN |
| 2 | [😷 Face Mask Detection](#-face-mask-detection) | Computer Vision | Binary Classification | CNN |
| 3 | [🌀 Hurricane Damage Classification](#-hurricane-damage-classification) | Computer Vision | Binary Classification | CNN |
| 4 | [🎬 Movie Genre Classification](#-movie-genre-classification) | NLP | Sentiment Analysis | BiLSTM |
| 5 | [🛰️ Satellite Image Classification](#️-satellite-image-classification) | Computer Vision | Multi-class Classification | CNN |

---

## 🌿 Cotton Plant Disease Classification

Classifies cotton plant leaf images into disease categories to assist in early detection and crop management.

- **Type:** Computer Vision — Multi-class Classification
- **Model:** Convolutional Neural Network (CNN)
- **Dataset:** Cotton plant leaf images
- **Use case:** Agricultural disease detection

📂 [`Cotton Plant Disease Classification/`](./Cotton%20Plant%20Disease%20Classification)

---

## 😷 Face Mask Detection

Detects whether a person in an image is wearing a face mask or not — useful for public safety monitoring.

- **Type:** Computer Vision — Binary Classification
- **Model:** CNN
- **Dataset:** Face images with / without masks
- **Use case:** Public health & surveillance

📂 [`Face Mask Detection/`](./Face%20Mask%20Detection)

---

## 🌀 Hurricane Damage Classification

Classifies satellite or aerial images to identify areas affected by hurricane damage.

- **Type:** Computer Vision — Binary Classification
- **Model:** CNN
- **Dataset:** Aerial imagery — damaged vs. undamaged
- **Use case:** Disaster response & damage assessment

📂 [`Hurricane Damage Classification/`](./Hurricane%20Damage%20Classification)

---

## 🎬 Movie Genre Classification

Classifies movie reviews as positive or negative using NLP and deep learning on ~50,000 reviews.

- **Type:** NLP — Sentiment Analysis
- **Model:** Bidirectional LSTM
- **Dataset:** ~49,551 unique movie reviews (binary sentiment)
- **Accuracy:** **89%** on test set
- **Use case:** Review analysis, recommendation systems

**Pipeline highlights:**
- HTML stripping, stopword removal, lemmatization
- Keras Tokenizer + sequence padding (maxlen=200)
- Embedding → SpatialDropout → BiLSTM → Dense

📂 [`Movie Genre Classification/`](./Movie%20Genre%20Classification)

---

## 🛰️ Satellite Image Classification

Classifies satellite images into land-use or scene categories such as forest, urban, water, and agriculture.

- **Type:** Computer Vision — Multi-class Classification
- **Model:** CNN
- **Dataset:** Satellite imagery with scene labels
- **Use case:** Land-use mapping, urban planning, environmental monitoring

📂 [`Satellite Image Classification/`](./Satellite%20Image%20Classification)

---

## 🛠️ Tech Stack

| Category      | Tools                                      |
|---------------|--------------------------------------------|
| Language      | Python 3.10+                               |
| Deep Learning | TensorFlow / Keras                         |
| Data Handling | Pandas, NumPy                              |
| Visualization | Matplotlib, Seaborn                        |
| NLP           | NLTK, BeautifulSoup                        |
| ML Utilities  | scikit-learn                               |
| Runtime       | Google Colab (T4 GPU)                      |

---



