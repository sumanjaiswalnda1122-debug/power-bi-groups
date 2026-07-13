# Power Query — Group By Practice Pack

This folder contains a small practice set for learning **Power Query's Group By feature**
(basic and advanced/multi-column grouping) using Excel and Power BI.

## Files

### 1. `PowerQuery_GroupBy_Advanced_Practice.xlsx`
An Excel workbook with two sheets:

- **Sales_Data** — a 12-row sample sales table with columns:
  `OrderID, Date, Region, City, Customer, Salesperson, Product, Category, Quantity, Unit Price, Total`
- **PowerQuery_Questions** — the practice exercises to solve in Power Query, split into two sections:

  **Basic Group By**
  1. Group by `Region` → Total Sales (sum of `Total`)
  2. Group by `Salesperson` → Total Quantity and Total Sales
  3. Group by `Category` → Average Unit Price

  **Advanced Group By (multiple columns)**
  4. Group by `Region` & `City` → Total Sales and Count of Orders
  5. Group by `Salesperson` & `Product` → Total Quantity and Max Unit Price

### 2. `error_solve.pbix`
A Power BI Desktop file with a single loaded table, **Raw_Data**, and one blank report page.
It's set up as a "spot the error / fix it" exercise — load the query, work through any errors
in the applied steps, and use it to reproduce the same Group By tasks as the Excel exercise
(or build visuals on top of the results once the query is clean).

## How to use this pack

1. Open the `.xlsx` file and inspect `Sales_Data`.
2. In Excel: select the table → **Data → From Table/Range** (or **Data → Get Data → Launch
   Power Query Editor**) to load it into Power Query.
3. Work through questions 1–5 in `PowerQuery_Questions` using **Transform → Group By**:
   - Questions 1–3 use a single grouping column.
   - Questions 4–5 use **Advanced** mode in the Group By dialog (multiple grouping columns
     and/or multiple aggregated columns).
4. Open `error_solve.pbix` in Power BI Desktop, go to the **Power Query Editor**
   (Transform Data), check the `Raw_Data` query's applied steps for errors, fix them, then
   practice the same grouping tasks there.

## Suggested outcomes to check your work

| # | Grouped by | Aggregation(s) | Expected rows |
|---|---|---|---|
| 1 | Region | Sum of Total | 3 (North, South, West) |
| 2 | Salesperson | Sum of Quantity, Sum of Total | 3 (Ravi, Neha, Amit) |
| 3 | Category | Average of Unit Price | 2 (Electronics, Accessories) |
| 4 | Region + City | Sum of Total, Count of Orders | 6 |
| 5 | Salesperson + Product | Sum of Quantity, Max of Unit Price | up to 6 |

*(Row counts assume no errors were introduced while grouping — use them as a sanity check.)*
