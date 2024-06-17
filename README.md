# Bike Sales Analysis Dashboard using Tableau

### Dashboard Link : https://public.tableau.com/app/profile/pradeesh.reddy/viz/VehicleSales_17186101471710/SalesDashboard?publish=yes

## Overview
This project involves creating an interactive dashboard in Tableau for analyzing bike sales data. The dashboard utilizes various types of visualizations to present insights into sales performance, profitability, and revenue trends.

## Dataset
The dataset used for this project is in CSV format and includes the following columns:
- Date
- Day
- Month
- Year
- Customer_Age
- Age_Group
- Customer_Gender
- Country
- State
- Product_Category
- Sub_Category
- Product
- Order_Quantity
- Unit_Cost
- Unit_Price
- Profit
- Cost
- Revenue

## Steps to Create the Dashboard

1. **Connect to Data**
    - Click on "Connect to Data" in Tableau.
    - Select "Excel" and load the CSV file.

2. **Data Preparation**
    - Ensure the dataset is error-free and properly structured.

3. **Visualizations Created**
    - **Horizontal Bar Chart**: Top 10 sales by product.
    - **Stacked Bar Chart**: Profit by sub-category.
    - **Bubble Chart**: Revenue by age group.
    - **Map**: Profit by country.
    - **Profit Card**: Displaying total profit.
    - **Year-on-Year (YoY) % Change Card**: Displaying YoY profit change.
    - **Revenue Card**: Displaying total revenue.
    - **Line Chart**: Revenue by year.
    - **Product Category Cost Card**: Displaying costs by product category.

4. **Creating Cards**
    - **Profit Card**:
        - Drag "Profit" into the text area.
        - Double click in columns and write "Profit" in quotation marks.
        - Increase text size and format appropriately.
        - Hide field labels.
    - **Year-on-Year (YoY) % Change Card**:
        - Right-click on the date field and create a custom date with detail as "Years" and name it "Date-Year".
        - Create a parameter named "Year Parameters" with data type as "Date" and allow values as a list from "Date-Year".
        - Create calculated fields:
            - **Year Filter**: `[Date - Years]=[Year Parameters]`
            - **Chosen Year Profit**: `IF [Date - Years]=[Year Parameters] THEN [Profit] END`
            - **Last Year Profit**: `IF [Date - Years] = DATEADD('year',-1, [Year Parameters]) THEN [Profit] END`
            - **YoY % Change**: `(SUM([Chosen Year Profit]) - SUM([Last Year Profit])) / SUM([Last Year Profit])`
        - Drag "YoY % Change" to the text area and format the number as needed.

5. **Parameter and Filter Integration**
    - Use the "Year Parameters" to filter trends by the selected year.
    - Use country filters to analyze trends by country.

## Usage
- Open Tableau and connect to the provided dataset.
- Follow the steps outlined above to recreate the visualizations.
- Utilize the year parameter and country filter to interact with the dashboard and analyze the data accordingly.

## Visualizations
1. **Top 10 Sales by Product**: Displays the top-selling products in a horizontal bar chart.
2. **Profit by Sub-Category**: Shows the profit distribution across different sub-categories using a stacked bar chart.
3. **Revenue by Age Group**: Visualized through a bubble chart to highlight revenue contribution by different age groups.
4. **Profit by Country**: A geographical map indicating profit margins across various countries.
5. **Profit and YoY % Change Cards**: Key metrics displayed for quick insights.
6. **Revenue by Year**: Line chart illustrating revenue trends over the years.
7. **Product Category Cost**: Card showcasing where the most money was spent in terms of product categories.

# Snapshot of Dashboard (Tableau Public)

![Snap of Bike Sales Dashboard](https://github.com/pradeeshculer/Bike-Sales-Analysis/assets/115096109/17e4985b-e799-4d33-aeaf-2ce8398e3b64)

## Conclusion
This Tableau dashboard provides a comprehensive analysis of bike sales data, enabling users to explore and derive insights into sales performance, profitability, and revenue trends across different dimensions such as product, age group, and country. 

