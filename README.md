 Customer Shopping Behavior — Data Analytics Project

 Overview

This project analyzes **customer shopping behavior** to uncover meaningful insights from transactional data. The project demonstrates an end-to-end data analytics workflow, starting from data loading and cleaning in Python through SQL analysis in PostgreSQL and visualization in Power BI.

The analysis focuses on customer characteristics, purchasing behavior, spending patterns, product categories, and customer segmentation.

---

 Project Objectives

- Understand customer shopping and purchasing patterns
- Perform Exploratory Data Analysis (EDA)
- Clean and prepare the dataset for analysis
- Analyze business questions using SQL and PostgreSQL
- Build an interactive Power BI dashboard
- Generate actionable business insights
- Present findings through a professional report and presentation

---

 Dataset

The project uses a **Customer Shopping Behavior** dataset containing information about customer demographics, purchases, product categories, and transaction-related attributes.

Key Data Attributes

- Customer ID
- Age
- Gender
- Item Purchased
- Category
- Purchase Amount
- Location
- Size
- Color
- Season
- Review Rating
- Subscription Status
- Payment Method
- Previous Purchases
- Discount Applied
- Promo Code Used
- Frequency of Purchases

---

 Tools & Technologies

| Tool | Purpose |
|---|---|
| **Python** | Data loading, cleaning, and analysis |
| **Pandas** | Data manipulation and preprocessing |
| **NumPy** | Numerical analysis |
| **Matplotlib** | Data visualization |
| **Seaborn** | Statistical visualization |
| **PostgreSQL** | SQL-based data analysis |
| **SQLAlchemy** | Connecting Python with PostgreSQL |
| **Power BI** | Interactive dashboard development |
| **Gamma** | Presentation/PPT creation |
| **Jupyter Notebook** | Python-based analysis |
| **GitHub** | Project documentation and version control |

---

 Project Workflow

```text
Dataset
   ↓
Python / Jupyter Notebook
   ↓
Data Cleaning & EDA
   ↓
PostgreSQL
   ↓
SQL Analysis
   ↓
Power BI
   ↓
Interactive Dashboard
   ↓
Business Insights & Report
   ↓
Gamma Presentation
```

---

 1.  Data Loading

The dataset was initially loaded into Python using **Pandas**.

```python
import pandas as pd

df = pd.read_csv("customer_shopping_behavior.csv")

df.head()
```

The dataset was then inspected to understand its structure, columns, data types, and overall quality.

---

 2.  Exploratory Data Analysis

EDA was performed to understand the dataset and identify patterns, trends, and potential data quality issues.

Key activities included:

- Understanding dataset dimensions
- Checking data types
- Identifying missing values
- Checking duplicate records
- Examining numerical statistics
- Analyzing categorical variables
- Identifying purchasing patterns
- Exploring customer demographics
- Visualizing important variables

Example:

```python
df.info()
df.describe()
df.isnull().sum()
df.duplicated().sum()
```

Visualizations were created using **Matplotlib** and **Seaborn**.

---

 3.  Data Cleaning

The dataset was cleaned and prepared for further analysis.

Key data-cleaning activities included:

- Handling missing values
- Removing duplicate records
- Correcting data types
- Standardizing categorical values
- Renaming columns where required
- Creating derived variables
- Preparing the dataset for SQL and Power BI analysis

The cleaned dataset was then loaded into PostgreSQL for further analysis.

---

 4.  PostgreSQL & SQL Analysis

The cleaned dataset was imported into a PostgreSQL database using **SQLAlchemy**.

Example connection workflow:

```python
from sqlalchemy import create_engine

engine = create_engine(connection_url)

df.to_sql(
    "customer",
    engine,
    if_exists="replace",
    index=False
)
```

SQL was then used to answer business-related questions and extract insights from the data.

Example Analysis Areas

- Customer segmentation
- Purchase behavior
- Revenue and spending analysis
- Product category performance
- Customer demographics
- Subscription behavior
- Previous purchase patterns
- Payment method analysis
- Seasonal purchasing trends

Example customer segmentation query:

```sql
WITH customer_type AS (
    SELECT
        customer_id,
        previous_purchases,
        CASE
            WHEN previous_purchases = 1 THEN 'New'
            WHEN previous_purchases BETWEEN 2 AND 10 THEN 'Returning'
            ELSE 'Loyal'
        END AS customer_segment
    FROM customer
)

SELECT
    customer_segment,
    COUNT(*) AS customer_count
FROM customer_type
GROUP BY customer_segment
ORDER BY customer_count DESC;
```

