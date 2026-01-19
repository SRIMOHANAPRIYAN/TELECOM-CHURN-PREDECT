# Customer Retention & Churn Risk Dashboard (End-to-End)

# Playable Dashboard Link 👉  [Dashboard Preview](https://lookerstudio.google.com/reporting/947fa59c-9d6a-4c3b-82e3-5e21721b6783)

# Project Overview
**Goal:** In the telecom industry, retaining customers is cheaper than acquiring new ones. This project builds a Machine Learning solution to predict which customers are at risk of leaving ("Churn") and identifies the root causes to minimize revenue loss.

**Business Impact:**
* Identified **$200k+ in monthly recurring revenue (MRR)** at risk.
* Built an interactive dashboard for the Retention Team to prioritize calls, improving intervention efficiency.
* Discovered that **Month-to-Month contracts** with **Electronic Check** payments are the #1 driver of churn.

# Tech Stack
* **Python (Back-end):** Pandas, NumPy for data manipulation.
* **Machine Learning:** XGBoost (optimized with SMOTE for class imbalance) achieving **80%+ Recall**.
* **Explainable AI:** SHAP values to explain *why* a specific customer is at risk.
* **Visualization:** Google Looker Studio for the executive dashboard.

# The Dashboard
The dashboard is designed for two stakeholders:
1.  **Executives:** To monitor high-level KPIs (Total Revenue at Risk).
2.  **Support Agents:** To download "High Priority" call lists based on risk probability.

### Key Features:
* **Risk Scorecard:** Quantifies the exact dollar amount at risk.
* **Interactive Filtering:** Click on "High Risk" to filter the customer list instantly.
* **Heatmap Analytics:** Visualizes churn probability for rapid decision-making.
