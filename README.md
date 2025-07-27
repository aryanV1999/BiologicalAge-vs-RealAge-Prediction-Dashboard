# 🧬 BioAge vs RealAge Prediction & Dashboard

This project analyzes biological age in comparison to chronological age using machine learning models on health-related data. It includes model training, data preprocessing, and an interactive Power BI dashboard for visual insights.

---

## 📌 Project Overview

- **Objective**: Predict Biological Age (`kdm0`) using physiological and demographic features, and compare it against Real (Chronological) Age to uncover aging trends.
- **Dataset**: Cleaned version of NHANES32 with 19K+ participants.

---

## 🧹 Data Preprocessing

- Removed outliers using **Z-score method** (threshold = 3)
- Handled missing values using **median imputation**
- Normalized features using **MinMaxScaler** and **StandardScaler**
- Features used: `age`, `fev`, `pulse`, `phenoage0`, `height`, `income_recode`, `poverty_ratio`, `hba1c`, `waist`, `kdm_advance0`

---

## 🤖 ML Models Used

| Model                 | R² Score | RMSE (yrs) | MAE (yrs) | MAPE (%) |
|----------------------|----------|------------|-----------|----------|
| Random Forest        | 0.9821   | 1.22       | 0.83      | 1.89     |
| XGBoost              | 0.9850   | 1.15       | 0.76      | 1.61     |
| **Stacked Ensemble** | **0.9880** | **1.07**   | **0.70**  | **1.50** |

✅ Final model: **StackingRegressor** (XGBoost, RF, GB as base + Ridge as meta-model)

---

## 📊 Power BI Dashboard Insights

![Dashboard Preview](https://github.com/aryanV1999/BiologicalAge-vs-RealAge-Prediction-Dashboard/blob/main/Dashboard.png)

- Total Participants: **19K**
- Avg Chronological Age: **49.49**
- Avg Biological Age: **49.79**
- Max Age Gap: **+27.98** years
- Min Age Gap: **–13.49** years
- Key visuals:
  - **BioAge gap trends by age group**
  - **Diabetes distribution vs Age**
  - **Health status vs BioAge deviation**
  - **Aging category breakdown (Older, Younger, Same)**

---

## 🚀 How to Run

1. Open the Colab notebook:  
   [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/drive/1dg-SusBMRGRZfvmlnS6sI-IHvzhAm057?usp=sharing)

2. Upload the dataset: `cleaned_kdm_bioage_NHANES32.csv`

3. Run all cells to:
   - Preprocess the data
   - Train the models
   - View evaluation metrics
   - Export predictions for Power BI

---

## 🛠 Tech Stack

- Python: `Pandas`, `Scikit-learn`, `XGBoost`, `Matplotlib`
- Power BI for dashboarding
- Google Colab for development

---


