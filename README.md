## **Mobile Sales Analytics Dashboard — Power BI**

An interactive Power BI dashboard analyzing mobile phone sales transactions — built to explore sales trends, customer behavior, and payment patterns across cities, brands, and time.

<img width="578" height="329" alt="Dash1" src="https://github.com/user-attachments/assets/572bd93d-c192-43da-8444-3dadb7336fd6" />


## **📊 Overview**

This project transforms raw mobile sales transaction data into a clean, interactive dashboard with KPI cards, a custom date dimension, and slicers for drill-down analysis.

Key metrics tracked:
Total Sales (₹769M)
Total Quantity Sold (19K units)
Total Transactions (4K)
Average Price per Unit (₹40.11K)
Interactive filters: Mobile Model, City, Payment Method, and Month (via a custom calendar table)

## **🗂️ Dataset**
Source: Mobile sales transaction records (Excel)
Size: ~3,835 rows
Fields: Transaction ID, Day/Month/Year, Day Name, Brand, Units Sold, Price Per Unit, Customer Name, Customer Age, City, Payment Method, Customer Ratings, Mobile Model

## **🛠️ Process & Key Decisions**

1. Data Cleaning in Power Query
Promoted headers, set correct data types for all columns
Handled a tricky date parsing bug: the source had separate Day/Month/Year columns in D/M/Y order. Merging them into text and converting with type date silently broke on ~60% of rows because Power Query's default locale interpreted the text as M/D/Y, not D/M/Y.
Fix: rebuilt the date column directly from the numeric columns using #date([Year],[Month],[Day]) instead of merging + parsing text — this sidesteps locale ambiguity entirely and is more robust for any dataset with separate date-part columns.
2. Custom Calendar Table
Built a dedicated date dimension table for consistent time-intelligence (month names, sorting, filtering) instead of relying on the transaction date column directly.
3. Dashboard Design
KPI cards for headline metrics, each paired with a custom icon for visual clarity
Slicers for Mobile Model (dropdown), City, and Month for fast filtering
Layout grouped and locked in Power BI's Selection pane to keep icon/card pairs aligned during edits

## **📈 Key Insights**

Delhi and Mumbai dominate the market, together accounting for ~₹33.1 Cr of the ₹76.9 Cr total revenue (~43%) and 1,662 of 3,835 transactions (~43%) — despite spanning dozens of other cities in the dataset.
Apple leads by revenue (₹16.2 Cr), narrowly ahead of Samsung (₹16.0 Cr) and OnePlus (₹15.4 Cr), even though Apple doesn't top the units-sold chart — reflecting its higher average price point.
iPhone SE is the single best-selling model, both by units (1,430) and revenue (₹5.96 Cr), narrowly ahead of OnePlus Nord and Galaxy Note 20.
UPI is the most-used payment method at 26.4% of transactions, just ahead of Debit Card and Credit Card (24.7% each) and Cash (24.2%) — payment methods are fairly evenly split, with no single method dominating.
Sales are spread evenly across the week, with Saturday (562) and Friday (547) marginally busier than other days — no strong weekday/weekend skew in this dataset.
Average customer rating across all transactions is 3.69 / 5.

## **🎥 Demo**


https://github.com/user-attachments/assets/98931094-78ae-401a-a1ff-548325cd5c9f







