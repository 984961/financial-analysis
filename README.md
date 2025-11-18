📊 Financial Data Analysis Project (Python • Power BI • SQL • Excel)

This project presents a complete Financial Data Analysis solution built using Python, SQL, Excel, and Power BI. It covers the end-to-end workflow from data cleaning to building an interactive dashboard for real-world business decision-making.

🚀 Project Overview

The goal of this project is to analyze financial customer transactions, understand loan performance, identify trends, and create a meaningful, interactive dashboard for stakeholders.

This project demonstrates:

Data cleaning & preprocessing (Python, Excel)

SQL-based data exploration

Data modeling, DAX measures & visuals (Power BI)

Insight generation with interactive dashboards

🛠️ Technologies & Tools Used
✔ Python (Pandas, NumPy, Matplotlib)

Data cleaning and preprocessing

Handling null values and duplicates

Feature engineering

Statistical summaries & EDA

✔ SQL

Data extraction

Aggregations and joins

Transaction-level insights

Filtering & analysis queries

✔ Excel

Initial dataset review

Formatting and pre-cleaning

CSV file management

✔ Power BI

Data modeling

DAX calculations

Interactive dashboard creation

Slicers, filters, drill-downs

Financial KPI monitoring

📁 Dataset Description

The dataset includes the following fields:

Column Name	Description
Customer_ID	Unique customer identity
Gender	Male / Female
Age	Customer age
Region	Geographic region
Transaction_Type	Deposit, Withdrawal, Loan, EMI
Amount	Transaction amount
Loan_Status	Approved / Rejected / Default
Credit_Score	Customer credit score
Transaction_Date	Date of transaction

Additional engineered columns using Python include:

Age_Group

Amount_Level

Year, Month, Day

Transaction_Flow

Loan_Risk Category

📊 Power BI Dashboard Features
🔹 KPIs

Total Customers

Total Transaction Amount

Average Credit Score

Approved Loans

Rejected Loans

🔹 Visuals

Total Amount by Region

Loan Status Breakdown (Donut Chart)

Sum of Amount by Transaction Type

Monthly & Yearly Trend Analysis

Transaction Type by Amount

Credit Score Distribution

Interactive Slicers:

Region

Gender

Account Type

Loan Status

Age Group

🧮 DAX Measures Used
Total Transaction Amount = SUM('Table'[Amount])

Average Credit Score = AVERAGE('Table'[Credit_Score])

Approved Loans = CALCULATE(COUNTROWS('Table'), 'Table'[Loan_Status] = "Approved")

Rejected Loans = CALCULATE(COUNTROWS('Table'), 'Table'[Loan_Status] = "Rejected")

Total Customers = DISTINCTCOUNT('Table'[Customer_ID])

🧼 Python Data Cleaning Steps
df['Amount'].fillna(df['Amount'].median(), inplace=True)
df['Region'].fillna(df['Region'].mode()[0], inplace=True)
df.drop_duplicates(inplace=True)

df['Transaction_Date'] = pd.to_datetime(df['Transaction_Date'])
df['Year'] = df['Transaction_Date'].dt.year
df['Month'] = df['Transaction_Date'].dt.month
df['Age_Group'] = pd.cut(df['Age'], bins=[0,25,40,60,100],
                         labels=["Young","Adult","Middle Age","Senior"])

📊 Example SQL Queries
Total amount by region
SELECT Region, SUM(Amount) AS Total_Amount
FROM financial_data
GROUP BY Region;

Loan status count
SELECT Loan_Status, COUNT(*) AS Total_Customers
FROM financial_data
GROUP BY Loan_Status;

Monthly trend of transactions
SELECT YEAR(Transaction_Date) AS Year,
       MONTH(Transaction_Date) AS Month,
       SUM(Amount) AS Total_Amount
FROM financial_data
GROUP BY YEAR(Transaction_Date), MONTH(Transaction_Date)
ORDER BY Year, Month;

🎯 Key Insights

East and North regions show the highest transaction volume.

Loan approvals and rejections are nearly balanced.

Deposit and withdrawal transactions dominate user activity.

Monthly analysis shows seasonal spikes in financial activity.

Credit score distribution reveals high-risk vs low-risk customers.

📌 How to Use This Project

Clone the repository

Open the Jupyter Notebook for Python data cleaning

Use SQL scripts to explore data

Open the Power BI file (.pbix) to view dashboard

Explore interactive slicers and visuals

📷 Dashboard Preview

![WhatsApp Image 2025-11-18 at 17 05 47_0478cc74](https://github.com/user-attachments/assets/cce8df6a-f87b-449c-990b-2b5414f236c5)


🤝 Contributions

Feel free to fork this project and submit pull requests.
Suggestions and improvements are always welcome!
