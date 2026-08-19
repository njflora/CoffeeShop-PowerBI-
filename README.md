# CoffeeShop-PowerBI-

Coffee Shop Sales Dashboard

A Power BI dashboard analyzing transaction-level sales data for a three-location coffee shop chain, built to answer core retail performance questions: revenue trends, peak trading hours, store comparison, and product-level profitability.

Business questions answered
How is revenue trending over time, and what does month-over-month growth look like?
Which hours of the day drive the most sales, and how should staffing/inventory respond?
How do the three store locations compare in performance?
Which products and categories contribute most to revenue?
Tools used

Power BI Desktop, Power Query (M), DAX, Power BI Service

Data source

Coffee Shop Sales — Maven Analytics Data Playground (public dataset, ~149,000 transaction records, Jan–Jun 2023)

What I did

Data modeling The source data arrived as a single flat file. I normalized it into a star schema in Power Query — splitting it into a Fact_Transactions table plus Dim_Product, Dim_Store, and Dim_Date dimension tables — to reflect standard BI data modeling practice and support efficient, scalable DAX measures.

DAX measures Built beyond basic aggregations, including:

Time intelligence: Revenue MTD, month-over-month growth %
Ranking & contribution: product revenue rank, % of total revenue per product (Pareto-style analysis)
Store and hourly performance breakdowns

Report design Two report pages — an Overview (KPIs, revenue trend, store comparison, hourly sales) and a Products deep-dive (top products, category mix, product-level detail table) — with synced store and date slicers across both pages.

Screenshots

<img width="1435" height="807" alt="Coffee Shop - Page 1" src="https://github.com/user-attachments/assets/99afcd1b-60ac-47e4-aca1-b6dbe6ca6b31" />
<img width="1416" height="806" alt="Coffee Shop - Page 2" src="https://github.com/user-attachments/assets/63e66a82-793c-454a-96dd-a3d4deaf2771" />
<img width="338" height="548" alt="Coffee Shop - Page 1 (Mobile)" src="https://github.com/user-attachments/assets/0fc5e216-1860-4733-b42b-26eaf281ab0b" />

Notes / limitations

Dataset covers Jan–Jun 2023 only, so year-over-year comparisons aren't possible — analysis focuses on month-over-month and intra-day patterns instead.

Dataset was already clean

Corrected a common DAX pitfall where a time-intelligence measure evaluated in the wrong filter context (whole-dataset instead of single-month), forcing correct month-over-month context using FILTER/ALL.

Kept 2nd page visually basic (to save time and move on to the next use case).

