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
