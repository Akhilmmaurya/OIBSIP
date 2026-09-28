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

* **Dataset:** `OnlineRetail.csv` https://storage.googleapis.com/kaggle-data-sets/3886183/6749811/compressed/OnlineRetail.csv.zip?X-Goog-Algorithm=GOOG4-RSA-SHA256&X-Goog-Credential=gcp-kaggle-com%40kaggle-161607.iam.gserviceaccount.com%2F20260920%2Fauto%2Fstorage%2Fgoog4_request&X-Goog-Date=20260920T163820Z&X-Goog-Expires=259200&X-Goog-SignedHeaders=host&X-Goog-Signature=40773559cca20665131987432dd0d13249c76f010f7d1390c8e1397809de7a295b44c687832ca6459bce1a1e0b642219fa5d7d41fbfa6bf13c4025453d45d3a062d0a0a0e48c6e1ed70c07eebf38d105e4362bbc4cfea1b0a9d5c84395bd5ee0db4478d4be0bf7082e7ab78fb8822e81a93669552a65cea3758e925514cbf3deb41af2c38770df8c039d300b07d24172bf5f162bd026c87e60d08a9a24eeff1b4b22c0dd8987385b31664fce8a121a09a6fae64a57587d82550de1c92188a578cea0f47ab0f84dbfb954ef07c5736dbd3a4a1c8503a27e345473e7096b4a90a92c6f135ec5f7e8a7ad8bbb98fdeb20d0e52f5b99d82b09572264b86f51fa018e
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

## 👨‍💻 Project Context

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
