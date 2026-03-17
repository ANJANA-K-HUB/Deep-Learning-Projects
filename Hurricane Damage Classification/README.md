# 🌀 Hurricane Damage Classification

A deep learning project that classifies aerial satellite images to detect whether an area has been damaged by a hurricane or not. Built using a custom CNN with TensorFlow/Keras, achieving **95% test accuracy** on 9,000 test images.

---

## 📌 Problem Statement

After a hurricane strikes, rapid damage assessment is critical for disaster response and relief operations. Manual inspection of aerial images is slow and resource-intensive. This project automates damage detection from satellite imagery using deep learning, enabling faster and more scalable post-disaster analysis.

---

## 🏷️ Classes

| Label | Condition |
|---|---|
| 0 | No Damage |
| 1 | Damage |

---

## 🗂️ Dataset

- **Training Images:** 10,000 (5,000 damaged + 5,000 no damage — balanced)
- **Test Images:** 9,000 (8,000 damaged + 1,000 no damage — imbalanced)
- **Image Size:** Resized to 128 × 128 × 3 (RGB)
- **Preprocessing:** Images read using OpenCV, converted from BGR to RGB, resized and normalized (pixel values / 255.0)
- **Structure:**
```
train_another/
├── damage/
└── no_damage/

test_another/
├── damage/
└── no_damage/
```

---

## 🧠 Model Architecture

A custom 3-layer CNN built from scratch using Keras Sequential API, deeper than a standard binary classifier to handle complex aerial image patterns.
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
Dense(1, Sigmoid)  ← Binary output
```

| Parameter | Value |
|---|---|
| Total Params | 3,304,769 (12.61 MB) |
| Trainable Params | 3,304,769 |

---

## ⚙️ Training Configuration

| Parameter | Value |
|---|---|
| Optimizer | Adam |
| Loss Function | Binary Crossentropy |
| Epochs | 20 |
| Batch Size | 32 |
| Validation Split | 10% of training data |
| Classification Threshold | 0.7 |
| Input Shape | (128, 128, 3) |

---

## 📊 Results

| Metric | Score |
|---|---|
| Training Accuracy | 99.40% |
| Test Accuracy | 95% |
| Weighted F1-Score | 0.95 |

### Per-Class Performance

| Class | Precision | Recall | F1-Score | Support |
|---|---|---|---|---|
| No Damage | 0.70 | 0.97 | 0.81 | 1,000 |
| Damage | 1.00 | 0.95 | 0.97 | 8,000 |

### Confusion Matrix
```
[[  963    37]
 [  358  7642]]
```

> **Note:** The dataset is imbalanced in the test set (8:1 ratio of damaged to no-damage), which affects the precision for the No Damage class.

---

## 🛠️ Tech Stack

| Library | Purpose |
|---|---|
| TensorFlow / Keras | Model building and training |
| OpenCV (cv2) | Image reading and preprocessing |
| scikit-learn | Metrics and confusion matrix |
| scikit-image | Image transformation |
| NumPy | Array operations |
| Matplotlib | Image visualizations |
| Seaborn | Confusion matrix heatmap |

---


## 🔮 Future Improvements

- Apply data augmentation to handle class imbalance in test data
- Use a pre-trained model like ResNet50 or EfficientNet for better feature extraction
- Deploy as a web app for real-time aerial image analysis
- Integrate with satellite image APIs for automated disaster monitoring
- Experiment with weighted loss functions to improve No Damage class precision

---

