# 🛰️ Satellite Image Classification

A deep learning project that classifies satellite images into 3 categories — Green Area, Desert, and Cloudy — using a custom CNN built with TensorFlow/Keras. Achieves **97% test accuracy** on 827 test images.

---

## 📌 Problem Statement

Satellite imagery is widely used in environmental monitoring, urban planning, agriculture, and climate research. Manually categorizing thousands of satellite images is time-consuming and impractical at scale. This project automates land cover and weather classification from satellite images using deep learning, enabling faster geospatial analysis.

---

## 🏷️ Classes

| Label | Class | Description |
|---|---|---|
| 0 | Green Area | Vegetation, forests, farmland |
| 1 | Desert | Arid, dry, barren land |
| 2 | Cloudy | Cloud-covered regions |

---

## 🗂️ Dataset

- **Total Images:** 4,131
- **Per Class:** Green Area — 1,500 | Desert — 1,131 | Cloudy — 1,500
- **Image Size:** Resized to 128 × 128 × 3 (RGB)
- **Train / Test Split:** 80% training (3,304) / 20% testing (827)
- **Preprocessing:** Images read using OpenCV, converted from BGR to RGB, resized and normalized (pixel values / 255.0)
- **Structure:**
```
green_area/
├── *.jpg

desert/
├── *.*

cloudy/
├── *.jpg
```

---

## 🧠 Model Architecture

A custom 3-layer CNN built from scratch using the Keras Sequential API, designed to capture multi-scale spatial features from satellite imagery.
```
Input (128×128×3)
      ↓
Conv2D(32, 3×3, ReLU)
      ↓
MaxPooling2D
      ↓
Conv2D(64, 3×3, ReLU)
      ↓
MaxPooling2D
      ↓
Conv2D(128, 3×3, ReLU)
      ↓
MaxPooling2D
      ↓
Flatten
      ↓
Dense(128, ReLU)
      ↓
Dropout(0.5)
      ↓
Dense(3, Softmax)  ← Multi-class output
```

| Parameter | Value |
|---|---|
| Total Params | 3,305,027 (12.61 MB) |
| Trainable Params | 3,305,027 |

---

## ⚙️ Training Configuration

| Parameter | Value |
|---|---|
| Optimizer | Adam |
| Loss Function | Sparse Categorical Crossentropy |
| Epochs | 30 |
| Validation Split | 10% of training data |
| Dropout Rate | 0.5 |
| Input Shape | (128, 128, 3) |

---

## 📊 Results

| Metric | Score |
|---|---|
| Training Accuracy | 97.31% |
| Test Accuracy | 97.22% |
| Macro Precision | 0.97 |
| Macro Recall | 0.97 |
| Macro F1-Score | 0.97 |

### Per-Class Performance

| Class | Precision | Recall | F1-Score | Support |
|---|---|---|---|---|
| Green Area | 1.00 | 1.00 | 1.00 | 278 |
| Desert | 0.93 | 0.98 | 0.95 | 233 |
| Cloudy | 0.98 | 0.94 | 0.96 | 316 |

> **Highlight:** Green Area achieved perfect precision and recall (1.00), while Desert and Cloudy also showed strong performance with F1-scores above 0.95.

---

## 🛠️ Tech Stack

| Library | Purpose |
|---|---|
| TensorFlow / Keras | Model building and training |
| OpenCV (cv2) | Image reading and preprocessing |
| scikit-learn | Train-test split, metrics, confusion matrix |
| scikit-image | Image transformation |
| NumPy | Array operations |
| Matplotlib | Image visualizations |
| Seaborn | Confusion matrix heatmap |

---


## 🔮 Future Improvements

- Add more classes such as Water Bodies, Urban Areas, and Snow Cover
- Apply data augmentation to handle class imbalance and improve generalization
- Use a pre-trained model like EfficientNet or ResNet50 for better feature extraction
- Deploy as a web app for real-time satellite image classification
- Integrate with Google Earth Engine or NASA Earth APIs for live data

---

