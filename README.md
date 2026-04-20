# 👁️ Smart-ITAM-Analytics

A hybrid IT asset risk analytics system that combines rule-based operational alerts with machine learning-based replacement risk scoring.

This project builds an end-to-end pipeline from raw maintenance logs to predictive decision support, enabling proactive IT asset management.

---

## 📌 Introduction

This project was inspired by my experience in IT asset management during my internship at Dcard, where I managed over 2,000 hardware assets and conducted a full-scale physical re-audit.

Through this experience, I observed that most IT operations are highly reactive — assets are typically replaced only after failures or excessive maintenance costs occur.

To address this gap, this project bridges IT infrastructure and data science by developing a hybrid system that detects immediate risks and predicts future asset replacement needs.

---

## 🎯 Project Objective

The system aims to:

- Identify assets requiring **immediate attention** (rule-based alerts)
- Predict assets likely to incur **high maintenance costs** (ML model)
- Generate a **replacement risk score** to support proactive decision-making

---

## 🏗️ System Architecture
# 👁️ Smart-ITAM-Analytics

A hybrid IT asset risk analytics system that combines rule-based operational alerts with machine learning-based replacement risk scoring.

This project builds an end-to-end pipeline from raw maintenance logs to predictive decision support, enabling proactive IT asset management.

---

## 📌 Introduction

This project was inspired by my experience in IT asset management during my internship at Dcard, where I managed over 2,000 hardware assets and conducted a full-scale physical re-audit.

Through this experience, I observed that most IT operations are highly reactive — assets are typically replaced only after failures or excessive maintenance costs occur.

To address this gap, this project bridges IT infrastructure and data science by developing a hybrid system that detects immediate risks and predicts future asset replacement needs.

---

## 🎯 Project Objective

The system aims to:

- Identify assets requiring **immediate attention** (rule-based alerts)
- Predict assets likely to incur **high maintenance costs** (ML model)
- Generate a **replacement risk score** to support proactive decision-making

---

## 🏗️ System Architecture

Raw Data
↓
Data Cleaning & Preprocessing
↓
Exploratory Data Analysis (EDA)
↓
────────────────────────────
│ │
│ Rule-Based Filter │
│ (Immediate Risk) │
│ │
│ ML Model (XGBoost) │
│ (Future Risk) │
│ │
────────────────────────────
↓
Risk Scoring Engine
↓
High-Risk Asset Output


---

## ⚠️ Rule-Based Risk Detection

To capture urgent operational risks, we implement a rule-based filter:

### 📌 Criteria

- Non-Compliant assets
- Warranty expiring within 90 days

### 📊 Output

- Immediate attention list
- Critical asset monitoring

This approach reflects real-world IT operations, where simple rules are used to detect urgent issues.

---

## 🤖 Machine Learning Model

### 🎯 Target

We formulate the problem as a classification task:
High_Cost = 1 if Maintenance_Cost is in top 25%


This allows us to identify assets likely to become costly rather than predicting exact values.

---

### 📌 Features

- Asset_Age
- Repair_Count
- Warranty_Status
- Asset_Type
- Department

---

### 🧠 Model

- XGBoost Classifier
- Baseline: Logistic Regression

---

### 📈 Evaluation

- Accuracy
- Precision / Recall
- ROC-AUC

---

## ⚙️ Replacement Risk Scoring

To integrate multiple signals, we define a risk scoring system:
Risk Score =
0.4 × High-Cost Probability
0.2 × Normalized Asset Age
0.2 × Normalized Repair Count
0.2 × Warranty Expiry Indicator

---

### 🚦 Risk Levels

| Score Range | Risk Level |
|------------|-----------|
| 0.0 – 0.4  | Low       |
| 0.4 – 0.7  | Medium    |
| 0.7 – 1.0  | High      |

---

## 📋 Key Outputs

The system produces two types of outputs:

### 1️⃣ Immediate Risk Alerts (Rule-Based)
- Assets requiring urgent action
- Near-expiry and non-compliant devices

### 2️⃣ Replacement Risk Ranking (ML-Based)
- High-risk assets prioritized for replacement
- Risk-based asset ranking

---

## 📊 EDA Insights

- Asset age is positively associated with maintenance cost
- Repair count shows a moderate correlation (~0.47) with cost
- Non-compliant assets tend to have higher maintenance costs
- Maintenance patterns vary across departments and asset types

---

## 💼 Business Impact

This system enables IT teams to:

- Shift from **reactive → proactive asset management**
- Reduce unexpected maintenance costs
- Prioritize hardware replacement effectively
- Improve budget allocation and planning

---

## 🛠 Tech Stack

- Python (Pandas, NumPy)
- Scikit-learn
- XGBoost
- Matplotlib / Seaborn
- SQL

---

## 🚀 Future Improvements

- Time-series modeling for failure prediction
- Real-time monitoring integration
- Dashboard (Streamlit / Power BI)
- Cost optimization modeling

---

## 📌 Key Takeaway

This project demonstrates a hybrid approach to IT asset management:

- Rule-based logic captures **immediate operational risks**
- Machine learning predicts **future cost and replacement risk**

Together, they form a practical and scalable decision-support system.