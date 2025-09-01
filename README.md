# Tata_ML-Predict-Delinquency-Risk

<details>

<details>

Prompts to try:

Summarize key patterns, outliers, and missing values in this dataset. Highlight any fields that might present problems for modeling delinquency.
Identify the top 3 variables most likely to predict delinquency based on this dataset. Provide brief reasoning.
Action: 

Document your findings in bullet points for your report. Focus on:

Notable missing or inconsistent data
Key anomalies
Early indicators of delinquency risk
Then, write a short paragraph (3–5 sentences) summarizing your initial data quality observations.
   
</details>

### 🔍 Data Quality & Pattern Summary

---

#### 📌 **Missing Values & Inconsistencies**
- **Income**: Missing in several rows (e.g., CUST0041, CUST0060, CUST0067, CUST0094, etc.)
- **Loan_Balance**: Missing in some records (e.g., CUST0009, CUST0024, CUST0026, etc.)
- **Credit_Score**: No missing values observed.
- **Employment_Status**: Inconsistent capitalization (e.g., “EMP”, “employed”, “Employed”, “Self-employed”, etc.)
- **Credit_Card_Type**: Values like “Student”, “Standard”, “Platinum”, “Gold”, “Business” — all valid but categorical.

---

#### 📊 **Key Anomalies & Outliers**
- **Credit_Utilization**: Some values exceed 1.0 (e.g., CUST0090: 1.026, CUST0266: 1.025) — may indicate data error or extreme debt.
- **Debt_to_Income_Ratio**: Several values are exactly 0.1 (e.g., CUST0035, CUST0115, CUST0121, etc.) — may be placeholder or imputed value.
- **Age**: Some very young customers (e.g., 18–20) with high income or high credit scores — may warrant verification.

---

#### ⚠️ **Early Indicators of Delinquency Risk**
- **Missed_Payments**: High correlation with `Delinquent_Account = 1`.
- **Credit_Utilization**: Higher values often associated with missed payments.
- **Payment History (Month_1 to Month_6)**: Patterns like repeated “Late” or “Missed” payments are strong predictors.
- **Employment_Status**: “Unemployed” or “Self-employed” show higher delinquency rates.
- **Credit_Score**: Lower scores correlate with higher risk.

---

### 🎯 **Top 3 Predictive Variables for Delinquency**

1. **Missed_Payments**  
   - Directly reflects past behavior; strong correlation with delinquency.

2. **Credit_Utilization**  
   - High utilization often precedes financial stress and missed payments.

3. **Payment History (e.g., Month_6 status)**  
   - Recent behavior is a strong indicator of future delinquency.

---

### 📄 **Summary Paragraph**

The dataset contains several missing values in `Income` and `Loan_Balance`, which may require imputation or exclusion. Inconsistencies in `Employment_Status` capitalization should be standardized. Anomalies like `Credit_Utilization` values above 1.0 and repeated `Debt_to_Income_Ratio` values of 0.1 suggest possible data entry errors or imputation. Key predictors like `Missed_Payments`, `Credit_Utilization`, and recent payment history show strong potential for forecasting delinquency. Overall, the data is moderately clean but requires preprocessing for reliable modeling.
  
</details>
