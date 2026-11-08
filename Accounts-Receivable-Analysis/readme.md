🧹 Data Cleaning, Preprocessing 
📌 Project Overview
This phase focuses on cleaning, preparing, and transforming the Accounts Receivable dataset to make it suitable for further analysis.The objective is to improve data consistency, validate important fields, prepare date and numerical columns, and create meaningful features to analyse customer payment behaviour and payment delays.
⚙️ Data Cleaning & Preprocessing Activities

The following activities were performed:

Dataset Loading & Backup

Imported the dataset using Pandas.

Created a separate working copy to preserve the original dataset.

Verified the dataset structure and data types.

Missing Value Analysis

Checked missing values across all columns.

Identified zero missing values.

No imputation was required.

Duplicate Record Validation

Checked for duplicate rows.

Identified zero duplicate records.

No duplicate records were removed.

Column Name Standardization

Converted column names to lowercase.

Removed unnecessary spaces and special characters.

Replaced spaces with underscores for consistency.

Date Format Conversion

Converted Doc_Date, Net_Due_Date, Posting_Date, and Clearing_date into datetime format.

Handled mixed date formats using Pandas.

Validated the conversion results.

Found zero date conversion failures.

Text Data Cleaning

Removed leading and trailing spaces from text columns.

Standardized text formatting for consistent analysis.

Numerical Data Validation

Examined numerical columns using descriptive statistics.

Reviewed invoice amounts, payment terms, customer age, and payment delays.

Identified unusually high payment delays and values for further investigation.

🔧 Feature Engineering

Created additional features to support Accounts Receivable analysis:

Payment Status: Classified transactions into Early Payment, On-Time Payment, and Late Payment based on payment delay.

Payment Cycle Days: Calculated the number of days between the document date and clearing date.

Clearing Year: Extracted the year from the clearing date.

Clearing Month: Extracted the month name from the clearing date.

Clearing Quarter: Extracted the quarter from the clearing date.

📈 Key Findings

1. Payment Behaviour Distribution

Payment Status

Records

Percentage

Late Payment

24,299

53.01%

Early Payment

15,743

34.34%

On-Time Payment

5,797

12.65%

Total

45,839

100%

Key Insight: More than half of the recorded transactions were paid after their due dates.

2. Payment Delay Analysis

Average payment delay: 0.97 days.

Median payment delay: 1 day.

Minimum payment delay: -117 days.

Maximum payment delay: 1,257 days.

Key Insight: Although the average delay was relatively low, some transactions had exceptionally long payment delays and require further investigation.

3. Payment Cycle Analysis

Average payment cycle: 14.76 days.

Median payment cycle: 6 days.

Minimum payment cycle: 0 days.

Maximum payment cycle: 1,437 days.

Key Insight: The median payment cycle was 6 days, while the maximum value indicates a small number of transactions with significantly longer settlement periods.

4. Data Quality Findings

45,839 records successfully loaded.

Zero missing values identified.

Zero duplicate records identified.

Zero date conversion failures.

All four date columns successfully converted into datetime format.

✅ Conclusion

Phase 2 successfully prepared the Accounts Receivable dataset for further analysis. Data quality checks confirmed that the dataset contained no missing or duplicate records, and all date columns were converted successfully.

Additional features were created to identify payment behaviour, calculate payment cycles, and support time-based analysis.

