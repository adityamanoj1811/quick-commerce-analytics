# 🛵 Quick-Commerce Delivery Analytics

[![Python](https://img.shields.io/badge/Python-3.10%2B-blue?logo=python)](https://python.org)
[![Platform](https://img.shields.io/badge/Platform-Google%20Colab-orange?logo=googlecolab)](https://colab.research.google.com)
[![Dataset](https://img.shields.io/badge/Dataset-Kaggle-20BEFF?logo=kaggle)](https://www.kaggle.com/datasets/rohitgrewal/quick-commerce-dataset)
[![License](https://img.shields.io/badge/License-MIT-yellow)](./LICENSE)
[![Status](https://img.shields.io/badge/Status-Complete-brightgreen)](https://github.com)

> A complete end-to-end Data Analytics project on a real-world Quick-Commerce delivery dataset with 5,91,539 records — covering all 4 units of the Introduction to Data Analytics syllabus.

---

## 📌 Project Overview

This project performs a full data analytics study on a **quick-commerce (q-commerce) delivery dataset** simulating operations across multiple companies and cities in India. It covers everything from descriptive statistics to machine learning models, time series forecasting, and prescriptive decision-making.

### Key Results

| Metric | Value |
|---|---|
| Total Records Analysed | 5,91,539 |
| Columns | 13 |
| New Features Engineered | 7 |
| Hypothesis Tests Applied | 5 |
| ML Models Built | 5+ |
| Best Classifier (XGBoost) Accuracy | ~79% |
| Best Classifier AUC-ROC | ~0.88 |
| K-Means Clusters Found | 4 |
| Best Forecast Model | Holt-Winters (MAE ~52) |
| Syllabus Units Covered | All 4 |

---

## 🗂️ Repository Structure

```
quick-commerce-analytics/
│
├── 📓 quick_commerce_analytics.ipynb     ← Main analysis notebook
├── 📊 Requirements.txt                   ← Python dependencies
├── 📄 README.md                          ← This file
├── 📄 LICENSE                            ← MIT License
├── 📄 Contributing.md                    ← Contribution guidelines
├── 📄 .gitignore                         ← Git ignore rules
```

> **Dataset:** Download from [Kaggle](https://www.kaggle.com/datasets/rohitgrewal/quick-commerce-dataset) and place as `quick_commerce_dataset.csv` in the root folder.

---

## 📊 Dataset

| Property | Details |
|---|---|
| **Name** | Quick-Commerce Delivery Dataset |
| **Source** | Kaggle — Rohit Grewal |
| **Records** | 5,91,539 rows |
| **Columns** | 13 |
| **Domain** | Q-Commerce / On-Demand Delivery (India) |
| **Access** | Free on Kaggle |

### Column Descriptions

| Column | Type | Description |
|---|---|---|
| `Order_ID` | Categorical | Unique identifier for each order |
| `Company` | Categorical | Q-commerce company (Blinkit, Zepto, Instamart, etc.) |
| `City` | Categorical | City where the order was placed |
| `Customer_Age` | Numerical | Age of the customer (years) |
| `Order_Value` | Numerical | Total monetary value of the order (₹) |
| `Delivery_Time_Min` | Numerical | Time taken to deliver (minutes) |
| `Distance_Km` | Numerical | Distance from dark store to customer (km) |
| `Items_Count` | Numerical | Number of items in the order |
| `Product_Category` | Categorical | Primary product category |
| `Payment_Method` | Categorical | Mode of payment used |
| `Customer_Rating` | Numerical | Customer satisfaction rating (1–5 stars) |
| `Discount_Applied` | Categorical | Whether a discount was used (Yes/No) |
| `Delivery_Partner_Rating` | Numerical | Rating given to delivery partner (1–5 stars) |

---

## 🤖 Analytics & ML Techniques

| # | Technique | Type | Purpose |
|---|---|---|---|
| 1 | **Descriptive Statistics** | Statistical | Mean, Median, Std, Skewness, IQR, Percentiles |
| 2 | **Exploratory Data Analysis** | Visual | Histograms, Box plots, Scatter, Pair plots |
| 3 | **Feature Engineering** | Data Prep | 7 new features created from raw columns |
| 4 | **Central Limit Theorem** | Probability | Sampling distribution demonstration |
| 5 | **Confidence Intervals** | Inferential Stats | 90%, 95%, 99% CI for mean order value |
| 6 | **t-test (One & Two-sample)** | Hypothesis Testing | Discount effect on order value |
| 7 | **One-Way ANOVA** | Hypothesis Testing | Order value differences across companies |
| 8 | **Two-Way ANOVA** | Hypothesis Testing | Company × Product_Category interaction |
| 9 | **Chi-Square Test** | Hypothesis Testing | Payment method vs discount association |
| 10 | **Pearson & Spearman Correlation** | Statistical | Feature relationship analysis |
| 11 | **Simple Linear Regression** | Predictive | Items_Count → Order_Value |
| 12 | **Multiple Linear Regression** | Predictive | Multi-feature → Order_Value + What-If |
| 13 | **Ridge & Lasso Regression** | Regularised ML | Overfitting control |
| 14 | **Decision Tree Classifier** | ML Classification | High-value order prediction |
| 15 | **Random Forest Classifier** | ML Classification | Ensemble high-value prediction |
| 16 | **XGBoost Classifier** | ML Classification | Best-performing classifier |
| 17 | **K-Means Clustering** | Unsupervised ML | 4-segment customer segmentation |
| 18 | **Moving Averages (SMA, WMA)** | Time Series | Trend smoothing |
| 19 | **Exponential Smoothing (Holt-Winters)** | Time Series | Trend + seasonality forecasting |
| 20 | **Autoregressive AR(7) Model** | Time Series | Lag-based demand forecasting |
| 21 | **Linear Programming** | Prescriptive | Delivery partner zone allocation |
| 22 | **Decision Theory (EMV, Maximax, etc.)** | Prescriptive | Optimal discount strategy selection |

---

## 👥 Customer Segments Discovered (K-Means, K=4)

### Cluster 0 — Premium Bulk Buyers (High Value, High Items)
- Average order value ~₹900 with ~9 items per order
- Longest delivery distance (~7 km) — outer zones
- **Strategy:** Offer loyalty subscriptions and priority delivery

### Cluster 1 — High-Spend, Low-Item Buyers (Premium Category)
- Average order value ~₹750 with only ~3 items
- Higher ratings (~3.8) — satisfied premium customers
- **Strategy:** Promote premium single-item categories and branded products

### Cluster 2 — Satisfied Budget Shoppers
- Average order value ~₹300 with ~5 items
- Highest customer rating (~4.2) — happiest segment
- **Strategy:** Discount bundles, combo offers, and repeat-order nudges

### Cluster 3 — Quick Low-Value Shoppers
- Average order value ~₹180 with ~2 items
- Lowest rating (~2.8) — at-risk for churn
- **Strategy:** Minimum order incentives, free delivery thresholds

---

## 🔄 Project Pipeline

```
Raw Dataset (5,91,539 rows × 13 cols)
        ↓
Data Cleaning & Validation
  ├── Missing value check (0 nulls found)
  ├── Duplicate removal
  ├── IQR outlier detection
  └── Categorical encoding
        ↓
Feature Engineering (7 new features)
  ├── Value_Per_Item
  ├── Delivery_Speed
  ├── High_Value_Order (classification target)
  ├── Age_Group
  ├── Order_Efficiency
  ├── Rating_Gap
  └── Log_Order_Value
        ↓
Descriptive Statistics + EDA
        ↓
Hypothesis Testing (5 tests)
  ├── One-Sample t-test
  ├── Independent t-test (Welch's)
  ├── One-Way ANOVA + Tukey HSD
  ├── Two-Way ANOVA
  └── Chi-Square Test
        ↓
┌─────────────────────────────────────────┐
│  Regression Models                      │
│  ├── Simple Linear Regression           │
│  ├── Multiple Linear Regression         │
│  ├── Ridge Regression (α=1.0, 10.0)     │
│  └── Lasso Regression (α=0.1, 1.0)      │
└─────────────────────────────────────────┘
        ↓
┌─────────────────────────────────────────┐
│  Classification Models                  │
│  ├── Decision Tree  (Acc ~75%, AUC 0.83)│
│  ├── Random Forest  (Acc ~78%, AUC 0.87)│
│  └── XGBoost        (Acc ~79%, AUC 0.88)│
└─────────────────────────────────────────┘
        ↓
K-Means Clustering (K=4 optimal)
  ├── Elbow Method
  ├── Silhouette Score
  └── Calinski-Harabasz Score
        ↓
Time Series Forecasting
  ├── Moving Averages (SMA-7, SMA-30, WMA-7)
  ├── ADF Stationarity Test
  ├── ACF / PACF Analysis
  ├── Seasonal Decomposition
  ├── SES → Holt's → Holt-Winters ← BEST
  └── AR(7) Autoregressive Model
        ↓
Prescriptive Analytics
  ├── Linear Programming (partner allocation)
  └── Decision Theory (EMV, Maximax, Maximin, etc.)
        ↓
Business Insights & Recommendations
```

---

## 🗒️ Notebook Sections

| Section | Description |
|---|---|
| 1 | Project Introduction & Industry Overview |
| 2 | Environment Setup & Library Installation |
| 3 | Data Loading & Structural Audit |
| 4 | Data Cleaning & Preprocessing |
| 5 | Feature Engineering (7 features) |
| 6 | Descriptive Statistics |
| 7 | Exploratory Data Analysis (EDA) |
| 8 | Delivery Performance Analysis |
| 9 | Customer Experience Analysis |
| 10 | Correlation & Covariance Analysis |
| 11 | Probability Theory & Hypothesis Testing |
| 12 | Regression Analysis + What-If Scenarios |
| 13 | Decision Tree Classification |
| 14 | Random Forest & XGBoost Classification |
| 15 | K-Means Clustering |
| 16 | Time Series Forecasting |
| 17 | Prescriptive Analytics |
| 18 | Business Insights |
| 19 | Business Recommendations |
| 20 | Conclusion & Summary |

---

## ⚙️ Setup & Usage

### Prerequisites
- Python 3.10+
- Google Account (for Colab)
- Kaggle account (to download dataset)

### Step 1 — Open in Google Colab

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/)

Go to [colab.research.google.com](https://colab.research.google.com), click **File → Upload Notebook**, and select `quick_commerce_analytics.ipynb`.

### Step 2 — Download the Dataset

Download from [Kaggle](https://www.kaggle.com/datasets/rohitgrewal/quick-commerce-dataset) and upload the CSV to your Colab session:

```python
from google.colab import files
uploaded = files.upload()
```

Or mount Google Drive and load:

```python
from google.colab import drive
drive.mount('/content/drive')
df = pd.read_csv('/content/drive/MyDrive/quick_commerce_dataset.csv')
```

### Step 3 — Install Dependencies

The first notebook cell handles installation:

```bash
pip install xgboost statsmodels
```

All other libraries (pandas, numpy, scikit-learn, matplotlib, seaborn, scipy) are pre-installed on Colab.

### Step 4 — Run All

```
Runtime → Run All (Ctrl+F9)
```

---

## 📦 Dependencies

```txt
# Install in Colab (only these 2 needed — rest are pre-installed)
xgboost>=1.7.0
statsmodels>=0.14.0

# Pre-installed on Google Colab
pandas>=1.5.0
numpy>=1.23.0
matplotlib>=3.6.0
seaborn>=0.12.0
scikit-learn>=1.2.0
scipy>=1.10.0
```

---

## 📈 Key Findings

### Hypothesis Testing Results

```
Test 1 — One-Sample t-test        : p < 0.05 → Mean order value ≠ ₹500 ✗ H₀ rejected
Test 2 — Independent t-test       : p < 0.05 → Discounts increase order value ✗ H₀ rejected
Test 3 — One-Way ANOVA            : p < 0.05 → Companies differ in order value ✗ H₀ rejected
Test 4 — Chi-Square Test          : p < 0.05 → Payment ↔ Discount associated ✗ H₀ rejected
Test 5 — Two-Way ANOVA            : p < 0.001 → Company × Category interaction ✗ H₀ rejected
```

### Top Predictors of Order Value

```
1. Items_Count        (r = +0.82) ← Strongest predictor
2. Value_Per_Item     (r = +0.75) ← Basket quality signal
3. Delivery_Speed     (r = −0.55) ← Operational proxy
4. Distance_Km        (r = +0.40) ← Moderate positive
5. Customer_Rating    (r = +0.02) ← Near-zero impact
```

### SLA Compliance

```
Delivered within 30 min : ~50%  ← SLA target
Delivered within 45 min : ~75%
Delivered within 60 min : ~95%
Average delivery time   : ~30 min
```

### Classification Model Comparison

```
Decision Tree  → Accuracy: ~75%  |  AUC: ~0.83
Random Forest  → Accuracy: ~78%  |  AUC: ~0.87
XGBoost        → Accuracy: ~79%  |  AUC: ~0.88  ← BEST
```

---

## 🎯 Business Recommendations

| Area | Priority | Key Action |
|---|---|---|
| Inventory Planning | 🟢 HIGH | Pre-stock top SKUs Fri–Sat; bundle promotions for 8+ item orders |
| Delivery Optimisation | 🟢 HIGH | Open dark stores in SLA-breach zones; target <3 km radius |
| Pricing & Discounts | 🔵 MEDIUM | Deploy 5% discount for orders ≥5 items (EMV optimal strategy) |
| Customer Experience | 🔵 MEDIUM | Set 25-min internal SLA; invest in partner training |
| Marketing Strategy | ⚪ ONGOING | Design campaigns per cluster; use ML for priority queuing |

---

## 📊 Syllabus Coverage

| Unit | Topic | Sections Covered |
|---|---|---|
| Unit 1 | Data Analytics overview, lifecycle, descriptive stats, plots | 1, 3, 4, 5, 6, 7 |
| Unit 2 | Probability, CLT, sampling, hypothesis testing, ANOVA, correlation | 8, 9, 10, 11 |
| Unit 3 | Regression, classification, clustering | 12, 13, 14, 15 |
| Unit 4 | Time series, forecasting, optimisation, decision theory | 16, 17 |

---

## 👨‍💻 Author

**Aditya Manoj** — Data Cleaning, Feature Engineering, Statistical Analysis, ML Modelling, Time Series, Business Insights

---

## 📄 License

This project is licensed under the MIT License — see the [LICENSE](./LICENSE) file for details.

---

## 🙏 Acknowledgements

- **Rohit Grewal** for the Quick-Commerce dataset on Kaggle
- **Scikit-learn** for ML algorithms
- **Statsmodels** for statistical modelling and time series
- **XGBoost** for gradient boosting classification
- **Google Colab** for free GPU/TPU compute

---

*Built with ❤️ using Google Colab + Python + Scikit-learn*
