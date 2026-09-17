# ☕ Coffee Shop Sales Analysis (Python)

An end-to-end analysis of 1,313 coffee sales transactions (March to August 2024), covering data quality checks, demand trends, product performance, pricing, and customer loyalty.

This project extends my earlier **Excel dashboard** built on the same data (Power Query, Power Pivot, DAX, PivotTables). Rebuilding it in Python let me test the dashboard's conclusions, and it changed some of them.

## Key findings

**1. August was the strongest month, not the weakest.** The Excel dashboard showed total orders per month, and August looked lowest. But the data ends on 17 August. After adjusting for the number of days covered, August had the highest demand of the period (10.6 orders per day, versus 6.6 in March).

![Monthly trend](figures/01_monthly_trend.png)

**2. Two drinks bring in almost half of revenue.** Americano with Milk is the most ordered drink, while Latte earns the most revenue. Together they generate 47.7% of revenue.

![Products](figures/02_products.png)

**3. Demand peaks from 10:00 to 11:59.** The morning shift accounts for 39% of orders, and the time of day matters much more than the day of the week.

![Heatmap](figures/03_weekday_hour_heatmap.png)

**4. A July price cut increased volume but reduced revenue.** Card prices were cut by 13% to 21% in July. In the following six weeks, orders per day rose by about 11%, but revenue per day fell by about 7%. Since this is observational data, the change cannot be attributed to the price cut alone.

![Price and demand](figures/04_price_and_demand.png)

**5. Revenue depends on a small loyal base.** 62% of customers bought only once, but the 197 repeat customers generated 74% of card revenue, and the top 10 customers alone generated 27%.

![Customer segments](figures/05_customer_segments.png)

## Recommendations
1. Track demand as orders per day so partial months do not mislead decisions.
2. Keep Latte and Americano with Milk well stocked ahead of the morning peak.
3. Introduce a loyalty reward to protect the repeat customer base.
4. Review the July price cut and test future price changes with a controlled experiment.

## Limitations
- One location and less than six months of data, so seasonality cannot be separated from trends.
- Cash payments (about 7% of orders) have no customer ID, so customer analysis uses card payments only.
- A card ID is only a proxy for a person.

## Project structure
```
coffee-sales-analysis/
├── coffee_sales_analysis.ipynb   # full analysis with code, charts, and commentary
├── src/data_prep.py              # data loading and feature engineering
├── data/coffee_sales.csv         # raw transactions
├── figures/                      # charts exported by the notebook
└── requirements.txt
```

## How to run
```bash
pip install -r requirements.txt
jupyter notebook coffee_sales_analysis.ipynb
```

## Tools
Python, pandas, matplotlib, seaborn, Jupyter

## Data source
Dataset: [ADD DATASET NAME AND LINK HERE]
