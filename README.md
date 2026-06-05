Task 5 — Exploratory Data Analysis (EDA) on Titanic Dataset
Data Analyst Internship — Elevate Labs

📌 Objective
Extract meaningful insights from the Titanic dataset using visual and statistical exploration techniques — covering univariate, bivariate, and multivariate analysis.

🛠️ Tools & Libraries
ToolPurposePython 3Core languagePandasData loading, cleaning, aggregationNumPyNumerical operations & log transformsMatplotlibBase plottingSeabornStatistical visualizations (heatmap, pairplot, boxplot)Jupyter NotebookInteractive analysis environment

📁 Repository Structure
task-5-titanic-eda/
│
├── Titanic_EDA.ipynb          # Main Jupyter Notebook with all code + observations
├── Titanic_EDA_Report.docx    # PDF-ready findings report
│
├── train.csv                  # Training dataset (891 rows × 12 columns)
├── test.csv                   # Test dataset
├── gender_submission.csv      # Sample submission file
│
└── README.md                  # This file

📊 What Was Done
1. Dataset Overview

Loaded train.csv (891 rows, 12 columns) using pd.read_csv()
Explored column types and descriptions using .info() and .describe()

2. Missing Value Analysis

Identified 3 columns with missing data using .isnull().sum()
Cabin: 77.1% missing → too sparse to use directly
Age: 19.87% missing → recommended median/group imputation
Embarked: 0.22% missing → filled with mode ('S')

3. Univariate Analysis

Plotted survival distribution (count + pie chart) — 38.4% survived
.value_counts() on categorical features: Pclass, Sex, Embarked
Histograms for numeric features: Age, Fare, SibSp, Parch

4. Bivariate Analysis

Survival rate grouped by Pclass, Sex, Embarked (bar charts)
Boxplots of Age & Fare by Survival status
Scatterplot of Age vs Fare coloured by Survival

5. Multivariate Analysis

Correlation heatmap (lower-triangle, sns.heatmap)
Pairplot with KDE diagonals, hued by Survived (sns.pairplot)
Pivot heatmap: Survival Rate by Pclass × Sex

6. Skewness & Outlier Detection

Computed skewness for all numeric features
Demonstrated log1p transform on Fare (skew: 4.79 → near-normal)
Boxplots for outlier detection on Age, Fare, SibSp, Parch

7. Feature Engineering

Created FamilySize = SibSp + Parch + 1
Created IsAlone = (FamilySize == 1)
Plotted survival rates by FamilySize and IsAlone


🔑 Key Findings
#FindingMetric1Overall survival rate is low38.4% survived2Gender is the strongest predictorFemale: 74% vs Male: 19%3Passenger class is critical1st: 63% vs 3rd: 24%4Fare positively correlates with survivalCorrelation = +0.265Children were prioritisedAges 0–12: 59.4% survival6Travelling with family improves survivalSolo: 30% vs Family: 51%7Cabin data is too sparse to use directly77% missing8Fare is heavily right-skewedSkew = 4.79 → use log1p9Embarkation port has a notable effectCherbourg: ~55% vs Southampton: ~34%101st class females had near-perfect survival96.8% survival rate

💡 Interview Q&A (Quick Reference)
Q1. What is EDA and why is it important?
EDA is the process of analysing datasets to summarise their main characteristics — often visually — before formal modelling. It uncovers data quality issues, distributions, relationships, and hypotheses. Without it, models are built on poorly understood data.
Q2. Which plots do you use to check correlation?
sns.heatmap() for correlation matrix, sns.pairplot() for pairwise relationships, and sns.scatterplot() for two-variable comparisons.
Q3. How do you handle skewed data?
Use log1p for right-skewed data (like Fare), sqrt for moderate skew, or Box-Cox for general use. Tree-based models are also naturally robust to skew.
Q4. How to detect multicollinearity?
Check the correlation heatmap for |r| > 0.8, and compute Variance Inflation Factor (VIF > 5–10 flags issues).
Q5. What are univariate, bivariate, and multivariate analyses?
Univariate = one variable (histogram, boxplot). Bivariate = two variables (scatter, bar). Multivariate = three+ variables (pairplot, heatmap, facet grids).
Q6. Difference between heatmap and pairplot?
Heatmap shows aggregated values (e.g., correlations) as a colour matrix — compact. Pairplot shows raw scatter plots for every variable pair + KDE on the diagonal — more detailed.
Q7. How do you summarize your insights?
Identify impactful patterns, quantify with numbers, relate to domain context, flag data quality issues, and recommend next steps (imputation, transforms, feature engineering).

▶️ How to Run
bash# 1. Clone the repo
git clone https://github.com/your-username/task-5-titanic-eda.git
cd task-5-titanic-eda

# 2. Install dependencies
pip install pandas numpy matplotlib seaborn jupyter

# 3. Launch the notebook
jupyter notebook Titanic_EDA.ipynb

Note: Make sure train.csv, test.csv, and gender_submission.csv are in the same directory as the notebook. Dataset available at Kaggle Titanic.


🙋 Author
Vandan — Data Analyst Internship, Elevate Labs · Task 5
