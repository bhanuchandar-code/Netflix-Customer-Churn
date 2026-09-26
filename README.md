# 🎬 Netflix Customer Churn Data Analysis

> **Author:** Alyana Bhanu Chandar  
> **Tools:** Python · Pandas · NumPy · Matplotlib · Seaborn · Jupyter Notebook

---

## 📌 Project Description

Customer churn — when a subscriber cancels or stops using a service — is one of the most critical challenges for subscription-based streaming platforms like Netflix. Retaining an existing customer is significantly more cost-effective than acquiring a new one, making churn prediction and prevention a high-priority business goal.

This project performs a complete, beginner-friendly **Exploratory Data Analysis (EDA)** on a Netflix Customer Churn dataset of **5,000 customer records** across **14 features**. The analysis uncovers behavioural and demographic patterns that distinguish churned customers from active ones, and translates those patterns into actionable business insights.

---

## 🎯 Objectives

- Understand the structure, data types, and quality of the dataset
- Clean the data and engineer new features for richer analysis
- Analyse the distribution of each feature individually (univariate analysis)
- Compare churned vs. active customers across all key variables (bivariate analysis)
- Compute churn rates by customer segment (subscription type, region, device, payment method, etc.)
- Build visualisations that communicate patterns clearly and intuitively
- Extract actionable business insights and propose next steps

---

## 📂 Dataset

