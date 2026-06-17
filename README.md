# Data Analyst Toolbox: Indian Retail Sales Power BI Dashboard

This repository serves as a portfolio project demonstrating data visualization, DAX modeling, and report design skills using **Power BI Desktop**, aligned with the **Data Analysts Toolbox** curriculum. 

The project models an Indian retail sales environment (utilizing Indian Rupees `₹` and Indian states) to track performance metrics across product categories and regional zones.

---

## Repository Contents

* **`Project.pbix`**: The primary Power BI report file containing report sheets, loaded queries, and calculations.
* **`sales_data.csv`**: The primary database containing 30 transactions across Indian states (Maharashtra, Karnataka, West Bengal, Delhi, etc.) mapped to regional zones.
* **`Custom_Innovative_Theme.json`**: A custom-designed **Aero-Glow Premium Dark** theme file containing drop shadows, 16px visual card border radii, and customized Segoe UI text styles.
* **`PowerBI_Dashboard_Guide.md`**: A step-by-step documentation guide explaining how the data query, DAX calculations, and visual alignments were built.

---

## Core Calculations (DAX Measures)

This dashboard utilizes custom **DAX (Data Analysis Expressions)** measures for performance reporting:

1. **Total Sales** (Sum of all order transactions):
   ```dax
   Total Sales = SUM(sales_data[Sales])
   ```
2. **Total Profit** (Net profit margin total):
   ```dax
   Total Profit = SUM(sales_data[Profit])
   ```
3. **Profit Margin** (Overall margin ratio):
   ```dax
   Profit Margin = DIVIDE([Total Profit], [Total Sales], 0)
   ```

---

## Visual Presentation & Layout

* **KPI Cards**: Dynamically display Total Sales (₹), Total Profit (₹), and Profit Margin (%) based on user filters.
* **Segment Slicers**: Interactive buttons to filter all visuals by customer segment (Consumer, Corporate, Home Office).
* **Matrix Grid**: Crosstab layout summarizing product category sales split by regional zones (North India, South India, East India, West India).
* **Visual Styling**: Translucent dark slate backgrounds, rounded card edges (16px), drop shadows, and glowing cyan/purple indicators.

---

## How to Run & View the Project

1. Install **Power BI Desktop** (available for free from the Microsoft Store).
2. Download or clone this repository folder to your local machine.
3. Double-click **`Project.pbix`** to open the report dashboard.
4. Interact with the **Segment Slicers** at the top of the canvas to filter the visual charts.
5. If you modify the underlying transaction values in `sales_data.csv`, click the **Refresh** button in the top Home menu bar of Power BI to pull in the new data automatically.
