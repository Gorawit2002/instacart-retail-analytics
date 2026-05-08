# Instacart Retail Customer Behavior & Market Basket Analytics

Analyzed 3M+ retail transactions from the Instacart Market Basket dataset to uncover customer purchasing behavior, identify cross-selling opportunities, and build actionable Power BI dashboards.

## Dashboard Preview

### Page 1: Executive Overview
![Executive Overview](assets/page1_executive_overview.png)

### Page 2: Customer Purchase Behavior
![Customer Behavior](assets/page2_customer_behavior.png)

### Page 3: Product & Category Performance
![Product Category](assets/page3_product_category.png)

### Page 4: Market Basket & Cross-Sell Insights
![Market Basket](assets/page4_market_basket.png)

## Key Findings

**Customer Behavior**
- Customers order most on weekends (Sat-Sun), peaking at 10 AM
- 39% are Regular shoppers (6-15 orders), while Heavy users (13%) drive the highest loyalty with 70% reorder rate
- Average basket size is ~10 items across all segments — loyalty comes from repeat purchases, not larger baskets

**Product & Category**
- Banana is the #1 product by volume (472K orders) with 84% reorder rate
- Produce and Dairy Eggs are hero departments, driving the most traffic
- Dairy products dominate the top reordered items — must-never-out-of-stock category

**Market Basket (Cross-Sell)**
- Organic Garlic + Yellow Onion: Lift 5.7 → strongest association, place together on shelves
- Large Lemon + Limes: Lift 4.1 → citrus bundle opportunity
- Organic Raspberries + Strawberries: Lift 3.0, high confidence → ideal for bundle promotions

## Business Recommendations

1. **Shelf Placement**: Place Garlic + Onion together, Lemon + Limes together (based on Lift scores)
2. **Promotion Timing**: Focus promotions on Saturday-Sunday 9AM-3PM for maximum reach
3. **Bundle Deals**: Create berry bundles (Raspberries + Strawberries) and citrus bundles (Lemon + Limes)
4. **Customer Retention**: Target Light users (29%) with personalized reminders at 14-day intervals

## Project Structure

```
instacart-retail-analytics/
├── assets/                  # Dashboard screenshots for README
├── data/
│   └── processed/           # Cleaned CSVs for Power BI
├── sql/
│   ├── 01_data_join.sql     # Analytical dataset creation
│   ├── 02_kpi_queries.sql   # Business KPIs and metrics
│   └── 03_reorder_analysis.sql  # Reorder & segmentation queries
├── notebooks/
│   └── 01_data_understanding.ipynb  # EDA, market basket, segmentation
├── powerbi/
│   └── instacart_dashboard.pbix
├── .gitignore
└── README.md
```

## Dataset

**Source**: [Instacart Market Basket Analysis](https://www.kaggle.com/c/instacart-market-basket-analysis/data) (Kaggle)

| Table | Rows | Description |
|-------|------|-------------|
| orders | 3,421,083 | Order-level data with timing info |
| order_products__prior | 32,434,489 | Line items for prior orders |
| products | 49,688 | Product names + category mapping |
| aisles | 134 | Aisle dimension |
| departments | 21 | Department dimension |

> Raw data files are not included due to size. Download from Kaggle and place in `data/raw/`.

## Tech Stack

- **Python**: Pandas, NumPy, Matplotlib, Seaborn (EDA & Market Basket Analysis)
- **SQL**: Analytical queries for KPIs, segmentation, and market basket
- **Power BI**: 4-page interactive dashboard
- **Google Colab**: Development environment

## Methodology

1. **Data Understanding**: Explored schema, validated join keys, checked data quality
2. **Data Cleaning**: Verified missing values (NaN in `days_since_prior_order` = first orders), no duplicates found
3. **Exploratory Analysis**: Order timing patterns, department/product rankings, basket size distribution
4. **Market Basket Analysis**: Computed co-purchase frequency, Support, Confidence, and Lift for top 100 products across 32M+ rows
5. **Customer Segmentation**: Grouped 206K users into 4 segments by order frequency (Light, Regular, Frequent, Heavy)
6. **Dashboard**: Built 4-page Power BI dashboard covering executive KPIs, customer behavior, product performance, and cross-sell insights

## Author

**Gorawit Khovintasets**
- GitHub: [Gorawit2002](https://github.com/Gorawit2002)
- Portfolio: [gorawit-portfolio.vercel.app](https://gorawit-portfolio.vercel.app/)