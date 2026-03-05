# loan_default_risk_analysis_EDA_Python_ML_Power-bi
# Loan Default Risk Analysis – Banking Credit Risk Management
Predicting loan defaults and identifying risk drivers to optimize lending decisions and reduce financial losses using **Python, Machine Learning, and Power BI**.

---

## 📌 Table of Contents
- Overview
- Business Problem
- Dataset
- Tools & Technologies
- Project Structure
- Data Cleaning & Preparation
- Exploratory Data Analysis (EDA)
- Research Questions & Key Findings
- Machine Learning Model
- Dashboard
- How to Run This Project
- Final Business Recommendations
- Author & Contact

---

# 📊 Overview

This project analyzes **148,670 bank loans** to identify default risk patterns and build predictive models for automated credit decisioning.

Using **exploratory data analysis and machine learning**, the project provides actionable strategies to reduce the bank's **24.6% default rate** and avoid **$2+ billion in annual losses**.

### Key Deliverables
- Identified **5 primary default risk drivers** (income, loan type, pre-approval, region, combinations)
- Built **Random Forest model with 91.6% accuracy**
- Created **Power BI dashboard for portfolio monitoring**
- Delivered **8 prioritized recommendations with quantified ROI**

---

# 💼 Business Problem

Banks face significant credit risk when borrowers fail to repay loans.

### Key Challenges

- High default rate (**24.6% vs 12–15% industry benchmark**)
- **$12.1 billion** in at-risk capital
- Lack of data-driven insights for predicting defaults
- Inconsistent underwriting across regions
- Underutilization of risk mitigation strategies

### Project Objectives

- Identify patterns associated with loan defaults
- Evaluate loan approval processes
- Segment customers by risk
- Build predictive ML model
- Provide actionable recommendations

---

# 📁 Dataset

**Source:** Historical bank loan records  
**Size:** 148,670 loans  
**Features:** 34 variables

### Borrower Information
- `income` – Monthly earnings  
- `Credit_Score` – FICO score (300–850)  
- `age` – Age bracket  
- `Region` – Geographic market  

### Loan Details
- `loan_amount` – Principal borrowed  
- `loan_type` – Product type  
- `rate_of_interest` – APR  
- `term` – Loan duration  

### Risk Metrics
- `LTV` – Loan-to-value ratio  
- `dtir1` – Debt-to-income ratio  
- `approv_in_adv` – Pre-approval flag  

### Target Variable
- `Status`
  - **0 = Repaid**
  - **1 = Default**

### Data Quality Issues
- 25% missing interest rates
- 16% missing DTIR
- 10% missing property values

Solution: **Group-based imputation + outlier removal**

---

# 🛠 Tools & Technologies

- Python (Pandas, NumPy, Matplotlib, Seaborn)
- Machine Learning (Scikit-learn)
- Statistical Analysis (SciPy)
- Power BI
- Jupyter Notebook
- Git & GitHub

---

# 📂 Project Structure
loan-default-risk-analysis/
│
├── README.md
├── .gitignore
├── requirements.txt
├── Loan_Default_Analysis_Report.pdf
│
├── notebooks/
│ ├── data_cleaning.ipynb
│ ├── eda_analysis.ipynb
│ └── ml_model.ipynb
│
├── data/
│ ├── Loan_Default.csv
│ └── Loan_Default_CLEANED.csv
│
├── models/
│ ├── random_forest_model.pkl
│ └── label_encoders.pkl
│
├── images/
│ ├── income_default_chart.png
│ ├── loan_type_analysis.png
│ └── regional_risk_heatmap.png
│
└── dashboard/
└── loan_default_dashboard.pbix

---

# 🧹 Data Cleaning & Preparation

### Missing Values
Filled using **group-based medians by loan type**.

### Outlier Removal

Removed **20,325 records (13.7%)** with impossible values:

- Negative income
- Credit score below 300
- LTV greater than 300%

### Feature Engineering

- Created **17 derived features**
- Risk categories
- Income brackets
- Customer segments

Final Dataset: **128,345 clean records**

---

# 🔍 Exploratory Data Analysis (EDA)

### Default Distribution

| Status | Percentage |
|------|-----------|
| Repaid | 81.5% |
| Default | 18.5% |

