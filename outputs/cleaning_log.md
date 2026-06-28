# Cleaning Log

## Overview

The raw retail orders dataset was cleaned and validated in Microsoft Excel to prepare it for business analysis. The cleaning process focused on improving data consistency, applying business rules, identifying data quality issues, and creating calculated fields for further analysis.

---

# Issues Found

The following data quality issues were identified in the raw dataset:

- Leading and trailing spaces in text fields
- Inconsistent text capitalization
- Mixed date formats
- Missing Region values
- Missing Ship Mode values
- Missing Discount values
- Exact duplicate records
- Duplicate Order IDs with conflicting information
- Negative discount values
- Ship dates earlier than Order dates
- Cancelled orders
- Failed payment records
- Refunded payment records

---

# Cleaning Actions Performed

The following cleaning actions were performed:

- Removed leading, trailing, and extra spaces using TRIM().
- Standardized text formatting for customer names, regions, cities, categories, sub-categories, ship modes, payment status, and order status.
- Standardized all dates into a consistent date format.
- Replaced missing Region values with **Unknown**.
- Replaced missing Ship Mode values with **Unknown**.
- Replaced missing Discount values with **0** where appropriate.
- Identified and removed exact duplicate records.
- Flagged duplicate Order IDs containing conflicting information for manual review.
- Identified invalid discount values.
- Flagged records where Ship Date occurred before Order Date.
- Created calculated columns for business analysis.

---

# Business Rules Applied

The following business rules were implemented:

- Missing Region values were replaced with **Unknown**.
- Missing Ship Mode values were replaced with **Unknown**.
- Missing Discount values were replaced with **0** when other sales-related fields were valid.
- Negative discounts were marked as **Invalid Discount**.
- Discounts greater than 100% were considered invalid.
- Orders with Ship Date earlier than Order Date were flagged as **Invalid Shipping**.
- Cancelled orders were retained but excluded from completed sales summaries.
- Failed payment records were retained but excluded from completed sales summaries.
- Refunded payment records were retained and summarized separately.

---

# Summary of Data Quality Issues

| Issue | Count |
|-------|------:|
| Missing Region | 25 |
| Missing Ship Mode | 21 |
| Missing Discount | 18 |
| Negative Discount | 15 |
| Invalid Shipping Records | 21 |
| Exact Duplicate Rows Found | 40 |
| Duplicate Order IDs Found | 63 |
| Records Removed | 20 |
| Records Flagged for Review | 24 |
| Cancelled Orders | 145 |
| Failed Payments | 69 |
| Refunded Payments | 71 |
| Returned Orders | 163 |

---

# Calculated Columns Created

The following calculated columns were added:

- cleaned_discount
- calculated_sales
- calculated_profit
- profit_margin
- shipping_delay_days
- order_month
- order_year
- data_quality_flag

---

# Assumptions Made

- Blank Region values were assumed to be **Unknown**.
- Blank Ship Mode values were assumed to be **Unknown**.
- Missing Discount values were treated as **0** only when the remaining sales information was available.
- Discounts were standardized to decimal format (e.g., 70% converted to 0.70).
- Exact duplicate records were removed after verification.
- Conflicting duplicate Order IDs were retained for manual review.

---

# Records Removed

- 20 exact duplicate records were removed.

---

# Records Flagged

- 24 records with conflicting duplicate Order IDs were flagged for manual review.
- 15 records contained invalid discounts.
- 21 records contained invalid shipping dates.

---

# Limitations

- Some sales and profit calculation mismatches may exist because the original dataset may use business rules or rounding methods different from the recalculated values.
- Flagged duplicate Order IDs require manual verification before deletion.
- Replacing missing values with **Unknown** preserves records but does not recover the original information.

---

# Outcome

The dataset has been cleaned, validated, and transformed into an analysis-ready format. Data quality issues were documented, calculated fields were created, and summary reports and pivot tables were prepared for business reporting.
