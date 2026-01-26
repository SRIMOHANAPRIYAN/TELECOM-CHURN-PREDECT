# Customer Retention & Churn Risk Dashboard (End-to-End)

# Playable Dashboard Link 👉  [Dashboard Preview](https://lookerstudio.google.com/reporting/947fa59c-9d6a-4c3b-82e3-5e21721b6783)

---
## 📖 Project Overview
Customer Churn (loss of customers) is a multi-billion-dollar problem in the Telecom industry. Acquiring a new customer costs **5-25x more** than retaining an existing one.

This project goes beyond simple prediction. It is an **End-to-End Retention System** that:
1.  **Predicts:** Identifies which customers are likely to leave using **XGBoost**.
2.  **Explains:** Uses **SHAP (Explainable AI)** to tell us *why* they are leaving (e.g., "Monthly charges too high").
3.  **Acts:** Uses **Google Gemini (GenAI)** to automatically draft a personalized retention email with specific offers to save the customer.

---

### Key Features:
* **Risk Scorecard:** Quantifies the exact dollar amount at risk.
* **Interactive Filtering:** Click on "High Risk" to filter the customer list instantly.
* **Heatmap Analytics:** Visualizes churn probability for rapid decision-making.

---

## ⚙️ Technical Architecture

The application follows a "Predict-Explain-Act" workflow:
1.  **Data Processing:** Pipelines to handle categorical data (One-Hot Encoding) and numerical scaling.
2.  **Predictive Model (The Brain):** An **XGBoost Classifier** trained on historical telecom data to calculate a "Churn Probability Score."
3.  **Explainability Layer (The Interpreter):** Integrated **SHAP (Shapley Additive Explanations)** to extract the top 3 contributing factors for *each individual prediction*.
4.  **Generative Layer (The Strategist):** A **LangChain** pipeline that feeds customer data + SHAP insights into **Google Gemini Pro**, generating a hyper-personalized email.
5.  **Deployment:** Containerized via Docker and hosted on **Google Cloud Run**.

---

## 🧠 Model & AI Details

### 1. The Predictive Model (XGBoost)
* **Algorithm:** Extreme Gradient Boosting (XGBoost).
* **Why XGBoost?** Chosen for its superior performance on tabular data and ability to handle missing values and non-linear relationships better than Random Forest or Logistic Regression.
* **Key Features:** `Tenure`, `Contract Type` (Month-to-month vs. Two year), `Monthly Charges`, `Internet Service Type`.
* **Handling Imbalance:** Applied **SMOTE (Synthetic Minority Over-sampling Technique)** during training to ensure the model doesn't just predict "No Churn" for everyone.

### 2. Explainable AI (SHAP)
Black-box models are dangerous in business. I used SHAP values to visualize local feature importance.
* *Example:* If the model predicts "80% Churn Risk," SHAP tells us: "Reason: Monthly Charges > $90" and "Reason: Fiber Optic Internet."

### 3. Generative AI Integration (Gemini Pro)
* **Role:** Automated Retention Specialist.
* **Prompt Engineering:** The system dynamically constructs a prompt:
  > *"You are a retention manager. A customer with [Tenure] years and [Contract Type] is at risk because [SHAP Factor 1] and [SHAP Factor 2]. Write a polite email offering a discount to fix [Main Pain Point]."*

---

**Business Impact:**
* Identified **$200k+ in monthly recurring revenue (MRR)** at risk.
* Built an interactive dashboard for the Retention Team to prioritize calls, improving intervention efficiency.
* Discovered that **Month-to-Month contracts** with **Electronic Check** payments are the #1 driver of churn.

---

# The Dashboard
The dashboard is designed for two stakeholders:
1.  **Executives:** To monitor high-level KPIs (Total Revenue at Risk).
2.  **Support Agents:** To download "High Priority" call lists based on risk probability.

---

## 🛠️ Tech Stack

| Component | Technology Used |
| :--- | :--- |
| **Machine Learning** | XGBoost, Scikit-Learn |
| **Explainable AI** | SHAP (Shapley Values) |
| **Generative AI** | Google Gemini Pro API, LangChain |
| **Data Processing** | Pandas, NumPy, Pickle |
| **Web Frontend** | Streamlit |
| **Deployment** | Docker, Google Cloud Run |

---
