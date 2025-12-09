# week-3
End-to-End Insurance Risk Analytics &amp; Predictive Modeling
This week’s project focuses on end-to-end car insurance risk analytics and premium optimization for AlphaCare Insurance Solutions (ACIS). Using historical insurance data, the goal is to explore risk patterns, validate business-critical hypotheses, and build predictive models that help identify low-risk customer segments. The project includes data exploration, statistical analysis, hypothesis testing, data version control (DVC), and machine learning modeling to support data-driven decisions for pricing and marketing strategy.

Task 1 — Exploratory Data Analysis (EDA)

In Task 1, we performed a detailed exploratory data analysis on the insurance dataset to understand patterns, distributions, and potential issues in the data. Key steps included:

Loss Ratio Analysis: Computed policy-level and aggregate-level loss ratios, and compared across provinces and gender.

Claim Frequency & Severity: Calculated monthly claim frequency and average claim severity for claims > 0.

Outlier Detection: Identified extreme claims using IQR and z-score methods; created a separate table for the top 1% of claim amounts.

Trends & Correlations: Examined temporal trends with rolling averages, checked correlations among numeric fields, and assessed differences across provinces and genders using t-tests, ANOVA, and non-parametric tests.

Vehicle Analysis: Aggregated total claims and average claim amounts by vehicle make and model.

Data Quality Checks: Evaluated missingness, duplicates, and other anomalies.

Deliverables:

Cleaned and processed dataset

Visualizations (loss ratio, claim distributions, temporal trends)

Tables and insights highlighting key patterns and recommendations

Task 2 — Data Version Control (DVC Setup)

In Task 2, we implemented a reproducible data management workflow using DVC (Data Version Control):

DVC Initialization: Initialized DVC in the project repository.

Tracking Raw Data: Added raw datasets (e.g., MachineLearningRating_v3.txt) to DVC instead of Git, enabling versioning without exceeding GitHub size limits.

Local DVC Remote Configuration: Configured local storage for DVC-tracked files.

Reproducibility: Documented steps to reproduce the data setup, allowing anyone to clone the repo, pull the latest data via DVC, and run the analysis notebooks.

Deliverables:

task-2 branch with DVC-tracked datasets

Updated README documenting reproducible setup

Clean separation of large data files from Git history

## Reproducibility with DVC

1. Install DVC: `pip install dvc`
2. Pull dataset: `dvc pull`
3. Run notebooks in `notebooks/`


Task 3 — A/B Hypothesis Testing

Objective:
Validate business hypotheses related to risk and profitability using statistical tests. The goal is to identify meaningful differences across provinces, postal codes, and genders, and provide actionable insights for ACIS.

Hypotheses Tested:

H₀₁: No risk difference across provinces

H₀₂: No risk difference between postal codes

H₀₃: No margin (profit) difference between postal codes

H₀₄: No risk difference between male and female policyholders

Metrics Used:

Claim Frequency: Proportion of policies with ≥1 claim

Claim Severity: Average claim amount for policies with claims

Margin: Total premium minus total claims

Statistical Tests Applied:

Two-proportion Z-test (for claim frequency)

t-test / ANOVA (for claim severity and margin)

Diagnostic checks: Shapiro-Wilk test, Levene test

Outputs:

Computed KPIs for each group

Hypothesis test results with p-values and decisions

Programmatic summary table for all hypotheses

Visualizations: bar plots, box plots, and violin plots for each group

All figures saved in week-3/outputs

Business Insights:

Significant differences in claim frequency observed between certain provinces (e.g., Gauteng vs Western Cape)

No significant differences in claim frequency, severity, or margin observed between postal codes or genders

Provides guidance on potential premium adjustments or underwriting criteria

Usage:
Open the notebook notebooks/task_3_ab_tests.ipynb and run all cells to reproduce the analysis, summary table, and visualizations.

Task 4 — Predictive Modeling

This task focuses on building and evaluating machine-learning models to predict insurance claim severity and support data-driven premium optimization.

🔍 Objectives

Train multiple regression models on the processed dataset.

Evaluate model performance using RMSE, MAE, and R².

Identify key drivers of claim severity using SHAP interpretability.

Generate advanced premium optimization outputs.

🧠 Models Trained

Linear Regression

Decision Tree Regressor

Random Forest Regressor

XGBoost Regressor

Random Forest achieved the best performance with an R² above 0.99, showing excellent predictive power.

📊 Model Evaluation

Each model was evaluated using:

RMSE (Root Mean Squared Error)

MAE (Mean Absolute Error)

R² Score

Results were consolidated into a comparison table to identify the best-performing model.

🔍 Model Interpretability

SHAP (SHapley Additive Explanations) was used to understand feature impact.
Top features influencing predictions included:

SumInsured

TotalPremium

PostalCode

UnderwrittenCoverID

cubiccapacity

💡 Premium Optimization

Using predicted:

Claim probability

Claim severity

A technical premium and a final quoted premium were calculated to demonstrate how ML outputs support underwriting decisions.