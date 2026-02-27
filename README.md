# 🏦 Bank Customer Churn Analysis
### Built with Power BI and DAX

---

## 📊 Dashboard Overview
![Dashboard](/Bank-Customer-Churn-Analysis_PowerBI/Dashboard/Bank_customer_churn_report_screenshot.jpeg
)

---

## 📌 Project Overview
Analyzed customer churn patterns for a retail bank 
dataset of 10,000 customers across France, Germany, 
and Spain to identify key drivers of customer attrition 
and provide actionable retention insights.

| Detail | Info |
|---|---|
| Dataset | Bank Customer Churn (Kaggle) |
| Tool | Power BI Desktop |
| Dataset Size | 10,000 customers, 12 variables |
| Overall Churn Rate | 20.38% |

--

## ❓ Business Problem
The bank is losing 1 in 5 customers with an overall 
churn rate of 20.38%. The analysis aims to answer:

- Which customer segments are at highest churn risk?
- What behavioral and demographic factors predict churn?
- Where should the bank focus its retention efforts?

---

## 🔍 Key Insights

**1. Age is a strong churn predictor**
Customers aged 46-60 churn at 51% — more than 6x 
the rate of 18-30 year olds (8%)

**2. Number of products is the strongest predictor**
Customers with 2 products have the lowest churn 
at just 8%. Customers with 3-4 products churn at 
83-100% — a critical and counterintuitive red flag 
suggesting possible product overselling

**3. Inactive members are high risk**
Inactive members churn at 27% versus 14% for active 
members — nearly double the rate

**4. Germany needs urgent attention**
German customers churn at 32%, double the rate of 
France (16%) and Spain (17%)

**5. Balance shows a U-shaped churn pattern**
Low balance customers (1-50k) churn at 35% and 
Very High balance customers (200k+) churn at 56%, 
while Medium balance customers are most stable at 20%

**6. Gender gap exists**
Female customers churn at 25% versus 16% for males —
a 9 percentage point difference worth investigating

**7. Credit card ownership is a surprising predictor**
Customers without a credit card churn at 27% versus 
14% for credit card holders — suggesting product 
engagement reduces attrition risk

---

## 📉 Variables Investigated But Excluded

| Variable | Finding |
|---|---|
| Credit Score | Less than 3% variation across all bands (18.65% to 21.75%) |
| Estimated Salary | Less than 2% variation across all bands (19.87% to 21.44%) |
| Tenure | No consistent directional pattern (18.87% to 21.30%) |

> Excluding weak predictors is a conscious analytical 
decision — a dashboard should show actionable insights, 
not every variable in the dataset.

---

## 💡 Business Recommendations

1. **Target 46-60 age group in Germany** with dedicated 
   retention campaigns — highest risk intersection 
   of age and geography

2. **Investigate 3-4 product customers immediately** — 
   83-100% churn rate despite deeper product engagement 
   suggests serious product dissatisfaction or overselling

3. **Re-engage inactive members** — 27% churn rate 
   is directly addressable through targeted 
   outreach programs

4. **Review premium services for Very High balance 
   customers** — 56% churn rate among wealthiest 
   customers suggests significantly unmet expectations

5. **Encourage credit card adoption** — credit card 
   holders churn at nearly half the rate of 
   non-holders (14% vs 27%)

---

## 🛠️ Technical Details

**DAX Measures Written:**
- Churn Rate % = DIVIDE(TotalChurned, TotalCustomers)
- Total Churned = CALCULATE(DISTINCTCOUNT(CustomerID), Exited = 1)
- Total Retained = CALCULATE(DISTINCTCOUNT(CustomerID), Exited = 0)
- Total Customers = DISTINCTCOUNT(CustomerID)

**Calculated Columns Created:**
- Age Group — 4 segments using SWITCH(TRUE())
- Balance Group — 5 segments using SWITCH(TRUE())
- Credit Score Group — industry standard bands
- Salary Group — 4 segments using SWITCH(TRUE())
- Tenure Group — 4 segments using SWITCH(TRUE())
- Churn Status — Churned / Retained labels

**Dashboard Features:**
- Conditional formatting highlighting high churn segments in red
- Interactive slicers for Credit Card and Active Status
- Data labels on all visuals for precise reading
- Matrix tables for non-significant variables

---

## 📁 Repository Structure

Bank-Customer-Churn-analysis-By-Shashank-Ojha/
│
├── Cleaned Dataset/
│   ├── Cleaned data screenshot-1.jpeg
│   ├── Cleaned data screenshot-2.jpeg
│   └── Cleaned data screenshot-3.jpeg
│   
├── Dashboard/
│   ├── Bank-Churn-by-Shashank-Ojha.pbix
│   ├── Bank_customer_churn_report_by_Shashank_Ojha 
│   └── Bank_customer_churn_report_screenshot.jpeg
│      
│
├── Raw Dataset/
│   └── Bank_Churn_Messy.csv
│
└── README.md

---

## 📖 Data Dictionary

| Column | Description | Type |
|---|---|---|
| CustomerID | Unique identifier | Integer |
| CreditScore | Credit score 300-850 | Integer |
| Geography | Customer country | Text |
| Gender | Customer gender | Text |
| Age | Age in years | Integer |
| Tenure | Years with bank | Integer |
| Balance | Account balance euros | Decimal |
| NumOfProducts | Bank products held | Integer |
| HasCrCard | Credit card 1=Yes 0=No | Binary |
| IsActiveMember | Active 1=Yes 0=No | Binary |
| EstimatedSalary | Annual salary euros | Decimal |
| Exited | Churned 1=Yes 0=No | Binary |

---

## 📂 Data Source
Dataset sourced from Kaggle —Bank Customer Churn Dataset
Used for educational and portfolio purposes only.
