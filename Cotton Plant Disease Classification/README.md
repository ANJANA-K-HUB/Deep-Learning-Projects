# 🌿 Cotton Plant Disease Classification

A deep learning project that automatically identifies diseases in cotton plant leaves using Transfer Learning with MobileNetV2. Early and accurate disease detection can help farmers minimize crop damage and improve yield.

---

## 📌 Problem Statement

Cotton is one of the most economically important crops worldwide. Diseases like Bacterial Blight, Powdery Mildew, and pest infestations such as Aphids and Army Worm can devastate entire harvests if not detected early. This project aims to automate disease detection using deep learning on leaf images, enabling faster and more accurate diagnosis.

---

## 🏷️ Classes

| Label | Condition | Description |
|---|---|---|
| 0 | Aphids | Tiny insects that damage leaves by sucking sap |
| 1 | Healthy Leaf | No disease or infection detected |
| 2 | Bacterial Blight | Caused by Xanthomonas bacteria, leads to dark lesions |
| 3 | Army Worm | Caterpillar pest that eats through leaves |
| 4 | Target Spot | Fungal disease causing circular brown spots |
| 5 | Powdery Mildew | Fungal infection leaving white powdery coating |

---

## 🗂️ Dataset

- **Total Images:** 2,400
- **Images per Class:** 400 (perfectly balanced)
- **Image Size:** Resized to 224 × 224 × 3 (RGB)
- **Train / Test Split:** 80% training (1,920) / 20% testing (480)
- **Source:** Stored as a zip file on Google Drive

---

## 🧠 Model Architecture

Transfer learning was used by leveraging a pre-trained MobileNetV2 model as a frozen feature extractor, with a custom classification head trained on top.
```
Input (224×224×3)
      ↓
MobileNetV2 Feature Extractor [Frozen] → Output: 1280-dim vector
      ↓
Dense(64, activation='relu')
      ↓
Dropout(0.6)
      ↓
Dense(14, activation='relu')
      ↓
Dense(6, activation='softmax')  ← Final prediction
```

**Why MobileNetV2?**
- Lightweight and efficient
- Pre-trained on ImageNet (rich visual features)
- Well-suited for image classification tasks with limited data

---

## ⚙️ Training Configuration

| Parameter | Value |
|---|---|
| Optimizer | Adam |
| Loss Function | Sparse Categorical Crossentropy |
| Epochs | 20 |
| Validation Split | 10% of training data |
| Dropout Rate | 0.6 |
| Input Shape | (224, 224, 3) |
| Hardware | Google Colab T4 GPU |

---

## 📊 Results

| Metric | Score |
|---|---|
| Training Accuracy | 99.32% |
| Test Accuracy | 96% |
| Macro Precision | 0.96 |
| Macro Recall | 0.95 |
| Macro F1-Score | 0.96 |

### Per-Class Performance

| Class | Precision | Recall | F1-Score |
|---|---|---|---|
| Aphids | 0.90 | 0.98 | 0.94 |
| Healthy Leaf | 0.98 | 0.99 | 0.98 |
| Bacterial Blight | 0.94 | 0.92 | 0.93 |
| Army Worm | 0.99 | 0.96 | 0.98 |
| Target Spot | 0.93 | 0.93 | 0.93 |
| Powdery Mildew | 1.00 | 0.95 | 0.97 |

---

## 🛠️ Tech Stack

| Library | Purpose |
|---|---|
| TensorFlow / Keras | Model building and training |
| TensorFlow Hub | MobileNetV2 pre-trained feature extractor |
| scikit-learn | Train-test split, metrics, confusion matrix |
| scikit-image | Image resizing |
| NumPy | Array operations |
| Matplotlib | Visualizations |
| Seaborn | Confusion matrix heatmap |
| Google Colab | Cloud training with T4 GPU |

---






## 🔮 Future Improvements

- Deploy as a web app using Flask or Streamlit
- Fine-tune MobileNetV2 layers for better accuracy
- Expand dataset with more diverse images
- Add data augmentation to improve generalization
- Try other architectures like EfficientNet or ResNet

---

