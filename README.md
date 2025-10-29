# 🩺 Predicting Diabetes Mellitus — WiDS Datathon 2021 (MATLAB Implementation)

## 📌 Overview
This project is a MATLAB-based solution for the **WiDS Datathon 2021** competition hosted on Kaggle.  
The goal is to **predict the likelihood of a patient developing diabetes mellitus** based on a variety of medical and demographic factors.

We used the dataset provided in the competition and implemented a **Decision Tree classifier** with additional visual analytics and evaluation metrics to interpret model performance.

---

## 📂 Dataset Information
The dataset is sourced from Kaggle’s official competition:
🔗 [WiDS Datathon 2021 — Kaggle Dataset](https://www.kaggle.com/competitions/widsdatathon2021/data?select=DataDictionaryWiDS2021.csv)

**Files Used:**
- `train.csv` — Training data with known diabetes outcomes.  
- `test.csv` — Test data for prediction.  
- `DataDictionaryWiDS2021.csv` — Metadata describing all features.

**Target Variable:**  
`diabetes_mellitus` (1 = Diabetes, 0 = No Diabetes)

**ID Column:**  
`encounter_id`

---

## ⚙️ Data Preprocessing
The preprocessing stage included:
- Handling **missing numeric values** using mean imputation.  
- Handling **categorical/text data** by converting to numeric codes.  
- Removing irrelevant identifiers and ensuring consistent formatting between train and test datasets.  
- Visualizing **feature correlations** using a correlation heatmap to understand dependencies among features.

```matlab
figure;
heatmap(corr(table2array(XTrain), 'Rows', 'pairwise'));
title('Correlation Heatmap of Features');
xlabel('Features'); ylabel('Features');
