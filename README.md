# retail-sales-data-validation-database-design
Data validation, cleaning, and relational database design for a retail sales dataset using Microsoft Excel and an ER Diagram.

## 💡 Skills Demonstrated
- Data Cleaning
- Data Validation
- Relational Database Design
- Database Normalization
- Entity Relationship Diagrams (ERD)
- Microsoft Excel
- Documentation

## 📌Overview
This project documents the initial stages of preparing a retail sales dataset for relational database design.
Rather than immediately importing the dataset into PostgreSQL, the dataset was first profiled, cleaned, validated, and normalized to identify data quality issues that could affect downstream analysis.
The project concludes with the design of a normalized Entity Relationship Diagram (ERD) that models the dataset as a relational database.

## Objective 
- Design a normalized relational database.
- Assess the quality of the original retail sales dataset.
- Identify duplicate and missing values.

## Dataset
Source: Retail Sales Dataset (Kaggle)
The dataset contains e-commerce orders from across India, spanning 2020–2024 - including customer information, product details, pricing, shipping information and sales metrics.

## 🛠 Tools used 
- Microsoft Excel - Data cleaning & validation
- Draw.io - Entity Relationship Diagram
- GitHub - Documentation & version control

## Data Cleaning
The following data quality checks were performed:
- Checked for duplicate Order IDs
- Standardized numeric formatting by removing unnecessary decimal places.
- Removed records containing invalid transactional values (e.g., negative quantities).
- Removed records with impossible customer ages (negative values and implausibly young customers).
- Trimmed leading and trailing whitespace from text fields.
- Removed duplicate records from the normalized Customer, Product and Category tables.
- Reviewed missing values to determine whether they should be retained, removed or investigated further.

## Data Validation
During validation, several observations were made:

## 📊 Validation Summary

| Validation Check | Result |
|------------------|--------|
| Duplicate Order IDs | Passed |
| Duplicate Customers | Removed |
| Duplicate Products | Removed |
| Leading/Trailing Spaces | Corrected |
| Invalid Ages | Removed |
| Negative Quantities | Removed |
| Missing Values | Reviewed |
| Sales Calculations | Inconsistent |

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
To reduce redundancy and improve data integrity, the original flat dataset was normalized into four relational entities:
- Customer
- Orders
- Product
- Category
Relationships were established using primary and foreign keys.
<img width="751" height="647" alt="ER Diagram drawio" src="https://github.com/user-attachments/assets/cb8542de-ffce-411c-8253-2e4dc3526d74" />


## 📂 Repository Contents
### 📁 Data
- [Raw Dataset](data/raw_retail_sales_dataset.csv) – Original retail sales dataset obtained from Kaggle.
- [Cleaned Dataset](data/cleaned_retail_sales_dataset.xlsx) – Dataset after cleaning, validation, and normalization preparation.

### 📄Documentation
- [Data Validation Findings](docs/data_validation_findings.md) – Documents the data quality assessment, validation checks, and cleaning decisions made during the project.

### 🖼️ Images
- **Entity Relationship Diagram (ERD)** – Visual representation of the normalized database schema.

## 📚 Lessons Learned
This project reinforced the importance of validating data before analysis.
Key lessons include:
- Never assume source data is internally consistent.
- Validate business rules before modifying values.
- Design database structures based on observed relationships rather than assumptions.
- Separate data cleaning from business analysis.

## Potential Improvements
Potential future improvements include:
- Investigating the source of pricing inconsistencies.
- Comparing this dataset with a production-quality retail dataset.
