# E-Commerce ETL Pipeline with Pandas

## Overview

This project is an end-to-end ETL (Extract, Transform, Load) pipeline built using **Python** and **Pandas** on the **Brazilian E-Commerce Public Dataset (Olist)**.

The objective of this project is to simulate a real-world Data Engineering workflow by extracting data from multiple CSV files, profiling and cleaning the data, transforming it into an analysis-ready format, and generating business insights.

---

## Project Objectives

* Read and explore multiple datasets.
* Perform data profiling.
* Handle missing values and duplicates.
* Validate candidate primary keys and relationships.
* Transform and clean the data.
* Merge datasets into a unified analytical dataset.
* Generate business KPIs.
* Export processed datasets.

---

## Dataset

The project uses the **Brazilian E-Commerce Public Dataset by Olist**.

### Tables Used

* Customers
* Orders
* Order Items
* Order Payments
* Products
* Sellers

---

## Project Structure

```text
ecommerce-etl/
│
├── data/
│   ├── raw/
│   └── processed/
│
├── notebooks/
│   └── ecommerce_etl.ipynb
│
├── README.md
└── requirements.txt
```

---

## ETL Workflow

### 1. Extract

* Load multiple CSV files using Pandas.
* Inspect the structure of each dataset.

### 2. Data Profiling

For each dataset:

* Preview records
* Check dataset dimensions
* Identify data types
* Find missing values
* Detect duplicate records
* Validate candidate primary keys
* Explore categorical columns
* Record observations

### 3. Data Cleaning *(In Progress)*

* Handle missing values
* Rename inconsistent columns
* Standardize data
* Convert data types
* Validate data quality

### 4. Data Transformation *(Upcoming)*

* Create derived columns
* Convert timestamps
* Calculate business metrics
* Prepare analytical datasets

### 5. Data Integration *(Upcoming)*

Merge the following datasets:

* Customers
* Orders
* Order Items
* Order Payments
* Products
* Sellers

to create a master dataset.

### 6. Load *(Upcoming)*

Export processed datasets to the `processed/` directory.

---

## Technologies Used

* Python
* Pandas
* Jupyter Notebook

---

## Current Progress

* [x] Dataset Exploration
* [x] Data Profiling
* [ ] Data Cleaning
* [ ] Data Transformation
* [ ] Data Integration
* [ ] Business Analysis
* [ ] Export Processed Data

---

## Skills Demonstrated

* Data Exploration
* Data Profiling
* Data Cleaning
* Data Validation
* Candidate Key Identification
* Feature Engineering
* Data Transformation
* Data Integration
* ETL Pipeline Design
* Business Data Analysis

---

## Future Improvements

* Refactor notebook into modular Python scripts.
* Implement the same ETL pipeline using PySpark.
* Store processed data in a relational database.
* Deploy the pipeline on AWS.

---

## Author

**Samarth Ghodake**

Aspiring Data Engineer | Python | SQL | Pandas | PySpark | AWS
