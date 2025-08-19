# Walmart_sql_Project

📊 Walmart Sales Data Analysis (SQL Project)
📌 Overview

This project analyzes Walmart Sales Data using SQL to uncover business insights, customer behavior trends, and financial performance metrics.

The analysis involves:

Building a database schema

Feature engineering (time, day, month transformations)

Financial calculations (COGS, VAT, Gross Profit, Margin %)

Exploratory analysis to generate strategic insights

Business recommendations for Walmart’s sales strategy

The goal is to leverage SQL for data-driven decision-making and present clear, actionable insights.

🗄️ Database Schema

The database is named walmartSales and contains a single table: wm_sales_data.

Schema Highlights:

Transaction details (invoice_id, branch, city, customer_type, product_line)

Product & sales metrics (unit_price, quantity, VAT, total, cogs, gross_income, gross_margin_pct)

Time-based attributes (date, time, engineered fields: time_of_day, day_name, month_name)

Customer feedback (rating)

📂 File: schema.sql
 defines and builds this structure.

⚙️ Feature Engineering

To support deeper analysis, additional fields were engineered:

time_of_day → Categorizes sales into Morning, Afternoon, Evening.

day_name → Extracts day of week (Mon, Tue, …).

month_name → Extracts month name (Jan, Feb, …).

These transformations enable time-series insights into customer and sales patterns.

💰 Financial Calculations

The financial-guide.md documents how financial metrics were calculated:

COGS = unit_price × quantity

VAT = 5% × COGS

Total (Gross Sales) = VAT + COGS

Gross Income = Total − COGS

Gross Margin % = Gross Income / Total

📂 File: financial-guide.md
 provides step-by-step examples.

🔍 Strategic Insights

Using SQL queries, several key insights were drawn (see insights.md
):

Branch & City

Naypyitaw generates the highest revenue.

Each city has unique opportunities for localized strategies.

Product Line Performance

Fashion Accessories → Top-selling category.

Food & Beverages → Highest revenue contribution.

Payment & Customer Segmentation

E-Wallets dominate → push digital payment promotions.

Member customers contribute significantly → loyalty programs matter.

Seasonality & Timing

March is peak revenue month.

Afternoons generally have higher ratings.

Tax Impact

Naypyitaw faces highest VAT, affecting pricing strategy.

📈 Recommendations

Based on the insights:

Run targeted marketing campaigns for top product lines.

Offer E-Wallet promotions to boost digital transactions.

Invest in branch-specific sales strategies.

Strengthen loyalty programs for "Member" customers.

Align pricing policies with regional VAT variations.

Launch seasonal campaigns (especially March).

Optimize staffing & resources in peak afternoon hours.

📂 Project Structure
├── schema.sql           # Database schema & feature engineering
├── financial-guide.md   # Financial calculations documentation
├── insights.md          # Strategic insights & recommendations
├── solution.md          # SQL solutions and queries
└── README.md            # Project overview (this file)

🚀 How to Run

Clone this repo:

git clone https://github.com/your-username/walmart-sales-sql.git


Import the schema:

source schema.sql;


Load the dataset (CSV or insert statements).

Run analysis queries from solution.md.

📚 Learnings

Using SQL for feature engineering in real-world datasets.

Extracting business insights beyond raw numbers.

Building strategic recommendations from data.

✨ This project showcases the power of SQL for business analytics, transforming raw sales data into actionable insights for decision-making.
