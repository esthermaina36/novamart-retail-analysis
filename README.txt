# NovaMart Retail Analysis

## Project Overview

This project explores a synthetic retail dataset containing order transactions, customer information, and product details.

The objective is to investigate the dataset, identify data-quality issues, understand sales patterns, and eventually generate insights that can support business decision-making.

The analysis is being conducted using Python, with further exploration and analysis planned using SQL and Power BI.

## Dataset Description

The dataset consists of three CSV files:

- **orders.csv:** Contains 2,508 rows and 16 columns.
- **customers.csv:** Contains 350 rows ands 8 columns.
- **products.csv:** Contains 60 rows ands 6 columns.

The three datasets are related through customer and product IDs
Customer table has CustomerID as the primary key, and product table has product Id as its primary keys.
These 2 keys serve as foreign keysin order table.


## Tools and Technologies

- Python
- Pandas
- Jupyter Notebook
- Git and GitHub


## Investigation 1: Data Quality Assessment

The initial investigation focused on understanding the structure of the datasets and identifying missing values, duplicates, invalid values, and inconsistencies.

### 1. Dataset Structure

The orders dataset contains 2,508 records and 16 columns. The customers dataset contains 350 records and 8 columns, while the products dataset contains 60 records and 6 columns.

### 2. Duplicate Records

The orders dataset contains 8 duplicate records. The customers and products datasets contain no duplicate records.

### 3. Missing Values

The investigation identified missing values in six columns across the datasets:

- `orders.CustomerID` contains 18 missing records.
- `orders.DiscountPct` contains 15 missing records.
- `orders.ShippingDays` contains 35 missing records.
- `orders.SalesChannel` contains 22 missing records.
- `customers.City` contains 8 missing records.
- `products.Subcategory` contains 4 missing records.

### 4. Invalid and Inconsistent Values

The investigation identified the following data-quality issues:

- Six order records have a quantity of zero.
- Five order records have a negative unit price of -1.
- Nine records have a shipping duration of 45 days, which requires further investigation.
- The `SalesChannel` column contains an inconsistent value (`" online "`) alongside the standard `"Online"` category.
- The `SalesChannel` column also contains missing values.

### 5. Sales Amount Validation

The recorded `SalesAmount` was compared against an independently calculated expected sales amount using the formula:

`Quantity × UnitPrice × (1 - DiscountPct)`

The comparison identified 11 records with absolute differences greater than 10.

Further investigation established that six of these records have a quantity of zero, while the remaining five have a unit price of -1. There are no overlapping records between these two groups.

The remaining records have differences within a few cents, consistent with rounding.

### 6. Missing Discount Investigation

Fifteen records have missing discount percentages.

Their recorded sales amounts have been extracted for further investigation. It has not yet been established whether the missing discounts were zero or whether discounts were applied but not recorded.

## Current Project Status

The initial data-quality assessment is underway.

The dataset inspection, assessment of dataset dimensions, duplicate assessment, and missing-value assessment have been completed.

The initial sales amount validation has also been completed, while the investigation of invalid values is still in progress.

The missing discount investigation is pending, as are data cleaning, exploratory data analysis, SQL analysis, and the development of a Power BI dashboard.

## Project Structure

```text
novamart-retail-analysis/
│
├── data/
│   └── raw/
│       ├── orders.csv
│       ├── customers.csv
│       └── products.csv
│
├── notebooks/
│   └── 01_data_quality_assessment.ipynb
│
├── README.md
└── .gitignore

---

TO be updated as I Progress.