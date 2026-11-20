<div align="center"><img src="images/ar_project_banner.png" alt="Accounts Receivable Analysis banner" width="100%">📊 Accounts Receivable Analysis
Historical Invoice Payment Behaviour, Payment Delays & Customer Insights
<p>
  <img src="https://img.shields.io/badge/Python-3.x-3776AB?logo=python&logoColor=white" alt="Python">
  <img src="https://img.shields.io/badge/Pandas-Data%20Analysis-150458?logo=pandas&logoColor=white" alt="Pandas">
  <img src="https://img.shields.io/badge/NumPy-Numerical%20Computing-013243?logo=numpy&logoColor=white" alt="NumPy">
  <img src="https://img.shields.io/badge/Matplotlib-Visualization-11557C" alt="Matplotlib">
  <img src="https://img.shields.io/badge/Seaborn-Statistical%20Charts-4C72B0" alt="Seaborn">
  <img src="https://img.shields.io/badge/Jupyter-Notebook-F37626?logo=jupyter&logoColor=white" alt="Jupyter">
</p>A Python-based data analytics project exploring invoice settlement patterns, payment delays, payment methods and customer-level receivables behaviour.
</div>📌 Project Overview

Accounts Receivable (AR) is an important part of financial operations because delayed customer payments can affect cash-flow visibility, working capital and collection efficiency.

This project analyses historical invoice-level records to understand how customers settle invoices, how payment delays vary, and whether payment terms and payment methods are associated with settlement behaviour.

Using Python and its data analysis libraries, the project follows a structured workflow covering data understanding, data quality assessment, preprocessing, feature engineering, exploratory data analysis (EDA), customer-level analysis and business recommendations.

The objective is to transform raw invoice data into meaningful insights that can support better Accounts Receivable monitoring and collection prioritisation.

Project focus: Historical payment behaviour analysis. This project does not calculate a live open-receivables balance or current overdue ageing because the available notebook results do not establish current open invoice balances.

🎯 Project Objectives
- Understand the structure and quality of the invoice dataset.
- Identify missing values, blank text values and duplicate records.
- Clean and standardise invoice, customer, payment and date fields.
- Create payment status and payment cycle features.
- Analyse early, on-time and late payment patterns.
- Explore invoice amounts, payment delays and payment cycles.
- Compare historical payment performance across payment methods.
- Examine the relationship between payment terms and actual payment cycles.
- Identify customer-level invoice exposure and late-payment patterns.
- Present findings through visualisations and actionable recommendations.

📂 Dataset Information

Source	Kaggle – Accounts Receivable and Payment Delay Analysis
File format	CSV
Invoice records analysed	45,839
Customer summary	69 unique customers
Initial columns	29
Main subject	Customer invoices, payment terms, payment methods, due dates and clearing activity

Key Dataset Attributes
Column	Description
cust_num	Customer number
document_no	Invoice/document reference
amount	Recorded invoice amount
payment_method_description	Description of payment method
payment_term	Recorded payment term
days_overdue_delay	Recorded payment delay
doc_date	Document/invoice date
net_due_date	Net due date
posting_date	Posting date
clearing_date	Invoice clearing date
region, city	Customer location attributes
customer_name	Customer name
no_of_orders_by_customer	Number of orders recorded for the customer

🛠️ Tools & Technologies
Tool / Library	Purpose
Python	Main programming language
Jupyter Notebook	Interactive analysis environment
Pandas	Data loading, cleaning, grouping and aggregation
NumPy	Numerical operations and feature engineering
Matplotlib	Static data visualisation
Seaborn	Statistical visualisation
Plotly Express	Interactive exploratory charts

🔍 Project Workflow
The project follows a step-by-step data analytics process.
1. Data Understanding
- Imported the required Python libraries.
- Loaded the CSV file into a Pandas DataFrame.
- Examined sample records and dataset dimensions.
- Reviewed column names, data types and unique values.
- Used descriptive statistics to understand numerical attributes.
2. Data Quality Assessment
- Checked missing values and null percentages.
- Checked blank values in text columns.
- Identified exact duplicate records.
- Reviewed data types and date fields.
- Inspected unusual values and extreme observations.
3. Data Cleaning & Preprocessing
- Created a separate working copy of the original dataset.
- Standardised column names using lowercase and underscore formatting.
- Converted document, due, posting and clearing date columns into datetime format.
- Trimmed unnecessary spaces from text columns.
- Reviewed missing values and duplicate records.
- Checked numerical fields and descriptive statistics.

