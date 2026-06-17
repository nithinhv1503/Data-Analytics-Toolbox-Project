# Data Analyst Toolbox: Indian Retail Sales Dashboard Portfolio Project

This repository serves as a complete portfolio project demonstrating skills from the **Data Analysts Toolbox: Excel, Python, Power BI, PivotTables** course, localized for the **Indian retail market**.

It implements an Indian sales database (using INR currency `₹` and Indian states) and contains two complementary pathways for analysis:
1. **Power BI Path**: A step-by-step tutorial and data source to build an interactive business intelligence dashboard in Power BI Desktop showing metrics formatted in Indian Rupees.
2. **Python & Excel Path**: A script that automates loading the data, creating pivot aggregations, exporting a styled Excel report, and plotting matplotlib charts.

---

## File Overview

- **`sales_data.csv`**: The primary dataset containing 30 transactions with attributes: Order ID, Order Date, Segment, Region, State, Category, Sales (₹), Quantity, and Net Profit (₹).
- **`PowerBI_Dashboard_Guide.md`**: Your step-by-step guide to load the CSV, write DAX measures (Total Sales, Total Profit, Profit Margin), and construct a functional Power BI dashboard with slicers and matrices.
- **`analyze.py`**: A python script that cleans the dataset, runs aggregations, saves charts, and builds a styled Excel sheet (`sales_pivot_report.xlsx`).
- **`README.md`**: Project overview and usage guidelines.

---

## Setup and Running

### Pathway A: Power BI Dashboard (Recommended Showcase)
1. Open **Power BI Desktop**.
2. Read the instructions in [PowerBI_Dashboard_Guide.md](file:///c:/Users/nithi/OneDrive/Documents/Data%20Analysis%20Project/PowerBI_Dashboard_Guide.md).
3. Import **`sales_data.csv`**, set up the DAX measures using Indian Rupees (₹), and design your visual cards, column charts, and slicers.

### Pathway B: Python and Excel Automation
1. Install Python dependencies:
   ```bash
   pip install pandas openpyxl matplotlib
   ```
2. Execute the python script:
   ```bash
   python analyze.py
   ```
3. Open the newly created **`sales_pivot_report.xlsx`** in Excel to see custom formatting (Classic Navy styling, double-border totals, conditional negative-profit highlighting) showing Rupees (₹) formatting, and view the Matplotlib chart images (`sales_by_category.png`, `profit_by_region.png`).
