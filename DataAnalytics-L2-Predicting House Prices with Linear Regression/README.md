# 🏠 House Price Prediction using Linear Regression

An end-to-end machine learning project for predicting house prices using **Linear Regression**. The project covers the complete workflow, from exploratory data analysis and preprocessing to model evaluation, interpretation, and regularization.

This project was developed as part of **Level 2 – Task 1** of my Data Analytics Internship.

---

## 📌 Project Overview

The objective of this project is to build and evaluate a machine learning model that predicts house prices based on various property-related features, including:

- Area
- Number of bedrooms
- Number of bathrooms
- Number of floors
- Year built
- Location
- Property condition
- Garage availability

The project follows an end-to-end machine learning pipeline covering **data exploration, preprocessing, model training, evaluation, visualization, and model interpretation**.

---

## 📊 Dataset

**Dataset:** `House Price Prediction Dataset.csv`

### Features

| Feature | Type | Description |
|---|---|---|
| `Area` | Numerical | Property area |
| `Bedrooms` | Numerical | Number of bedrooms |
| `Bathrooms` | Numerical | Number of bathrooms |
| `Floors` | Numerical | Number of floors |
| `YearBuilt` | Numerical | Year the property was built |
| `Location` | Categorical | Property location |
| `Condition` | Categorical | Property condition |
| `Garage` | Categorical | Garage availability/type |
| `Price` | Target | House price |

The dataset contains **0 missing values**.

---

## 🛠️ Tech Stack

| Technology | Purpose |
|---|---|
| **Python 3** | Programming language |
| **Pandas** | Data manipulation and preprocessing |
| **NumPy** | Numerical operations |
| **Scikit-Learn** | Machine learning, preprocessing, and evaluation |
| **Matplotlib** | Data visualization |
| **Seaborn** | Statistical visualization |
| **Jupyter Notebook** | Interactive development |

---

## 🔄 Project Workflow

### 1. 🔍 Exploratory Data Analysis (EDA)

- Inspected the dataset structure.
- Checked data types and dimensions.
- Verified missing values.
- Confirmed that the dataset contains **0 missing values**.
- Analyzed the distribution of the target variable (`Price`).

### 2. 🧹 Data Preprocessing

The following preprocessing steps were performed:

- Removed the non-predictive `Id` column.
- Applied **One-Hot Encoding** to categorical features:
  - `Location`
  - `Condition`
  - `Garage`
- Prepared the resulting dataset for machine learning.

### 3. 📈 Correlation Analysis

A correlation heatmap was generated to examine relationships between the independent variables and the target variable (`Price`).

This helped identify the strength of linear relationships within the dataset.

### 4. 🤖 Model Training

The dataset was divided into:

- **80% Training Data**
- **20% Testing Data**

A standard **Linear Regression** model was then trained using the training dataset.

### 5. 📏 Model Evaluation

The model was evaluated using the following metrics:

- **Mean Squared Error (MSE)**
- **Root Mean Squared Error (RMSE)**
- **R² Score**

These metrics were used to assess the model's prediction error and overall explanatory performance.

### 6. 📊 Model Visualization

The project includes:

#### Actual vs. Predicted Prices

A scatter plot comparing the actual house prices with the prices predicted by the model.

#### Residual Plot

A residual plot used to examine the distribution of prediction errors and assess whether the errors show a meaningful pattern.

### 7. 🔎 Model Interpretation

The trained model's linear coefficients were extracted and analyzed to understand which features had the highest positive and negative influence on the predicted house price.

### 8. ⚡ Regularization — Bonus Analysis

The standard Linear Regression model was additionally compared with:

- **Ridge Regression (L2 Regularization)**
- **Lasso Regression (L1 Regularization)**

This comparison was performed to examine how regularization affects model performance.

---

## 🔑 Key Findings & Observations

### 📉 Data Characteristics

The correlation analysis showed that the features in this particular dataset have **very low correlation with the target variable (`Price`)**.

### 📊 Model Performance

Because the underlying dataset does not contain a strong linear relationship between the available features and house prices, the resulting **R² score is relatively low** across:

- Standard Linear Regression
- Ridge Regression
- Lasso Regression

### 💡 Key Takeaway

This project demonstrates an important practical machine learning lesson:

> **Good preprocessing and model implementation cannot compensate for weak predictive relationships within the underlying data.**

Even when the machine learning pipeline is technically sound, model performance ultimately depends on the predictive information contained within the dataset.

---

## 📁 Repository Structure

```text
House-Price-Prediction/
│
├── 📓 House Price Prediction.ipynb
├── 📊 House Price Prediction Dataset.csv
└── 📄 README.md
```

> **Note:** Update the notebook filename above if your actual `.ipynb` filename is different.

---

## 🚀 How to Run

### 1. Clone the Repository

```bash
git clone <repo-url>
cd <repo-folder>
```

### 2. Install Required Libraries

```bash
pip install pandas numpy matplotlib seaborn scikit-learn
```

### 3. Add the Dataset

Make sure the following dataset is placed in the same directory as the notebook:

```text
House Price Prediction Dataset.csv
```

### 4. Launch Jupyter Notebook

```bash
jupyter notebook
```

Open the project notebook and run all cells sequentially from **top to bottom**.

---

## 🎯 Project Objective

The primary objective of this project is to demonstrate an end-to-end **machine learning workflow for house price prediction**, including:

- Exploratory Data Analysis
- Data preprocessing
- One-Hot Encoding
- Correlation analysis
- Linear Regression
- Model evaluation
- Residual analysis
- Model interpretation
- Ridge and Lasso regularization

---

## 👨‍💻 Project Context

This project was developed as part of **Level 2 – Task 1** of my Data Analytics Internship and demonstrates the practical application of Python-based data analysis and machine learning techniques.
