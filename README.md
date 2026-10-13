# Trenzy Interior & Frames — Dashboard Data

This repository contains dummy data and supporting project files for the Trenzy Interior & Frames dashboard. The dataset is designed for sales, lead conversion, order operations, and business reporting analysis.

## Project purpose
The project is built to help visualize:
- order-level sales performance
- payment and order status trends
- lead generation and conversion by source, city, and executive
- customer segments and work types
- overall business performance for Trenzy Interior & Frames

## Dataset overview
The repo includes the following data sources:

### 1) trenzy_orders
This table stores order-level transactional data.

Columns:
- Item_Description
- Unit
- Quantity
- Rate_Per_Unit
- Amount
- Order_Date
- Work_Start_Date
- Work_End_Date
- Order_Status
- Payment_Status
- Sales_Executive
- Total_Order_Value

Purpose:
- Track order value, order status, payment status, and work lifecycle.
- Useful for dashboards on sales volume, payment collection, and operational completion.

### 2) trenzy_final
This table stores lead-level data and sales pipeline information.

Columns:
- Lead_ID
- Customer_Name
- Phone
- City
- Lead_Source
- Campaign_Name
- Work_Type
- Lead_Date
- Month
- Month_NO
- Year
- Quarter
- Followup_Count
- Last_Contact_Date
- Lead_Status
- Estimated_Budget
- Final_Deal_Value
- Conversion_Date
- Sales_Executive
- Response_Time_Hours
- Lead_Rating
- Remarks
- Client_Segment

Purpose:
- Measure lead generation, response efficiency, and conversion performance.
- Support reporting on campaign effectiveness, city-wise demand, and sales executive productivity.

## Recommended dashboard output
The final dashboard should include:
- KPI cards for total sales, orders count, average order value, conversion rate
- Monthly sales trend
- Order status summary
- Payment status summary
- Sales by executive
- Leads by source and city
- Lead conversion funnel
- Work type analysis
- Response time and follow-up metrics

## Data model recommendations
- Add a unique Order_ID to the orders table if it is not already present.
- Add Lead_ID to the order table when possible to create a direct relationship with lead records.
- If Lead_ID is unavailable in the orders table, use Phone or Customer_Name after careful data cleaning.
- Normalize sales executive names and city values before building visuals.
- Create a date table in Power BI for month, quarter, and year analysis.

## File structure
- `Trenzy_Orders.xlsx` — order dataset
- `Trenzy_FINAL_DONE.xlsx` — final lead / sales dataset
- `Builder_FINAL_DONE.xlsx` — additional builder/project-level data
- `Trenzy Project.pbix` — Power BI dashboard file
- `Trenzy Project.pdf` — project PDF output
- `Trenzy_Master_Project_Booklet.pdf` — project booklet
- `data-dictionary.md` — explanation of each field and model guidance
- `docs/UPLOAD_POWERBI.md` — Git LFS / release instructions for Power BI files

## Power BI usage
Open the `.pbix` file in Power BI Desktop to view or edit the dashboard.

Steps:
1. Load the Excel files into Power BI.
2. Create relationships between orders and leads using Lead_ID or cleaned customer identifiers.
3. Build the KPI cards and charts listed above.
4. Publish or export the final dashboard for reporting.

## Notes
- This project is a dummy dataset for demonstration and reporting purposes.
- Data should be cleaned and standardized before business-level reporting.
- The repository is intended to support a visual dashboard for Trenzy Interior & Frames performance tracking.
