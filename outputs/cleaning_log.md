# Data Cleaning Log

## Issues Found

* 26 missing values in region.
* 22 missing values in ship_mode.
* 18 missing values in discount.
* 15 negative discount values.
* 2 exact duplicate rows.
* 59 duplicate order ID records.
* 22 invalid date sequences where ship_date occurred before order_date.
* Mixed date formats across order_date and ship_date fields.

## Cleaning Actions Performed

* Standardized text fields using trimming and formatting.
* Filled missing region values with "Unknown".
* Filled missing ship_mode values with "Unknown".
* Replaced missing discount values with 0 when supporting sales fields were available.
* Standardized date formats.
* Removed exact duplicate rows.
* Flagged duplicate order IDs for review.
* Flagged invalid shipping records.
* Created calculated fields for sales, profit, profit margin, shipping delay, order month, order year, and data quality status.

## Business Rules Applied

* Missing region values were replaced with Unknown.
* Missing ship_mode values were replaced with Unknown.
* Missing discounts were replaced with 0 when appropriate.
* Negative discounts were flagged as invalid.
* Cancelled, refunded, and failed transactions were excluded from completed-sales summaries.
* Ship dates earlier than order dates were flagged as invalid.
* Duplicate order IDs were retained and flagged for manual review.

## Assumptions Made

* Discounts greater than 1 were treated as percentages and standardized.
* Missing discount values were treated as 0 only when sales-related fields were available.
* Duplicate order IDs may represent legitimate business records and were not automatically removed.

## Records Removed

* 2 exact duplicate rows were removed.

## Records Flagged

* 59 records flagged for duplicate order IDs.
* 15 records flagged for invalid discounts.
* 22 records flagged for invalid shipping date sequence.

## Limitations

* Some mixed date formats required manual interpretation.
* Duplicate order IDs require business review to determine whether they are valid transactions.
* Data quality assessment was based on available fields only.

