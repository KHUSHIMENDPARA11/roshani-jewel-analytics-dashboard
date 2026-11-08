# Roshani Jewel: Business Analytics Dashboard

A Microsoft Fabric and Power BI project that answers four business questions in one place: what is selling, which campaigns work, what is running low, and who is buying.

**Tools:** Microsoft Fabric (Lakehouse) | Power BI | DAX | SQL | Excel

![Dashboard](images/dashboard.png)

> **About the data:** this project uses a small sample dataset (3 orders, 3 customers, 3 products, 3 campaigns). The goal was to design a clean data model and dashboard that can scale to real data. Insights are directional, not statistically conclusive.

## Business questions

- How much revenue and net sales are we making, and from which products?
- Which marketing campaigns give the best return on spend?
- Which products are running low on stock?
- Which sales channels and customers drive orders?

## Data model (star schema)

| Table | Type | What it holds |
|---|---|---|
| FactSales | Fact | Orders, quantity, unit price, discount, shipping cost, sales channel |
| FactMarketing | Fact | Campaign spend, clicks, conversions, revenue generated |
| FactInventory | Fact | Stock available, reorder level, warehouse |
| DimProduct | Dimension | Product name, category, material, cost price, selling price, supplier |
| DimCustomer | Dimension | Age group, city, state, new or returning segment |
| DimDate | Dimension | Date, month, quarter, year |

## KPIs

| KPI | Value |
|---|---|
| Total Revenue | 425 |
| Net Sales | 410 |
| Total Orders | 3 |
| Customer Count | 3 |
| Marketing ROI | 11.71 (about 11.7x the spend) |

## Dashboard pages and visuals

- Total revenue by order date
- Total revenue by product
- Marketing spend vs marketing revenue by campaign
- Inventory available by product
- Slicers: ProductName, CampaignName, SalesChannel

## Key findings

- **Products:** Pearl Gold Necklace earned the most revenue (170 of 425).
- **Campaigns:** the email campaign (Minimal Jewelry Promo) had the best ROI (13.0x) and the lowest cost per conversion (5.00). Google Ads had the best conversion rate (3.6%). Instagram had the lowest (2.3%).
- **Inventory:** Kundan Bridal Earrings had 25 units against a reorder level of 40, the only product below its threshold.

## Repository structure

```
roshani-jewel-analytics-dashboard/
├── README.md
├── data/                 Customer, Products, Sales, Inventory, Marketing, Date (Excel)
├── lakehouse/            Fabric Lakehouse table definitions (SQL)
├── dashboard/            Dashboard PDF export
└── images/               Dashboard screenshots
```

## Next steps

- Calculate profit from cost price (the Products table already has it).
- Add more months of data for trends and forecasting.
- Compare new and returning customers by city and age group.
- Schedule automatic data refresh.

## Read the full write-up

Article on Medium: *add your link here after publishing*

## Contact

**Khushi Mendpara** | Data and Marketing Analytics Analyst, New York
Portfolio: https://khushimendpara11.github.io/
LinkedIn: https://www.linkedin.com/in/khushi-mendpara/
