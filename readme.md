# Predicting Trending TikTok Songs Using Machine Learning 🎵📈

This project builds a **data-driven predictive analytics system** to predict whether a song will become **Trending** on TikTok using **audio features + artist metadata**.  
It follows **University of London CM3070 Final Project — Template 5 (Data-Driven System / Predictive Analytics)**.

---

## 📌 Project Overview

TikTok is one of the biggest platforms driving music discovery. Some songs go viral rapidly due to short-form trends (challenges, edits, memes, etc.).  
This project aims to predict **whether a song will trend** based on:

- **Audio features** (danceability, energy, valence, tempo, etc.)
- **Artist popularity metadata**

The final system outputs:
- **Binary prediction:** Trending (1) / Not Trending (0)
- **Probability score:** `P(trending)`

---

## 🎯 Problem Definition

### Target Label: Trending
The dataset includes a popularity score (`track_pop`).  
Trending is defined as:

✅ **Trending = Top 25% of songs by `track_pop` (75th percentile threshold)**  
✅ This avoids arbitrary thresholds and supports defensible evaluation.

---

## 🧠 Models Implemented

### Baseline Model
- **Logistic Regression**
- Feature scaling using **StandardScaler**
- Used to establish a clear benchmark

### Advanced Model
- **Random Forest Classifier**
- `class_weight="balanced"` to reduce class imbalance bias
- Hyperparameter tuning with **GridSearchCV**

### Additional Improvements
- **5-Fold Cross-Validation**
- **Probability Calibration** with `CalibratedClassifierCV`
- **Imbalance-aware evaluation** using PR-AUC
- **Threshold Optimisation** for improved F1-score
- **Interpretability** using permutation feature importance

---

## ✅ Key Results (Summary)

- Logistic Regression ROC-AUC: **~0.80**
- Random Forest ROC-AUC: **~0.84**
- Cross-Validation ROC-AUC: **~0.85**
- PR-AUC (Average Precision): **~0.51**
- Best F1-score (threshold optimised): **~0.70**

> Note: Due to class imbalance, threshold tuning significantly improves trending-class performance.

---

## 📊 Evaluation Metrics Used
- Accuracy
- Precision / Recall / F1-score
- ROC-AUC
- PR-AUC (Average Precision)
- Confusion Matrix
- Threshold optimisation curve
- Sensitivity analysis on alternative trending thresholds (70th / 75th / 80th percentile)

---

## 📦 Dataset

Source: Kaggle  
**TikTok Popular Songs 2022 Dataset**  
https://www.kaggle.com/datasets/sveta151/tiktok-popular-songs-2022

---

## 🛠️ Tech Stack

- Python 3
- Jupyter Notebook
- pandas, numpy
- scikit-learn
- matplotlib

---

## 🚀 How to Run

1) Clone the repository:
```bash
git clone https://github.com/Samuel611S/final_project.git
cd final_project