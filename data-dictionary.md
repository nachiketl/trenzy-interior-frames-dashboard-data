# Trenzy Data Dictionary

This file documents the fields for the two primary tables used in the Trenzy dashboard: trenzy_orders and trenzy_leads. Use these definitions when preparing/cleaning data to load into the dashboard.

## Table: trenzy_orders
Primary key: Order_ID (recommended)

Columns
- Order_ID — string/int — Unique order identifier (e.g., ORD-0001).
- Item_Description — text — Product or service description (e.g., "Wooden Door - Oak").
- Unit — text — Unit measure (e.g., "piece", "sqm").
- Quantity — integer — Count of units ordered (>= 0).
- Rate_Per_Unit — decimal (currency) — Price per unit, 2 decimals.
- Amount — decimal (currency) — Quantity * Rate_Per_Unit (validate calculation).
- Order_Date — date (YYYY-MM-DD) — When the order was placed.
- Work_Start_Date — date — When work started (nullable until started).
- Work_End_Date — date — When work completed (nullable until complete).
- Order_Status — category — e.g., Placed, In Progress, Completed, Cancelled.
- Payment_Status — category — e.g., Pending, Partial, Paid, Refunded.
- Sales_Executive — text/lookup — Sales person name or code.
- Total_Order_Value — decimal (currency) — Order-level total when multi-line orders exist.

Validation notes
- Ensure Quantity and numeric fields are numeric and non-negative.
- Confirm Amount ≈ Quantity * Rate_Per_Unit within rounding tolerance.
- Standardize Order_Status and Payment_Status values.
- Use Order_ID to dedupe; if absent, create a synthetic ID.

## Table: trenzy_leads
Primary key: Lead_ID

Columns
- Lead_ID — string/int — Unique lead identifier (e.g., L-1001).
- Customer_Name — text — Lead / customer name.
- Phone — string — Normalize to E.164 (e.g., +91XXXXXXXXXX) where possible.
- City — text — City name.
- Lead_Source — text — e.g., Website, Referral, Walk-in, Ad.
- Campaign_Name — text — Marketing campaign name.
- Work_Type — text — Request type (e.g., Framing, Interior Fitout).
- Lead_Date — date (YYYY-MM-DD) — Date lead was created.
- Month — text — (optional) derived from Lead_Date.
- Month_NO — integer — (optional) derived from Lead_Date.
- Year — integer — (optional) derived from Lead_Date.
- Quarter — text — (optional) derived (Q1..Q4).
- Followup_Count — integer — Number of followups.
- Last_Contact_Date — date — Most recent contact date (nullable).
- Lead_Status — category — e.g., New, Contacted, Qualified, Lost.
- Estimated_Budget — decimal (currency).
- Final_Deal_Value — decimal (currency) — 0 or NULL if not converted.
- Conversion_Date — date — Date of conversion to deal (nullable).
- Sales_Executive — text/lookup — Owner of lead.
- Response_Time_Hours — decimal — Hours from creation to first response.
- Lead_Rating — integer/text — e.g., 1-5 or Hot/Warm/Cold.
- Remarks — text — Free-form notes.
- Client_Segment — text — e.g., Residential, Commercial.

Validation notes
- Clean Phone for matching across datasets.
- Derive Month/Year/Quarter from Lead_Date in the model (avoid storing if possible).
- Final_Deal_Value should be NULL or 0 for non-converted leads.

## Recommended relationships
- Add Lead_ID to trenzy_orders to connect orders to leads when available.
- If Lead_ID is not available in orders, use Phone (preferred) or Customer_Name (careful with duplicates) to match.
- Normalize Sales_Executive into a small dimension table to avoid typos.

## Power BI modeling tips
- Create a central Date dimension and mark it as the Date table.
- Build orders as the Orders fact and leads as the Leads fact; link by Lead_ID when possible.
- Key measures to include:
  - Total Sales = SUM(trenzy_orders[Amount])
  - Orders Count = DISTINCTCOUNT(trenzy_orders[Order_ID])
  - Average Order Value = DIVIDE([Total Sales],[Orders Count])
  - Lead Conversion Rate = Converted Leads / Total Leads

---
Created and maintained in /data-dictionary.md
