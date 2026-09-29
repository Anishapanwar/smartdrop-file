# Smart drop  company
##  overview

This data describe the overall performance of smart drop company. That include data cleaning transformation of data visualization data etc. using python.

##  libraries use 
*Pandas=use to analyse and describe a data
*Matplotlib=visualization tool
*Seaborn=visualization tool

## import data
*Messy_customer=contaion all customer information
*Messy_orderDetails=contain orderdetails info
*Messy_order=order information
*Messy_product=product info 


##  Data description
The pipeline processes four backend transactional and master tables containing typical real-world data tracking anomalies (missing records, case-sensitivity noise, and duplicate inputs):

   1. messy_customers.csv (520 rows): Operational ledger tracking customer identifiers, names, geographical distributions, and account signup dates.
   2. messy_orders.csv (1,176 rows): Master transactional log documenting order nodes, customer mapping keys, purchase dates, and payment settlement types.
   3. messy_order_items.csv (1,930 rows): Granular line-item breakdown linking individual item quantities, transactional unit price yields, and stock references to master order IDs.
   4. messy_products.csv (90 rows): Product master catalog cataloging catalog inventory, descriptive identities, categories, and structural base costs.


## data cleaning
Fill null value ,delete duplicate column , transform data
*	Changing the type of data
*	Capitalizing the data 
*	Title the data 
*	Changing data into string
*	Replacing the similar name or common name 
*	Finding average value to fill is null value
*	Filling value in is null 
*	Finding duplicate value
*	Droping duplicate
##  Data  Cleaning Protocol
The script implements a sequential programmatic cleaning protocol to enforce transactional integrity across dimensions:

* Descriptive Structural Standardization: Cleared structural noise across raw rows by programmatically imputing blank records and standardizing casing:
* Filled null customer names with "unknown" and string-capitalized the entries.
   * Standardized fuzzy geographical labels (e.g., mapped "DELHI" and "delhi" strictly to "Delhi"; reconciled "Bangalore" to "Bengaluru"), then enforced Title Case.
   * Extracted and filled missing product categories by merging string variances (e.g., streamlined "Accessory" vs. "Accessories"; "Smart phone" vs. "Smartphone").
* Deduplication Matrix: Programmatically removed trailing whitespace and structurally duplicate rows across datasets via .drop_duplicates(inplace=True) to prevent mathematical overreporting during relational joins.
* Imputation & Statistical Balancing: Resolves missing numeric metrics without dropping rows:
* Imputed missing line-item quantities with a fallback baseline structure of 1.
   * Reconciled unpopulated sales values by calculating the column mean values (INR 44,956 for item sales and INR 45,047 for product base costs) to keep financial matrices unbroken.
* Temporal Node Transformations: Converted messy mixed-format date text layers into strict pandas datetime64[ns] objects to unlock logical calendar engineering (.dt.month_name(), .dt.year, and .dt.quarter).

 ##  Core Business Intelligence Inquiries
Once cleaned and unified into a single database frame (Data), the pipeline computes and answers five key macroeconomic performance metrics:

   1. Total System Volume Generated: Computes absolute gross earnings via vectorized array math (quantity * unit_price), yielding a total system volume of INR 158,513,136.0.
   2. Product Categories by Volume vs. Velocity: Aggregates physical product flow alongside gross revenue yields across key categories.
   3. Payment Settlement Preferences: Tracks customer preference leaderboards among settlement formats like UPI, Credit Card, Cash, and Debit Card.
   4. Geographical Target Boundaries: Ranks structural revenue capture by city to highlight high-value operational zones.
   5. Chronological Revenue Flow: Groups financial activity across years, quarters, and months to map microeconomic growth trends and seasonal performance baselines.



## data transforming
•	Transforming string or float data type in data data type using pandas function
•	Creating new column and finding new value such as month name, year etc .

## data intergration
Merge the table using a common column.
## insight
•	Total revenue
•	Top product base on qty sold
•	Top category base on revenue
•	Most prefer payment method
•	Top revenue per year
•	Total revenue per month
•	Total revenue per quarter
•	Top city per revenue
•	Signup date
##  Visualizations Included
The script outputs clean, presentation-ready charts to map backend aggregates:

* Payment Method Preferences: Horizontal bar chart mapping transaction counts across settlement types.
* Total Category Revenue: Vertical seaborn bar chart isolating revenue capture by structural category.
* Quarterly Velocity Trend: Line plot charting macro chronological performance over fiscal quarters.
* Geographical Distribution Profile: Horizontal bar chart ranking absolute city revenue capture.
* Yearly Account Creation Proportions: Pie chart visualizing historical changes in user account creation velocity.

## coclusion
The data analysis for Smart Drop Company reveals a business with clear market strengths but facing data infrastructure challenges and a recent drop in sales velocity.
On the commercial side, Smartphones and Accessories in the Delhi region are the company's clear primary profit drivers. The balanced use of UPI, Credit Cards, and Cash also indicates a well-diversified checkout experience that accommodates various consumer preferences.






