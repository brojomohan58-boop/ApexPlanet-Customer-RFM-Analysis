<div align="center">

# 📊 ApexPlanet Sales & Customer Analytics Capstone

### End-to-End Data Analytics Case Study

![Python](https://img.shields.io/badge/Python-3.11-blue?style=for-the-badge&logo=python)
![Pandas](https://img.shields.io/badge/Pandas-Data%20Analysis-150458?style=for-the-badge&logo=pandas)
![NumPy](https://img.shields.io/badge/NumPy-Numerical%20Computing-013243?style=for-the-badge&logo=numpy)
![SQL](https://img.shields.io/badge/SQL-Analytics-blue?style=for-the-badge)
![BigQuery](https://img.shields.io/badge/Google%20BigQuery-SQL-4285F4?style=for-the-badge&logo=googlecloud)
![Power BI](https://img.shields.io/badge/Power%20BI-Interactive%20Dashboard-F2C811?style=for-the-badge&logo=powerbi)
![SciPy](https://img.shields.io/badge/SciPy-Statistics-8CAAE6?style=for-the-badge)
![Matplotlib](https://img.shields.io/badge/Matplotlib-Visualization-orange?style=for-the-badge)
![Seaborn](https://img.shields.io/badge/Seaborn-Visualization-4C72B0?style=for-the-badge)
![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-F37626?style=for-the-badge&logo=jupyter)
![GitHub](https://img.shields.io/badge/GitHub-Portfolio-black?style=for-the-badge&logo=github)

**A portfolio-grade end-to-end sales and customer analytics case study**

**Author:** Brojo Mohan Dutta

</div>

---

# 📌 Project Overview

This project is an end-to-end **Sales & Customer Analytics Capstone** demonstrating how raw transactional data can be transformed into reliable business intelligence, customer-level insights, statistical evidence, and actionable recommendations.

The analytical lifecycle is:

**Raw Data → Data Quality → Transformation → SQL Analytics → Python EDA → RFM Segmentation → Interactive BI → Statistical Validation → Business Recommendations**

The analysis uses a **1,000-record transactional sales dataset** covering **January 2025 to January 2026**.

---

# 🎯 Business Objectives

The project answers four core business questions:

1. What is driving revenue and sales performance?
2. Which products, categories, cities, and customers contribute the most value?
3. Which customer segments represent retention or revenue-at-risk opportunities?
4. Which observed demographic patterns are statistically supported by evidence?

The final outcome is a **decision-oriented analytics product**, not simply a collection of charts.

---

# 📊 Executive Snapshot

| Metric | Result |
|---|---:|
| Total Revenue | **₹139.4M** |
| Total Orders | **1,000** |
| Unique Customers | **947** |
| Average Order Value | **₹139K** |
| Top Category | **Electronics — 36.4% of revenue** |
| Top City by Revenue | **Patna — ₹19.29M** |
| Average RFM Score | **7.50 / 12** |
| At-Risk Revenue Exposure | **₹35.4M** |
| Potential Loyalist Revenue | **₹40.6M** |

---

# 🧭 Analytical Workflow

```text
                    RAW TRANSACTION DATA
                            │
                            ▼
                 ┌─────────────────────┐
                 │ Data Quality &      │
                 │ Data Preparation    │
                 └──────────┬──────────┘
                            ▼
                 ┌─────────────────────┐
                 │ Transformation &    │
                 │ Feature Engineering │
                 └──────────┬──────────┘
                            │
                ┌───────────┴───────────┐
                ▼                       ▼
        ┌───────────────┐       ┌────────────────┐
        │ SQL Analytics │       │ Python EDA     │
        │   BigQuery    │       │ Statistics &   │
        └───────┬───────┘       │ Visualization  │
                │               └───────┬────────┘
                └──────────┬────────────┘
                           ▼
                ┌─────────────────────┐
                │ Customer RFM        │
                │ Segmentation        │
                └──────────┬──────────┘
                           ▼
                ┌─────────────────────┐
                │ Interactive Power BI│
                │ Decision Dashboard  │
                └──────────┬──────────┘
                           ▼
                ┌─────────────────────┐
                │ Statistical        │
                │ Validation          │
                └──────────┬──────────┘
                           ▼
                ┌─────────────────────┐
                │ Business Insights & │
                │ Recommendations     │
                └─────────────────────┘
```

---

# 🔎 1. Data Preparation & Quality Engineering

The original dataset contains **1,000 transactions and 12 source columns**.

## Data Quality Findings

| Issue | Finding |
|---|---:|
| Missing Age | 20 records — 2.0% |
| Missing City | 13 records — 1.3% |
| Full-row duplicates | 0 |
| Order ID collision | 9 rows |
| Order Date stored as text | 1,000 rows |
| IQR outliers | 0 detected |

The nine rows sharing `ORD100050` were treated as distinct transactions rather than deleted as duplicates. Unique surrogate identifiers were assigned while preserving the original identifier for auditability.

## Data Preparation

- Missing-value treatment
- Date standardization
- Order ID reconciliation
- Duplicate validation
- Age-group creation
- Year/month feature extraction
- Average-price reconciliation
- Clean CSV export

**Output:** `cleaned_sales_dataset.csv`

---

# 📈 2. SQL Business Analytics & Exploratory Analysis

Google BigQuery SQL was used to answer business questions around revenue, products, categories, cities, customers, and monthly growth.

## Business Questions

- How does revenue change month over month?
- Which products generate the most revenue?
- Which categories contribute the most revenue?
- Which cities drive revenue and orders?
- How does purchasing behavior vary across demographics?
- Who are the highest-value customers?
- Which categories are growing or declining?

## SQL Techniques

- CTEs
- Aggregations
- `GROUP BY`
- `COUNT(DISTINCT)`
- Date functions
- `DATE_TRUNC`
- Window functions
- `LAG`
- Month-over-month growth
- KPI calculations

## Key Findings

- March 2025 peaked at approximately **₹13.06M** in full-month revenue.
- September 2025 recorded approximately **₹9.18M**, the lowest full-month revenue.
- January 2026 is a partial month and is not treated as a genuine decline.
- Electronics generated **₹50.78M / 36.43%** of revenue.
- Patna recorded the highest city revenue at approximately **₹19.29M**.

---

# 📊 3. Python Multivariate EDA

The Python analysis examined relationships among:

- Age
- Quantity
- Unit Price
- Total Sales
- Category
- Gender
- City
- Age Group

## Visualizations

- Correlation matrix
- Pair plot
- Age vs. Total Sales scatter plot
- Quantity vs. Unit Price scatter plot
- City × Category AOV heatmap
- Age Group × Category AOV heatmap
- Category × Gender box plots
- Static executive dashboard

## Key Findings

`Total_Sales` correlated most strongly with:

- `Unit_Price`: **r = 0.69**
- `Quantity`: **r = 0.65**

Age showed negligible linear relationships with the transactional variables.

The City × Category analysis indicated that category differences in AOV were more pronounced than geographic differences in many combinations.

---

# 👥 4. Customer Analytics & RFM Segmentation

The project moves from transaction-level reporting to customer-level analysis using **RFM — Recency, Frequency and Monetary value**.

### Recency
Days since the customer's most recent purchase.

### Frequency
Number of distinct purchases.

### Monetary
Total historical customer spending.

RFM scores were created using quartile-based `NTILE(4)` logic.

```text
RFM Total = Recency Score + Frequency Score + Monetary Score
```

Score range: **3–12**

## Customer Segments

| Segment | Customers | Revenue |
|---|---:|---:|
| Potential Loyalist | 244 | ₹40.6M |
| At Risk | 238 | ₹35.4M |
| Loyal Customers | 200 | ₹29.2M |
| New / Recent | 111 | ₹15.7M |
| Champions | 35 | ₹12.3M |
| Lost | 119 | ₹6.2M |

### Customer Insight

Potential Loyalists are the largest revenue-contributing segment, while At-Risk customers represent a substantial revenue exposure.

Champions are smaller in population but have the highest average monetary value.

---

# 📊 5. Interactive Power BI Analytics

The Power BI reporting layer turns the analysis into an interactive decision-support dashboard.

## Executive Overview

Includes:

- Total Revenue
- Total Orders
- Average Order Value
- Top Category
- Monthly Revenue & Order Trend
- Revenue by Category
- Revenue by City
- City × Category AOV analysis

**Filters:** Month, City, Gender, Age Group

## Customer Segmentation Deep-Dive

Includes:

- Champions count
- At-Risk count
- Lost count
- Average RFM Score
- Segment Distribution
- Segment Revenue Contribution
- Customer Value vs. Recency
- Segment × City Heatmap

**Filters:** Customer Segment, City, Gender, Age Group

The dashboard also supports customer-level drill-through.

---

# 🧮 Core Power BI / DAX Measures

```DAX
Total Revenue =
SUM('cleaned_sales-data'[Total_Sales])
```

```DAX
Total Orders =
DISTINCTCOUNT('cleaned_sales-data'[Order_ID])
```

```DAX
AOV =
DIVIDE([Total Revenue], [Total Orders], 0)
```

```DAX
Total Customers =
DISTINCTCOUNT('customer_rfm_segments'[Customer_ID])
```

```DAX
Champions Count =
CALCULATE(
    [Total Customers],
    Customer_Segment = "Champions"
)
```

```DAX
At Risk Count =
CALCULATE(
    [Total Customers],
    Customer_Segment = "At Risk"
)
```

```DAX
Avg RFM Score =
AVERAGE(customer_rfm_segments[RFM_Total])
```

---

# 🧪 6. Statistical Validation

Two hypotheses were tested to distinguish visible patterns from statistically supported relationships.

## Hypothesis 1 — Gender & Spending

**H₀:** Mean spending is equal between male and female customers.

**Test:** Independent two-sample t-test.

| Statistic | Result |
|---|---:|
| Male mean | ₹141,807.34 |
| Female mean | ₹136,883.21 |
| Mean difference | ₹4,924.13 |
| t-statistic | 0.6820 |
| p-value | 0.495389 |
| 95% CI | −₹9,214.68 to ₹19,062.94 |

At α = 0.05, the analysis **failed to reject H₀**.

**Business interpretation:** The observed gender spending difference was not statistically significant in this dataset.

---

# 📐 Hypothesis 2 — Age Group & Category Preference

**H₀:** Age Group and Category are independent.

**Test:** Chi-Square test of independence.

| Statistic | Result |
|---|---:|
| χ² statistic | 10.5361 |
| Degrees of freedom | 16 |
| p-value | 0.837174 |
| Cramér's V | 0.0513 |

At α = 0.05, the analysis **failed to reject H₀**.

**Business interpretation:** Age group did not demonstrate a statistically significant association with category preference in this dataset.

---

# 💡 Key Business Insights

### Electronics is the primary revenue engine

Electronics contributes approximately **36.4% of total revenue**, creating both a strong revenue base and a category concentration risk.

### At-Risk customers represent a meaningful retention opportunity

The At-Risk segment is associated with approximately **₹35.4M** in revenue.

### Potential Loyalists represent the largest segment-level revenue pool

Potential Loyalists contribute approximately **₹40.6M**, making re-engagement an important customer-growth opportunity.

### Champions are small but valuable

Only **35 customers** are classified as Champions, but they contribute approximately **₹12.3M** and have the highest average monetary value.

### Demographic assumptions require evidence

Neither gender-based spending nor age-group/category association was statistically significant in the tested sample.

### Behavioral segmentation is more actionable

The combined analysis supports using customer lifecycle and purchasing behavior, such as RFM, alongside—not simply demographic assumptions.

---

# 🎯 Business Recommendations

| Business Area | Recommended Direction |
|---|---|
| At-Risk Customers | Win-back and reactivation campaigns |
| Potential Loyalists | Loyalty and re-engagement programs |
| Champions | VIP retention and personalized offers |
| New / Recent | Encourage second purchase |
| Electronics | Protect leadership while diversifying |
| Geographic AOV | Investigate high-value city × category combinations |
| Demographics | Avoid over-targeting based solely on age or gender |

---

# 🔍 Data Model Reconciliation

A reconciliation check was performed between the sales and RFM datasets.

| Validation | Result |
|---|---:|
| Cleaned Sales Revenue | ₹139,399,439.65 |
| RFM Monetary Total | ₹139,399,439.65 |
| Revenue Match | **100% exact** |
| RFM Frequency | 1,000 distinct orders |
| Cleaned Sales Orders | 1,000 |

This confirms that the customer-level RFM pipeline preserved the underlying sales value.

---

# 🧠 Technical Skills Demonstrated

## Languages

- Python
- SQL
- DAX

## Data Analysis

- Pandas
- NumPy
- Data cleaning
- Data validation
- Feature engineering
- Data reconciliation
- Aggregation

## Business Analytics

- KPI development
- Revenue analysis
- Product/category analysis
- Geographic analysis
- Customer analytics
- RFM segmentation
- Business storytelling

## Statistics

- Independent two-sample t-test
- Chi-Square test of independence
- Shapiro-Wilk test
- Levene's test
- Confidence intervals
- Cramér's V
- Statistical significance

## Visualization & BI

- Power BI
- DAX
- Matplotlib
- Seaborn
- Interactive dashboards
- Heatmaps
- Scatter plots
- Box plots
- Treemaps
- KPI cards

## Tools

- Google BigQuery
- Jupyter Notebook
- Git
- GitHub

---

# 📁 Repository Structure

```text
BrojoMohanDutta-Data-Analytics-Capstone/
│
├── 01_Data_Wrangling/
│   ├── 01_data/
│   │   ├── ApexPlanet_DataAnalytics_Dataset.xlsx
│   │   └── cleaned_sales_dataset.csv
│   ├── 02_notebook/
│   │   ├── Data_Wrangling.ipynb
│   │   └── Data_Wrangling.py
│   └── 03_report/
│       ├── Data_Wrangling_Report.docx
│       └── Data_Wrangling_Report.pdf
│
├── 02_EDA_Business_Intelligence/
│   ├── 01_sql/
│   │   └── EDA_BI_SQL_Queries.sql
│   ├── 02_python/
│   │   ├── Multivariate_EDA_Dashboard.ipynb
│   │   └── Multivariate_EDA_Dashboard.py
│   ├── 03_visuals/
│   │   ├── 01_chart_correlation_heatmap.png
│   │   ├── 02_chart_pairplot_category.png
│   │   ├── 03_chart_scatter_age_sales.png
│   │   ├── 04_chart_scatter_qty_price.png
│   │   ├── 05_chart_heatmap_city_category.png
│   │   ├── 06_chart_heatmap_age_category.png
│   │   ├── 07_chart_boxplot_category_gender.png
│   │   └── dashboard_mockup.png
│   └── 04_data/
│       └── sales_dataset_python_analysis.csv
│
├── 03_RFM_PowerBI/
│   ├── 01_data/
│   │   └── customer_rfm_segments.csv
│   ├── 02_power_bi/
│   │   └── Apexplanet_Sales_Customer_Analysis.pbix
│   ├── 03_dashboards/
│   │   ├── Executive_Overview.jpg
│   │   └── Customer_Segmentation.jpg
│   └── 04_report/
│       ├── Deep-Dive_Analysis_Interactive_Dashboard.docx
│       └── Deep-Dive_Analysis_Interactive_Dashboard.pdf
│
├── 04_Hypothesis_Testing/
│   ├── 01_notebook/
│   │   ├── Hypothesis_Testing_Statistical_Inference.ipynb
│   │   └── Hypothesis_Testing_Statistical_Inference.py
│   ├── 02_report/
│   │   └── Hypothesis_Testing_Statistical_Inference_Report.pdf
│   └── 02_visuals/
│       ├── hypothesis1_gender_analysis.png
│       └── hypothesis2_age_category_analysis.png
│
├── 05_Final_Deliverables/
│   ├── 01_presentation/
│   │   ├── ApexPlanet_Capstone_Presentation.pptx
│   │   └── ApexPlanet_Capstone_Presentation.pdf
│   └── 02_report/
│       ├── ApexPlanet_Capstone_Case_Study_Report.docx
│       └── ApexPlanet_Capstone_Case_Study_Report.pdf
│
├── .gitignore
├── LICENSE
└── README.md
```

---

# 📦 Final Deliverables

### 📊 Interactive Power BI Dashboard

[View / Download Power BI Dashboard](PASTE-YOUR-POWER-BI-LINK-HERE)

### 📑 Comprehensive Case Study Report

[View Case Study Report](PASTE-YOUR-REPORT-LINK-HERE)

### 🎤 Final Presentation

[View Capstone Presentation](PASTE-YOUR-PRESENTATION-LINK-HERE)

---

# 📸 Dashboard Preview

### Executive Overview

![Executive Overview](03_RFM_PowerBI/03_dashboards/Executive_Overview.jpg)

### Customer Segmentation

![Customer Segmentation](03_RFM_PowerBI/03_dashboards/Customer_Segmentation.jpg)

### Statistical Analysis

![Gender Analysis](04_Hypothesis_Testing/02_visuals/hypothesis1_gender_analysis.png)

![Age Category Analysis](04_Hypothesis_Testing/02_visuals/hypothesis2_age_category_analysis.png)

---

# 🧩 Analytical Methodology

```text
DESCRIPTIVE
What happened?
        ↓
DIAGNOSTIC
What patterns explain the results?
        ↓
CUSTOMER ANALYTICS
Who creates and risks value?
        ↓
STATISTICAL INFERENCE
Are observed relationships supported by evidence?
        ↓
BUSINESS INTELLIGENCE
How can decision-makers monitor performance?
        ↓
ACTION
What business responses should be considered?
```

---

# ⚠️ Analytical Limitations

- The analysis is based on a 1,000-transaction dataset.
- January 2026 is a partial month and should not be compared directly with complete months.
- RFM segmentation is descriptive and does not establish causality.
- Statistical conclusions apply to the analyzed sample and tested relationships.
- Scenario-based business impact or ROI estimates should be treated as planning assumptions, not guaranteed outcomes.

---

# 🚀 Future Enhancements

Potential extensions include:

- Customer Lifetime Value modelling
- Churn prediction
- Revenue forecasting
- Customer cohort retention analysis
- Product recommendation modelling
- Marketing campaign measurement
- A/B testing
- Automated Power BI refresh
- Automated KPI monitoring
- Predictive customer segmentation
- Streamlit/web deployment

---

# 🧠 Professional Reflection

This capstone demonstrates how an analyst can move beyond simply reporting numbers.

The workflow starts with imperfect transactional data, establishes data quality, identifies business patterns, segments customers based on behavior, validates assumptions statistically, and converts the findings into an interactive decision-support product.

The key lesson is that strong analytics connects **data quality, technical analysis, statistical evidence, business context, and clear storytelling**. The result is a workflow that moves from **raw data → insight → evidence → action**.

---

# 👨‍💻 About the Author

**Brojo Mohan Dutta**

Data Analyst | Python | SQL | Power BI | Statistics

📧 brojomohan58@gmail.com

🔗 LinkedIn:  
https://www.linkedin.com/in/brojomohandutta

💻 GitHub:  
https://github.com/brojomohan58-boop

---

<div align="center">

## 📊 From Raw Transactions to Business Decisions

**Data → Insights → Evidence → Action**

⭐ If you find this project useful, consider giving the repository a Star.

</div>
