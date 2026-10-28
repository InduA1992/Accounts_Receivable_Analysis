# Accounts_Receivable_AnalysisInvoice Ageing, Payment Delays and Collection Patterns

Using accounts receivable data to explore overdue-payment patterns, customer payment behaviour, and potential collection-management insights.

Project Overview
Accounts receivable (AR) management is an important part of business cash flow and working-capital control. Understanding invoice ageing and payment delays can help receivables teams prioritize follow-ups, monitor settlement patterns, and identify areas that may require further investigation.
This project explores an accounts receivable dataset to examine recorded invoice amounts, payment terms, days overdue, customer and regional details, and invoice clearing dates. The aim is to transform transaction-level data into clear, evidence-based insights that can support receivables monitoring and collection planning.
The analysis will use the fields available in the dataset and will validate their meaning before drawing conclusions. In particular, the Amount field will not automatically be treated as the outstanding balance unless its definition is confirmed.

Business Problem
Receivables teams need to understand where payment delays occur and how overdue patterns vary across customers, payment terms, invoice amounts, and regions. Without a structured view of these patterns, it can be difficult to prioritize collection activity and communicate trends clearly.
This project addresses the following question:
What patterns in invoice amounts, payment terms, customer and regional information, and recorded payment delays can help explain accounts receivable ageing and support more focused collection follow-up?
The analysis is intended to identify patterns for further review. It will not assume that a relationship between a field and payment delay proves causation.

Project Objectives
•	Inspect the structure and quality of the accounts receivable dataset.
•	Analyze the distribution of recorded payment delays and delay categories.
•	Explore how payment delays vary across payment terms and invoice-amount categories.
•	Compare recorded delay patterns across customers and regions where the available data supports meaningful comparisons.
•	Examine invoice, due, posting, and clearing dates to understand recorded timing patterns.
•	Explore clearing patterns by weekday and quarter where the relevant fields are valid.
•	Create clear summaries and visualizations to communicate findings relevant to receivables monitoring.
•	Document data limitations and avoid unsupported assumptions about outstanding balances or collection performance.

Dataset Information

Attribute	Details
Dataset	Accounts Receivable Analysis Dataset
File format	CSV
Number of records	45,839
Number of columns	29
Domain	Finance / Accounts Receivable Analytics
Unit of observation	To be validated from document-level records and the dataset's data dictionary
Original source	https://www.kaggle.com/datasets/sonalisingh1411/accounts-receivable-and-payment-delay-analysis?select=Dataset.csv

Key Fields
Fields planned for initial investigation include:
•	Cust_Num – Customer identifier
•	Customer_Name – Customer name or dataset label
•	Document_No – Accounting document identifier
•	Amount – Recorded document amount; meaning, currency, and whether it represents invoice value or outstanding balance must be verified
•	Payment_Method_description – Recorded payment-method description
•	Payment_Term and Payment_Term_Bins – Payment-term values and categories
•	Days_Overdue_Delay and Delay_Bins – Recorded delay measure and delay category
•	Doc_Date – Document date
•	Net_Due_Date – Net due date
•	Posting_Date – Posting date
•	Clearing_date – Clearing date, where populated
•	Region and City – Regional and city fields
•	Amount_Bins – Amount category
•	DelayFlag – Dataset-provided delay indicator; definition must be verified
•	Weekday_clearing and Quarter_clearing – Clearing-time categories

Tools and Technologies
•	Python – Data analysis
•	Pandas – Data loading, inspection, cleaning, and tabular analysis
•	NumPy – Numerical operations
•	Matplotlib / Seaborn – Data visualization, if used in the notebook
•	Jupyter Notebook – Analysis and documentation
•	GitHub – Version control and project presentation
•	Power BI or Excel – Optional reporting and dashboard development, if included in the final project

Project Workflow
The project will follow a structured data analytics workflow:
1.	Understand the data: Load the CSV and inspect sample records, dimensions, column names, and data types.
2.	Validate field definitions: Confirm the meanings of amount, delay, payment terms, clearing status, currency, and the unit of observation.
3.	Assess data quality: Check missing values, duplicate records, inconsistent categories, date formats, and implausible values.
4.	Prepare the data: Apply documented cleaning and transformation steps where necessary.
5.	Analyze payment delays: Review delay distributions and compare categories relevant to receivables management.
6.	Explore customer and regional patterns: Compare results only where record counts and field definitions support fair interpretation.
7.	Analyze date patterns: Examine due dates, clearing dates, weekdays, and quarters where valid.
8.	Visualize and report: Present relevant KPIs, tables, and charts with clear explanations.
9.	Interpret limitations: Separate observed patterns from assumptions and recommendations.
Planned Analysis

Analysis Area	Key Questions
Delay distribution	How are records distributed across the available delay categories?
Payment terms	Do recorded delays differ across payment-term categories?
Amount categories	How do delay patterns vary across the available amount bands?
Customer patterns	Which customers have higher recorded delays or larger recorded amounts, subject to data validation?
Regional patterns	Are there differences in recorded delays across regions or cities?
Date analysis	What patterns appear between document, due, posting, and clearing dates?
Clearing patterns	How are recorded clearing events distributed by weekday or quarter?
Data quality	Are there missing, inconsistent, duplicated, or implausible values that could affect the results?

Expected Business Value
The project aims to demonstrate how accounts receivable data can be used to:
•	Improve visibility into recorded payment-delay patterns.
•	Support prioritization of accounts for further review and collection follow-up.
•	Compare payment-term and delay categories in a consistent way.
•	Identify data-quality issues that may affect receivables reporting.
•	Communicate trends through clear, understandable charts and summary metrics.
•	Demonstrate practical data analytics skills relevant to receivables, finance operations, and reporting.
These are intended uses of the analysis. The dataset alone may not establish the reasons for payment delays or provide a complete measure of collection effectiveness.

Repository Structure
The repository can be organized as follows:
accounts-receivable-analysis/
│
├── data/
│   └── Account receivable analysis data set.csv
│
├── Accounts_Receivable_Analysis_Phase1.ipynb
│
├── Accounts_Receivable_Analysis_SRS.docx
│
└── README.md

•	data/ – Dataset used for the project, subject to source and sharing permissions.
•	Accounts_Receivable_Analysis_Phase1.ipynb – Project overview, business problem, objectives, initial dataset inspection, planned analysis, and scope.
•	Accounts_Receivable_Analysis_SRS.docx – Software Requirements Specification for the project.
•	README.md – Project overview, dataset information, workflow, and limitations.
Scope and Limitations
•	The meanings of Amount, Days_Overdue_Delay, DelayFlag, clearing status, and the date fields must be confirmed before interpreting results.
•	Currency and amount units are not assumed until verified.
•	The dataset's unit of observation must be validated; repeated customer or document identifiers may not necessarily indicate duplicate rows.
•	Customer names and location fields may be anonymized or coded, so their labels may not represent actual customer identities or locations.
•	Analysis will be limited to the fields and time period available in the dataset.
•	Observed associations do not establish the causes of payment delays.
•	Any recommendations will be framed as analytical suggestions, not as confirmed causes or guaranteed collection outcomes.

Project Status
Phase 1 – Project Proposal and Initial Dataset Inspection
The project topic, business problem, objectives, dataset structure, and planned analysis have been outlined. The working CSV contains 45,839 rows and 29 columns.
Before final analysis, the original dataset source and key field definitions must be verified. Detailed cleaning, exploratory analysis, visualizations, and findings will be documented in later project phases.
