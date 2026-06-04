# Bank Customer Churn Analysis

### End-to-End Exploratory Data Analysis, Statistical Testing, Time-Based Analysis, and Feature Engineering

## Project Overview

This project performs a comprehensive Exploratory Data Analysis (EDA) on a Bank Customer Churn dataset containing customer demographic, financial, account, and behavioral information.

The objective is to identify factors influencing customer churn, uncover customer behavior patterns, validate findings using statistical tests, engineer meaningful features, and generate actionable business insights for customer retention strategies.

The project follows a structured EDA workflow including data profiling, cleaning, preprocessing, visualization, statistical testing, time-based analysis, and feature engineering.

---

# Dataset Description

## Dataset Characteristics

* Total Records: 10,100
* Total Features: 17 columns
* Numerical Variables
* Categorical Variables
* Date Variables
* Customer Churn Target Variable

## Key Features

| Feature | Description |
|----------|-------------|
| Row_Number | Record identifier |
| Customer_Id | Unique customer identifier |
| Surname | Customer surname |
| Credit_Score | Customer credit score |
| Geography | Customer region |
| Gender | Customer gender |
| Age | Customer age |
| Tenure | Years with the bank |
| Balance | Account balance |
| Num_Of_Products | Number of products used |
| Has_Cr_Card | Credit card ownership |
| Is_Active_Member | Active member status |
| Estimated_Salary | Estimated annual salary |
| Exited | Customer churn status |
| Join_Date | Customer joining date |
| Last_Transaction_Date | Most recent transaction date |
| Account_Type | Customer account type |

### Target Variable

**Exited**

* 0 → Customer Retained
* 1 → Customer Churned

---

# Project Objectives

* Understand customer demographics and banking behavior.
* Identify factors associated with customer churn.
* Handle data quality issues.
* Perform data cleaning and preprocessing.
* Conduct univariate and bivariate analysis.
* Validate findings using statistical testing.
* Analyze customer trends over time.
* Engineer meaningful features.
* Generate business recommendations to reduce churn.

---

# Project Workflow


## Day 1 – Data Understanding & Profiling

### Tasks Completed

* Dataset overview and business understanding
* Data inspection using `.head()`, `.info()`, and `.describe()`
* Identification of numerical, categorical, and date columns
* Missing value analysis
* Data quality assessment

### Notebook

`01_data_overview.ipynb`

---

## Day 2 – Data Cleaning & Preprocessing

### Tasks Completed

* Corrected data types
* Standardized categorical variables
* Removed duplicate records
* Handled missing values
* Detected and treated outliers using the IQR method
* Applied necessary data transformations

### Notebook

`02_cleaning_preprocessing.ipynb`

### Output

`data/interim/cleaned_day2.csv`

---

## Day 3 – Univariate & Bivariate EDA

### Univariate Analysis

Performed:

* Histograms
* KDE Plots
* Boxplots
* Countplots
* Frequency Tables

Analyzed Variables:

* Credit Score
* Age
* Balance
* Tenure
* Number of Products
* Estimated Salary
* Geography
* Gender
* Account Type
* Churn Status

### Bivariate Analysis

#### Numerical vs Numerical

* Scatterplots
* Correlation Heatmap

#### Numerical vs Categorical

* Boxplots
* Grouped Bar Charts

### Segment Analysis

* Geography vs Churn
* Gender vs Churn
* Account Type vs Churn
* Age Group vs Churn

### Notebook

`03_univariate_bivariate_eda.ipynb`

### Figures

`reports/figures/`

---

## Day 4 – Statistical Tests, Time-Based EDA & Feature Engineering

### Statistical Tests

**Significance Level (α): 0.05**

#### Independent T-Test

Used to compare:

* Balance between Male and Female customers
* Balance between Churned and Non-Churned customers

#### ANOVA

Used to determine:

* Whether average age differs across account types
* Whether average balance differs across geographical regions

#### Chi-Square Test

Used to analyze:

* Relationship between Gender and Churn
* Relationship between Geography and Churn

---

### Time-Based EDA

Extracted Date Features:

* Join Year
* Join Month
* Join Day

Trend Analysis:

* Customer Join Year Trend
* Monthly Customer Join Trend

