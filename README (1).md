# Power Query — Group By Practice Pack

This folder contains a practice set for learning **Power Query's Group By feature**
(basic and advanced/multi-column grouping) using Excel and Power BI.

## Files

### 1. `PowerQuery_GroupBy_Advanced_Practice.xlsx`
The exercise sheet. Two tabs:

- **Sales_Data** — a 12-row sample sales table with columns:
  `OrderID, Date, Region, City, Customer, Salesperson, Product, Category, Quantity, Unit Price, Total`
- **PowerQuery_Questions** — the 5 Group By tasks to solve, split into two sections:

  **Basic Group By**
  1. Group by `Region` → Total Sales (sum of `Total`)
  2. Group by `Salesperson` → Total Quantity and Total Sales
  3. Group by `Category` → Average Unit Price

  **Advanced Group By (multiple columns)**
  4. Group by `Region` & `City` → Total Sales and Count of Orders
  5. Group by `Salesperson` & `Product` → Total Quantity and Max Unit Price

### 2. `groups.pbix`
The Power BI solution/working file. Its data model holds **6 queries**:

| Query name | Likely purpose |
|---|---|
| `Sales_Data` | The original raw data, loaded as-is |
| `Sales_Data (2)` – `Sales_Data (6)` | One grouped-output query per practice question (5 queries → questions 1–5 above) |

The report itself has a single blank page — the file is meant for working inside the
**Power Query Editor** (Transform Data), not for viewing pre-built visuals.

## How to use this pack

1. Open `PowerQuery_GroupBy_Advanced_Practice.xlsx` and read the 5 questions on
   `PowerQuery_Questions`.
2. Open `groups.pbix` in Power BI Desktop → **Transform Data** to enter the Power Query
   Editor.
3. Inspect each `Sales_Data (n)` query's **Applied Steps** to see how that Group By was
   built (which column(s) were grouped, which aggregations were used, Basic vs Advanced
   mode).
4. Try rebuilding each grouping yourself from `Sales_Data` (right‑click a column →
   **Group By**) before checking it against the matching `Sales_Data (n)` query.

## Expected results (for self-checking)

| # | Grouped by | Aggregation(s) | Expected rows |
|---|---|---|---|
| 1 | Region | Sum of Total | 3 (North, South, West) |
| 2 | Salesperson | Sum of Quantity, Sum of Total | 3 (Ravi, Neha, Amit) |
| 3 | Category | Average of Unit Price | 2 (Electronics, Accessories) |
| 4 | Region + City | Sum of Total, Count of Orders | 6 |
| 5 | Salesperson + Product | Sum of Quantity, Max of Unit Price | up to 6 |

*(Row counts assume no duplicate/typo values were introduced while grouping — use them as
a sanity check against your own Group By results.)*
