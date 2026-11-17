# 📊 Retail Sales Performance Dashboard

**An interactive Power BI dashboard that turns four years of retail order data into clear answers: how sales are growing, when and where they happen, and what the business should do next.**

Built with **Excel, Power BI, and DAX** | Dataset: Superstore sales data (Kaggle)

---

## 🧭 Overview

Retail businesses generate thousands of orders, but totals alone don't explain performance. This project analyses **9,799 order lines (4,922 orders from 793 customers)** placed between **January 2015 and December 2018** to answer the questions a sales manager would ask:

- Is the business growing, and what is driving that growth?
- When do sales peak, and when are they weak?
- Which regions, states, categories, and products bring in the most revenue?
- Which customer segments matter most?
- What should the business do next?

The data was audited and cleaned, modelled in Power BI, and presented as an interactive dashboard with KPIs, trends, and filters. The analysis ends with data-backed recommendations.

## 📊 Dashboard Preview

![Dashboard Overview](screenshots/overview.png)

## 🌍 Key Features

- **KPI cards:** Total Orders, Total Sales, Total Customers, Average Days to Ship, and Average Order Value
- **Sales trend:** Monthly sales with one line per year, to spot seasonality and growth
- **Regional and state performance:** Sales by region and by state
- **Category and product analysis:** Sales by category and top products by sales
- **Segment split:** Share of sales across Consumer, Corporate, and Home Office
- **Interactive slicers:** Filter the whole page by Year, Region, and Segment
- **Cross-filtering:** Click any chart element to filter the rest of the page

## 📂 Dataset

