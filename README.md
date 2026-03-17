# Customer Segmentation using RFM Modeling and CLV Analysis

A data science project performing end-to-end customer segmentation on the **Sample Superstore dataset** using **RFM (Recency, Frequency, Monetary) Analysis** and **Customer Lifetime Value (CLV)** modeling to identify high-value customer cohorts and drive targeted marketing strategy.

---

## Key Results

| Metric | Value |
|---|---|
| Total Customers Analysed | 793 |
| Champions Identified | 81 (10.2%) |
| At-Risk Customers | 132 (16.7%) |
| Top 20% of customers | Drive **48% of total CLV** |
| Mean CLV | ₹43.8 |
| Max CLV | ₹378.9 |

---

## Project Overview

This project combines two powerful customer analytics frameworks:

- **RFM Analysis** — Descriptive segmentation based on past purchasing behaviour (Recency, Frequency, Monetary value)
- **CLV Analysis** — Predictive estimation of total future revenue a customer brings over their relationship with the business

Together they provide a **360° view** of customer behaviour — capturing both past actions and future potential.

---

## Dataset

- **Source:** Sample Superstore Dataset
- **Features:** Order ID, Customer ID, Order Date, Sales, Quantity, Discount, Profit, Region, Category

---

## Methodology

### RFM Analysis
1. Group transactions by Customer ID
2. Calculate:
   - **Recency** — Days since last purchase
   - **Frequency** — Total number of orders
   - **Monetary** — Total spend
3. Apply quantile scoring (1–5) for each dimension
4. Combine R_Score, F_Score, M_Score into a single RFM Score
5. Classify customers using regex-based segment rules

### RFM Segmentation Rules

| Segment | RFM Pattern | Description |
|---|---|---|
| Champions | `^[4-5][4-5][4-5]$` | Recent, frequent, high spenders — most valuable customers |
| Loyal Customers | `^[3-5][3-5][3-5]$` | Frequent buyers with moderate-to-high spending |
| Potential Loyalists | `^[2-4][2-4][2-4]$` | Promising behaviour — need nurturing |
| At-Risk Customers | `^[1-3][1-3][1-3]$` | Haven't purchased recently, low frequency and spend |

### CLV Calculation
```
CLV = Average Order Value × Purchase Frequency × Customer Lifespan

where:
  Average Order Value = Total Sales / Order Count
  Frequency = Orders per Customer
```

---

## Key Insights

**RFM Segmentation:**
- **81 Champions** (10.2%) — Avg CLV ₹80.8 → Ideal for upselling and loyalty rewards
- **132 At-Risk** (16.7%) — Previously active, now dormant → Target for reactivation campaigns
- **14 Loyal Customers** (1.8%) — Avg CLV ₹34.3 → Cross-sell to increase value

**CLV Analysis:**
- Top **20% of customers contribute 48% of total CLV** — classic Pareto distribution confirmed
- Mean CLV: ₹43.8 | Median: ₹34.1 | 75th Percentile: ₹57.3 | Max: ₹378.9
- CLV distribution is right-skewed — majority have low CLV with a few high-value outliers

---

## Strategic Recommendations

1. **Retain Champions** — Loyalty programmes, early-access offers, premium support
2. **Personalised Marketing** — Targeted messaging for Champions and Loyal segments
3. **Win-back Campaigns** — Limited-time offers for At-Risk customers
4. **Quarterly Re-segmentation** — Refresh RFM and CLV regularly to capture evolving behaviour
5. **CLV-Guided Budget Allocation** — Focus retention where long-term value is highest

---

## Tech Stack

- **Python 3** | **Pandas** | **NumPy** | **Matplotlib** | **Seaborn** | **Scikit-learn** | **Jupyter Notebook**

---

## File Structure

```
customer-segmentation/
├── RFM_Data_Analysis.ipynb    # Main analysis notebook
├── README.md                  # Project documentation
└── data/
    └── superstore.csv         # Sample Superstore dataset
```

---

## How to Run

```bash
git clone https://github.com/Faiz1314/customer-segmentation
cd customer-segmentation
pip install pandas numpy matplotlib seaborn scikit-learn jupyter
jupyter notebook RFM_Data_Analysis.ipynb
```

---

## Author

**Ali Faiz Khan**  
[LinkedIn](https://linkedin.com/in/ali-faiz-khan-44a50b30b) | [GitHub](https://github.com/Faiz1314)
