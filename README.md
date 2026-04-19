Order Sales Performance Dashboard Power BI
Tool: Microsoft Power BI
Pages: 3 Interactive Dashboard Pages
Dataset: Sales order data across 2020–2021

📌 Project Overview
This project involved designing and building a comprehensive 3-page Power BI dashboard to track and analyse order sales performance across products, warehouses, customer types, and geographic regions.
The dashboard gives business stakeholders instant visibility into revenue trends, order performance, customer rankings, and regional distribution — with month-over-month (MoM) comparisons on every key metric.

📊 Key KPIs Tracked
MetricCurrent PeriodPrevious MonthChangeTotal Revenue$3.48M$4.12M▼ -15.37%Total Quantity85,995100,745▼ -14.64%Total Orders2,7053,157▼ -14.32%Average Order Value (AOV)$456.67$539.61▼ -15.37%Order Completed Rate95%——

📄 Dashboard Pages
Page 1 — Sales Overview
The main performance page giving a high-level summary of all key metrics.
Visuals Included:

4 KPI cards with MoM comparison (Revenue, Quantity, Orders, AOV)
Total Revenue Monthly Trending — line chart with average benchmark
Total Revenue by Product — horizontal bar chart (19 products)
Top 5 Customers by Amount Spent — ranked table with Quantity, AOV, and Order Count

Key Finding:
Chocolate Truffle is the highest revenue product at $0.78M — more than double the second highest product (Nougat at $0.36M)

Page 2 — Performance Analysis
A deeper analytical page exploring warehouse performance, product MoM trends, and the relationship between volume and revenue.
Visuals Included:

Total Revenue by Warehouse — bar chart (4 warehouses: AXW291, GUT930, NXH382, FLR025)
Order Completed Rate — donut gauge showing 95% completion
Product MoM Growth Table — showing Quantity, Revenue, PM, ΔPM, MoM Growth, and AOV per product
Scatter Plot — "Is there a relationship between Volume Sales and Revenue?" broken down by Customer Type (Club, Distributor, Export, Online, Wholesale)

Key Finding:
Warehouse AXW291 leads with $1.63M in revenue — more than double Warehouse GUT930 ($0.78M). The scatter plot confirms a positive correlation between volume and revenue across all customer types.

Page 3 — Geographic & Customer Analysis
A regional and customer segmentation page providing insight into where revenue comes from and who is driving it.
Visuals Included:

Total Revenue by Customer Type — donut chart (Wholesale, Online, Distributor, Club, Export)
Total Revenue by Region — bar chart (West, South, Midwest, Northeast)
Total Revenue by State — interactive US map visual
Bottom 5 Customers by Amount Spent — switchable bar chart (Top 5 / Bottom 5 toggle)

Key Finding:
Wholesale customers dominate at 41.78% ($1.46M) of total revenue. The West region leads geographically at $1.11M — more than double the Northeast at $0.47M.

💡 Key Insights & Findings
Revenue & Orders:

Total revenue declined 15.37% vs previous month — a significant drop requiring investigation
All four KPIs declined in the same period suggesting a broader demand issue rather than a product-specific one

Product Performance:

Chocolate Truffle alone accounts for 22.4% of total revenue ($0.78M of $3.48M)
Top 5 products (Chocolate Truffle, Nougat, Turkish Delight, Toffee, Brittle) account for over 50% of total revenue
Marshmallow has the lowest revenue ($0.03M) and the lowest AOV ($82.74) — a candidate for review or discontinuation

Customer Performance:

Avon Corp is the top customer by amount spent ($91,307) with 1,932 units across 57 orders
Wuxi Group has the highest order count (72) despite not being the top spender — indicating smaller but more frequent orders

Warehouse Performance:

AXW291 handles 46.8% of total revenue ($1.63M) — over-dependence on one warehouse is a supply chain risk
FLR025 handles only 10.3% ($0.36M) — may be underutilised or in a lower-demand region

Geographic Distribution:

West region leads with $1.11M — driven by high wholesale activity
Northeast significantly underperforms at $0.47M — a potential growth market


🛠️ Tools & Features Used
FeatureDetailsKPI CardsRevenue, Quantity, Orders, AOV with MoM deltaLine ChartMonthly revenue trend with average reference lineBar ChartsProduct revenue, warehouse revenue, regional revenueDonut ChartCustomer type breakdown, order completion rateScatter PlotVolume vs Revenue by Customer TypeMap VisualRevenue distribution by US StateMatrix TableCustomer ranking and product MoM performanceToggle ButtonTop 5 / Bottom 5 customer switcherYear Filter2020 / 2021 toggle with Reset buttonDAX MeasuresMoM comparison, ΔPM, AOV, Order Completed Rate

📐 DAX Measures Used
dax-- Total Revenue
Total Revenue = SUM(Orders[Amount])

-- Previous Month Revenue
PM Revenue = CALCULATE([Total Revenue], DATEADD('Date'[Date], -1, MONTH))

-- Month over Month Change
ΔPM Revenue = [Total Revenue] - [PM Revenue]

-- MoM Growth %
MoM Growth % = DIVIDE([ΔPM Revenue], [PM Revenue], 0)

-- Average Order Value
AOV = DIVIDE([Total Revenue], [Total Orders], 0)

-- Order Completed Rate
Order Completed Rate = 
DIVIDE(
    CALCULATE(COUNTROWS(Orders), Orders[Status] = "Completed"),
    COUNTROWS(Orders), 0
)

🔍 Recommendations

Investigate the 15.37% revenue decline — all KPIs dropped simultaneously suggesting an external demand issue, seasonal pattern, or data pipeline gap worth investigating
Reduce warehouse dependency on AXW291 — at 46.8% of revenue, any disruption to this warehouse poses a significant business risk. Capacity balancing across GUT930 and NXH382 is recommended
Review low-performing products — Marshmallow ($0.03M, AOV $82.74) and S'mores ($0.05M) generate minimal revenue. Consider whether promotional investment or discontinuation is more appropriate
Target Northeast region for growth — at $0.47M the Northeast significantly underperforms vs the West ($1.11M). A targeted wholesale and distributor strategy in this region could close the gap
Leverage Wuxi Group's order frequency — with 72 orders (the highest order count), Wuxi Group represents a high-engagement customer. A volume discount or loyalty incentive could increase their AOV and total spend
Monitor Bubblegum MoM decline — at -17.41% MoM decline Bubblegum has the steepest drop of any product. Investigate whether this is seasonal, a supply issue, or a pricing problem
