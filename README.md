# 2020 Restaurant Industry Performance Analysis

SQL | PostgreSQL | Business Intelligence

# Project Overview

This project analyzes restaurant performance data from 2020 using rankings published by Restaurant Business:

Top 250 Chains

Top 100 Independents

Future 50

The goal was to understand:

Does scale guarantee dominance?

Which business models performed best during the pandemic?

Is revenue driven by expansion or operational efficiency?

# Dataset Description

The dataset contains three tables:

Table	Description
top_250	Large restaurant chains ranked by revenue

independence100	Top performing independent restaurants

future50	Emerging restaurant brands

Key columns analyzed:

restaurant

sales

units

average_check

city

state

# Tools Used

PostgreSQL

SQL (Aggregation, Grouping, Ranking, Derived Metrics)

Data Cleaning & Type Handling

# Business Questions

Do large chains outperform independents?

Does number of units (locations) correlate with efficiency?

Which brands generate the highest revenue per location?

What business model proved strongest in 2020?

# Key Analysis
1️⃣ Average Sales Comparison
SELECT 'Top 250' AS category, AVG(sales)
FROM top_250
UNION ALL
SELECT 'Independents', AVG(sales)
FROM independence100;

Initial observation showed Independents had higher average sales.

However, this comparison was misleading because chains operate multiple locations.

2️⃣ Revenue Per Location (True Efficiency Metric)
SELECT restaurant,
       sales,
       units,
       ROUND(sales / units, 2) AS sales_per_unit
FROM top_250
ORDER BY sales_per_unit DESC
LIMIT 10;

This adjusted for scale by measuring performance per unit.

# Major Insight

Mastro's Restaurants ranked #1 in revenue per location while operating only 18 units.

This reveals:

Premium positioning strategy

High average ticket value

Strong unit-level profitability

In contrast, large-scale chains such as McDonald's generate high total revenue through scale, but lower revenue per location.

# Strategic Interpretation

The data reveals two successful business models in 2020:

Scale Model

Many units

Revenue driven by expansion

Lower per-location revenue

Premium Efficiency Model

Fewer locations

High revenue per unit

Strong pricing power

2020 demonstrated that efficiency at the unit level can outperform expansion-based growth during economic stress.

# Business Recommendation

Organizations should:

Measure performance at unit level

Benchmark revenue per location against premium competitors

Prioritize profitability per store before aggressive expansion

# Conclusion

The analysis shows that larger size does not automatically equal stronger performance.

During 2020, operational efficiency and premium positioning were stronger resilience indicators than scale alone.than scale alone.
