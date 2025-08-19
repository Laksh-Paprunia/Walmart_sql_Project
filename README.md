# Walmart_sql_Project

📊 Walmart Sales Data Analysis (SQL Project)
📌 Overview

This project analyzes Walmart Sales Data using SQL to uncover business insights, customer behavior trends, and financial performance metrics.

The analysis involves:

🗄️ Database schema design

⚙️ Feature engineering (time, day, month transformations)

💰 Financial calculations (COGS, VAT, Gross Profit, Margin %)

🔍 Exploratory analysis to generate strategic insights

📈 Business recommendations for Walmart’s sales strategy

The goal is to leverage SQL for data-driven decision-making and present clear, actionable insights.

🗄️ Database Schema

The database is named walmartSales and contains one main table: wm_sales_data.

Schema Highlights:

Transaction details → invoice_id, branch, city, customer_type, product_line

Product & sales metrics → unit_price, quantity, VAT, total, cogs, gross_income, gross_margin_pct

Time-based attributes → date, time, engineered fields (time_of_day, day_name, month_name)

Customer feedback → rating

📂 File: schema.sql
 builds this structure.

⚙️ Feature Engineering

Additional fields created to support deeper analysis:

time_of_day → Categorizes sales into Morning, Afternoon, Evening

day_name → Extracts day of the week (Mon, Tue, …)

month_name → Extracts month name (Jan, Feb, …)

These transformations enable time-series insights into customer and sales patterns.

💰 Financial Calculations

The financial metrics were computed as follows:

COGS = unit_price × quantity

VAT = 5% × COGS

Total (Gross Sales) = VAT + COGS

Gross Income = Total − COGS

Gross Margin % = Gross Income / Total

📂 Details documented in financial-guide.md
.

🔍 Strategic Insights

Key findings from the SQL analysis (see insights.md
):

Branch & City Performance

Naypyitaw generates the highest revenue.

Cities show unique opportunities for localized strategies.

Product Line Performance

Fashion Accessories → Top-selling category.

Food & Beverages → Highest revenue contribution.

Customer Behavior & Payments

E-Wallets are the most used → digital promotions recommended.

Member customers contribute significantly → loyalty programs matter.

Seasonality & Timing

March is peak revenue month.

Afternoons see higher customer ratings.

Tax Insights

Naypyitaw faces the highest VAT, affecting pricing strategy.

📈 Recommendations

Run targeted marketing campaigns for top product lines.

Offer E-Wallet promotions to strengthen digital adoption.

Create branch-specific sales strategies.

Strengthen loyalty programs for members.

Adjust pricing policies to account for VAT differences.

Focus seasonal campaigns around March.

Allocate staffing/resources strategically during peak afternoon hours.

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

Using SQL for feature engineering on real-world datasets

Extracting business insights beyond raw numbers

Building strategic recommendations from data

✨ This project showcases how SQL can transform raw sales data into actionable insights for decision-making.
