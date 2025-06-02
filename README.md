# 📊 NTC - Full Application: Credit Risk Modeling for New-To-Credit (NTC) Customers

This project presents a practical data science workflow focusing on exploratory data analysis (EDA) and predictive modeling to assess credit risk for New-To-Credit (NTC) customers. The goal is to build a model that helps financial institutions estimate the likelihood of charge-offs among individuals with little to no prior credit history.
Additionally, the project outlines an NTC Credit Underwriting Model & Strategy to support risk-based decision-making when approving credit applications from new-to-credit customers.

---

## 🔍 Project Goals

- Understand credit risk metrics and their application to NTC segments.
- Perform thorough Exploratory Data Analysis (EDA).
- Identify and handle outliers and missing data.
- Build a predictive model for `Ever_ChargeOff`.
- Optimize model for precision to support growth-oriented credit strategies.

---

## 🧰 Technologies Used

- Python, Pandas, NumPy, Seaborn, Matplotlib
- Scikit-learn (Random Forest, Decision Tree, XGBoost)
- Google Colab (for code execution)
- CSV-based data ingestion from Google Drive

---

## 🔢 Dataset Overview

The dataset includes anonymized customer credit profiles with:
- Binary target: `Ever_ChargeOff` (0 or 1)
- Continuous target: `ChargeOff_Balance`
- Credit-related features: `FICO`, `No_Hit`, `Income`, `Delinquencies`, etc.

---

## 🔎 Exploratory Data Analysis (EDA)

The EDA process covers:
- Descriptive statistics and data types
- Value counts of categorical and binary features
- Correlation heatmaps with target variables
- Distribution plots (histograms + KDE)
- Outlier detection using the IQR method
- Missing value handling with strategy documentation

---

## 🧼 Data Cleaning & Feature Engineering

- **Outliers:** Removed using 1.5*IQR method per column.
- **Missing Values:** Imputed `FICO` scores with a special value (999) and retained `No_Hit` as context.
- **Data Splits:** Training (70%), Validation (15%), Test (15%).

---

## 🤖 Modeling Approach

We build and evaluate a **Random Forest Classifier** to predict `Ever_ChargeOff`.

### Highlights:
- Features: 26 engineered and cleaned features
- Imbalance handled using `class_weight='balanced'`
- Custom threshold at 0.7 for high-precision decisioning
- Visualization of tree structure and feature importances

### Evaluation Metrics:
| Metric          | Validation | Test     |
|-----------------|------------|----------|
| Precision       | ~0.67      | ~0.53    |
| AUC             | ~0.95      | ~0.94    |
| Strategy Focus  | Prioritize precision over recall |

---

## 📈 Feature Importance

Top contributing features include:
- Income, Delinquencies, Collection_History
- FICO_Imputed (transformed FICO + No_Hit)
- Loan Amount and Term Info

---

## 💡 Business Insight

> With a focus on the NTC population (e.g., young adults), this model helps lenders expand their market while managing risk conservatively. A higher precision threshold ensures fewer false positives, retaining more creditworthy new applicants.

---

## 🔮 Next Steps

- Compare Random Forest with XGBoost for enhanced precision.