### Key Risk Patterns

| Risk Factor | Default Rate | Impact |
|-------------|-------------|-------|
| Low Income (<$3K) | 36% | 16pp increase |
| Type2 Loans | 30.5% vs 16.6% | 13.9pp increase |
| No Pre-Approval | 20.3% vs 16.0% | 4.3pp increase |
| North-East Region | 23.5% vs 16.6% | 6.9pp increase |

### Multivariate Insights

- Worst combination: **Central + Type2 = 41% default**
- Best combination: **North + Type1 = 21% default**
- Risk factors **multiply rather than add**

---

# ❓ Research Questions & Key Findings

### 1️⃣ What is the current default rate?
**Finding:** 18.5% after cleaning  
Estimated **$7.16B at risk**

---

### 2️⃣ Does borrower income affect defaults?
Low-income borrowers default at **36% vs 20% high-income**

**Recommendation:** Minimum income requirement = **$5,000**

---

### 3️⃣ Does loan type influence defaults?
Type2 loans default **30.5%**

**Recommendation:** Reprice Type2 by **+4%**

---

### 4️⃣ Does pre-approval reduce defaults?
Yes — reduces default by **4.3 percentage points**

Potential savings: **$575M annually**

---

### 5️⃣ Do defaults vary by region?
Regional spread: **6.9 percentage points**

Solution: **regional pricing strategy**

---

### Top Risk Drivers

1. Monthly Income
2. Loan Type
3. Pre-Approval Process
4. Geographic Region
5. Multi-factor risk combinations

---

# 🤖 Machine Learning Model

### Objective
Predict **loan default probability**.

### Models Tested

- Logistic Regression
- Random Forest (final model)

### Training Setup

- 80/20 train-test split
- 14 features
- Class imbalance handling

### Model Performance

| Metric | Score |
|------|------|
| Accuracy | 91.6% |
| Precision | 78.1% |
| Recall | 76.2% |
| ROC-AUC | 0.97 |

### Top Predictive Features

1. DTIR (Debt burden)
2. Credit Score
3. LTV Ratio
4. Income
5. Loan Type

---

# 📊 Dashboard

Power BI dashboard includes:

### Portfolio Overview
- Total loans
- Default rate
- Regional distribution

### Risk Analysis
- Risk factor KPIs
- Pre-approval effectiveness
- LTV risk profile

### Customer Segmentation
- 4-tier risk segmentation
- Default rates by segment
- Risk-return matrix

---

# 🚀 How to Run This Project

### 1️⃣ Clone Repository
git clone https://github.com/yourusername/loan-default-risk-analysis.git

cd loan-default-risk-analysis


### 2️⃣ Install Dependencies


pip install -r requirements.txt


### 3️⃣ Run Notebooks


jupyter notebook notebooks/data_cleaning.ipynb
jupyter notebook notebooks/eda_analysis.ipynb
jupyter notebook notebooks/ml_model.ipynb


### 4️⃣ Open Dashboard


dashboard/loan_default_dashboard.pbix


---

# 💡 Final Business Recommendations

### Immediate Actions

1️⃣ Minimum income requirement **$5,000**

2️⃣ Suspend Type2 loans temporarily

---

### Short-Term Actions

3️⃣ Expand pre-approval program  
Savings: **$575M annually**

4️⃣ Implement regional pricing

---

### Medium-Term Actions

5️⃣ Deploy ML risk scoring system

6️⃣ Customer segmentation strategy

---

### Long-Term Actions

7️⃣ Expand lending in North region

8️⃣ Continuous ML model improvement

---

### Expected Business Impact

| Metric | Current | Target |
|------|------|------|
| Default Rate | 18.5% | 13–14% |
| Capital at Risk | $7.16B | $5B |
| Processing Time | 2–3 days | 30 sec |

---

# 👤 Author & Contact

**Sneha Dandi**

Data Analyst | Credit Risk Analytics | Machine Learning

📧 Email: snehadandi20@gmail.com

🔗 LinkedIn:https://www.linkedin.com/in/sneha-dandi-829257377/

💻 GitHub: https://github.com/sneha-dandi

---

⭐ If you found this project useful, consider giving it a star!