4. Feature Engineering
Created additional fields to support payment analysis.
Feature	Definition
payment_status	Early Payment when delay < 0; On-Time Payment when delay = 0; Late Payment when delay > 0
payment_cycle_days	Clearing date minus document date, in days
clearing_year	Year extracted from clearing date
clearing_month	Month extracted from clearing date
clearing_quarter	Quarter extracted from clearing date

Payment status logic:

df_clean["payment_status"] = np.where(
    df_clean["days_overdue_delay"] < 0,
    "Early Payment",
    np.where(
        df_clean["days_overdue_delay"] == 0,
        "On-Time Payment",
        "Late Payment"
    )
)

Payment cycle calculation:
df_clean["payment_cycle_days"] = (
    df_clean["clearing_date"] - df_clean["doc_date"]
).dt.days

5. Customer-Level Analysis
Grouped invoice records by customer number to create a customer payment summary.
The customer-level analysis includes:
- Total invoice count
- Total recorded invoice amount
- Average payment delay
- Maximum payment delay
- Early payment count
- On-time payment count
- Late payment count
- Late-payment rate

Late-payment rate formula:
late_payment_rate = (
    late_payments / total_invoices
) * 100

6. Exploratory Data Analysis (EDA)
The analysis is organised into three approaches:
- Univariate Analysis – examines individual variables and their distributions.
- Bivariate Analysis – explores relationships between two variables.
- Multivariate Analysis – examines combined relationships among multiple financial and customer variables.

📈 Key Performance Indicators
The following metrics are reported in the notebook:
KPI	Result
Total invoice records	45,839
Unique customers in customer summary	69
Late-payment invoices	24,299
Late-payment share	53.01%
Early-payment invoices	15,743
Early-payment share	34.34%
On-time-payment invoices	5,797
On-time-payment share	12.65%
Average payment delay	0.97 days
Median payment delay	1 day
Maximum recorded payment delay	1,257 days
Average payment cycle	14.76 days
Median payment cycle	6 days
Average invoice amount	17,807.16
Median invoice amount	3,196

📊 Data Visualizations & Analysis
1. Payment Status Distribution
The payment status analysis compares early, on-time and late invoice records.

Key observation: Late payments represent 53.01% of the invoice records and form the largest payment-status category.
2. Invoice Volume by Payment Method
This analysis identifies the payment methods most frequently recorded in the dataset.

Key observation: Direct Debits 2 and Direct Debits 1 account for the majority of invoice records.
3. Late-Payment Rate by Payment Method
The chart compares the historical late-payment percentage across selected payment methods.

Key observation: Third Part Payments and No Payment Method have the highest reported late-payment rates among the listed categories. Lower-volume categories should be interpreted carefully.
4. Correlation Analysis
Correlation analysis explores the direction and strength of relationships between selected financial variables.

Key observation: Payment terms and payment cycle days show a strong positive correlation of approximately 0.891. Invoice amount and payment delay show a very weak correlation of approximately 0.044.

Additional Analyses in the Jupyter Notebook
The notebook also includes interactive visualisations such as:
- Invoice amount distribution.
- Payment delay distribution.
- Payment terms vs. payment cycle.
- Invoice amount vs. payment delay.
- Invoice amount by payment status.
- Payment method vs. payment delay.
- Payment status composition by payment method.
- Customer payment behaviour and invoice exposure.
- Correlation matrix of selected numerical variables.

💡 Key Findings & Business Insights
1. Late Payment Is the Largest Category
- 24,299 invoice records (53.01%) are classified as late.
- 15,743 records (34.34%) are classified as early payments.
- 5,797 records (12.65%) are classified as on-time payments.
This indicates that late payment is the largest category in the historical records.

2. Invoice Amounts Are Positively Skewed
- Average invoice amount: approximately 17,807.16.
- Median invoice amount: 3,196.
- Maximum recorded invoice amount: 5,709,354.
The difference between the mean and median indicates that high-value records influence the average. Median and percentile measures should therefore be considered alongside the mean.

3. Payment Delays Include Extreme Values
- Average payment delay: approximately 0.97 days.
- Median payment delay: 1 day.
- Minimum recorded delay: −117 days.
- Maximum recorded delay: 1,257 days.
Negative delay values represent early settlement under the notebook's classification rule. Some historical records show exceptionally long delays.

