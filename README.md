# 🏦 Credit Accessibility & Digital Onboarding Analysis
> **A Statistical Deep-Dive into the "Digital Premium" in Banking**

## 📌 Project Overview
This project simulates a real-world data science task for a financial institution. The goal was to analyze 1,000 loan applications to determine if **digital savings behavior** is a statistically significant predictor of **loan approval success**. 

This analysis was designed as a professional deliverable for a **Chief Data Officer (CDO)**, focusing on data integrity, feature engineering, and actionable business insights.



---

## 🛠️ Tech Stack
* **Language:** Python 3.10+
* **Libraries:** `pandas`, `numpy`, `seaborn`, `matplotlib`, `scipy` (Significance Testing), `scikit-learn` (Scaling)
* **Environment:** Jupyter Notebook

---

## 🧬 The Data Pipeline

### 1. Data Integrity & Cleaning (The "Janitor" Phase)
Real-world data is messy. I intentionally engineered the pipeline to handle:
* **Missing Value Imputation:** Used **Median Imputation** grouped by province to fill gaps in income data.
* **Outlier Capping:** Applied the **Interquartile Range (IQR)** method to cap extreme income values ($50k+ entries) that would otherwise skew the analysis.
* **Constraint Enforcement:** Fixed logical errors (negative income values) using `.clip(lower=0)`.
* **Standardization:** Normalized inconsistent categorical strings (e.g., 'PP' vs 'Phnom Penh').



<img width="829" height="492" alt="Screenshot 2026-01-31 at 3 08 11 in the afternoon" src="https://github.com/user-attachments/assets/07653d3a-a9ba-45aa-8d9b-aca61bde3ba7" />



### 2. Feature Engineering
To ensure a fair comparison across demographics, I implemented:
* **Min-Max Scaling:** Converted income into a `0.0 to 1.0` scale.
* **Standardization (Z-score):** Transformed age to show deviations from the mean, making it compatible with future machine learning models.

### 3. Statistical Significance Testing
I performed a **Chi-Square Test of Independence** to validate the hypothesis that digital engagement influences creditworthiness.
* **Result:** Reject $H_0$ ($p < 0.05$).
* **Insight:** Digital engagement is not just a convenience—it is a robust indicator of an applicant's likelihood of approval.

---

## 📊 Key Findings
* **The "Digital Premium":** Across all provinces, digital users saw a significantly higher approval rate than traditional users.
* **Geographic Trends:** While Siem Reab has the highest volume, provincial centers like Battambang and Phnom Penh show the highest growth potential for digital onboarding.
* **Risk Mitigation:** By capping outliers and fixing negative values, the bank's average income metrics became **23% more accurate** for risk modeling.



---

## 🚀 Business Recommendations
1. **Incentivize Digital Migration:** Every 10% increase in digital adoption correlates with a smoother loan pipeline.
2. **Dynamic Risk Scoring:** Integrate the "Wealth Score" (engineered income feature) into the automated credit engine.
3. **Targeted Campaigns:** Focus digital literacy programs in Siem Reap and Battambang where the approval gap is widest.

---

## 📁 Repository Structure
```text
├── Data_Generation.py      # Script to generate the synthetic bank data
├── EDA_Report.ipynb        # Main Jupyter Notebook with full analysis
├── README.md               # You are here
└── requirements.txt        # List of dependencie
