# Smart-ITAM-Analytics
A machine learning-based early warning system for IT asset replacement, featuring an end-to-end data pipeline from raw maintenance logs to predictive risk scoring. Built with Python, XGBoost, and SQL.

# 👁️ Predictive\_ITAM\_Ops
## ☞ Introduction

This is a **personal side project** inspired by my professional experience in IT asset management. [cite_start]During my internship at **Dcard**, I managed a fleet of 2,000+ hardware assets and executed a ground-up physical re-audit[cite: 22, 58]. I realized that most IT departments operate in a reactive mode. This project aims to bridge the gap between **IT Infrastructure** and **Data Science** by building a predictive model that anticipates hardware failures and compliance risks before they happen.

## ☞ Objectives

  - **Proactive Maintenance:** Predicting which laptops or servers are likely to fail or be decommissioned based on historical repair logs and age.
  - **Cost-Efficiency Analysis:** Identifying "money pit" assets by analyzing the correlation between vendor types and maintenance costs.
  - [cite_start]**Risk & Compliance Integration:** Aligning technical metadata with **ISO 27001** standards, flagging assets with outdated OS versions or expired warranties as critical risks[cite: 9, 23, 60].
  - **Data-Driven Procurement:** Generating automated "Replacement Alert Lists" to help IT managers plan budgets more effectively.

## ☞ Project Process

1.  **Problem Definition:** Identifying common bottlenecks in IT asset lifecycles.
2.  **Raw Data Generation:** Simulating 500+ raw records with "dirty" characteristics (inconsistent dates, missing values) to test data engineering skills.
3.  **ETL & Data Cleaning:** Building a robust pipeline to standardize dates, handle nulls, and remove outliers (e.g., impossible repair counts).
4.  **Feature Engineering:** Creating high-impact features like `Warranty_Gap`, `Repair_Frequency`, and `Asset_Age`.
5.  **Predictive Modeling:** Implementing **XGBoost/Random Forest** classifiers to score asset failure probabilities.
6.  **Insight Visualization:** Outputting a prioritized replacement list for proactive decision-making.

## ☞ Data Overview

| Column Name         | Description                                                |
|---------------------|------------------------------------------------------------|
| `Asset_ID`          | Unique hardware identifier (A001-A500). |
| `Asset_Type`        | Category including Laptop, Server, Software, and **Other** for edge cases. |
| `Department`        | Dept assigned to the asset (IT, HR, Marketing, R\&D, etc.). |
| `Acquisition_Date`  | **Raw Date**, includes mixed formats (YYYY-MM-DD vs DD/MM/YYYY). |
| `Warranty_Expiry`   | Critical date for manufacturer support eligibility. |
| `Maintenance_Cost`  | Cumulative repair spending; contains missing values to simulate lost records. |
| `Repair_Count`      | Number of support tickets associated with the asset. |
| `OS_Version`        | [cite_start]Operating system state, essential for **ISO 27001** compliance[cite: 23, 60]. |
| `Compliance_Status` | Target indicator for security posture (Compliant, At Risk, Non-Compliant). |

## ☞ Summary & Key Insights

| **Discovery Category** | **Insight** |
|---------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Usage Impact** | **R\&D assets** show a 25% higher failure rate compared to Finance, likely due to high-intensity hardware stress. |
| **Vendor Analysis** | **Apple** devices maintain compliant status longer but face steep maintenance cost spikes after Year 3. |
| **Compliance Risk** | **Expired Warranties** combined with **Outdated OS** versions are the strongest predictors for an asset being "Retired" within 6 months. |

## ☞ Implementation Details

For the full Python implementation, data cleaning logic, and model evaluation, please see: