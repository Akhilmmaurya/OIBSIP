# 🛍️ Retail Sales Exploratory Data Analysis (EDA)

An end-to-end Exploratory Data Analysis (EDA) project on transaction-level retail sales data. This project explores **customer demographics, purchasing patterns, product performance, and monthly/quarterly sales trends** to uncover actionable business insights.

---

## 📌 Project Overview

The goal of this analysis is to understand what drives revenue across different customer segments and product categories.

The analysis focuses on:

* Customer demographics
* Purchasing behavior
* Product category performance
* Monthly and quarterly sales trends
* Age-group and gender segmentation
* Correlation between numerical variables
* High-value customer micro-segments

---

## 🔍 Key Insights

### 💰 Top-Performing Micro-Segment

Customers aged **56–65** purchasing **Electronics** generated the highest average spend, at approximately **$507 per transaction**.

### 📦 Product Performance

Unit sales volume is relatively similar across product categories. However, **Electronics generates the highest total revenue**, primarily because of its higher price per unit.

### 👥 Customer Demographics

The customer base is relatively evenly distributed across genders, while customers in the **46–65 age range** account for higher overall spending.

### 📈 Sales Trends

Monthly sales show some mid-year fluctuations, but there are **no major seasonal drop-offs**. Quarterly revenue remains relatively stable throughout the year.

---

## 📊 Dataset Structure

The dataset contains **1,000 transaction records** and **9 columns**, with **zero missing values**.

| Column             | Data Type  | Description                                            |
| ------------------ | ---------- | ------------------------------------------------------ |
| `Transaction ID`   | `int64`    | Unique identifier for each transaction                 |
| `Date`             | `datetime` | Date of the transaction                                |
| `Customer ID`      | `object`   | Unique identifier for each customer                    |
| `Gender`           | `object`   | Customer gender (`Male` / `Female`)                    |
| `Age`              | `int64`    | Customer age (18–65)                                   |
| `Product Category` | `object`   | Product category (`Beauty`, `Clothing`, `Electronics`) |
| `Quantity`         | `int64`    | Number of units purchased                              |
| `Price per Unit`   | `int64`    | Price per unit in USD                                  |
| `Total Amount`     | `int64`    | Total transaction value in USD                         |

---

## 🔄 Workflow & Methodology

### 1. 🧹 Data Cleaning & Verification

* Checked dataset dimensions
* Verified data types
* Confirmed dataset shape: **1,000 × 9**
* Checked for missing/null values
* Verified that all columns contain valid data

### 2. 📊 Descriptive Statistics

Calculated key statistical measures for numerical variables:

* Mean
* Median
* Mode
* Standard deviation

Variables analyzed:

* `Age`
* `Quantity`
* `Price per Unit`
* `Total Amount`

### 3. 📅 Time Series Analysis

Analyzed revenue trends over time by:

* Aggregating total sales by month
* Aggregating total sales by quarter
* Visualizing monthly revenue trends
* Comparing quarterly performance
* Identifying fluctuations and potential seasonality

### 4. 👥 Demographic Segmentation

Customers were segmented into five age groups:

* **18–25**
* **26–35**
* **36–45**
* **46–55**
* **56–65**

The analysis also examined:

* Gender distribution
* Spending patterns across age groups
* Average transaction value by demographic segment

### 5. 🛒 Product & Correlation Analysis

Performed deeper analysis using:

* Product category comparisons
* Average spending by age group
* Cross-tabulation of age groups and product categories
* Correlation matrices
* Seaborn heatmaps

---

## 🛠️ Tech Stack

| Technology           | Purpose                        |
| -------------------- | ------------------------------ |
| **Python 3.x**       | Programming language           |
| **Pandas**           | Data manipulation and analysis |
| **Matplotlib**       | Data visualization             |
| **Seaborn**          | Statistical visualization      |
| **Jupyter Notebook** | Interactive analysis           |

---

## 📁 Project Structure

```text
retail-sales-eda/
│
├── 📓 L1-Retail Sales Data.ipynb
├── 📊 retail_sales_dataset.csv
├── 📄 README.md
└── 📁 images/
    └── charts and visualizations
```

---

## 🚀 How to Run

### 1. Clone the Repository

```bash
git clone https://github.com/your-username/retail-sales-eda.git
```

### 2. Navigate to the Project Directory

```bash
cd retail-sales-eda
```

### 3. Install Dependencies

```bash
pip install pandas matplotlib seaborn notebook
```

### 4. Add the Dataset

Make sure the following dataset is present in the project root:

```text
retail_sales_dataset.csv
```

### 5. Launch Jupyter Notebook

```bash
jupyter notebook
```

Then open:

```text
L1-Retail Sales Data.ipynb
```

---

## 📈 Analysis Highlights

This project demonstrates practical application of:

* Data cleaning
* Exploratory data analysis
* Statistical analysis
* Data aggregation
* Time series analysis
* Demographic segmentation
* Correlation analysis
* Data visualization
* Business insight generation

---

## 🎯 Project Objective

The primary objective of this project is to transform raw retail transaction data into **clear, interpretable business insights** that can help understand customer behavior, product performance, and revenue trends.

---

## 👨‍💻 Author

**Akhil**

This project was created as part of my journey toward building practical **Data Analytics and Python projects**.
