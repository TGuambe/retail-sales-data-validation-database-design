# Data Validation Findings

## Overview
Before database implementation, the dataset was assessed to determine its suitability for relational database design and business intelligence analysis.

---

## Validation Performed

### Duplicate Records

- Checked for duplicate Order IDs.
- No duplicate Order IDs were identified.

---

### Missing Values
Missing values were identified in several columns and assessed individually based on their impact on business analysis.

Examples include:
- Order Date
- Age
- Quantity
- Dscount Percentage
- Customer Satisfaction
- Days to ship

---

### Business Rule Validation

The following validation was performed:

Expected Sales Amount = Quantity × Unit Price × (1 − Discount Percentage)

The calculated values did not consistently match the provided Sales Amount values.

This indicates that either:
- additional business logic exists,
- the dataset is synthetic,
- or pricing calculations were generated independently.

For this reason, original source values were preserved.

## Data Quality Issues Discovered
During validation, several issues were identified:

- Negative quantity values.
- Impossible customer ages.
- Missing values in selected attributes.
- Inconsistent relationship between Quantity, Unit Price, Discount Percentage and Sales Amount.

These findings were documented to ensure that any analysis performed later on was based on validated data.

---
## Validation Summary
The following validation checks were performed:

| Validation                    | Result |
|-------------------------------|--------|
| Duplicate Order IDs           | Passed |
| Primary Key Assessment        | Passed |
| Leading / Trailing Spaces     | Corrected |
| Duplicate Customers           | Removed |
| Duplicate Categories          | Removed |
| Impossible Ages               | Removed |
| Negative Quantities           | Removed |
| Missing Values                | Reviewed |
| Sales Calculation Validation  | Failed (Dataset Inconsistency) |

---

## Conclusion

The dataset is appropriate for demonstrating:
- Data cleaning
- Data validation
- Database normalization
- Relational database design

At the end, I realized that some business metrics may not follow expected transactional relationships.