---

 5.  Power BI Dashboard

The analyzed data was connected to **Power BI** to create an interactive dashboard.

 Dashboard Components

The dashboard provides insights into:

- Total customers
- Total purchases
- Purchase amount
- Average purchase value
- Customer segmentation
- Category performance
- Gender-based purchasing behavior
- Subscription status
- Payment methods
- Seasonal trends
- Customer purchasing patterns

 Dashboard Preview

_Add your Power BI dashboard screenshot here._

```text
![Power BI Dashboard](images/dashboard.png)
```

---

 6.  Results & Insights

The analysis provides a comprehensive view of customer purchasing behavior.

Key areas of insight include:

- Customer purchasing patterns
- Differences in spending behavior across customer groups
- Product category performance
- Customer segmentation based on previous purchases
- Subscription and purchasing behavior
- Preferred payment methods
- Seasonal purchasing trends
- Demographic patterns in customer purchases

These insights can help businesses better understand customers and support data-driven decisions related to marketing, customer retention, product strategy, and sales.

---

 7.  Report

A detailed report was created to document the complete analytical process.

The report covers:

1. Business problem
2. Dataset description
3. Data preparation
4. Exploratory data analysis
5. SQL analysis
6. Power BI dashboard
7. Key findings
8. Business insights
9. Recommendations

---

 8.  Presentation

A professional presentation was created using **Gamma** to communicate the project's findings in a concise and visually engaging format.

The presentation includes:

- Project overview
- Business objectives
- Dataset
- Data preparation
- SQL analysis
- Power BI dashboard
- Key insights
- Business recommendations
- Conclusion

---

 How to Run


Make sure you have the following installed:

- Python 3.x
- Jupyter Notebook
- PostgreSQL
- Power BI Desktop

 Step 1 — Clone the Repository

```bash
git clone https://github.com/your-username/customer-shopping-behavior-analysis.git
cd customer-shopping-behavior-analysis
```

 Step 2 — Create a Virtual Environment

```bash
python -m venv .venv
```

Activate it on Windows:

```bash
.venv\Scripts\activate
```

 Step 3 — Install Dependencies

```bash
pip install pandas numpy matplotlib seaborn sqlalchemy psycopg2-binary notebook
```

 Step 4 — Launch Jupyter Notebook

```bash
python -m notebook
```

Open the project notebook and run the analysis cells sequentially.

Step 5 — Configure PostgreSQL

Create a PostgreSQL database and update the connection details in the notebook.

```python
username = "postgres"
password = "YOUR_PASSWORD"
host = "localhost"
port = 5432
database = "customer_behavior"
```


Step 6 — Run SQL Analysis

Open the SQL files in the project and execute the queries against the PostgreSQL database.

### Step 7 — Open Power BI

Open the `.pbix` file using Power BI Desktop.

If necessary, update the data source connection to your local PostgreSQL database.

---

 Project Structure

```text
customer-shopping-behavior-analysis/
│
├── data/
│   └── customer_shopping_behavior.csv
│
├── notebooks/
│   └── customer_behavior_analysis.ipynb
│
├── sql/
│   └── customer_analysis.sql
│
├── powerbi/
│   └── customer_behavior_dashboard.pbix
│
├── report/
│   └── customer_behavior_report.pdf
│
├── presentation/
│   └── customer_behavior_presentation.pdf
│
├── images/
│   └── dashboard.png
│
├── requirements.txt
└── README.md
```

---

 Key Skills Demonstrated

This project demonstrates practical experience in:

- Python for Data Analytics
- Pandas & NumPy
- Exploratory Data Analysis
- Data Cleaning & Preprocessing
- Data Visualization
- SQL
- PostgreSQL
- Database Connectivity
- Customer Segmentation
- Power BI
- Dashboard Development
- Business Intelligence
- Data Storytelling
- Business Reporting
- Presentation Development

---

 Conclusion

This project demonstrates an end-to-end **data analytics workflow**, combining Python, SQL, PostgreSQL, and Power BI to transform raw customer data into meaningful business insights.

It showcases the ability to work across the complete analytics lifecycle — from data preparation and exploration to SQL analysis, dashboard development, reporting, and business communication.

---

 Author

Harshavardhan M

📧 Email: your-email@example.com  
🔗 LinkedIn: [Your LinkedIn Profile](https://linkedin.com/)  
💻 GitHub: [Your GitHub Profile](https://github.com/)

---

⭐ If you found this project useful, consider giving the repository a star!
