# Task 3: Customer Segmentation Deep Dive

## ApexPlanet Data Analytics Internship

## Project Objective

This project completes **Task 3: Deep-Dive Analysis & Interactive Dashboarding** of the ApexPlanet Data Analytics Internship. The objective is to identify high-value, medium-value, and low-value customers using sales data, and present the findings through a functional, interactive Power BI dashboard.

## Business Problem

Not every customer contributes the same amount of revenue. This analysis segments customers by their total revenue contribution so that the business can identify valuable customers, understand their buying behaviour, and make more focused marketing and retention decisions.

## Dataset

The dashboard uses the cleaned sales dataset created in Task 1 and previously analysed in Task 2.

- **Records:** 1,000 sales transactions
- **Customer identifier:** `Customer_ID`
- **Transaction identifier:** `Transaction_ID`
- **Key fields:** Order Date, City, Age Group, Category, Product, Quantity, Unit Price, and Total Sales

## Tools Used

- Power BI Desktop
- DAX
- Microsoft Excel

## Customer Segmentation Method

A customer-level summary table was created using `Customer_ID`. Customers were segmented according to their total revenue contribution:

| Segment | Rule | Business Meaning |
|---|---|---|
| High Value | Top 25% customers by total revenue | Highest-priority customers for retention and personalised offers |
| Medium Value | Middle 50% customers by total revenue | Customers with potential to grow into the high-value group |
| Low Value | Bottom 25% customers by total revenue | Customers suitable for awareness, activation, and low-cost campaigns |

## Core KPIs

| KPI | Formula / Definition | Business Purpose |
|---|---|---|
| Total Revenue | Sum of `Total_Sales` | Measures overall sales performance |
| Total Transactions | Distinct count of `Transaction_ID` | Measures completed sales activity |
| Average Order Value | Total Revenue / Total Transactions | Measures average revenue earned per transaction |
| Revenue per Customer | Total Revenue / Distinct Customers | Measures customer value |
| Total Quantity | Sum of `Quantity` | Measures units sold and product demand |

## Power BI Dashboard Features

### Interactive Slicers

- Customer Segment
- City
- Age Group
- Category
- Order Date

### Deep-Dive Visuals

- Revenue by Customer Segment
- Customers by Segment
- Revenue by City and Customer Segment
- Customer Value Analysis scatter chart
- Top 10 High-Value Customers table

The slicers interact with the KPI cards, charts, and customer table, allowing users to explore the dashboard by customer group, location, demographics, product category, and date range.

## Data Model

Two tables are used in the report:

1. **Sales_Dataset** - Transaction-level sales data.
2. **Customer_Summary** - Customer-level table containing customer revenue, transactions, total units, and customer segment.

An active one-to-many relationship connects:

```text
Customer_Summary[Customer_ID] (1) --> Sales_Dataset[Customer_ID] (*)
```

This relationship allows the Customer Segment slicer to filter transaction-level sales visuals correctly.

## Key Business Insights

- High-value customers generate the largest share of total revenue and should receive retention-focused campaigns and personalised offers.
- Medium-value customers represent the largest customer group and are strong candidates for upselling and cross-selling.
- City and category filters reveal where each customer segment contributes most to revenue.
- The customer-value scatter chart helps identify customers with high transaction frequency and high revenue contribution.
- The Top 10 High-Value Customers table supports targeted customer relationship management.

## Project Files

```text
ApexPlanet-Task3-Customer-Segmentation-Dashboard/
|
|-- README.md
|-- Task3_Customer_Segmentation_Interactive_Dashboard.pbix
|-- Task3_Deep_Dive_Report.pdf
|
`-- images/
    `-- task3_dashboard.png
```

## How to Use the Dashboard

1. Open `Task3_Customer_Segmentation_Interactive_Dashboard.pbix` in Power BI Desktop.
2. Navigate to the **Customer Segmentation Deep Dive** page.
3. Use the slicers to filter the analysis by segment, city, age group, category, and date.
4. Hover over chart points for details and select visuals to cross-filter the dashboard.
5. Review the Top 10 High-Value Customers table for customer-level insights.

## Deliverables

- Interactive Power BI dashboard (`.pbix`)
- Deep-dive report (`.pdf`)
- Dashboard screenshot

## Key Skills Demonstrated

- Customer segmentation
- Deep-dive sales analysis
- DAX measures and calculated tables
- Power BI data modelling and relationships
- Interactive slicers and cross-filtering
- KPI dashboard design
- Customer value analysis