| Detail | Info |
|---|---|
| Source | [Superstore sales dataset on Kaggle](https://www.kaggle.com/datasets/rohitsahoo/sales-forecasting) |
| Size | 9,800 rows in the raw file, 9,799 after cleaning |
| Period | January 2015 to December 2018 |
| Coverage | 4,922 orders, 793 customers, about 1,850 products |
| Original columns (18) | Row ID, Order ID, Order Date, Ship Date, Ship Mode, Customer ID, Customer Name, Segment, Country, City, State, Postal Code, Region, Product ID, Category, Sub-Category, Product Name, Sales |
| Columns added (4) | Year, Month Number, Month, Days to Ship |

## 🛠️ Tools & Skills Used

- **Microsoft Excel:** data checks and pivot-table exploration
- **Power BI Desktop:** data modelling, dashboard design, interactive visuals
- **Power Query:** data type setup and loading
- **DAX:** calculated measures
- **GitHub:** version control and documentation

## 🗂️ Repository Structure

```
Retail-Sales-DB/
├── data/
│   ├── raw/          # Original dataset (unchanged)
│   └── cleaned/      # Cleaned dataset used in Power BI
├── dashboard/        # Power BI (.pbix) file
├── screenshots/      # Dashboard images
└── README.md
```

## 🧹 Data Cleaning

| Check | Finding | Action |
|---|---|---|
| Duplicate rows | 1 exact duplicate order line (Row ID 3407) | Removed it |
| Postal codes | 429 codes had lost their leading zero (e.g. 1852 instead of 01852) | Padded to 5 digits |
| Blank postal codes | 11 rows, all for Burlington, Vermont | Filled with 05401 |
| Date format | dd-mm-yyyy text, which can be misread as mm-dd | Converted to yyyy-mm-dd |
| Sales precision | Values with up to 4 decimals | Rounded to 2 decimals |
| Other checks | No other blanks, extra spaces, invalid dates, or zero/negative sales | None needed |
| Helper columns | None in the source | Added Year, Month Number, Month, and Days to Ship |

The original file is kept untouched in `data/raw/`.

## 🔄 Methodology

1. **Defined business questions** first, so every chart has a purpose.
2. **Audited and cleaned the data** (see the table above).
3. **Explored the data with pivot tables** to find trends and outliers before designing visuals.
4. **Loaded the cleaned CSV into Power BI** and set column types in Power Query (dates as Date, postal codes as Text, sales as Decimal).
5. **Created DAX measures** for the KPIs (below).
6. **Designed the dashboard** with KPI cards, a trend line, region, state, category, product, and segment views, and slicers.
7. **Extracted insights** and turned them into recommendations using an Insight → Recommendation format.

### DAX Measures

```DAX
Total Sales = SUM(Orders[Sales])
Total Orders = DISTINCTCOUNT(Orders[Order ID])
Avg Order Value = DIVIDE([Total Sales], [Total Orders])
Total Customers = DISTINCTCOUNT(Orders[Customer ID])
Avg Days to Ship = AVERAGE(Orders[Days to Ship])
```

## 💡 Key Insights

1. **Overall:** Total sales of **$2.26M** from **4,922 orders** and **793 customers**, with an average order value of **$459**.
2. **Growth:** Sales rose 30.6% in 2017 and 20.3% in 2018 after a 4.2% dip in 2016. Growth came from more orders (947 in 2015 to 1,661 in 2018), while average order value fell from $506 to $435.
3. **Seasonality:** September, November, and December generate **43%** of sales. November is the biggest month and February the weakest.
4. **Regions:** West leads with **31.4%** of sales, then East (29.6%), Central (21.8%), and South (17.2%). Since 2015, West grew 70% and East 65%, while South grew only 18%.
5. **States:** California (19.7%) and New York (13.5%) together bring in about a third of all sales.
6. **Categories:** Technology leads with **36.6%**, then Furniture (32.2%) and Office Supplies (31.2%). Phones and Chairs are the top sub-categories at about 14% each.
7. **Segments:** Consumer accounts for 50.8% of sales, Corporate 30.4%, and Home Office 18.8%.
8. **Customers:** The top 20% of customers account for **48%** of sales.

## ✅ Business Recommendations

**1. Plan around the peak season**
- **Insight:** September, November, and December produce 43% of annual sales, while January and February are the weakest months.
- **Recommendation:** Build stock, staffing, and marketing plans ahead of the peak, and run promotions to lift the slow early-year months.

**2. Grow the South**
- **Insight:** South is the smallest region (17.2% of sales) and the slowest-growing (+18% since 2015, compared with +70% for West).
- **Recommendation:** Investigate local demand and test targeted campaigns or promotions in the South.

**3. Reduce reliance on a few states**
- **Insight:** California and New York account for about 33% of sales, and the top five states for 52%.
- **Recommendation:** Protect these markets while building up mid-sized states such as Washington, Pennsylvania, and Florida.

**4. Retain the best customers**
- **Insight:** The top 20% of customers generate 48% of sales.
- **Recommendation:** Introduce a loyalty or repeat-purchase programme aimed at high-value customers.

**5. Increase order size**
- **Insight:** Average order value fell from $506 in 2015 to $435 in 2018 while the number of orders grew.
- **Recommendation:** Bundle related products, such as Technology accessories with Phones and Machines, and promote add-ons at checkout.

## ▶️ How to Use

1. Clone or download this repository.
2. Open `dashboard/Retail_Sales_Dashboard.pbix` in **Power BI Desktop** (Windows).
3. If prompted, point the data source to `data/cleaned/sampledb_cleaned.csv` on your machine (Home → Transform data → Data source settings → Change Source).
4. Use the Year, Region, and Segment slicers, and click on charts to explore.

## ⚠️ Limitations

- The dataset has **no profit, discount, or quantity data**, so this analysis covers revenue only. It cannot show which products or regions are the most profitable.
- It is a sample (educational) dataset, so the findings illustrate the method rather than a real company.
- The analysis is historical and does not include forecasting.

## 🚧 Future Improvements

- Add profit and discount data to analyse margins and loss-making products
- Add a Date table and a year-over-year growth measure
- Add customer segmentation (RFM analysis)
- Add a sales forecast
- Publish to Power BI Service with a scheduled refresh

## 📜 Note

This project was built for learning and portfolio purposes. The Superstore dataset is a publicly available sample dataset.

## 👤 Author

**Sharon Elizabeth Rinu**
MCA Student | Aspiring Data Analyst / Business Analyst

📧 [sharoneliz204@gmail.com](mailto:sharoneliz204@gmail.com)
💼 [LinkedIn](https://www.linkedin.com/in/sharon-elizabeth-rinu-79063b312)
🐙 [GitHub](https://github.com/sharonelizabeth204)
