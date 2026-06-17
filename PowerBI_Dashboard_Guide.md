# Step-by-Step Guide: Building a Basic Power BI Sales Dashboard

This guide walks you through importing the retail dataset and building a clean, professional sales performance dashboard in **Power BI Desktop**. This is an excellent project to present for your **Data Analyst Toolbox** certificate, localized for the Indian market!

---

## Dashboard Overview
Your dashboard will contain:
1. **KPI Cards**: Total Sales (₹), Total Profit (₹), and Overall Profit Margin (%).
2. **Category Sales Chart**: Bar chart displaying total revenue per category.
3. **Regional Profitability Chart**: Column chart showing net profit by region (North/South/East/West).
4. **Data Matrix (Pivot Table)**: Cross-tabulation of Sales by Category (Rows) and Region (Columns).
5. **Interactive Filter (Slicer)**: Filters data dynamically by **Customer Segment**.

---

## Step 1: Getting Started & Importing Data

1. Open **Power BI Desktop**. (If you get a startup splash screen, close it or click "Get Data").
2. In the **Home** tab ribbon, click **Get Data** > **Text/CSV**.
3. Navigate to your project folder: `C:\Users\nithi\OneDrive\Documents\Data Analysis Project\` and select **`sales_data.csv`**.
4. In the preview panel that appears, click **Transform Data** (this opens **Power Query Editor**).

---

## Step 2: Data Transformation in Power Query

Before building visuals, we must ensure our columns are in correct formats:
1. Look at the column headers in the Power Query window.
2. Verify the **Data Types** (indicated by icons next to column headers):
   - `Order_ID`: **Text** (`Abc`)
   - `Order_Date`: **Date** (calendar icon)
   - `Segment`, `Region`, `State`, `Category`: **Text** (`Abc`)
   - `Sales`: **Decimal Number** (`1.2` - represents currency in ₹)
   - `Quantity`: **Whole Number** (`123`)
   - `Profit`: **Decimal Number** (`1.2` - represents currency in ₹)
3. If any data type is incorrect, click the data type icon next to the column name and select the correct type.
4. In the **Home** tab ribbon of Power Query, click **Close & Apply** to load the data into the Power BI main canvas.

---

## Step 3: Writing DAX Measures (Best Practices)

To show that you understand Power BI best practices, we will write **DAX (Data Analysis Expressions)** measures for our KPIs instead of dragging raw columns:

### Measure 1: Total Sales
1. On the right side under the **Data** pane, right-click on the `sales_data` table and select **New measure**.
2. Type the following formula in the formula bar at the top:
   ```dax
   Total Sales = SUM(sales_data[Sales])
   ```
3. Press **Enter**. 
4. **Click/Select** the newly created measure (`Total Sales`) in the **Data** pane on the right. This will make the **Measure tools** tab appear in the top ribbon menu.
5. In the **Measure tools** tab at the top:
   - Click the **Format** dropdown and select **Currency**.
   - Click the currency symbol dropdown (next to the format option) and select **₹ English (India)** to format it in Indian Rupees with **2 decimal places**.

### Measure 2: Total Profit
1. Right-click the table again and select **New measure**.
2. Type the following formula:
   ```dax
   Total Profit = SUM(sales_data[Profit])
   ```
3. Press **Enter**, set format to **Currency**, and choose symbol **₹ (Indian Rupee)** with **2 decimal places**.

### Measure 3: Profit Margin
1. Right-click the table and select **New measure**.
2. Type the following formula (using `DIVIDE` prevents divide-by-zero errors):
   ```dax
   Profit Margin = DIVIDE([Total Profit], [Total Sales], 0)
   ```
3. Press **Enter**. Under the **Measure tools** tab, select the **Percentage (%)** format with **1 decimal place**.

---

## Step 4: Building the Dashboard Visuals

Now, drag-and-drop visuals onto the canvas layout.

### A. Key Performance Indicator (KPI) Cards
1. In the **Visualizations** pane, select the **Card** visual (the icon with `123`).
2. Drag the `Total Sales` measure into the **Fields / Data** section of the card.
3. Repeat this step to create two more separate card visuals for `Total Profit` and `Profit Margin`.
4. Place these three cards side-by-side at the very top of your canvas sheet.

### B. Sales by Category (Bar Chart)
1. Select the **Clustered Bar Chart** visual (horizontal bars).
2. Drag `Category` to the **Y-Axis** (or Axis).
3. Drag `Total Sales` to the **X-Axis** (or Values).
4. *Tip*: Turn on **Data labels** in the formatting pane (brush icon) so readers can see exact numbers.

### C. Net Profit by Region (Column Chart)
1. Select the **Clustered Column Chart** visual (vertical bars).
2. Drag `Region` to the **X-Axis**.
3. Drag `Total Profit` to the **Y-Axis**.
4. You will see some bars go below the line (representing regional net losses visually).

### D. Category vs Region Matrix (Pivot Table Equivalent)
1. Select the **Matrix** visual (grid icon).
2. Drag `Category` to **Rows**.
3. Drag `Region` to **Columns**.
4. Drag `Total Sales` to **Values**.
5. This reproduces your Excel PivotTable directly inside Power BI!

### E. Interactive Segment Slicer (Filter)
1. Select the **Slicer** visual (funnel/table icon).
2. Drag `Segment` into the slicer field.
3. In the visual settings, choose to display it as a **Slicer Header** or **Tile list** (horizontal buttons).
4. Click on "Consumer", "Corporate", or "Home Office" to watch all charts on your page update dynamically.

---

## Step 5: Formatting and Designing for Impact

To make your dashboard feel premium, follow these click-paths in Power BI Desktop:

### A. Setting the Canvas Background & Alignment
1. **Click on any empty space** on the dashboard canvas (make sure no chart is currently selected).
2. Look at the **Visualizations** pane on the right-hand side and click the **Format page** icon (it looks like a paintbrush with a checklist/canvas).
3. Expand the **Canvas background** group.
4. Click the **Color** bucket, select a light grey shade (or click *More colors* and enter `#F3F4F6`).
5. **Important**: Slide the **Transparency** slider down from 100% to **0%** (otherwise the color remains invisible).
6. To align charts, simply click and drag them. Power BI will show red dashed alignment gridlines to help you snap them perfectly into place.

### B. Customizing Visual Titles
1. **Click on the chart** you want to customize (e.g. your Sales by Category bar chart).
2. In the **Visualizations** pane, click the **Format visual** icon (paintbrush).
3. Switch from the *Visual* tab to the **General** tab at the top of the formatting list.
4. Expand the **Title** section.
5. In the **Text** input field, overwrite the title (e.g. change it to `"Revenue Distribution by Product Category"`). You can also center-align it and change font styling here.

### C. Choosing a Professional Color Theme
1. Look at the very top ribbon menu and click on the **View** tab (located in the top menu next to *Home* and *Insert*).
2. Locate the **Themes** section on the far left. You will see a row of small color palettes.
3. Click the **"More" dropdown arrow** on the right side of the theme row (it looks like a small downward-facing triangle with a line above it `▼`).
4. At the bottom of the expanded themes panel, click **Browse for themes**.
5. Navigate to your project folder: `C:\Users\nithi\OneDrive\Documents\Data Analysis Project\` and select **`Custom_Innovative_Theme.json`**.
6. This custom theme will instantly convert your dashboard into a modern, dark-slate theme with 12px rounded visual borders and a vibrant teal/purple data color scheme!

---
**Congratulations!** You now have a complete, professional Power BI dashboard that demonstrates data loading, cleaning, DAX modelling, and interactive report building.
