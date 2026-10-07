# BankPulse: Customer Churn Analytics

## 📌 Project Overview

A bank has experienced an increase in customer churn alongside a decline in growth. The product team wants to understand the characteristics and behaviors associated with customers leaving the bank and identify opportunities to improve retention and support future customer acquisition.

As a **Data Scientist**, I was tasked with preparing and exploring a customer dataset that would serve as the foundation for two machine learning initiatives:

* **Customer Churn Prediction** — identify customers who may be at higher risk of leaving.
* **Customer Segmentation** — identify meaningful groups of customers based on their characteristics and financial profiles.

This project focuses on **data preparation and exploratory data analysis (EDA)** to transform raw customer information into a clean, consistent, and model-ready dataset while uncovering meaningful business insights.

---

## 🎯 Business Objectives

The analysis aims to help the bank:

* Understand the overall customer churn situation.
* Identify customer characteristics associated with higher churn.
* Compare churn patterns across demographic and geographic groups.
* Detect unusual or potentially problematic data values.
* Prepare a reliable dataset for downstream machine learning.
* Identify meaningful customer characteristics that can support segmentation.
* Provide actionable insights that can guide customer retention and growth strategies.

---

## 💼 Business Problem

The bank's product team has noticed two concerning trends:

**1. Increasing customer churn**

Customers are leaving the bank at a higher rate, potentially affecting revenue, customer lifetime value, and long-term growth.

**2. Declining customer growth**

The bank needs to better understand its existing customer base and identify opportunities to attract, retain, and engage customers more effectively.

To address these challenges, the bank needs a better understanding of **who is leaving, what characteristics are associated with churn, and how customers differ from one another.**

---

## 🔍 Analytical Approach

### 1. Data Import & Quality Assurance

The customer and account datasets were combined using a **left join on `CustomerId`**.

Data-quality checks included:

* Identifying duplicate records.
* Removing duplicate rows.
* Checking for duplicate column names.
* Validating the resulting dataset structure.

The merged dataset contained **10,004 rows**, with **4 duplicate rows removed**, resulting in **10,000 unique records**.

### 2. Data Cleaning

The dataset was prepared for analysis by:

* Checking and correcting data types.
* Identifying missing values.
* Replacing missing categorical values with `"MISSING"`.
* Replacing missing numeric values with the column median.
* Profiling numeric variables for extreme or nonsensical values.
* Imputing invalid numeric values where appropriate.
* Standardizing variations in country names within the `Geography` column.

### 3. Exploratory Data Analysis

The cleaned dataset was explored to understand the bank's customer base and investigate potential drivers of churn.

The analysis included:

* Churner vs. non-churner distribution.
* Churn rates across geographic regions.
* Churn rates across genders.
* Comparison of numeric customer characteristics between churners and non-churners.
* Box plots to examine distributions and potential outliers.
* Histograms to compare customer distributions by churn status.

### 4. Feature Preparation

A modeling dataset was created by removing fields unsuitable for machine learning, such as customer identifiers and free-text names.

Categorical variables were converted into numerical dummy variables.

An additional feature, **`balance_v_income`**, was created:

```text
balance_v_income = Balance / EstimatedSalary
```

This feature provides an additional perspective on a customer's financial position relative to their estimated income.

---

## 📊 Key Analysis Areas

The exploratory analysis focuses on questions such as:

* How prevalent is customer churn?
* Which geographic groups have the highest churn rates?
* Are there differences in churn between genders?
* Do churners have different financial characteristics from non-churners?
* Are there meaningful differences in customer age, credit score, balance, tenure, product usage, or salary?
* Does the balance-to-income relationship differ between churners and non-churners?
* Which customer characteristics could be useful for future churn prediction and segmentation models?

---

## 🤖 Machine Learning Readiness

The purpose of this project is not to build the final machine learning models, but to **prepare and explore the data that will be used to build them**.

The resulting dataset provides a foundation for:

### Churn Prediction

A supervised learning model can use customer characteristics to estimate the probability that an individual customer will churn.

Potential applications include:

* Early identification of high-risk customers.
* Targeted retention campaigns.
* Personalized offers and interventions.
* Prioritization of customer-success resources.

### Customer Segmentation

An unsupervised learning model can group customers based on similarities in their demographic, financial, and behavioral characteristics.

Potential applications include:

* Personalized marketing.
* Targeted product recommendations.
* Customer acquisition strategies.
* Segment-specific retention programs.
* More effective resource allocation.

---

## 📈 Business Value

The analysis helps move the bank from simply observing churn to understanding **where and how churn occurs**.

The insights can support the product and marketing teams in developing:

* More targeted retention strategies.
* Customer-specific engagement campaigns.
* Data-driven acquisition strategies.
* Better customer segmentation.
* More effective product recommendations.

Ultimately, the analysis establishes a reliable data foundation for predictive and segmentation models that can help the bank **reduce customer churn, improve retention, and support sustainable customer growth.**

---

## 🛠️ Tools & Technologies

* **Python**
* **Pandas** — data manipulation and cleaning
* **NumPy** — numerical operations and feature engineering
* **Matplotlib** — data visualization
* **Jupyter Notebook** — analysis and documentation
* **Excel** — source data and initial data inspection
* **Exploratory Data Analysis (EDA)**
* **Feature Engineering**
* **Data Cleaning & Preparation**

---

## 📁 Dataset

The project uses customer and account-level banking data containing information such as:

* Customer ID
* Surname
* Credit Score
* Geography
* Gender
* Age
* Tenure
* Account Balance
* Number of Products
* Credit Card Status
* Active Member Status
* Estimated Salary
* Churn Status

The target variable is:

**`Exited`**

* `0` — Non-churner
* `1` — Churner

---

## 📂 Project Structure

```text
BankPulse-Customer-Churn-Analytics/
│
├── data/
│   ├── Bank_Churn_Messy.xlsx
│   ├── Bank_Churn.csv
│   └── Bank_Churn_Data_Dictionary.csv
│
├── notebooks/
│   └── Bank_Customer_Churn_Analysis.ipynb
│
├── README.md
│
└── requirements.txt
```

---

## 🚀 Project Workflow

```text
Raw Customer & Account Data
          ↓
     Data Import
          ↓
   Data Quality Checks
          ↓
      Data Cleaning
          ↓
 Missing Value Treatment
          ↓
  Invalid Value Detection
          ↓
 Geography Standardization
          ↓
 Exploratory Data Analysis
          ↓
   Feature Engineering
          ↓
    Modeling Dataset
          ↓
 ┌───────────────────────┐
 │                       │
 ▼                       ▼
Churn Prediction    Customer Segmentation
```

---

## 💡 Conclusion

This project demonstrates how customer data can be transformed from a raw and inconsistent dataset into a structured analytical foundation for machine learning.

Through systematic data cleaning, exploratory analysis, visualization, and feature engineering, the project identifies patterns that can help the bank better understand customer churn and customer characteristics.

The resulting dataset and insights provide the groundwork for developing **churn prediction and customer segmentation models**, enabling the bank to make more targeted, data-driven decisions around **customer retention and growth**.
