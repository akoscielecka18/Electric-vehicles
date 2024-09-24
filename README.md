# Electric-vehicles
Challenge #12: Provide Insights to an Automotive company on Electric vehicles launch 

AtliQ Motors is an automotive giant from the USA specializing in electric vehicles (EV). In the last 5 years, their market share rose to 25% in electric and hybrid vehicles segment in North America. As a part of their expansion plans, they wanted to launch their bestselling models in India where their market share is less than 2%. Bruce Haryali, the chief of AtliQ Motors India wanted to do a detailed market study of existing EV/Hybrid market in India before proceeding further. 
#### Power Bi techniques implemented

- Data modeling (established relationships tables)
- Data cleaning (Trim, Clean)
- DAX measures (CALCULATE, MAXX, MINX, AVERAGEX, SUMMARIZE itp)
- Bookmarks
- Tooltips
- Buttoms
- Page navigation using buttons
- Applied Dynamic titles
- Conditional formatting 
- Create additional table with dates and individual table for measures
- Publishing & sharing reports on PowerBI Services
#### Dashboard View

- Overall: Overall Analysis with crucial KPI's (total sales, average sales)
- States: Electric vehicles (EV) Penetration Rate, Analysis of the percentage of total car sales represented by electric vehicles, broken down by state.
- Maker:


#### KPIs
Key Performance Indicatos(KPIs):
- Total Sales (all vehicles), Electric vehicles total sales, average total sales per state, average electric vehicles sales per state
- Electric vehicles penetration rate 


#### Key Measures

- AVERAGEX - calculating expressions for each row of the table, and then using the resulting set of values to calculate the arithmetic mean. Therefore, the function takes a table as the first argument and an expression as the second argument.
- SUMMARIZE - create a new table based on a column state and then create column "StateSales" where include total sales for every state.

AvgVehicleSalesPerState = 
AVERAGEX(
   SUMMARIZE(electric_vehicle_sales_by_state, electric_vehicle_sales_by_state[state], "StateSales", [total_vehicle]),
   [StateSales]
)

- MINX - returns the lowest value resulting from calculating the expression for each row of the table.
- ALLSELECTED - returns all selected items from the data, ignoring the current row context, allowing calculations on a broader set of data.( for example when I use ALL instead of ALLSELECTED I can see the min value but when I use slicer (years) I don't see a min value for selected year, it'll show only the min value over the years)

minEV = 
var minsum = minx(ALLSELECTED(dim_date), [EV_total])

RETURN
IF([EV_total] = minsum, [EV_total], BLANK())

- MAXX - returns the highest value resulting from calculating the expression for each row of the table.

maxsumm = 
var _var = maxx(ALLSELECTED(dim_date), [EV_total])

RETURN
IF([EV_total] = _var, [EV_total], BLANK())
#### Insights
Overall analysis

- 
- 
- 

States

- 
-
-

Maker

-
-
-

#### Key Enhancements to Dashboard



