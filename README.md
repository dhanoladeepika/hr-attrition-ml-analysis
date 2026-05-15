HR Employee Attrition — ML Prediction & Power BI Dashboard
An end-to-end people analytics project combining machine learning and business intelligence to predict employee attrition and enable data-driven HR intervention.
🔗 Live Power BI Dashboard

Project Overview
Employee attrition is one of the most costly challenges facing HR teams — replacing a single employee can cost up to 200% of their annual salary. This project addresses the question:

"Can we predict which employees are at risk of leaving, and identify the key drivers of attrition — so HR teams can intervene before it's too late?"

Using the IBM Watson HR Analytics dataset, I built a Random Forest classification model to predict attrition risk for each employee, then surfaced the results in an interactive 3-page Power BI dashboard designed for HR decision-makers.

Key Results
MetricValueDataset size1,470 employees, 35 featuresOverall attrition rate16.1%ModelRandom Forest ClassifierROC-AUC Score0.757High-risk employees identified193Actual leavers captured in high-risk group191 out of 237 (80%)

The model identified 193 high-risk employees — capturing 80% of actual attrition cases — enabling targeted HR intervention on just 13% of the workforce.


Top Attrition Drivers (Feature Importance)
RankFeatureImportance Score1Monthly Income0.07552Age0.07443Total Working Years0.05904Daily Rate0.05675Monthly Rate0.05176Years at Company0.04787Distance from Home0.04638Overtime0.0444
Key business insight: Employees working overtime had a 30.5% attrition rate vs 10.4% for those without — nearly 3x higher risk.

Dashboard Pages
Page 1 — Executive Overview
KPI cards showing total employees, attrition rate, high-risk headcount, and average risk score. Charts showing attrition by department and overtime status, plus a risk band distribution donut chart.
Page 2 — Driver Analysis
Deep-dive into the factors driving attrition — by job role, job satisfaction, tenure band, and monthly income. Sales Representatives (39%) and Laboratory Technicians showed the highest attrition rates by role.
Page 3 — ML Risk Register
Interactive employee-level risk table with ML-generated risk scores and risk bands (Low / Medium / High). Filterable by risk band slicer. Designed for direct HR use — identifies exactly which employees need a retention conversation.

Technical Approach
Machine Learning Pipeline

Data cleaning: Removed zero-variance columns (EmployeeCount, Over18, StandardHours)
Encoding: Label encoding for all categorical variables
Class imbalance handling: class_weight='balanced' in Random Forest to address 16.1% minority class
Model: Random Forest Classifier (100 estimators, random_state=42)
Evaluation: Classification report, confusion matrix, ROC-AUC curve
Output: Per-employee risk scores (0-100) and risk band classification exported to CSV

Power BI Dashboard

Multi-source data model integrating ML outputs with original HR dataset
DAX measures for dynamic attrition rate, high-risk headcount, and average risk score
Conditional formatting on risk score column (white → red gradient)
Interactive slicer filtering across all Page 3 visuals
Published to Power BI Service with public embed link


Tools & Technologies
ToolPurposePython (pandas, scikit-learn, matplotlib, seaborn)Data cleaning, EDA, ML modellingRandom Forest ClassifierAttrition predictionPower BI Desktop & ServiceDashboard development and publishingDAX & Power QueryMeasures and data transformationGoogle ColabDevelopment environmentGitHubVersion control and project documentation

Files in this Repository
FileDescriptionWA_Fn-UseC_-HR-Employee-Attrition.csvOriginal IBM Watson HR datasethr_attrition_powerbi.csvCleaned dataset with ML predictions and risk scoresfeature_importance.csvRandom Forest feature importance scoreseda_plots.pngExploratory data analysis visualisationsmodel_evaluation.pngConfusion matrix and ROC curvefeature_importance.pngTop 15 features driving attrition

Dataset
Source: IBM Watson HR Analytics Employee Attrition & Performance
Available on: Kaggle
Size: 1,470 rows × 35 columns
Target variable: Attrition (Yes/No) — 16.1% positive class

About
Built by Deepika Dhanola — BI & Data Analyst with expertise in Power BI, Python, and ML-integrated analytics.
🔗 LinkedIn | 🔗 Live Dashboard
