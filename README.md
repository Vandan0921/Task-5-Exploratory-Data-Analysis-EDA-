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
├── Titanic_EDA_Report.pgf    # PDF-ready findings report
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



🙋 Author
Vandan — Data Analyst Internship, Elevate Labs · Task 5
