---
layout: page
title: "Q156551: HOWTO: Use SYS(3054) to Optimize a Query"
permalink: /kb/156/Q156551/
---

## Q156551: HOWTO: Use SYS(3054) to Optimize a Query

{% raw %}

	Article: Q156551
	Product(s): Microsoft FoxPro
	Version(s): 
	Operating System(s): 
	Keyword(s): kbprint kbFont kbPrinting kbvfp500 kbvfp600
	Last Modified: 11-SEP-2001
	
	-------------------------------------------------------------------------------
	The information in this article applies to:
	
	- Microsoft Visual FoxPro for Windows, versions 5.0, 6.0 
	-------------------------------------------------------------------------------
	
	SUMMARY
	=======
	
	Visual FoxPro 5.0 added a new SYS() function that allows you to see the Rushmore
	optimization level of query. This information can help you optimize your queries
	in relation to their use of Rushmore.
	
	SYS(3054) actually accepts the following three different parameters:
	
	- 1 - to turn on reporting of filter optimization
	
	- 11 - to turn on reporting of join optimization
	
	- 0 - to turn off the reporting of optimization levels
	
	MORE INFORMATION
	================
	
	To demonstrate how this function works, follow the steps below:
	
	1. Copy the Customer.dbf and Orders.dbf files from the \Samples\Data folder to
	  another folder where you can make changes to the tables. For the purpose of
	  this example, copy only the .dbf files as they are the only files that you
	  need. After you have copied the files, open them exclusively so you can
	  remove the database container references and the Structural CDXs. When you
	  open the tables, a dialog box opens stating that the Testdata.dbc could not
	  be opened, click delete (you do not need the .dbc for this example). If you
	  have SET SAFETY ON, you also get a dialog box stating that the Structural CDX
	  file could not be found, click ignore.
	
	2. Now you can type the following in the Command window:
	
	        ? SYS(3054,1)
	        SELECT * FROM customer WHERE customer.country = 'USA'
	
	  The following is returned:
	
	        Rushmore optimization level for table customer: none
	
	3. Next, add an index tag on country field and repeat the query above:
	
	        INDEX on country TAG country
	
	  NOTE: Be sure to re-select the customer table first (SELECT customer) so you
	  are operating on the original data. Now, you should see the following:
	
	        Using index tag Country to rushmore optimize table customer
	        Rushmore optimization level for table customer: full
	
	4. Now, if you try the following query:
	
	        SELECT * FROM customer WHERE customer.country = 'USA' and ;
	           customer.maxordamt>2000
	
	  You see the following:
	
	        Using index tag Country to rushmore optimize table customer
	        Rushmore optimization level for table customer: partial
	
	  Adding a tag on maxordamt makes the second query fully optimizable.
	
	5. Next, if you join the two tables:
	
	        SELECT * FROM customer, orders WHERE ;
	           customer.cust_id = orders.cust_id
	
	  You see the following:
	
	        Rushmore optimization level for table customer: none
	        Rushmore optimization level for table orders: none
	
	6. Now, add tags to both tables for the cust_id field:
	
	        SELECT customer
	        INDEX ON cust_id TAG cust_id
	        SELECT orders
	        INDEX ON cust_id TAG cust_id
	
	  Try the query again:
	
	        SELECT * FROM customer, orders WHERE ;
	           customer.cust_id = orders.cust_id
	
	  You see the following:
	
	        Rushmore optimization level for table customer: none
	        Rushmore optimization level for table orders: none
	
	  Since the query is joining the tables and not doing any filtering, this is
	  correct. Since there is no filter, there is no filter optimization.
	
	7. Next, issue the following command:
	
	        ? SYS(3054,11)
	
	  Try the query again and you see the following:
	
	        Rushmore optimization level for table customer: none
	        Rushmore optimization level for table orders: none
	        Joining table customer and table orders using index tag Cust_id
	
	8. Now, try this query:
	
	     SELECT * FROM customer, orders WHERE customer.cust_id=orders.cust_id ;
	        AND customer.country = 'USA' AND orders.order_amt>500
	
	  You see the following:
	
	        Rushmore optimization level for table customer: full
	        Rushmore optimization level for table orders: none
	        Joining table customer and table orders using index tag Cust_id
	
	  Since there is no tag for orders.order_amt, that filter expression cannot be
	  optimized. Add a tag to orders for the order_amt field and the optimization
	  for orders is full.
	
	Additional query words: query performance
	
	======================================================================
	Keywords          : kbprint kbFont kbPrinting kbvfp500 kbvfp600 
	Technology        : kbVFPsearch kbAudDeveloper kbVFP500 kbVFP600
	Issue type        : kbhowto
	
	=============================================================================
	

{% endraw %}
