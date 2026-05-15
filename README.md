# HR Employee Attrition — ML Prediction & Power BI Dashboard

**An end-to-end people analytics project combining machine learning and business intelligence to predict employee attrition and enable data-driven HR intervention.**

🔗 [Live Power BI Dashboard](https://app.powerbi.com/view?r=eyJrIjoiOWZhMjY4OGQtMTFlNC00ZGRmLThkOTYtYzZjNGZmZTFiMzZlIiwidCI6IjM5MjIwMTU5LTFhOGQtNDExMC1iOGI4LWMzODk1MjQzODlhYSJ9)

---

## Project Overview

Employee attrition is one of the most costly challenges facing HR teams — replacing a single employee can cost up to 200% of their annual salary. This project addresses the question:

> *"Can we predict which employees are at risk of leaving, and identify the key drivers of attrition — so HR teams can intervene before it's too late?"*

Using the IBM Watson HR Analytics dataset, I built a Random Forest classification model to predict attrition risk for each employee, then surfaced the results in an interactive 3-page Power BI dashboard designed for HR decision-makers.

---

## Key Results

| Metric | Value |
|--------|-------|
| Dataset size | 1,470 employees, 35 features |
| Overall attrition rate | 16.1% |
| Model | Random Forest Classifier |
| ROC-AUC Score | 0.757 |
| High-risk employees identified | 193 |
| Actual leavers captured in high-risk group | 191 out of 237 (80%) |

> The model identified 193 high-risk employees — capturing 80% of actual attrition cases — enabling targeted HR intervention on just 13% of the workforce.

---

## Top Attrition Drivers (Feature Importance)

| Rank | Feature | Importance Score |
|------|---------|-----------------|
| 1 | Monthly Income | 0.0755 |
| 2 | Age | 0.0744 |
| 3 | Total Working Years | 0.0590 |
| 4 | Daily Rate | 0.0567 |
| 5 | Monthly Rate | 0.0517 |
| 6 | Years at Company | 0.0478 |
| 7 | Distance from Home | 0.0463 |
| 8 | Overtime | 0.0444 |

**Key business insight:** Employees working overtime had a 30.5% attrition rate vs 10.4% for those without — nearly 3x higher risk.

---

## Dashboard Pages

### Page 1 — Executive Overview
KPI cards showing total employees, attrition rate, high-risk headcount, and average risk score. Charts showing attrition by department and overtime status, plus a risk band distribution donut chart.

### Page 2 — Driver Analysis
Deep-dive into the factors driving attrition — by job role, job satisfaction, tenure band, and monthly income. Sales Representatives (39%) and Laboratory Technicians showed the highest attrition rates by role.

### Page 3 — ML Risk Register
Interactive employee-level risk table with ML-generated risk scores and risk bands (Low / Medium / High). Filterable by risk band slicer. Designed for direct HR use — identifies exactly which employees need a retention conversation.

---

## Technical Approach

### Machine Learning Pipeline
- **Data cleaning:** Removed zero-variance columns (`EmployeeCount`, `Over18`, `StandardHours`)
- **Encoding:** Label encoding for all categorical variables
- **Class imbalance handling:** `class_weight='balanced'` in Random Forest to address 16.1% minority class
- **Model:** Random Forest Classifier (100 estimators, random_state=42)
- **Evaluation:** Classification report, confusion matrix, ROC-AUC curve
- **Output:** Per-employee risk scores (0-100) and risk band classification exported to CSV

### Power BI Dashboard
- Multi-source data model integrating ML outputs with original HR dataset
- DAX measures for dynamic attrition rate, high-risk headcount, and average risk score
- Conditional formatting on risk score column (white → red gradient)
- Interactive slicer filtering across all Page 3 visuals
- Published to Power BI Service with public embed link

---

## Tools & Technologies

| Tool | Purpose |
|------|---------|
| Python (pandas, scikit-learn, matplotlib, seaborn) | Data cleaning, EDA, ML modelling |
| Random Forest Classifier | Attrition prediction |
| Power BI Desktop & Service | Dashboard development and publishing |
| DAX & Power Query | Measures and data transformation |
| Google Colab | Development environment |
| GitHub | Version control and project documentation |

---

## Files in this Repository

| File | Description |
|------|-------------|
| `WA_Fn-UseC_-HR-Employee-Attrition.csv` | Original IBM Watson HR dataset |
| `hr_attrition_powerbi.csv` | Cleaned dataset with ML predictions and risk scores |
| `feature_importance.csv` | Random Forest feature importance scores |
| `eda_plots.png` | Exploratory data analysis visualisations |
| `model_evaluation.png` | Confusion matrix and ROC curve |
| `feature_importance.png` | Top 15 features driving attrition |

---

## Dataset

**Source:** IBM Watson HR Analytics Employee Attrition & Performance  
**Available on:** [Kaggle](https://www.kaggle.com/datasets/pavansubhasht/ibm-hr-analytics-attrition-dataset)  
**Size:** 1,470 rows × 35 columns  
**Target variable:** Attrition (Yes/No) — 16.1% positive class

---

## About

Built by **Deepika Dhanola** — BI & Data Analyst with expertise in Power BI, Python, and ML-integrated analytics.

🔗 [LinkedIn](https://www.linkedin.com/in/deepika-dhanola) | 🔗 [Live Dashboard](https://app.powerbi.com/view?r=eyJrIjoiOWZhMjY4OGQtMTFlNC00ZGRmLThkOTYtYzZjNGZmZTFiMzZlIiwidCI6IjM5MjIwMTU5LTFhOGQtNDExMC1iOGI4LWMzODk1MjQzODlhYSJ9)
