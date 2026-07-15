# AI-Powered Retail Analytics Dashboard | Power BI

An end-to-end business intelligence system built for AdventureWorks, a multinational retail company selling bikes, accessories, and clothing across multiple continents. The report goes beyond static reporting — it models pricing scenarios, segments customer behavior, and uses Power BI's AI visuals to surface drivers that aren't visible in a plain table.

**Tools used:** Power BI Desktop · DAX · Power Query (M) · Data Modeling · AI Visuals (Q&A, Decomposition Tree, Key Influencers)

🎥 **Video walkthrough:** 
<p align="center">
  <video src="https://github.com/AyemaAmir/AI-Powered-Retail-Analytics-Dashboard-Power-BI/raw/main/AI-Powered%20Retail%20Analytics%20Dashboard%202026-07-15%2011-30-05.mp4" width="80%" controls>
    Your browser does not support the video tag.
  </video>
</p>

---

## Business Context

AdventureWorks had transactional data sales, returns, customers, products, territories, but no unified way to answer the questions that actually drive decisions:

- Is the business growing, and where is it heading? *(Leadership)*
- Which regions should we prioritize for expansion? *(Sales)*
- Which products are profitable, and what happens if we adjust price? *(Merchandising)*
- Who are our most valuable customers, and what do they have in common? *(Marketing)*

This report was built to answer each of those, for each of those audiences, in one connected model.

## Data Source

Data is derived from the official [Microsoft AdventureWorks sample database](https://learn.microsoft.com/en-us/sql/samples/adventureworks-install-configure). It arrived as disconnected operational exports — Calendar, Customer, Product, Product Subcategory, Product Category, Territory, Sales (2020–2022), and Returns — with no relationships or calculations, replicating a real raw data handoff.

## The Pipeline

```
Raw Data → Power Query → Cleaning & Transformation → Unpivot → Relationships 
→ Star Schema → DAX Measures → Business KPIs → Interactive Reports → AI Insights → Business Decisions
```

## Project Highlights

This project involved:

- Cleaning and transforming raw exports into an analysis-ready model using Power Query
- Unpivoting a wide regional sales table (Product Category Sales) into a proper long format
- Building a star schema with two fact tables (Sales, Returns) around Calendar, Customer, Territory, and Product dimensions, with Product snowflaking into Subcategory and Category
- Creating a disconnected Rolling Calendar table for rolling time-intelligence calculations independent of the main date filtering
- Building disconnected parameter tables to drive Field Parameters and a What-If price simulator
- Writing 38 DAX measures spanning KPIs, time intelligence, targets, and simulation logic
- Designing a fully interactive, branded dashboard with custom tooltips, conditional formatting, and AI-powered visuals

## DAX Measures — Organized by Purpose

- **Core KPIs:** Total Revenue, Profit, Orders, Returns, Customers, Return Rate, Average Price
- **Contribution Analysis:** % of All Orders, % of All Returns (via `ALL`/`ALLSELECTED` context transition)
- **Time Intelligence:** Rolling 10-day Revenue, Rolling 90-day Profit, Previous Month comparisons, YTD Revenue
- **Targets & Gaps:** Order/Profit/Revenue Targets with matching Gap measures, feeding the gauge visuals
- **What-If Simulation:** Adjusted Price, Revenue, and Profit — driven by a live pricing parameter
- **Behavioral Segmentation:** Bulk Orders, High Ticket Orders, Weekend Orders
- **Category Deep-Dive:** Bike Sales, Bike Returns, Bike Return Rate

## Report Walkthrough — 4 Pages, 4 Business Questions

**Executive Dashboard**  *Is the business healthy?* High-level KPIs for revenue, profit, orders, and return rate, with trend and forecast, plus drill-through into product detail.

**Map View**  *Where are we strong, and where should we expand?* Orders and revenue by country and continent, filterable by region.

**Product Detail**  *Which products win, and what if we change price?* Performance against order/revenue/profit targets, plus a live What-If price adjustment simulator comparing total vs. adjusted profit.

**Customer Detail**  *Who are our best customers?* Total customers vs. revenue-per-customer toggle, top 100 customer ranking, and segmentation by income and occupation.

## AI & Advanced Analytics

- **Q&A:** Natural language exploration for non-technical stakeholders
- **Decomposition Tree:** Drills Category → Subcategory → Product to root-cause order and revenue movement
- **Key Influencers / Top Segments:** Surfaces non-obvious drivers e.g., marital status predicts homeownership more strongly than income or education; product cost correlates directly with average retail price increases

## Custom UI Elements

- Branded, dark-themed design across all pages
- Conditional formatting highlighting high-return products in red
- Custom tooltip page showing a mini-dashboard on hover instead of the default tooltip
- Filter pane for year and geography

## Key Insights

- Revenue grew from ~$300–400K/month to over $1.5M/month starting mid-2021 — a clear inflection point worth investigating for cause (campaign, seasonality, or channel shift)
- Tires and Tubes dominate order volume within Accessories, while Sport-100 Helmets carry a disproportionately high return rate (3%+) despite strong revenue
- Marital status is a stronger predictor of homeownership than income or education level (1.62x likelihood)
- Skilled Manual customers, despite a lower average income bracket, include some of the highest individual revenue drivers in the customer base
