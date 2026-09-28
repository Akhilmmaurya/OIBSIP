# 🎯 Customer Segmentation Analysis using K-Means (RFM Analysis)

## 📌 Project Overview

This project was developed as part of a **Data Analytics Internship (Level 1 – Task 2)**.

The goal of the project is to segment an e-commerce platform's customer base into distinct behavioural groups using **unsupervised machine learning (K-Means Clustering)**.

By analyzing transactional history through **RFM (Recency, Frequency, Monetary)** features, businesses can transition from generic mass communication to data-driven, targeted marketing strategies.

---

## ⚠️ Important Note / Disclaimer

>> **Note on Project Assistance:**
> This project was developed with the assistance of AI-based tools. AI assistance was utilized for aspects including code structuring, debugging, documentation, and the organization and clarification of technical explanations. The project was not developed entirely independently from scratch; rather, it was developed and verified iteratively with the support, guidance, and feedback provided by AI tools.


---

## 📊 Dataset Description

* **Dataset:** [Online Retail Customer Segmentation Dataset](https://www.kaggle.com/code/vishnupriyagarige/online-retail-customer-segmentation/input)`
* **Source:** Online Retail transaction records
* **Initial Dimensions:** `541,909 rows × 8 columns`

### Features Used

| Feature       | Purpose                                                                  |
| ------------- | ------------------------------------------------------------------------ |
| `InvoiceNo`   | Transaction identifier; used to track frequency and detect cancellations |
| `CustomerID`  | Unique client identifier                                                 |
| `InvoiceDate` | Timestamp of order placement; used for Recency                           |
| `Quantity`    | Number of units purchased                                                |
| `UnitPrice`   | Price per unit; used with Quantity to calculate total monetary spend     |

---

## 🔄 Workflow & Methodology

### 1. 🧹 Data Inspection & Cleaning

* Identified and handled missing values.
* `CustomerID` missing in approximately **24.9% of rows** was removed.
* Filtered out order cancellations (`InvoiceNo` starting with `C`).
* Removed non-positive values:

  * `Quantity <= 0`
  * `UnitPrice <= 0`
* Removed duplicate transaction logs.

### 2. 🧮 Feature Engineering — RFM Metrics

The following customer-level metrics were calculated:

#### Recency (R)

Days since the customer's last purchase relative to the reference date.

#### Frequency (F)

Total number of distinct completed orders per customer.

#### Monetary (M)

Total lifetime spend across all purchases.

#### Average Order Value (AOV)

Spend per order:

```text
AOV = Monetary / Frequency
```

### 3. ⚖️ Data Preprocessing & Scaling

Features were standardized using `StandardScaler`.

This ensures that monetary spend does not dominate distance calculations simply because it has a larger numerical scale than purchase frequency or recency.

### 4. 🤖 K-Means Clustering & Optimal K

Cluster performance was evaluated for:

```text
K = 1 to K = 10
```

using the **Elbow Method (Inertia / WCSS)**.

**K = 3** was identified as the optimal balance of intra-cluster similarity and business interpretability.

### 5. 📈 Visualization & Customer Profiling

The analysis includes:

* Elbow curve
* `Recency vs. Monetary` scatter plot
* `Frequency vs. Monetary` scatter plot
* Customer distribution bar chart
* Customer segment profiling

---

## 👥 Customer Segments Profile & Strategy

| Cluster | Segment Name           | Customer Count | Avg Recency | Avg Frequency | Avg Monetary | Recommended Action                                                        |
| :-----: | ---------------------- | -------------: | ----------: | ------------: | -----------: | ------------------------------------------------------------------------- |
|  **0**  | **At-Risk / Inactive** |         ~1,082 |   ~247 days |  ~1.58 orders |     ~£629.66 | Automated "We Miss You" win-back discounts and re-engagement campaigns.   |
|  **1**  | **Active Regulars**    |         ~3,230 |  ~41.5 days |  ~4.67 orders |   ~£1,849.67 | Loyalty rewards, cross-sell recommendations, and product updates.         |
|  **2**  | **VIP / High-Value**   |            ~26 |   ~6.0 days |  ~66.4 orders |  ~£85,826.08 | Dedicated account manager, bulk purchase benefits, and concierge service. |

---

## 🛠️ Tech Stack

| Technology                          | Purpose                        |
| ----------------------------------- | ------------------------------ |
| **Python 3.x**                      | Programming language           |
| **Pandas**                          | Data manipulation and analysis |
| **NumPy**                           | Numerical operations           |
| **Matplotlib**                      | Data visualization             |
| **Seaborn**                         | Statistical visualization      |
| **Scikit-learn**                    | Machine learning               |
| **StandardScaler**                  | Feature standardization        |
| **KMeans**                          | Customer clustering            |
| **Jupyter Notebook / Google Colab** | Development environment        |

---

## 🚀 How to Run the Project

### 1. Clone or Download the Repository

```bash
git clone <repo-url>
cd <repo-folder>
```

### 2. Install Dependencies

```bash
pip install pandas numpy matplotlib seaborn scikit-learn
```

### 3. Place the Data File

Ensure that `OnlineRetail.csv` is located in the same directory as the notebook.

```text
project-folder/
│
├── OnlineRetail.csv
├── customer_segmentation.ipynb
└── README.md
```

### 4. Launch the Notebook

If using Jupyter Notebook:

```bash
jupyter notebook customer_segmentation.ipynb
```

Alternatively, the notebook can be opened and executed using **Google Colab**.

### 5. Run the Analysis

Run all cells sequentially from **top to bottom** to reproduce the analysis and generate the visualizations.

---

## 📌 Project Objective

The primary objective of this project is to use **RFM analysis and K-Means clustering** to identify distinct customer behavioural segments and translate those segments into targeted marketing strategies.

---

## 👨‍💻 Author
Akhil

This project was developed as part of a **Data Analytics Internship — Level 1, Task 2** and demonstrates the practical application of:

* Data cleaning
* Feature engineering
* RFM analysis
* Feature scaling
* Unsupervised machine learning
* K-Means clustering
* Elbow Method
* Data visualization
* Customer segmentation
* Business-oriented interpretation
