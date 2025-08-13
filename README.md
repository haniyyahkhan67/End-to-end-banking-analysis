Banking Risk Analytics Dashboard

Problem Statement
The objective of this project is to build an understanding of risk analytics in banking and financial services and to demonstrate how data can be used to minimize the risk of losing money while lending to customers.

Solution
This project combines Python, SQL, and Power BI to deliver an end-to-end banking analytics solution.
Data was imported from Excel into SQL, analyzed and cleaned using Python, and visualized in Power BI.
The final dashboards provide insights to help decide whether a loan applicant is likely to repay a loan.

About the Dataset
The dataset contains multiple tables with bank and client details, connected through primary and foreign keys.
Tables included:

Banking Relationship
Client-Banking
Gender
Investment Advisor
Period

Data Cleaning (Python & SQL)
Created new columns:
Engagement Timeframe: Duration of a client’s relationship with the bank
Engagement Days: Number of days since joining
Income Band: Categorized Estimated Income as Low (<100,000) and Mid (<300,000)
Processing Fees: Derived from Fee Structure (High = 0.05)
Standardized column names and formats
Verified data consistency for categorical and numerical values

Calculated Functions (DAX in Power BI)
Some examples:

DAX Formulas:
-- Total Clients
Total Clients = DISTINCTCOUNT('Clients - Banking'[Client ID])

-- Total Loan
Total Loan = [Bank Loan] + [Business Lending] + [Credit Cards Balance]

-- Processing Fees
Total Fees = SUMX('Clients - Banking', [Total Loan] * 'Clients - Banking'[Processing Fees])

-- Engagement Days
Engagement Days = DATEDIFF('Clients - Banking'[Joined Bank], TODAY(), DAY)
Functions used: SUM, DISTINCTCOUNT, SUMX, SWITCH, DATEDIFF.

Key KPIs
Total Clients
Total Loan
Bank Loan
Business Lending
Total Deposit
Processing Fees
Checking Account Amount
Savings Account Amount
Foreign Currency Amount
Engagement Days
Credit Card Balance

Data Visualization (Power BI Dashboards)
Home Dashboard

Overview of KPIs with filters for year and gender

Loan Analysis Dashboard

Loan distribution by occupation, nationality, income band, gender, banking relationship, investment advisor, and joining year

Deposit Analysis Dashboard

Deposit distribution by occupation, nationality, gender, and other categories

Summary Dashboard

Clients by nationality, gender, and year, along with overall trends in loans and deposits

Python EDA and Visualization
Connected SQL to Python using mysql.connector

Explored data using:
head() and tail()
Shape, column names, and data types
Missing value checks
Summary statistics with describe()
Value counts for categorical variables

Created visualizations:
Histograms, bar charts, and pie charts
Box plots and count plots
Correlation heatmaps

Conclusion
The combination of Python, SQL, and Power BI enables clear, interactive insights into banking operations.
This project helps:

Identify total loan amounts by client profile

Compare client counts across different banks

See which nationalities have the highest bank loans

Understand the amounts in different account types

Future Work
Automating data refresh from SQL to Power BI
Adding machine learning models to predict loan repayment likelihood
Enhancing dashboards with trend forecasting
Including real-time client activity tracking

Tools and Technologies
Python (Pandas, Matplotlib, Seaborn, MySQL Connector)
MySQL
Power BI
Excel

