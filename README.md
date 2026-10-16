# Bike Store Sales Report — Power BI

An end-to-end Power BI report analyzing a bike retailer's sales, customer demographics, and product performance across 6 countries and 6 years of transaction data (113,036 records).

## Purpose
Built to help a bike retailer boost sales, understand customer segments, and optimize product offerings through data-driven decisions.

## Business Questions
- Which product categories and countries drive the most revenue, and how does that differ from what drives profit?
- How does customer demographic mix (age, gender) relate to purchasing behavior, spend, and seasonality?
- Which specific products or sub-categories are underperforming on margin despite strong revenue?

## Data Source
Public "Bike Sales" transaction dataset. One fact table + a custom date table. Fields include order date, customer age/gender, country/state, product hierarchy (category → sub-category → product), quantity, cost, price, profit, and revenue.

## ⚠️ Data Quality Note

No unique customer identifier: the source data has no order ID or customer ID — only order-level demographic attributes (age, gender, country). The Customer Overview page therefore reflects **order-level demographic patterns**, not individual customer behavior, retention, or lifetime value. This limitation is called out directly on that page.

## Report Structure
| Page | Purpose |
|---|---|
| Overview (Landing) | Navigation, report purpose, and page guide |
| Sales Overview | Revenue, profit, and margin trends by time, category, and geography |
| Customer Overview | Demographic breakdown by age and gender, including seasonal purchasing patterns |
| Product Overview | Category/sub-category/product performance, cost-profit comparison, margin analysis |
| About the Project | Design approach and methodology notes |
| About the Author | Background and contact |

## Approach
- Custom contiguous date table (`CALENDAR()` DAX) with a Year → Quarter → Month → Day drill hierarchy
- DAX measures for revenue share by segment, profit margin %, and a dynamic text-based insight callout that automatically names the top-performing age group
- Drillthrough page for product-level detail, used instead of in-chart drill-down due to high product cardinality
- 100% stacked "mix" charts used consistently wherever the goal is proportional share rather than raw volume, with matching naming convention across pages
- Visual design built in Figma (backgrounds, typography, iconography), paired with a custom Power BI theme file for chart colors and fonts

## Key Insights
- **Bikes generate the most revenue ($62M) but carry the lowest profit margin (~33%) of any category** — Accessories, despite far lower revenue ($15M), runs the highest margin (~59%)
- **Adults (35–64) drive roughly 50% of total revenue**, the single largest demographic segment
- **Road Bikes and Mountain Bikes together account for the majority of category revenue**, well ahead of any other sub-category
- Overall blended profit margin sits at 37.8%, masking significant variation by category

## Tech Stack
Power BI Desktop · DAX · Power Query (M) · Figma

## Limitations
- See Data Quality Notes above (duplicated years, no customer ID)
- Geography visuals reflect the 6 countries present in the source data; not a global view

## View the Report
https://app.powerbi.com/view?r=eyJrIjoiN2IyNGM2MDgtNGRlZC00ZTQ2LTk4YmYtMTc0MmZhYTYxYTk2IiwidCI6IjNkZmU5YWI2LTgxYmYtNDkxYy1iNjcwLTAxYzgyNGEwOWUxOSJ9&pageName=75d10ceed1270a4d4082&language=en-US&formatLocale=en-US

---
*Built by Karolina Literska as part of a career transition into data analytics. Feedback welcome — [LinkedIn/email].*