---

### Feature Engineering

The following features were created:

#### High_Balance

Customers whose account balance is above the dataset median.

#### High_Credit_Score

Customers with a credit score greater than or equal to 700.

#### Customer_Age_Days

Number of days between the customer's join date and last transaction date.

#### Long_Term_Customer

Customers with tenure greater than or equal to 5 years.

#### Credit_Category

Credit score categorized into:

* Poor
* Fair
* Good
* Excellent

### Notebook

`04_stats_time_features_final_insights.ipynb`

### Output

`data/processed/final_cleaned_day4.csv`


# Top 10 Key Insights

### 1. Approximately 20% of customers have churned from the bank.

### 2.Germany exhibits the highest customer churn proportion among all regions.

### 3.France contains the largest customer base.

### 4.Customers aged 51–60 show higher churn tendencies compared to younger age groups.

### 5.Most customers belong to the 31–40 age group.

### 6.Balance differs significantly between churned and retained customers.

### 7.Customer age varies significantly across account types.

### 8.Regional differences significantly affect customer balances.

### 9.Most customers fall under the Fair credit score category.

### 10.Customer acquisition remains relatively stable across years and months.

---

# Segment Findings

## Geography Analysis

* Germany shows the highest churn tendency.
* France contributes the largest share of customers.
* Spain has comparatively lower churn rates.

## Age Group Analysis

* Customers aged 51–60 exhibit the highest churn risk.
* Customers aged 18–30 show lower churn rates.

## Account Type Analysis

* Current accounts dominate the customer base.
* Premium account holders show noticeable churn levels.

---

# Statistical Test Findings

## T-Test

### Gender vs Balance

* p-value > 0.05
* No significant balance difference exists between male and female customers.

### Churn vs Balance

* p-value < 0.05
* Significant balance difference exists between churned and retained customers.

---

## ANOVA

### Age vs Account Type

* Mean age differs significantly across account types.

### Balance vs Geography

* Mean balance differs significantly across geographical regions.

---

## Chi-Square Test

### Gender vs Churn

* Significant association exists between gender and churn.

### Geography vs Churn

* Strong association exists between geography and churn.

---

# Data Quality Issues Identified

* Date columns required conversion to datetime format.
* Outliers detected in Age and Credit Score.
* Churn target variable was imbalanced.
* Categorical variables required standardization.
* Additional features were needed to improve analysis.

---

# Business Recommendations

### 1.

Develop targeted retention campaigns for customers in Germany.

### 2.

Focus retention efforts on customers aged 51–60.

### 3.

Monitor high-balance customers proactively.

### 4.

Increase engagement programs for inactive customers.

### 5.

Create personalized offers based on customer tenure and account type.

### 6.

Use engineered features for future churn prediction models.

---

# Project Structure


```text
Banking-customer-churn-Analysis-EDA/
│
├── data/
│   ├── raw/
│   ├── interim/
│   └── processed/
│
├── notebooks/
│   ├── 01_data_overview.ipynb
│   ├── 02_cleaning_preprocessing.ipynb
│   ├── 03_univariate_bivariate_eda.ipynb
│   └── 04_stats_time_features_final_insights.ipynb
│
├── reports/
│   └── figures/
│
├── .gitignore
├── README.md
└── requirements.txt
```

---

# Technologies Used

* Python
* Pandas
* NumPy
* Matplotlib
* Seaborn
* SciPy
* Jupyter Notebook
* Git
* GitHub

---

# How to Run

## 1. Clone the Repository

```bash
git clone https://github.com/mohammednihalkp321/Banking-customer-churn-Analysis-EDA.git
```

## 2. Navigate to Project Folder

```bash
cd Banking-customer-churn-Analysis-EDA
```

## 3. Install Dependencies

```bash
pip install -r requirements.txt
```

## 4. Run Notebooks

Execute notebooks in the following order:

1. 01_data_overview.ipynb
2. 02_cleaning_preprocessing.ipynb
3. 03_univariate_bivariate_eda.ipynb
4. 04_stats_time_features_final_insights.ipynb

---

# Author

**Mohammed Nihal**

Data Analytics Intern

GitHub: https://github.com/mohammednihalkp321