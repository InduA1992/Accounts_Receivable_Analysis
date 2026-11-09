Phase 2 – Data Cleaning and Preprocessing

The following activities were completed during this phase:

1. Data Loading and Inspection
- Imported the dataset using Pandas.
- Checked the dataset structure, columns, data types and sample records.
- Created a separate copy (df_clean) to preserve the original dataset.

2. Data Quality Checking
- Checked missing values in all columns.
- Identified blank values in text columns.
- Checked exact duplicate records.
- Reviewed numerical columns using descriptive statistics.

3. Data Standardisation
- Converted column names into lowercase.
- Replaced spaces with underscores.
- Removed unwanted special characters from column names.
- Removed leading and trailing spaces from text values.

4. Date Conversion
Converted the following columns into datetime format:
- doc_date
- net_due_date
- posting_date
- clearing_date

5. Feature Engineering
Created five new analytical columns:
New column	Purpose
payment_status:-	Categorised payments as Early, On-Time or Late
payment_cycle_days:-	Calculated days between document date and clearing date
clearing_year:-	Extracted clearing year
clearing_month:-	Extracted clearing month
clearing_quarter:-	Extracted clearing quarter

6. Customer Payment Analysis
Grouped the records by customer number (cust_num) and calculated:
- Total invoice records
- Total invoice amount
- Average payment delay
- Maximum payment delay
- Early payment count
- On-time payment count
- Late payment count
- Late payment rate (%)

7. Final Dataset Validation
- Checked missing values and duplicate records again.
- Reviewed column names and data types.
- Validated customer payment counts.
- Checked whether late payment rates were between 0% and 100%.
- Confirmed successful CSV exports.

8. Final Output

Two datasets were generated:
1. Accounts_Receivable_Cleaned.csv – cleaned invoice-level dataset.
2. Customer_Payment_Analysis.csv – customer-level payment summary.

Phase 2 Outcome:
   The original dataset was cleaned, standardised and enhanced with new analytical features. A separate customer payment analysis dataset was also created. Both files are prepared for Phase 3 – Exploratory Data Analysis (EDA).
