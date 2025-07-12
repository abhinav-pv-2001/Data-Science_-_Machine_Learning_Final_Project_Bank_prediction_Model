# 💼 Bank Term Deposit Subscription Prediction

This repository contains an end-to-end machine learning classification project that predicts whether a customer will subscribe to a term deposit based on various personal and campaign-related attributes. The project uses the **Bank Marketing Dataset** from the UCI Machine Learning Repository.

---

## 📌 Project Overview

- **Business Problem**: Financial institutions need to optimize their marketing campaigns by targeting customers who are most likely to subscribe to term deposits. This reduces costs and increases campaign effectiveness.
- **Goal**: Build a predictive model to identify potential customers likely to say "yes" to term deposit offers.

---

## 📊 Dataset Information

- **Source**: [UCI Bank Marketing Dataset](https://archive.ics.uci.edu/ml/datasets/bank+marketing)
- **Total Records**: 45,211
- **Target Variable**: `y` → Whether the client subscribed to a term deposit ("yes"/"no")

---

## 🧪 Key Steps Performed

### 1. 🔎 Exploratory Data Analysis (EDA)
- Analyzed target imbalance (~11.7% said "yes").
- Identified important features: `age`, `balance`, `campaign`, `month`, etc.
- Visualized relationships using countplots, histograms, and heatmaps.

### 2. 🧼 Data Preprocessing
- **Outlier Handling**: Used IQR method to clip extreme values.
- **Skewness Correction**: Applied log1p and Yeo-Johnson transformations.
- **Encoding**: OneHotEncoding and LabelEncoding for categorical variables.
- **Binning**: Converted `pdays` and `previous` into categorical bins for interpretability.

### 3. ⚖️ Handling Class Imbalance
- Applied **ADASYN** (Adaptive Synthetic Sampling) to oversample minority class (`yes`).
- Balanced data significantly improved model recall and F1-score.

### 4. 🤖 Model Building
Tested the following models:
- Logistic Regression
- Decision Tree
- Random Forest
- Support Vector Machine
- K-Nearest Neighbors
- Naive Bayes

### 5. 🔍 Hyperparameter Tuning
- Used `GridSearchCV` for **SVM**.
- Used `RandomizedSearchCV` for **Random Forest**.

### 6. 🛠️ Final ML Pipeline
- Created a full Scikit-learn pipeline (preprocessing + model).
- Saved final model using `joblib`.

---

## 📈 Model Performance

| Model                     | Accuracy | ROC-AUC |
|--------------------------|----------|---------|
| Logistic Regression      | 83.7%    | 64.8%   |
| Decision Tree            | 82.4%    | 62.1%   |
| Random Forest (Tuned)    | 85.0%    | 70.1%   |
| SVM (Tuned)              | 84.8%    | 66.7%   |
| Final ML Pipeline (RF)   | **88.6%** | **74.3%** |

✅ Final pipeline performs best on test data and is saved for deployment.

---

## 📂 Folder Structure


