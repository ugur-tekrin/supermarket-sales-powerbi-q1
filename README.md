# Supermarket Sales Analysis (2019 Q1) | Power BI Dashboard

This project presents an interactive Power BI dashboard analyzing supermarket sales data for the first quarter of 2019 (Q1).  
The dashboard focuses on revenue trends, product performance, sales distribution, and dynamic currency conversion using an external API.

The goal of this project is to demonstrate practical Business Intelligence skills including data cleaning, data modeling, DAX calculations, visualization design, and API integration.

---

# Project Overview

The dataset contains transactional sales data from a supermarket, including product categories, customer information, payment methods, and sales amounts.

Key analysis areas:

- Monthly revenue trends
- Product category performance
- Sales distribution by payment type
- Sales volume analysis
- Dynamic currency conversion (USD ↔ TRY)
- Interactive filtering by date and product category

---

# Dataset

Dataset: Supermarket Sales (2019 Q1)

Main fields:

- Invoice ID → unique transaction identifier
- Branch → store branch (A, B, C)
- City → store location
- Customer Type → member / normal customer
- Gender → customer gender
- Product Line → product category
- Unit Price → price per product
- Quantity → number of items purchased
- Tax → tax amount
- Total → total transaction value
- Date → transaction date
- Time → transaction time
- Payment → payment method

---

# Dashboard Features

## 1. Revenue Analysis
Monthly revenue trend visualized using a line chart.

Helps identify:
- revenue growth patterns
- seasonal effects
- monthly performance changes

## 2. Product Performance
Average unit price and sales volume analyzed by product category.

Helps answer:
- which product categories generate the highest revenue
- which categories sell the most units

## 3. Sales Distribution
Sales distribution visualized by:

- product line
- city
- payment method

Includes stacked charts and pie charts for quick comparison.

## 4. Interactive Filters
Dashboard includes slicers for:

- Year
- Month
- Currency selection (USD / TRY)

These filters allow dynamic exploration of the dataset.

## 5. Dynamic Currency Conversion (API integration)

An external API from the National Bank was connected to dynamically convert values between USD and TRY.

API source:
https://bank.gov.ua/ua/open-data/api-dev

Example API response:

{
"rate": 43.2413,
"cc": "USD"
}


Currency conversion is handled using DAX measures:

Example:

Total by Currency =
IF(
SELECTEDVALUE(Currency[Currency]) = "TRY",
SUM('supermarket_sales'[Total]) * MAX(USD[rate]),
SUM('supermarket_sales'[Total])
)

This allows users to switch currency dynamically without changing the data source.

---

# Data Preparation Steps

Data cleaning performed in Power Query:

- Date column cleaned and converted to proper date format
- Year and Month columns created
- Data types validated
- Errors removed
- dataset prepared for time-based analysis

---

# Tools Used

Power BI Desktop  
Power Query  
DAX (Data Analysis Expressions)  
External API connection (Web data source)  
GitHub for version control and portfolio presentation  

---

# Example Business Questions Answered

Which product categories generate the highest revenue?

How do sales trends change over time?

Which payment methods are most commonly used?

How does revenue change when converted into a different currency?

Which months perform best in terms of sales volume?

---

# Author

Created as part of Data Analytics training.

This project demonstrates practical BI development skills and dashboard design principles using Power BI.

