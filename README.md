
# Reliance Smart Sales Project



# Reliance Smart Sales Report



## Problem Statement

This dashboard helps the stakeholders understand their sales better. It helps them to know if their sales in different places match with their preplanned scenarios or not. Through different visuals and data representation, they get to know their improvement area, & thus they can improve their products by identifying these areas.




### Steps followed 

- Step 1 : First open power bi desktop application.

- Step 2 : Add all datasheets from get data option  which were in csv format and added them to power query.

 - Step 3 : For calendar table set the first row as header.

- Step 4 :In calendar table dates were in US format so changed the regional setting of the power bi as "United States" and change the data type of "calendar table" from "text" to "date".

- Step 5 : Change the "date of birth" and "account opening date" column's format from "text" to "date" at "Customer Table".

- Step 6 : Change products rate from "deciamal number" to "whole number" at "Product table"

- Step 7 : 	7. Use "appened queries" option to create one single table by merging " transaction 1997" and "transaction 1998" table.
 
- Step 8 : Add "year", "month name" and "quarter of the year" columns in "Calender table".

- Step 9 : check correctness of data by using "column distribution" option and "column quality" and replace all "null" values into "product table" as "0" and then close and apply power query.


        
- Step 10 : at the time of creating relation ship between the table hide "transaction 1997 and 1998 table" and create relationship manually between all tables, and Create hierarchy into date table.


- Step 11 :
following measure I have to create for this project are below with dax syntax

a> Total transactions:-
        Dax syntax :-

	
	Total transactions = 
	COUNT('Transaction 1997-1998'[transaction_date]
)

b> total cost
dax syntax:-
	
	
	

	Total cost = 
	SUMX('Transaction 1997-1998',
	'Transaction 1997-1998'[quantity]
	*
	RELATED(Products[product_cost]
	)
	)

c> total returns
	Dax syntax:-
	
	Total returns = 
	COUNT('Returns-1997-1998'[return_date]
	)

d> Total quantity sold
dax syntax:-


	
	
	Total quantity sold= 
	SUM('Transaction 1997-1998'[quantity]
)

e> total quantity return
dax syntax:-


	
	Total qunatity return = 
	SUM('Returns-1997-1998'[quantity]
)

f> total revenue
dax sysntax:- 


	
	Total revenue = 
	SUMX('Transaction 1997-1998',
	'Transaction 1997-1998'[quantity]
	*
	RELATED(Products[product_retail_price]
	)
)

g> total profit
dax syntax :- 



	
	Total profit = 
[Total revenue] - [Total cost]

h> total unique products
dax syntax:-
	
	
	Total unique products = 
DISTINCTCOUNT(Products[product_id]

i> all returns
	Dax syntax



	
 All returns = 
	CALCULATE([Total returns],
	ALL('Returns-1997-1998'
	)
)

j> Previous month revenue
	Dax syntax


	
	11. Previous month revenue =
	CALCULATE([Total revenue],
	DATEADD('Calendar'[date],
	-1,
	MONTH
	)
)

k> previous month profit
dax syntax


	
	Previous month profit = 
	CALCULATE([Total profit],
	DATEADD('Calendar'[date],
	-1,
	MONTH
	)
)

l> previous month returns
dax syntax:



	
	Previous month returns = 
	CALCULATE([Total returns],
	DATEADD('Calendar'[date],
	-1,
	MONTH
	)
)

m> previous month transactions
dax syntax


	
	Previous month transactions = 
	CALCULATE([Total transactions],
	DATEADD('Calendar'[date],
	-1,
	MONTH
	)
)

n> YTD revenue
dax syntax


	
	YTD REVENUE = 
CALCULATE([Total revenue],DATESYTD('Calendar'[date]))

o>  Profit margin
dax syntax


	
	Profit mergin = 
[Total profit] / [Total revenue]

  
   # Primary Dashboard creation:-

- Step 12 : First insert "Reliance smart" logo image from device using "image option" from "insert tab".

- Step 13 : Insert a matrix table and into this "matrix table" add "product brands" into "row" and then add "total transactions","Total quantity sold", "total revenue" and "total profit", "total returns" into value section  of the table respectively.

- Step 14 : Add "map" into the dashboard to show "total revenue" by "sales region".

- Step 15 : Add a treemap in to dash board to show "total transaction" by "store state".

-Step 16 : Add 3 kpi cards "total revenue by previous month revenue", "total profit by previous month profit" and "total returns by previous month returns" respectively.

- Step 17 : Add a "reset" button from "insert" option.

- Step 18 : Add a "bookmark" and named it as "reset" and For "reset" button from the "action" option select type "bookmark" and add the "bookmark" option.


# Secondary Dashboard creation:-
- Step 19: first insert rounded rectangle shape into dashbord and streached horizontally at the upperside of the dashboard.

- Step 20 : Insert a text box and write "Reliance Smart Sales Report" as heading.

- Step 21 : Then  insert 3 donut charts and add country wise transactions, country wise profit, country wise returns respectively.

- Step 22 : Inset a "stacked bar chart" to reflect the value of "country wise total revenue".

- Step 23 : Insert a "area chart" to reflect "store type wise total Revenue".

- Step 24 : change all visuals colours to get eye catchy look.

- Step 25 : add "buttons" by using "bookmarks" in both Primary and Secondary dashboard for reset the dashboard and to jump from one dashboard to another using buttons. 






 
 # Snapshot of Primary Dashboard (Power BI DESKTOP)

 
![image](https://github.com/user-attachments/assets/b67b275d-2e77-4ea3-9d42-c9624819cce9)

# Snapshot of Secondary Dashboard (Power BI Desktop)

![image](https://github.com/user-attachments/assets/c6bcc9b8-5bdd-491b-988a-75af5c0c34bc)

# Insights

A double page report was created on Power BI Desktop.

Following inferences can be drawn from the dashboard;

### [1] Total Profit = 1096264
Country wise profit

Canada 285K, Mexico 799K, USA 1032K

   
           
### [2] Total Returns = 7087

Country wise returns

Canada = 467 Mexico = 1975 USA = 4645 

   
  
    
  
  ### [3] total Transactions = 269720

Country wise transactions

Canada = 72K Mexico = 196K USA = 255K 

 ### [3] total Revenue  = 1809877

Country wise Revenue

Canada = 473K Mexico = 1319K USA = 1703K 

  
      
      