4. Payment Method Performance Varies
Payment Method	Late-Payment Rate
Third Part Payments	77.55%
No Payment Method	73.62%
Direct Debits 2	59.20%
Direct Debits 1	46.42%
Regulatory 2	25.17%
Regulatory	7.00%

Third Part Payments has the highest reported late-payment rate. Payment method alone should not be treated as the cause of late payment.

5. Payment Terms and Payment Cycle
The correlation between payment terms and payment cycle days is approximately 0.891, indicating a strong positive association.

This suggests that invoices with longer payment terms generally tend to have longer payment cycles in the analysed records. Correlation does not prove causation.

6. Invoice Amount and Payment Delay
The correlation between invoice amount and payment delay is approximately 0.044, indicating a very weak positive linear relationship.

Invoice value alone is therefore not a strong indicator of historical payment delay in this dataset.

7. Customer Payment Behaviour
The customer summary includes 69 unique customers.
- Customer 5039221094 has the highest total recorded invoice amount: approximately 227,964,488 across 9,712 invoices.
- Customer 5039221090 has the highest invoice count: 10,219.
- Customer 5039221093 has a late-payment rate of 77.73% and average delay of 3.60 days.
- Customer 5039221097 has a late-payment rate of 71.11% and average delay of 20.13 days.
- Customer 5039221071 has an average delay of −23.58 days, indicating early-payment behaviour on average.

🎯 Recommendations
1. Prioritise further review of customers with both high invoice exposure and high late-payment rates.
2. Investigate customers with unusually high average or maximum payment delays.
3. Review payment terms against actual payment cycles.
4. Examine payment methods with higher historical late-payment rates, while considering the number of invoices in each category.
5. Use median and percentile measures alongside averages to account for extreme invoice amounts and delays.
6. Build a separate open-invoice ageing report for current collection monitoring.

⚠️ Limitations & Assumptions
- The analysis is based on historical invoice/payment records and does not establish current open invoice balances.
- A current outstanding receivables balance and current overdue ageing cannot be calculated from the reported notebook results alone.
- The currency and exact unit of the amount field are not confirmed.
- The definitions and derivation of supplied delay fields should be checked against the original dataset documentation.
- Correlation indicates association, not causation.
- Payment-method categories with fewer records may have less stable rates.
- Customer identifiers should be anonymised if necessary before public publication.
- This is a descriptive analysis, not a predictive credit-risk model or collection forecast.

🚀 Future Scope
- Include invoice open/cleared status and outstanding balances as at a defined reporting date.
- Calculate overdue days for open invoices only.
- Create ageing buckets: Not Due, 1–30, 31–60, 61–90 and 90+ days.
- Include collection owner, dispute status, promised payment date and last follow-up date where available.
- Develop a Power BI dashboard with total outstanding, overdue amount, overdue percentage, top overdue customers and ageing trends.
- Explore predictive analysis after validating data definitions and collecting suitable historical outcomes.

📁 Suggested GitHub Repository Structure

Accounts-Receivable-Analysis/
│
├── README.md
├── images/
│   ├── ar_project_banner.png
│   ├── payment_status.png
│   ├── payment_method.png
│   ├── late_rate.png
│   └── correlations.png
│
├── notebooks/
│   └── Accounts_Receivable_Analysis.ipynb
│
├── data/
│   ├── raw/
│   │   └── Account receivable analysis data set.csv
│   └── processed/
│       ├── Accounts_Receivable_Cleaned.csv
│       └── Customer_Payment_Analysis.csv
│
├── reports/
│   └── Accounts_Receivable_Analysis_Project_Report.docx
│
└── requirements.txt

📦 Project Outputs
Output File	Description
Accounts_Receivable_Cleaned.csv	Cleaned invoice-level data with engineered payment features
Customer_Payment_Analysis.csv	Customer-level invoice and payment behaviour summary


📝 Conclusion
This project analyses 45,839 historical invoice records across 69 customers to understand payment delays, payment cycles, payment methods and customer payment behaviour.

The findings show that 53.01% of invoice records are classified as late payments. Payment terms have a strong positive association with payment cycle days, while invoice amount alone has a very weak relationship with payment delay. Payment behaviour also varies across payment methods and customers.

The project demonstrates how Python-based data cleaning, feature engineering, exploratory data analysis and visualisation can turn invoice data into meaningful Accounts Receivable insights. Adding current open balances and invoice ageing would be the next step toward a practical collection-monitoring solution.

<div align="center">✨ Better Data. Clearer Insights. Smarter Receivables Decisions.
Accounts Receivable Analysis | Python Data Analytics Project
</div>

