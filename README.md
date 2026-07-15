# retail-sales-data-validation-database-design
Data validation, cleaning, and relational database design for a retail sales dataset using Microsoft Excel and an ER Diagram.

## Overview
This project documents the beginning stages of preparing a retail sales dataset for database implementation and business intelligence analysis.
Instead of than immediately importing the dataset into PostgreSQL for analysis, I first designed a normalized relational database schema using an Entity Relationship Diagram (ERD), evaluated the quality of the data, and performed cleaning in Microsoft Excel.
The objective was to ensure the dataset was suitable for further SQL analysis and reporting.

## Objective 
- Design a normalized relational database.
- Assess the quality of the original retail sales dataset.
- Identify duplicate and missing values.
- Prepare the dataset for future PostgreSQL implementation.

## Dataset
Source: Retail Sales Dataset (Kaggle)
The dataset contains e-commerce orders from across India, spanning 2020–2024 - including customer information, product details, pricing, shipping information and sales metrics.

## Tools used
- Microsoft Excel
- Draw.io
- GitHub

## Data Cleaning
The following data quality checks were performed:
- Checked for duplicate Order IDs
- Investigated missing values
- Standardized data formatting
- Reviewed potential primary and foreign keys
- Examined data suitable for normalization

## Data Validation
During validation, several observations were made.

### Order IDs
- Order IDs were verified to be unique. No duplicates were found

### Missing Values
- Missing values were identified in several attributes.
- Essential transactional fields and descriptive fields were evaluated separately before deciding how to treat missing values.

### Business Rule Validation
A validation exercise compared sales values against expected calculations using:

Sales Amount = Quantity × Unit Price × (1 − Discount)
The provided Sales Amount values could not consistently be reproduced from the available pricing fields.
This suggests the dataset is either synthetic or incorporates undocumented business logic.
To preserve data integrity, the original values were retained rather than modified.

## Database Design
The original dataset consisted of a single flat table.

To reduce redundancy, the data model was normalized into four entities:
- Customer
- Orders
- Product
- Category
Relationships were established using primary and foreign keys.
<img width="751" height="647" alt="ER Diagram drawio" src="https://github.com/user-attachments/assets/cb8542de-ffce-411c-8253-2e4dc3526d74" />


## Repository Contents
data/
- Original dataset
- Cleaned dataset

images/
- Entity Relationship Diagram

docs/
- Data validation findings

README.md

## Lessons Learned
This project reinforced the importance of validating data before analysis.

Key lessons include:
- Never assume source data is internally consistent.
- Validate business rules before modifying values.
- Design database structures based on observed relationships rather than assumptions.
- Separate data cleaning from business analysis.
