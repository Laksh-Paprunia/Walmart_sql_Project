# Walmart Sales Data Analysis (SQL Project)

## Overview
This project analyzes **Walmart sales data** using SQL to uncover **business insights, customer behavior patterns, and financial performance metrics**. It includes schema design, feature engineering, financial calculations, and a set of analysis queries that surface actionable findings.

**Key objectives:**
- Design a clear, query-friendly schema.
- Engineer time features (time of day, weekday, month) for richer analysis.
- Compute core finance metrics (COGS, VAT, Gross Income, Gross Margin %).
- Answer business questions and compile insights and recommendations.

## Dataset & Schema
The database is named `walmartSales` and contains the main table `wm_sales_data` with fields for transactions, pricing, taxes, timestamps, and ratings.

- Transaction details: `invoice_id`, `branch`, `city`, `customer_type`, `product_line`
- Pricing & totals: `unit_price`, `quantity`, `VAT`, `total`, `cogs`, `gross_income`, `gross_margin_pct`
- Timestamps: `date`, `time`
- Engineered features: `time_of_day`, `day_name`, `month_name`
- Customer feedback: `rating`

See **[`schema.sql`](./schema.sql)** for the DDL and feature-engineering steps.

## Feature Engineering
To enable time-based insights, the following features were added:
- **time_of_day** — buckets transactions into Morning / Afternoon / Evening
- **day_name** — day of week (Mon–Sun)
- **month_name** — month label (Jan–Dec)

These help analyze seasonality, weekday effects, and time-of-day trends in sales and ratings.

## Financial Metrics
Financial calculations used throughout the analysis (documented in **[`financial-guide.md`](./financial-guide.md)**):
- **COGS** = `unit_price × quantity`
- **VAT** = `5% × COGS`
- **Total (Gross Sales)** = `COGS + VAT`
- **Gross Income** = `Total − COGS`
- **Gross Margin %** = `Gross Income / Total`

## Analysis Highlights
The analysis queries (in **[`solution.md`](./solution.md)**) and synthesized insights (in **[`insights.md`](./insights.md)**) cover:
- **Branch & City performance** — revenue leaders and margin differences
- **Product line performance** — top sellers vs. top revenue contributors
- **Payment preferences** — mix and opportunities for digital incentives
- **Customer segmentation** — member vs. non-member behavior
- **Seasonality** — month-level trends (e.g., March spikes)
- **Time-of-day patterns** — sales and ratings by Morning/Afternoon/Evening
- **Tax impact** — VAT patterns by region and implications for pricing

## How to Run
1. **Clone the repository**
   ```bash
   git clone https://github.com/<your-username>/<your-repo>.git
   cd <your-repo>
   ```

2. **Create the schema and engineered features**
   ```sql
   -- In your SQL client (MySQL example)
   SOURCE schema.sql;
   ```

3. **Load data**
   - Import your CSV/data into `walmartSales.wm_sales_data` (use your client’s import tools or INSERTs).

4. **Run analysis queries**
   - Execute queries from **`solution.md`** to reproduce findings.
   - Review **`insights.md`** for key takeaways and recommendations.

## Sample Query
Top 5 product lines by revenue:
```sql
SELECT product_line,
       ROUND(SUM(total), 2) AS total_revenue
FROM wm_sales_data
GROUP BY product_line
ORDER BY total_revenue DESC
LIMIT 5;
```

## Project Structure
```
├── schema.sql           # Database schema & feature engineering (DDL + helpers)
├── financial-guide.md   # Finance metric definitions and examples
├── insights.md          # Business insights and recommendations
├── solution.md          # Collection of analysis queries
└── README.md            # Project overview (this file)
```

## Learnings
- Using SQL for **feature engineering** on real data.
- Translating raw outputs into **strategic business insights**.
- Building reproducible analytics workflows using plain SQL.

---

If you have feedback or ideas for extending the analysis (e.g., building dashboards or adding forecasting), feel free to open an issue or PR.
