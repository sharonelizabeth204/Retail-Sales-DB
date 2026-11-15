# Retail-Sales-DB
#heading1
Retail Sales Performance Dashboard
An interactive Power BI dashboard that turns raw retail order data into clear answers: where the business makes money, where it loses it, and what to do about it. Program built with Excel, Power BI, and DAX. Dataset: Sample Superstore


🧭 Overview
Retail businesses generate thousands of orders, but totals alone don't explain performance. This project analyses 100+ orders across 4 years to answer the questions a sales or business manager would actually ask: How are sales and profit trending over time?, Which regions, states, and customer segments perform best and worst?, Which products and sub-categories drive profit, and which lose money?, How much does discounting hurt margins?
What actions should the business take next?
The data was cleaned in Excel, modelled in Power BI, and presented as an interactive dashboard with KPIs, trends, and drill-down filters. 

🌍 Key Features
1)KPI summary cards: Total Sales, Total Profit, Profit Margin %, Total Orders, Average Order Value, and Year-over-Year growth.
2)Time-series analysis: Monthly sales and profit trends to spot seasonality and growth.
3)Regional performance: Sales and profit by region and state, with loss-making areas highlighted.
3)Product analysis: Top 10 and bottom 10 products by profit, plus category and sub-category breakdowns.
4)Discount impact: Scatter plot showing how discount levels relate to profit.
5)Interactive slicers: Filter everything by Year, Region, and Customer Segment.
6)Cross-filtering: Click any chart to filter the rest of the page.

📂 Dataset
Detail	Info
Source	Sample Superstore (https://www.kaggle.com/datasets/rohitsahoo/sales-forecasting)
Records	100+ orders
Period	[2014 to 2017]
Key columns	Order Date, Ship Mode, Segment, Region, State, Category, Sub-Category, Product Name, Sales, Quantity, Discount, Profit

🛠️ Tools & Skills Used
Microsoft Excel: data cleaning, pivot tables, exploratory analysis
Power BI Desktop: data modelling, Power Query, dashboard design
DAX: calculated measures and time intelligence
GitHub: version control and project documentation

🗂️ Repository Structure
Retail-Sales-Dashboard/
├── data/
│   ├── raw/          # Original dataset (unchanged)
│   └── cleaned/      # Cleaned Excel file
├── dashboard/        # Power BI (.pbix) file
├── screenshots/      # Dashboard images and PDF export
└── README.md

🔄 Methodology

1. Define business questions. Wrote the questions first so every chart has a purpose.
2. Clean the data (Excel). Removed duplicates, fixed data types, handled blanks, and created helper columns (Year, Month, Profit Margin %). Original data was kept untouched in data/raw/.
3. Explore (Excel pivot tables). Ran quick pivots to find trends, outliers, and loss-making items before designing visuals.
4. Model (Power BI). Loaded the cleaned table, confirmed data types in Power Query, and built a Date table linked to Order Date.
5. Calculate (DAX). Created the measures below.

DAX
Total Sales = SUM(Orders[Sales])
Total Profit = SUM(Orders[Profit])
Profit Margin % = DIVIDE([Total Profit], [Total Sales])
Total Orders = DISTINCTCOUNT(Orders[Order ID])
Avg Order Value = DIVIDE([Total Sales], [Total Orders])
Sales LY = CALCULATE([Total Sales], SAMEPERIODLASTYEAR('Date'[Date]))
YoY Growth % = DIVIDE([Total Sales] - [Sales LY], [Sales LY])

6. Visualise. Designed the dashboard with a consistent colour palette, clear titles, and a grid layout.
7. Interpret. Turned findings into recommendations using an Insight → Evidence → Action format.


💡 Key Insights

Fill in with your actual findings.

Overall: Total sales of [$X] and profit of [$X], with a profit margin of [X%].
Growth: Sales grew [X%] year over year, peaking in [months].
Regions: [Region] led in sales; [Region] had the weakest margin at [X%].
Products: [Sub-category] was the most profitable; [Sub-category] lost [$X] overall.
Discounts: Orders with discounts above [X%] averaged a margin of [-X%].

▶️ How to Use
Clone or download this repository.
Open dashboard/Retail_Sales_Dashboard.pbix in Power BI Desktop (Windows).
If prompted, point the data source to data/cleaned/[your-file-name].xlsx on your machine.
Use the slicers (Year, Region, Segment) and click on charts to explore.

⚠️ Limitations
The dataset is a sample dataset, so results illustrate the method rather than a real company.
The analysis is historical; it does not include forecasting.
Profit figures depend on the cost data included in the source file.

🚧 Future Improvements
Add a sales forecast using Power BI's built-in forecasting
Add customer segmentation (RFM analysis)
Publish to Power BI Service with a scheduled refresh
Add a SQL layer for data preparation

📜 License
The Superstore dataset is a publicly available sample dataset used here for educational purposes.

👤 Author

Sharon Elizabeth Rinu MCA Student | Aspiring Data Analyst / Business Analyst 📧 sharoneliz204@gmail.com | 💼  