| Property | Detail |
|---|---|
| **File** | `netflix_customer_churn.csv` |
| **Records** | 5,000 customers |
| **Features** | 14 columns |
| **Target Variable** | `churned` (1 = churned, 0 = active) |
| **Missing Values** | None |
| **Source** | [Kaggle — Netflix Customer Churn Dataset](https://www.kaggle.com/datasets/abdulwaheedahmad/netflix-customer-churn) |

### Column Summary

| Column | Type | Description |
|---|---|---|
| `customer_id` | String | Unique UUID — dropped before analysis |
| `age` | Integer | Customer age (18 – 70) |
| `gender` | Categorical | Female / Male / Other |
| `subscription_type` | Categorical | Basic / Standard / Premium |
| `watch_hours` | Float | Total hours watched |
| `last_login_days` | Integer | Days since last login (0 – 60) |
| `region` | Categorical | Africa / Asia / Europe / North America / Oceania / South America |
| `device` | Categorical | Desktop / Laptop / Mobile / Tablet / TV |
| `monthly_fee` | Float | Subscription fee in USD (8.99 / 13.99 / 17.99) |
| `churned` | Integer (0/1) | **Target** — 1 = churned, 0 = active |
| `payment_method` | Categorical | Credit Card / Crypto / Debit Card / Gift Card / PayPal |
| `number_of_profiles` | Integer | Profiles on the account (1 – 5) |
| `avg_watch_time_per_day` | Float | Average hours watched per day |
| `favorite_genre` | Categorical | Action / Comedy / Documentary / Drama / Horror / Romance / Sci-Fi |

---

## 🛠️ Technologies Used

| Library | Version | Purpose |
|---|---|---|
| Python | 3.x | Core programming language |
| Pandas | 3.0.1 | Data loading, cleaning, manipulation |
| NumPy | 2.4.3 | Numerical operations and array handling |
| Matplotlib | 3.11.2 | Base plotting engine |
| Seaborn | 0.13.2 | Statistical visualisations |
| Jupyter Notebook | 1.1.1 | Interactive analysis environment |

---

## 🗂️ Project Structure

```
netflix-churn-analysis/
│
├── netflix_customer_churn.csv                    # Raw dataset
├── Alyana_Bhanu_Chandar_NetflixCustomerChurn.ipynb  # Main analysis notebook
├── Alyana_Bhanu_Chandar_ProjectReport.docx       # Full written project report
├── requirements.txt                              # Python dependencies
└── README.md                                     # Project overview (this file)
```

---

## ⚙️ Setup & Run Instructions

### 1. Clone or Download the Repository

```bash
git clone https://github.com/your-username/netflix-churn-analysis.git
cd netflix-churn-analysis
```

### 2. (Recommended) Create a Virtual Environment

```bash
python -m venv venv

# Activate on Windows
venv\Scripts\activate

# Activate on macOS / Linux
source venv/bin/activate
```

### 3. Install Dependencies

```bash
pip install -r requirements.txt
```

### 4. Launch the Jupyter Notebook

```bash
jupyter notebook Alyana_Bhanu_Chandar_NetflixCustomerChurn.ipynb
```

> Make sure `netflix_customer_churn.csv` is in the **same folder** as the notebook before running.

### 5. Run All Cells

In Jupyter: **Kernel → Restart & Run All** to execute the full analysis from top to bottom.

---

## 🔍 Analysis Steps

The notebook follows this structured pipeline:

| Step | Section | What Happens |
|---|---|---|
| 1 | Import Libraries | Load pandas, numpy, matplotlib, seaborn |
| 2 | Load Dataset | Read CSV, preview shape and first/last rows |
| 3 | Data Overview | `.info()`, missing values, duplicates, descriptive stats |
| 4 | Data Cleaning | Drop `customer_id`, validate ranges, engineer 3 new features |
| 5 | EDA — Distributions | Histograms, bar charts for all 14 features |
| 6 | EDA — Feature vs Churn | Box plots, violin plots, KDE plots comparing churned vs active |
| 7 | Correlation Heatmap | Pearson correlations between all numeric features and churn |
| 8 | Churn Rate by Segment | Bar charts showing churn % per category with overall reference line |
| 9 | Key Insights | Summary statistics table + top-churn segment finder |
| 10 | Conclusion | Findings recap and recommended next steps |

---

## 💡 Key Insights

| # | Insight | Value |
|---|---|---|
| 1 | **Overall churn rate** | 50.3% (2,515 of 5,000 customers churned) |
| 2 | **Strongest churn signal** | Inactivity >30 days → **75.1% churn rate** |
| 3 | **Highest churn by plan** | Basic ($8.99) → **61.8% churn rate** |
| 4 | **Highest churn by payment** | Crypto → **59.7% churn rate** |
| 5 | **Engagement gap** | Active customers watch **10×** more per day (1.59 hrs vs 0.16 hrs) |
| 6 | **Gender & region** | Minimal impact — all rates within ±3% of the overall average |
| 7 | **No single predictor** | All numeric feature correlations with churn are weak (|r| < 0.15) |

> **Top business takeaway:** Customers who haven't logged in for more than 30 days are the highest-priority re-engagement target — 3 in 4 will churn without intervention.

---

## ✅ Conclusion

This project demonstrates the full EDA pipeline applied to a real-world business problem using Python. Key conclusions:

- **Churn is multi-dimensional** — no single feature drives it; a combination of inactivity, low engagement, and low-tier subscription best characterises at-risk customers.
- **Inactivity is the most actionable signal** — a login-inactivity alert at 20+ days could intercept the majority of churn events before they happen.
- **The groundwork is laid for machine learning** — the cleaned dataset and feature insights provide a solid foundation for training a Logistic Regression, Random Forest, or XGBoost churn classifier.

---

## 🚀 Future Scope

- [ ] Train a machine learning classification model (Random Forest / XGBoost)
- [ ] Build a real-time churn scoring dashboard (Streamlit / Plotly Dash)
- [ ] Design A/B tests for re-engagement campaigns targeting inactive users
- [ ] Apply customer segmentation using K-Means clustering
- [ ] Integrate time-series analysis once subscription timestamp data is available

---

## 📎 Project Files

| File | Description |
|---|---|
| [`Alyana_Bhanu_Chandar_NetflixCustomerChurn.ipynb`](Alyana_Bhanu_Chandar_NetflixCustomerChurn.ipynb) | Complete annotated Jupyter Notebook |
| [`Alyana_Bhanu_Chandar_ProjectReport.docx`](Alyana_Bhanu_Chandar_ProjectReport.docx) | Full 14-section written project report |
| [`netflix_customer_churn.csv`](netflix_customer_churn.csv) | Raw dataset (5,000 rows × 14 columns) |
| [`requirements.txt`](requirements.txt) | Python package dependencies |

---

## 👩‍💻 Author

**Alyana Bhanu Chandar**  
Data Analysis Project — Netflix Customer Churn  
*Built with Python, Pandas, NumPy, Matplotlib, and Seaborn*

---

*© 2025 Alyana Bhanu Chandar. For educational and portfolio purposes.*
