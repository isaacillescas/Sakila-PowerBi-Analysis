# Sakila Database Analysis with Power BI

Data analysis project using the Sakila sample database (SQL Server) with 
Power BI for data modeling and visualization.

## 👤 Author

**Isaac Illescas**
- GitHub: [@isaacillescas](https://github.com/isaacillescas)

-----------------------------------------------------------------------------------------------
-----------------------------------------------------------------------------------------------

## Report Pages

- **Executive Summary** — Key KPIs (total rentals, revenue, active customers, 
  average ticket) and monthly revenue trend.
- **Top Rented Films (Top 10 Annual)** — Most rented films by count.
- **Revenue by Genre** — Revenue distribution by film category.
- **Active Customers** — Rentals and spending per customer.
- **Employee Performance** — Revenue and rentals processed per staff member.
- **Seasonality** — Rental distribution by day of the week and a calendar 
  heatmap (month vs. day of week).

-----------------------------------------------------------------------------------------------

## Tech Stack
- SQL Server (Sakila sample database)
- Power BI Desktop (data modeling and visualization)
- DAX (measures and relationships, including USERELATIONSHIP for 
  ambiguous relationship paths)

-----------------------------------------------------------------------------------------------

##  Repository Contents
- `data/` — SQL scripts to create and populate the Sakila database
- `powerbi/` — Full Power BI report (.pbix)

-----------------------------------------------------------------------------------------------

##  How to Use
1. Run `data/createtables.sql` on your SQL Server instance.
2. Run `data/sql-server-sakila-insert-data.sql` to populate the data.
3. Open `powerbi/Business Data Analysis with Power BI.pbix` in Power BI Desktop.
4. Update the data source connection (server/instance) to match your environment.

----------------------------------------------------------------------------------------------

## Technical Challenges Solved
- Resolved datetime vs. date mismatch between the fact tables (`rental`, 
  `payment`) and the `Calendario` date table using calculated columns 
  (`DATEVALUE`) to enable correct time-based analysis.
- Managed inactive/ambiguous relationships between `rental`, `payment`, 
  `customer`, and `staff` using `USERELATIONSHIP()` in DAX measures, 
  since multiple relationship paths existed between these tables.
- Applied custom sort order to categorical columns (Month, Day of Week) 
  via "Sort by Column" to avoid default alphabetical ordering.
