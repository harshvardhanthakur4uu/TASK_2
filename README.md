📊 Superstore Sales Dashboard – Power BI

This project presents an interactive sales and profit dashboard built in Power BI using the Superstore dataset. It offers deep insights into regional performance, category-wise trends, sub-category profitability, and time-based sales analysis.

🔍 Key Features

    Dynamic Slicers for:

        Month selection

        Year selection

    KPIs:

        💰 Total Profit: $286.4K

        💵 Total Sales: $2.30M

    Visuals Included:

        Bar chart of Sales by Region

        Bar chart of Sales by Category

        Bar chart of Profit by Sub-Category

        Time-series line chart for Monthly Sales

        Dynamic interaction through slicers

📈 Business Insights

    Technology is the top-performing category by sales.

    The West region leads in overall sales volume.

    Bookcases and Tables show consistent negative profit, signaling potential issues in pricing or cost.

    Noticeable spikes in sales occur during Q4 (November–December), likely due to holiday season promotions.

🔧 DAX Measures Used
✅ Total Sales

Total Sales = SUM('Sales'[Sales])

✅ Total Profit

Total Profit = SUM('Sales'[Profit])

🗓️ Calendar Table (DAX)

Calendar = 
ADDCOLUMNS (
    CALENDAR (MIN('Sales'[Order Date]), MAX('Sales'[Order Date])),
    "Year", YEAR([Date]),
    "Month Number", MONTH([Date]),
    "Month Name", FORMAT([Date], "MMMM"),
    "MonthYear", FORMAT([Date], "MMM-YYYY"),
    "MonthYearSort", YEAR([Date]) * 100 + MONTH([Date]),
    "Quarter", "Q" & FORMAT([Date], "Q"),
    "Weekday", FORMAT([Date], "dddd")
)

    📌 Remember to sort MonthYear by MonthYearSort in the Modeling tab to maintain chronological slicer order.

🧩 Data Model Relationships

Ensure a relationship is established:

Calendar[Date] → Sales[Order Date]

💡 How to Use the Dashboard

    Use Month and Year slicers to drill down into time-specific insights.

    Hover over bars and lines to explore exact values.

    Compare sub-category profits to identify loss-making products.

    Observe monthly trends to identify seasonality in customer behavior.
