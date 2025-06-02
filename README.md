# 📊 NTC - Full Application: Credit Risk Modeling for New-To-Credit (NTC) Customers

This project presents a full-stack data science workflow to analyze, clean, and model credit risk for New-To-Credit (NTC) customers. The objective is to build a predictive model that helps financial institutions assess the likelihood of charge-offs among individuals with little to no prior credit history.

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
- Scikit-learn (Random Forest, Decision Tree)
- Google Colab (for code execution)
- CSV-based data ingestion from Google Drive

---

## 📁 Project Structure

NTC_Full_Application/
│
├── eda_ntc_credit.py # Full EDA and preprocessing script
├── modeling_rf.py # Model training and evaluation
├── data/
│ └── v_credit_data_NTC_v51825.csv
├── figures/
│ └── *.png # Saved plots (optional)
├── README.md # This file


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
| Precision       | ~0.53      | ~0.53    |
| AUC             | ~0.76      | ~0.76    |
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
- Add SHAP values for better model explainability.
- Extend pipeline for real-time scoring or API deployment.
- Integrate reject inference if available.

---

## 📜 License

This project is intended for educational and internal use. Please contact the repository owner for any commercial applications.

---

## 🙋‍♂️ Author

**Chau**  
_Data Science & Credit Risk Analyst_

---

## 📬 Contact

Feel free to reach out via [LinkedIn](https://www.linkedin.com) or open an issue in the repo.
