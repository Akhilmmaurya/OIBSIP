Titanic Dataset - Data Cleaning & Preprocessing

A clean and documented data cleaning pipeline for the classic Titanic dataset using Python and pandas. This project takes the raw, messy dataset and systematically cleans it for exploratory analysis and machine learning.

📌 Project Overview

The goal of this project is to fix common real-world data issues:

Missing values in numerical and categorical fields

Inconsistent string formats and casing

Extreme outliers in fare prices

Incorrect data types (e.g., IDs stored as numbers)

Redundant or missing structural records

🛠️ Tech Stack

Language: Python

Libraries: pandas, numpy

Environment: Jupyter Notebook / Google Colab

🚀 Key Cleaning Steps

Initial Quality Audit: Checked null counts, duplicate rows, data types, and value ranges across all 12 columns.

Missing Data Handling:

Embarked: Filled the 2 missing records with the most common port ('S').

Age: Extracted passenger titles (Mr, Mrs, Miss, Master, etc.) and filled missing ages using the median age of each specific title group.

Cabin: Replaced missing values with 'Unknown' and extracted the deck letter code.

Duplicate Check: Verified that no duplicate passenger records exist.

Text Standardisation: Stripped whitespace and normalized text fields (e.g., standardizing Sex values to 'Male' and 'Female').

Outlier Treatment:

Retained valid older ages (historical records up to age 80).

Applied soft capping to extreme luxury suite ticket fares at the 99th percentile to prevent distortion while keeping all rows.

Data Type Casting: Converted PassengerId to string, and categorical columns (Sex, Embarked, Pclass, Title, Deck) to proper categorical types.

Export: Saved the clean dataset to titanic_cleaned.csv.

📊 Before vs. After Summary

Metric / Field

Before Cleaning

After Cleaning

Total Rows

891

891

Missing Age

177

0 (imputed by title median)

Missing Cabin

687

0 (labeled as 'Unknown')

Missing Embarked

2

0 (imputed with 'S')

Duplicate Rows

0

0

PassengerId Type

int64

object / string

Categorical Types

object strings

category (memory efficient)

Max Fare

£512.33 (extreme skew)

£249.01 (99th percentile cap)

📁 Repository Structure

├── Titanic-Dataset.csv       # Raw source dataset
├── data_cleaning.ipynb       # Jupyter notebook with step-by-step code & markdown
├── titanic_cleaned.csv       # Cleaned, ready-to-use dataset
└── README.md                 # Project documentation


⚙️ How to Run

Clone or download this repository:

git clone <repo-url>
cd <repo-folder>


Install dependencies:

pip install pandas numpy


Open and run the notebook:

jupyter notebook data_cleaning.ipynb
