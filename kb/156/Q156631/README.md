---
layout: page
title: "Q156631: PRB: Parameterized View Discrepancy Using IN() Filter Criteria"
permalink: /kb/156/Q156631/
---

## Q156631: PRB: Parameterized View Discrepancy Using IN() Filter Criteria

{% raw %}

	Article: Q156631
	Product(s): Microsoft FoxPro
	Version(s): 5.0,6.0
	Operating System(s): 
	Keyword(s): kbvfp500 kbvfp600
	Last Modified: 18-DEC-2001
	
	-------------------------------------------------------------------------------
	The information in this article applies to:
	
	- Microsoft Visual FoxPro for Windows, versions 5.0, 6.0 
	-------------------------------------------------------------------------------
	
	SYMPTOMS
	========
	
	A Parameterized View returns incorrect results when assigning multiple string
	values to a parameter of the IN() Filter criteria.
	
	CAUSE
	=====
	
	The View Designer is not designed to handle queries where multiple values are
	assigned to a parameter in the IN() clause.
	
	WORKAROUND
	==========
	
	To use View Designer to create a parameterized View that returns the correct
	values when using the IN() filter criteria, you need to specify multiple
	parameters instead of a single one. For example, you would specify the following
	in the Filter tab of the View:
	
	  Field Name = "customer.customer_id"
	  Criteria = IN
	  Example = ?a, ?b, ?c
	
	This will produce the following SQL statement:
	
	     SELECT *;
	       FROM tastrade!customer;
	       WHERE Customer.customer_id IN (?a, ?b, ?c)
	
	When you browse the View, it prompts you three times to enter each of the three
	parameters. If, for example, you enter "ALFKI," "ANATR," and "ANTON" as the
	first, second, and third parameters, respectively for the parameters, then three
	records display correctly. Alternately, you can assign the strings, for example
	"ALFKI," "ANATR," and "ANTON" respectively, to each of the variables a, b, and c
	respectively before browsing the View.
	
	STATUS
	======
	
	This behavior is by design.
	
	MORE INFORMATION
	================
	
	Steps to Reproduce Behavior
	---------------------------
	
	1. Issue the following command in the Command window:
	
	  MODIFY DATABASE HOME()+"samples\tastrade\data\tastrade.dbc"
	
	2. Create a New Local View using the View Designer.
	
	3. Add the table "Customer" to the View.
	
	4. Select all fields for output.
	
	5. In the filter section, enter "customer.customer_id" as the "Field Name,"
	  select "IN" as the Criteria, and enter "?lcKeyList" as the Example.
	
	6. When you select the View SQL option, you should see the following:
	
	        SELECT *;
	         FROM tastrade!customer;
	         WHERE Customer.customer_id IN (?lcKeyList)
	
	7. Save the view and close the View Designer.
	
	8. In the Command window, execute:
	
	  lcKeyList=' "ALFKI,","ANATR,","ANTON" '
	
	9. Open and then Browse the View.
	
	10. Note that you get an empty cursor. Close the Browse window. Close the view
	  using the USE command.
	
	11. Again, in the Command window, release lcKeyList by executing the following:
	
	  CLEAR MEMO lcKeyList ALL
	
	12. Open and then Browse the View.
	
	13. When asked for the value for lcKeyList, enter the following exactly as
	  follows:
	
	  " "ALFKI",ANATR","ANTON" " (without the quotation marks)
	
	14. Note that you get a single record. Close the Browse window. Close the view
	  with the USE command.
	
	15. In the Command window, execute the following:
	
	  lcKeyList=' "ALFKI","ANATR","ANTON" '
	
	16. In the Command window, execute the following:
	
	        SELECT * FROM tastrade!customer
	         WHERE customer_id IN (&lcKeyList)
	
	17. Note that a cursor with three records is returned.
	
	The result in step 17 is correct and this is what is expected to be returned by
	the View created with the View Designer and displayed using steps 8-10 and then
	steps 11-14.
	
	Additional query words: kbdse VFoxWin PARAMETER MULTIPLE
	
	======================================================================
	Keywords          : kbvfp500 kbvfp600 
	Technology        : kbVFPsearch kbAudDeveloper kbVFP500 kbVFP600
	Version           : :5.0,6.0
	
	=============================================================================
	

{% endraw %}
