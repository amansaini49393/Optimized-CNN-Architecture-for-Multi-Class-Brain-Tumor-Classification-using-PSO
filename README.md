# 🧠 Optimized CNN Architecture for Multi-Class Brain Tumor Classification using PSO

This project demonstrates a deep learning approach for classifying brain tumors from MRI scans using a Convolutional Neural Network (CNN), with training enhanced by **Particle Swarm Optimization (PSO)**. The model is benchmarked against a traditionally trained CNN using the **Adam optimizer**.

---

## 📁 Dataset

We use the [PMRAM Bangladeshi Brain Cancer MRI Dataset](https://www.kaggle.com/datasets/masumrumi/pmram-bangladeshi-brain-cancer-mri-dataset), which contains:

- ✅ 6004 augmented MRI images
- 🧠 4 classes: **Glioma**, **Meningioma**, **Pituitary**, **Normal**
- 📐 Images are resized to `224x224 RGB` for model input

---

## 🔧 Preprocessing

- Resizing images to `224x224`
- Label encoding
- Normalizing pixel values to `[0,1]`
- Splitting into:
  - 80% Training
  - 10% Validation
  - 10% Testing
- Visualizations: Pie and bar charts of class distribution

---

## 🧠 Model Architecture

The CNN contains 5 convolutional blocks with:

- `Conv2D → BatchNorm → MaxPooling`
- Global Average Pooling
- Dense layer with 512 units
- Output layer: 4 neurons with softmax activation


---

## 🚀 Optimization Techniques

### 1. PSO (Particle Swarm Optimization)
- Treats model weights as particles
- Optimizes the entire weight space without backpropagation
- Config: `5 particles`, `3 epochs`, `w=0.5`, `c1=c2=1.0`

### 2. Adam Optimizer
- Gradient-based optimizer
- Faster convergence for small-scale training
- Benchmarking against PSO

---

## 📊 Evaluation Metrics

- Accuracy
- F1-Score
- Confusion Matrix
- Training/Validation curves
- Per-class performance
- Visualizations for model predictions

---

## 📈 Results Summary

| Optimizer | Accuracy | Validation Loss | F1-Score (Macro Avg) |
|----------|----------|------------------|-----------------------|
| Adam     | 87.18%   | 0.6994           | 0.76                  |
| PSO      | ~75%     | 3.07             | 0.76 (with fewer epochs) |

> **Note:** PSO can achieve better performance with more particles and training iterations.

