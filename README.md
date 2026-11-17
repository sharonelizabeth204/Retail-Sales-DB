

<h1>Retail Sales Performance Dashboard</h1>
An interactive Power BI dashboard that turns raw retail order data into clear answers: where the business makes money, where it loses it, and what to do about it. Program built with Excel, Power BI, and DAX. Dataset: Sample Superstore


<h1>🧭 Overview</h1>
Retail businesses generate thousands of orders, but totals alone don't explain performance. This project analyses 100+ orders across 4 years to answer the questions a sales or business manager would actually ask: How are sales and profit trending over time?, Which regions, states, and customer segments perform best and worst?, Which products and sub-categories drive profit, and which lose money?, How much does discounting hurt margins?
What actions should the business take next?
The data was cleaned in Excel, modelled in Power BI, and presented as an interactive dashboard with KPIs, trends, and drill-down filters. 

<h1>🌍 Key Features</h1>
1)KPI summary cards: Total Sales, Total Profit, Profit Margin %, Total Orders, Average Order Value, and Year-over-Year growth.

2)Time-series analysis: Monthly sales and profit trends to spot seasonality and growth.

3)Regional performance: Sales and profit by region and state, with loss-making areas highlighted.

4)Product analysis: Top 10 and bottom 10 products by profit, plus category and sub-category breakdowns.

5)Discount impact: Scatter plot showing how discount levels relate to profit.

6)Interactive slicers: Filter everything by Year, Region, and Customer Segment.

7)Cross-filtering: Click any chart to filter the rest of the page.

<h1>📂 Dataset</h1>
Detail	Info
Source	Sample Superstore (https://www.kaggle.com/datasets/rohitsahoo/sales-forecasting)
Records	100+ orders
Period	[2014 to 2017]
Key columns	Order Date, Ship Mode, Segment, Region, State, Category, Sub-Category, Product Name, Sales, Quantity, Discount, Profit

<h1>🛠️ Tools & Skills Used</h1>
Microsoft Excel: data cleaning, pivot tables, exploratory analysis
Power BI Desktop: data modelling, Power Query, dashboard design
DAX: calculated measures and time intelligence
GitHub: version control and project documentation

<h1>🗂️ Repository Structure</h1>
Retail-Sales-Dashboard/
├── data/
│   ├── raw/          # Original dataset (unchanged)
│   └── cleaned/      # Cleaned Excel file
├── dashboard/        # Power BI (.pbix) file
├── screenshots/      # Dashboard images and PDF export
└── README.md

<h1>🛠️ Tools & Skills Used</h1>
Power BI Desktop: data modelling, dashboard design, interactive visuals

Power Query: data type setup and loading

DAX: calculated measures

GitHub: version control and documentation

Excel: pivot tables for exploration. 


<h1>🔄 Methodology</h1>
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


<h1>💡 Key Insights</h1>
1)Overall: Total sales of $2.26M from 4,922 orders and 793 customers, with an average order value of $459.

2)Growth: Sales rose 30.6% in 2017 and 20.3% in 2018 after a 4.2% dip in 2016. Growth came from more orders (947 in 2015 to 1,661 in 2018), while average order value fell from $506 to $435.

3)Seasonality: September, November, and December generate 43% of sales. November is the biggest month and February the weakest.

3)Regions: West leads with 31.4% of sales, then East (29.6%), Central (21.8%), and South (17.2%). Since 2015, West grew 70% and East 65%, while South grew only 18%.

4)States: California (19.7%) and New York (13.5%) together bring in about a third of all sales.

5)Categories: Technology leads with 36.6%, then Furniture (32.2%) and Office Supplies (31.2%). Phones and Chairs are the top sub-categories at about 14% each.

6)Segments: Consumer accounts for 50.8% of sales, Corporate 30.4%, and Home Office 18.8%.

7)Customers: The top 20% of customers account for 48% of sales.

<h1>✅ Business Recommendations</h1>

1. Plan around the peak season

Insight: September, November, and December produce 43% of annual sales, while January and February are the weakest months.
Recommendation: Build stock, staffing, and marketing plans ahead of the peak, and run promotions to lift the slow early-year months.

2. Grow the South

Insight: South is the smallest region (17.2% of sales) and the slowest-growing (+18% since 2015, compared with +70% for West).
Recommendation: Investigate local demand and test targeted campaigns or promotions in the South.

3. Reduce reliance on a few states

Insight: California and New York account for about 33% of sales, and the top five states for 52%.
Recommendation: Protect these markets while building up mid-sized states such as Washington, Pennsylvania, and Florida.

4. Retain the best customers

Insight: The top 20% of customers generate 48% of sales.
Recommendation: Introduce a loyalty or repeat-purchase programme aimed at high-value customers.

5. Increase order size

Insight: Average order value fell from $506 in 2015 to $435 in 2018 while the number of orders grew.
Recommendation: Bundle related products, such as Technology accessories with Phones and Machines, and promote add-ons at checkout.


<h1>How to Use</h1>
Clone or download this repository.
Open dashboard/Retail_Sales_Dashboard.pbix in Power BI Desktop (Windows).
If prompted, point the data source to data/cleaned/[your-file-name].xlsx on your machine.
Use the slicers (Year, Region, Segment) and click on charts to explore.

<h1>⚠️ Limitations</h1>
The dataset has no profit, discount, or quantity data, so this analysis covers revenue only. It cannot show which products or regions are the most profitable. It is a sample (educational) dataset, so the findings illustrate the method rather than a real company.
The analysis is historical and does not include forecasting.

<h1>🚧 Future Improvements</h1>
Add a sales forecast using Power BI's built-in forecasting
Add customer segmentation (RFM analysis)
Publish to Power BI Service with a scheduled refresh
Add a SQL layer for data preparation

<h1>📜 License</h1>
The Superstore dataset is a publicly available sample dataset used here for educational purposes.

<h1>Author</h1>

Sharon Elizabeth Rinu MCA Student | Aspiring Data Analyst / Business Analyst 📧 sharoneliz204@gmail.com | 💼  https://www.linkedin.com/in/sharon-elizabeth-rinu-79063b312?utm_source=share_via&utm_content=profile&utm_medium=member_ios
