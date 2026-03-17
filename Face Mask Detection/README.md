# 😷 Face Mask Detection

A deep learning project that detects whether a person is wearing a face mask or not using a custom CNN (Convolutional Neural Network). Built with TensorFlow/Keras, achieving **95% test accuracy** on 3,584 face images.

---

## 📌 Problem Statement

During health crises like the COVID-19 pandemic, monitoring mask compliance in public spaces became critical. Manual monitoring is time-consuming and error-prone. This project automates face mask detection using a CNN model trained on labeled face images, enabling real-time and scalable compliance checking.

---

## 🏷️ Classes

| Label | Condition |
|---|---|
| 0 | With Mask |
| 1 | Without Mask |

---

## 🗂️ Dataset

- **Total Images:** 3,584
- **Images per Class:** 1,792 (perfectly balanced)
- **Image Size:** Resized to 64 × 64 × 3 (RGB)
- **Train / Test Split:** 80% training / 20% testing
- **Preprocessing:** Images read using OpenCV, converted from BGR to RGB, resized and normalized

---

## 🧠 Model Architecture

A custom CNN built from scratch using Keras Sequential API.
```
Input (64×64×3)
      ↓
Conv2D(32, 3×3, ReLU)
      ↓
MaxPooling2D
      ↓
Conv2D(64, 3×3, ReLU)
      ↓
MaxPooling2D
      ↓
Flatten
      ↓
Dense(64, ReLU)
      ↓
Dense(1, Sigmoid)  ← Binary output
```

| Parameter | Value |
|---|---|
| Total Params | 822,337 (3.14 MB) |
| Trainable Params | 822,337 |

---

## ⚙️ Training Configuration

| Parameter | Value |
|---|---|
| Optimizer | Adam |
| Loss Function | Binary Crossentropy |
| Epochs | 10 |
| Batch Size | 32 |
| Validation Split | 20% of training data |
| Input Shape | (64, 64, 3) |

---

## 📊 Results

| Metric | Score |
|---|---|
| Test Accuracy | 95% |
| Macro Precision | 0.95 |
| Macro Recall | 0.95 |
| Macro F1-Score | 0.95 |

### Per-Class Performance

| Class | Precision | Recall | F1-Score | Support |
|---|---|---|---|---|
| With Mask | 0.94 | 0.96 | 0.95 | 369 |
| Without Mask | 0.96 | 0.94 | 0.95 | 348 |

---

## 🛠️ Tech Stack

| Library | Purpose |
|---|---|
| TensorFlow / Keras | Model building and training |
| OpenCV (cv2) | Image reading and preprocessing |
| scikit-learn | Train-test split, metrics, confusion matrix |
| scikit-image | Image transformation |
| NumPy | Array operations |
| Matplotlib | Visualizations |
| Seaborn | Confusion matrix heatmap |

---


## 🔮 Future Improvements

- Integrate with real-time webcam feed using OpenCV
- Deploy as a web app using Flask or Streamlit
- Add data augmentation to improve generalization
- Use a pre-trained model like MobileNetV2 for better accuracy
- Extend to detect improper mask usage (e.g., mask below nose)

---

