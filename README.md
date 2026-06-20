# Retail Sales Data Cleaning, Validation and Reporting

## Assignment Part Title

Retail Sales Data Cleaning, Validation, Data Quality Assessment, and Business Reporting using Excel.

---

## Business Problem Summary

The retail company exported order-level sales data from multiple internal systems. The dataset contained several data quality issues including missing values, inconsistent text formatting, mixed date formats, duplicate records, invalid discounts, and business rule violations.

The objective was to clean and validate the dataset, create an analysis-ready version of the data, generate data quality reports, and prepare business summary reports for management review.

---

## Dataset Used

**Input File:**

* raw_orders.xlsx

**Output Files:**

* cleaned_orders.xlsx
* data_quality_report.xlsx
* pivot_summary.xlsx
* cleaning_log.md

---

## Tools Used

* Microsoft Excel / Google Sheets
* Pivot Tables
* Excel Functions:

  * TRIM
  * SUBSTITUTE
  * IF
  * COUNTIF
  * MONTH
  * YEAR
  * ROUND
  * DATEDIF
* Conditional Formatting
* Sorting and Filtering

---

## Steps Performed

### Task 1: Dataset Review

* Reviewed all columns and identified data quality issues.
* Created a separate cleaned workbook.

### Task 2: Text Cleaning

Standardized:

* customer_name
* segment
* region
* state
* city
* category
* sub_category
* ship_mode
* payment_status
* order_status

Actions:

* Removed extra spaces
* Removed leading/trailing spaces
* Corrected case inconsistencies
* Standardized similar values

### Task 3: Date Cleaning and Validation

* Standardized order_date and ship_date.
* Converted dates into a consistent format.
* Identified invalid date sequences.
* Created shipping_delay_days.

### Task 4: Duplicate Handling

* Identified exact duplicate rows.
* Removed exact duplicates.
* Identified duplicate order IDs.
* Flagged duplicate order IDs for manual review.

### Task 5: Business Rule Validation

Applied:

* Missing Region → Unknown
* Missing Ship Mode → Unknown
* Missing Discount → 0 when valid
* Negative Discount → Invalid
* Cancelled/Refunded/Failed Orders excluded from completed sales summaries
* Ship Date before Order Date → Invalid Shipping Record

### Task 6: Calculated Columns

Created:

* cleaned_discount
* calculated_sales
* calculated_profit
* profit_margin
* shipping_delay_days
* order_month
* order_year
* data_quality_flag

### Task 7: Data Quality Reporting

Generated:

* Missing Value Summary
* Duplicate Summary
* Invalid Discount Summary
* Date Issue Summary
* Order Status Summary
* Sales/Profit Mismatch Summary
* Final Clean vs Flagged Record Count

### Task 8: Pivot Reporting

Created pivot summaries for:

* Sales and Profit by Region
* Sales and Profit by Category and Sub-Category
* Order Count by Ship Mode
* Profit Margin by Customer Segment
* Refunded/Cancelled Orders by Region
* Monthly Sales Trend

### Task 9: Documentation

Prepared cleaning log documenting all cleaning decisions and assumptions.

---

## Key Outputs

### cleaned_orders.xlsx

Contains cleaned and validated data with calculated fields.

### data_quality_report.xlsx

Contains all data quality summaries and issue counts.

### pivot_summary.xlsx

Contains management-level business summaries and trends.

### cleaning_log.md

Contains cleaning decisions, assumptions, and limitations.

---

## Business Insights

* Certain regions contained missing information and required standardization.
* Duplicate order IDs were identified and flagged for business review.
* Negative discount values were detected and classified as invalid.
* Multiple records contained shipping dates earlier than order dates.
* Sales and profit performance varied across regions and categories.
* Monthly sales trends were identified through pivot analysis.
* Cancelled and refunded orders impacted overall business performance and were separately analyzed.

---

## Assumptions Made

* Missing Region values were replaced with "Unknown".
* Missing Ship Mode values were replaced with "Unknown".
* Missing Discount values were replaced with 0 when supporting sales fields were available.
* Negative discounts were considered invalid.
* Duplicate Order IDs may represent valid business activity and were therefore flagged rather than removed.
* Calculated fields were used for reporting and validation purposes.

---

## Known Limitations

* Mixed date formats required interpretation and standardization.
* Duplicate Order IDs require business review before final deletion decisions.
* Some business rules were applied based on available data fields only.
* Data quality validation was limited to information available in the provided dataset.

---

## Screenshots

### Raw Dataset Preview

* screenshots/raw_data_preview.png

### Cleaned Dataset Preview

* screenshots/cleaned_data_preview.png

### Pivot Summary 1

* screenshots/pivot_summary_1.png

### Pivot Summary 2

* screenshots/pivot_summary_2.png

These screenshots provide visual evidence of the cleaning process and reporting outputs.
