# E-Commerce ETL Pipeline with Pandas

## Overview

An end-to-end ETL pipeline built using **Python and Pandas** on the Brazilian E-Commerce Public Dataset by Olist.

The project demonstrates how raw data from multiple related CSV files can be extracted, profiled, cleaned, transformed, integrated, analyzed, and exported as processed datasets.

## Architecture

The following diagram illustrates the ETL pipeline and data integration architecture:

![E-Commerce ETL Pipeline Architecture](src/etl_architecture.png)

## ETL Workflow

```text
Raw CSV Files
     ↓
Data Exploration
     ↓
Data Cleaning
     ↓
Data Transformation
     ↓
Data Integration
     ↓
Business KPIs
     ↓
Visualization
     ↓
Processed Data
```

## Dataset

The project uses the **Brazilian E-Commerce Public Dataset by Olist**.

The pipeline works with the following datasets:

* Customers
* Orders
* Order Items
* Order Payments
* Products
* Sellers

## Project Structure

```text
ecommerce-pandas-etl/
│
├── data/
│   ├── raw/
│   └── processed/
│
├── notebooks/
│   └── ecommerce_etl.ipynb
│
├── README.md
├── requirements.txt
└── .gitignore
```

## Data Exploration

Each dataset was profiled to understand its structure and data quality.

The exploration included:

* Dataset dimensions
* Column names
* Data types
* Missing values
* Duplicate records
* Unique values
* Candidate primary keys
* Categorical value distributions
* Business meaning of important fields

## Data Cleaning

The cleaning phase included:

* Converting timestamp columns to appropriate datetime types.
* Correcting inconsistent column names in the Products dataset.
* Investigating missing values.
* Preserving business-valid missing values rather than blindly removing them.
* Validating duplicate records and candidate keys.

## Data Transformation

### Orders

The following features were created:

* `delivery_days`
* `order_year`
* `order_month`
* `order_weekday`
* `delivery_vs_estimated_days`
* `approval_time_hours`

### Order Items

Created:

* `total_item_value`

where:

```text
total_item_value = price + freight_value
```

## Data Integration

The Orders dataset acts as the central entity.

```text
Customers
    │
    │ customer_id
    ↓
Orders
    │
    │ order_id
    ↓
Order Items
    │
    ├── product_id → Products
    │
    └── seller_id  → Sellers
```

Payment records were first aggregated at the order level before being merged with the master dataset.

This prevents payment records from unnecessarily multiplying the order-item level data.

## Business KPIs

The pipeline generates:

1. Total Revenue
2. Total Orders
3. Average Order Value
4. Monthly Revenue
5. Orders by Status
6. Average Delivery Time
7. Early / On-Time / Late Delivery
8. Top 10 Products by Revenue
9. Revenue by Customer State
10. Payment Method Distribution

## Visualizations

The project includes visualizations for:

* Monthly revenue trends
* Top products by revenue
* Delivery performance

## Output

Processed datasets are exported to:

```text
data/processed/
```

including:

* `master_dataset.csv`
* `cleaned_orders.csv`
* `cleaned_products.csv`
* `monthly_revenue.csv`
* `top_products.csv`
* `kpi_summary.csv`

## Technologies

* Python
* Pandas
* NumPy
* Matplotlib
* Jupyter Notebook

## How to Run

Clone the repository and install the required dependencies:

```bash
pip install -r requirements.txt
```

Place the raw Olist CSV files inside:

```text
data/raw/
```

Open the notebook:

```text
notebooks/ecommerce_etl.ipynb
```

Run the notebook from top to bottom.

## Key Data Engineering Concepts Demonstrated

* ETL pipeline development
* Data profiling
* Data quality validation
* Missing-value analysis
* Datetime transformation
* Feature engineering
* GroupBy and aggregation
* One-to-many relationships
* Composite/candidate key analysis
* Relational data integration
* KPI generation
* Data export

## Future Improvements

Potential extensions include:

* Converting the notebook into modular Python ETL scripts.
* Implementing the pipeline using PySpark.
* Loading processed data into a relational database.
* Orchestrating the pipeline using Airflow.
* Deploying the pipeline on a cloud platform such as AWS.

## Author

**Samarth Ghodake**

Data Engineer
