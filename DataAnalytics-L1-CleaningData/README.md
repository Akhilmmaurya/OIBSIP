# 🚢 Titanic Dataset — Data Cleaning & Preprocessing

A clean and well-documented data cleaning pipeline for the classic Titanic dataset using **Python** and **pandas**. This project transforms the raw dataset into a structured, analysis-ready version suitable for exploratory data analysis and machine learning.

---

## 📌 Project Overview

This project was developed as part of a Data Analytics Internship (Level 1 – Task 3).

The objective of this project is to address common real-world data quality issues through a systematic preprocessing workflow.

The pipeline includes:

* Handling missing values
* Standardizing categorical text
* Treating extreme outliers
* Correcting data types
* Preserving historical records
* Exporting a clean, reusable dataset

---

## 🛠️ Tech Stack

| Technology                          | Purpose                      |
| ----------------------------------- | ---------------------------- |
| **Python**                          | Programming language         |
| **Pandas**                          | Data cleaning & manipulation |
| **NumPy**                           | Numerical operations         |
| **Jupyter Notebook / Google Colab** | Development environment      |

---

## 🚀 Data Cleaning Workflow

### 1. 🔍 Initial Quality Audit

Performed a complete inspection of the raw dataset by checking:

* Null values
* Duplicate records
* Data types
* Value ranges
* Dataset structure across all **12 columns**

### 2. 🧹 Missing Data Handling

**Embarked**

* Filled the **2 missing values** using the most frequent embarkation port: `'S'`.

**Age**

* Extracted passenger titles (`Mr`, `Mrs`, `Miss`, `Master`, etc.).
* Imputed missing ages using the **median age of each title group**.

**Cabin**

* Replaced missing values with `'Unknown'`.
* Extracted the deck letter as a new categorical feature.

### 3. ✅ Duplicate Validation

* Verified that the dataset contains **no duplicate passenger records**.

### 4. 📝 Text Standardization

Cleaned categorical text fields by:

* Removing leading and trailing whitespace
* Standardizing casing
* Normalizing `Sex` values to **Male** and **Female**

### 5. 📉 Outlier Treatment

* Retained valid historical ages (up to **80 years**).
* Applied **soft capping** to extreme luxury ticket fares using the **99th percentile**, reducing skew while preserving every observation.

### 6. ⚙️ Data Type Optimization

Converted the following columns into more appropriate formats:

* `PassengerId` → `string`
* `Sex` → `category`
* `Embarked` → `category`
* `Pclass` → `category`
* `Title` → `category`
* `Deck` → `category`

### 7. 💾 Export

The cleaned dataset was exported as:

```text
titanic_cleaned.csv
```

---

## 📊 Before vs. After Cleaning

| **Metric / Field**  | **Before Cleaning** |              **After Cleaning** |
| ------------------- | ------------------: | ------------------------------: |
| Total Rows          |                 891 |                             891 |
| Missing `Age`       |                 177 |   0 *(imputed by title median)* |
| Missing `Cabin`     |                 687 |        0 *(`Unknown` assigned)* |
| Missing `Embarked`  |                   2 |           0 *(filled with `S`)* |
| Duplicate Rows      |                   0 |                               0 |
| `PassengerId` Type  |             `int64` |                        `string` |
| Categorical Columns |            `object` |                      `category` |
| Maximum Fare        |             £512.33 | £249.01 *(99th percentile cap)* |

---

## 📁 Repository Structure

```text
Titanic-Data-Cleaning/
│
├── Titanic-Dataset.csv
├── data_cleaning.ipynb
├── titanic_cleaned.csv
└── README.md
```

---

## ⚙️ How to Run

### 1. Clone the Repository

```bash
git clone <repo-url>
cd <repo-folder>
```

### 2. Install Dependencies

```bash
pip install pandas numpy
```

### 3. Open the Notebook

```bash
jupyter notebook data_cleaning.ipynb
```

Run all notebook cells sequentially from **top to bottom** to reproduce the complete data cleaning pipeline and generate the cleaned dataset.

---

## 📌 Project Objective

The primary objective of this project is to demonstrate a practical, end-to-end **data cleaning and preprocessing workflow** by transforming raw Titanic passenger data into a clean, consistent, and machine learning–ready dataset.

---

## 👨‍💻 Author
Akhil

PROJECT CONTEXT

This project demonstrates practical skills in:

* Data quality assessment
* Missing value imputation
* Feature engineering
* Text standardization
* Outlier treatment
* Data type optimization
* Dataset preparation for analytics and machine learning
