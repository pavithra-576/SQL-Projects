# 📊 **Exploratory Data Analysis Using SQL**

## 🧩 **Overview**

This project demonstrates how to use **Structured Query Language (SQL)** for performing **Exploratory Data Analysis (EDA)** on structured datasets. SQL remains one of the most powerful tools for quick data exploration, summarization, and pattern discovery directly from relational databases without the need for exporting to external analysis tools.

---

## 🎯 **Objectives**

- ✅ Understand the structure and features of the dataset  
- 🔍 Perform summary statistics and group-wise analysis using SQL queries  
- 📊 Visualize results derived from SQL-based aggregations (optional via integration)  
- 💡 Gain insights for further machine learning or reporting tasks  

---

## 🗃️ **Dataset Information**

The dataset used in this project contains various features suitable for EDA such as:

- **Categorical fields**: Gender, Marital Status, Education, etc.  
- **Numerical fields**: Income, Loan Amount, Age, etc.  
- **Target fields** (if applicable): Approval status, churn, etc.

> 📌 The dataset can either be imported into a local or cloud-based SQL environment such as MySQL, PostgreSQL, SQLite, BigQuery, etc.

---

## ⚙️ **Tools & Technologies**

| Purpose            | Tools/Technologies       |
|--------------------|--------------------------|
| Query Execution    | SQL (PostgreSQL, SQLite) |
| Interface          | pgAdmin, DBeaver, DB Browser, Google BigQuery |
| Optional Visuals   | Excel / Python / Tableau |

---

## 🔎 **Key SQL Operations Performed**

### 📌 **1. Schema and Data Inspection**
```sql
SELECT * FROM dataset LIMIT 10;
SELECT COUNT(*) FROM dataset;
DESCRIBE dataset;
📌 2. Missing Value Checks
sql
Copy
Edit
SELECT COUNT(*) FROM dataset WHERE column_name IS NULL;
📌 3. Group-wise Aggregation
sql
Copy
Edit
SELECT gender, COUNT(*) AS total
FROM dataset
GROUP BY gender;
📌 4. Distribution Analysis
sql
Copy
Edit
SELECT education, AVG(income) AS avg_income
FROM dataset
GROUP BY education;
📌 5. Conditional Filtering
sql
Copy
Edit
SELECT * FROM dataset
WHERE income > 50000 AND loan_status = 'Approved';
📌 6. Correlation Analysis (Using Binned Data)
sql
Copy
Edit
SELECT income_range, AVG(loan_amount) AS avg_loan
FROM (
  SELECT 
    CASE 
      WHEN income < 20000 THEN 'Low'
      WHEN income BETWEEN 20000 AND 50000 THEN 'Medium'
      ELSE 'High'
    END AS income_range,
    loan_amount
  FROM dataset
) AS sub
GROUP BY income_range;
🧠 Insights Derived
💼 Higher income groups tend to apply for higher loan amounts.

🧾 Applicants with a positive credit history are more likely to be approved.

🏙️ Urban area applicants had a higher loan application frequency.

📚 Education level influences loan approval probability marginally.

🧪 Next Steps
Integrate SQL output with Python or BI tools for data visualization

Prepare features for predictive modeling (ML)

Create dashboards for real-time SQL reporting

📁 Folder Structure
bash
Copy
Edit
EDA-SQL-Project/
├── queries/
│   └── analysis_queries.sql
├── data/
│   └── dataset.csv (if using SQLite)
├── output/
│   └── sql_results.csv
├── README.md
🙌 Credits
Project By: [Your Name or Team Name]

Tools Used: PostgreSQL, SQLite, DBeaver

Dataset Source: [Dataset link or description]

License: MIT or open-source license of your choice

