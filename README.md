# E-Commerce Customer Intelligence & Retention Analysis

A data-driven project that transforms e-commerce transaction data into customer insights using SQL, Python, machine learning, and business intelligence.

## 1. Project Background

Understanding customer behavior is essential for improving customer relationships, increasing repeat purchases, and identifying high-value customer groups.

This project uses the Brazilian E-Commerce Public Dataset by Olist to analyze order transactions, purchasing patterns, customer segments, and retention trends. It also explores machine learning techniques to identify customer groups and evaluate churn prediction.

## 2. Project Goals

- Examine order and customer data using SQL.
- Measure customer purchasing behavior through RFM analysis.
- Identify customer segments based on purchasing patterns.
- Analyze monthly customer activity and cohort retention.
- Explore customer clustering using K-Means.
- Evaluate a baseline churn prediction model.
- Present key business metrics through Power BI reporting.

## 3. Technology Stack

| Technology | Application |
|---|---|
| MySQL | Data querying, aggregation, and analytics |
| Python | Data processing and modeling |
| Pandas and NumPy | Data preparation and numerical analysis |
| Scikit-learn | Customer clustering and model evaluation |
| Matplotlib | Data visualization |
| Power BI | Interactive business reporting |
| Git and GitHub | Source control and project sharing |

## 4. Analytical Workflow

### Phase 1 — Data Preparation

The project uses Olist's relational dataset, including customer, order, item, payment, review, product, seller, geolocation, and category translation data.

Initial checks cover table sizes, missing identifiers, order status distribution, and invalid numeric values.

### Phase 2 — SQL-Based Business Analysis

SQL queries are organized into separate scripts for:

- Data quality checks
- Order-level revenue analysis
- Customer purchase summaries
- RFM metrics and scoring
- Customer segmentation
- Monthly activity and cohort retention

The scripts are stored in the `sql/` directory for easier maintenance and review.

### Phase 3 — Customer Behavior Analysis

RFM analysis classifies customers according to purchase recency, frequency, and monetary value.

The current segmentation results include seven groups:

- Champions
- Loyal Customers
- Potential Loyalists
- Recent Customers
- At Risk
- Hibernating
- Needs Attention

The existing results cover 93,358 customers.

### Phase 4 — Machine Learning Exploration

**Customer clustering:** K-Means was evaluated with two clusters and a recorded silhouette score of approximately 0.7118. The cluster sizes were 90,557 and 2,801 customers, respectively.

**Churn prediction:** A baseline Logistic Regression model was tested using historical purchase features. Its recorded ROC-AUC was approximately 0.6036.

The churn dataset is highly imbalanced, so these results should be treated as an initial experiment rather than a production-ready prediction system.

### Phase 5 — Retention Reporting

Cohort analysis groups customers by their first purchase month and tracks activity in later months.

The retention analysis includes cohort size, active customers, elapsed months since first purchase, and retention percentages.

Power BI reporting was developed to communicate customer and retention insights. Dashboard files and screenshots should be added to the repository when available.

## 5. Project Findings

- RFM analysis provides a structured view of different customer purchasing behaviors.
- The clustering results suggest a large group of low-frequency customers and a smaller group with higher average frequency and monetary value.
- Cohort analysis helps identify repeat purchasing patterns across different customer acquisition periods.
- Severe class imbalance limits the usefulness of accuracy alone for churn prediction.
- Further model validation and improved churn definitions are needed before applying predictions to customer targeting.

## 6. Repository Structure

ecommerce-customer-analytics/
│
├── sql/
│   ├── 01_data_quality_checks.sql
│   ├── 02_order_analytics.sql
│   ├── 03_customer_summary.sql
│   ├── 04_rfm_analysis.sql
│   ├── 05_customer_segmentation.sql
│   └── 06_monthly_activity_retention.sql
│
├── outputs/
├── requirements.txt
├── .gitignore
└── README.md


## 7. How to Set Up the Project

### Requirements

- Python 3
- MySQL 8.0 or compatible version
- Git
- Power BI Desktop (for dashboard work)

Create a virtual environment:
# Python
__pycache__/
*.py[cod]
venv/
.venv/
.env

# Raw dataset files
data/raw/
*.csv

# Keep selected analysis outputs, but exclude large temporary files
# Remove this rule if you intentionally want to upload every CSV
# outputs/

# Local databases and logs
*.db
*.sqlite
*.log

# Editor/system files
.vscode/
.DS_Store
Thumbs.db
