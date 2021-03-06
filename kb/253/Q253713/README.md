---
layout: page
title: "Q253713: HOWTO: Move Data from an XML Document into a FoxPro Table"
permalink: /kb/253/Q253713/
---

## Q253713: HOWTO: Move Data from an XML Document into a FoxPro Table

{% raw %}

	Article: Q253713
	Product(s): Microsoft FoxPro
	Version(s): 2.5,2.6,3.0,6.0
	Operating System(s): 
	Keyword(s): kbDatabase kbInternet kbvfp600 KbDBFDBC kbXML kbGrpDSFox kbDSupport kbMSXML kbGrpDSMSXM
	Last Modified: 06-DEC-2000
	
	-------------------------------------------------------------------------------
	The information in this article applies to:
	
	- Microsoft Visual FoxPro for Windows, version 6.0 
	- Microsoft XML, versions 2.5, 2.6, 3.0 
	-------------------------------------------------------------------------------
	
	SUMMARY
	=======
	
	This is a simple example of how the Microsoft XML parser (MSXML) object can be
	used to move XML data from an XML document into a Microsoft FoxPro table. A
	FoxPro table similar in structure to the Orders table is created and the data in
	the XML document is moved to the table.
	
	MORE INFORMATION
	================
	
	This example uses the MSXML parser to move data from an XML document to a FoxPro
	table. The parser is available at:
	
	  http://msdn.microsoft.com/xml/default.asp
	
	This code takes the XML document below, creates a new table called SampOrd and
	populates the table with the XML data.
	
	NOTE: Ensure that any XML document to be used as a datasource for the sample code
	below has a root tag or basename in the document; otherwise an error might
	occur.
	
	1. Install the MSXML parser.
	
	2. Create an XML document from the XML code below.
	
	3. Create a FoxPro program file with the following code and then run the
	  program:
	
	  CREATE TABLE SampOrd (  ;
	      order_id    c(10), ;
	      cust_id     c(10), ;
	      emp_id      c(10), ;
	      to_name     c(25), ;
	      to_address  c(50), ;
	      to_city     c(25), ;
	      to_region   c(10), ;
	      postalcode  c(10), ;
	      to_country  c(15), ;
	      ship_count  c(15), ;
	      ship_via    c(6),  ;
	      order_date  c(8),  ;
	      order_amt   c(10), ;
	      order_dsc   c(10), ;
	      order_net   c(10), ;
	      require_by  c(8),  ;
	      shipped_on  c(8),  ;
	      freight     c(10))
	
	  *** Uncomment the following line if you want access to oXML 
	  *** outside of this program.
	  *PUBLIC oXML  
	
	  oXML=CREATEOBJECT('msxml.domdocument')  && This creates the parser object
	  oXML.LOAD(GETFILE('xml'))  && This gets and loads the XML document. 
	
	  *** Select the XML document created from the XML code below.
	  *** The following gives the basename of the XML document
	  *?oXML.DocumentElement.Basename 
	  *** The following gives the number of nodes (or records)           
	  *?oXML.documentelement.childnodes.LENGTH  
	
	  ** The following snippet appends a blank record and parses 
	  ** through each node element and adds it to the table.
	
	  ** REMEMBER that the object model is in base zero.
	  WITH oXML.DocumentElement.ChildNodes
	      FOR iCount = 0 TO .LENGTH - 1
	          APPEND BLANK
	          FOR iChild = 0 TO .ITEM(0).ChildNodes.LENGTH - 1
	              lcVar = .ITEM(iCount).ChildNodes(iChild)
	              REPLACE (lcVar.NodeName) WITH (lcVar.TEXT)
	          ENDFOR
	      ENDFOR
	  ENDWITH
	
	  BROWSE
	
	XML Code
	--------
	
	  <orders_table>
	
	  <orders>
	  	<order_id> 10040</order_id>
	  	<cust_id>WHITC </cust_id>
	  	<emp_id>     3</emp_id>
	  	<to_name>White Clover Markets                    </to_name>
	  	<to_address>1029 - 12th Ave. S.                  </to_address>
	  	<to_city>Bellevue       </to_city>
	  	<to_region>WA             </to_region>
	  	<postalcode>98124     </postalcode>
	  	<to_country>USA            </to_country>
	  	<ship_count>USA            </ship_count>
	  	<ship_via>     3</ship_via>
	  	<order_date>09/09/93</order_date>
	  	<order_amt>$1,991.00</order_amt>
	  	<order_dsc>10</order_dsc>
	  	<order_net>$1,842.88</order_net>
	  	<require_by>10/07/93</require_by>
	  	<shipped_on>09/18/93</shipped_on>
	  	<freight>$51.88</freight>
	  </orders>
	  <orders>
	  	<order_id> 10095</order_id>
	  	<cust_id>LAZYK </cust_id>
	  	<emp_id>     3</emp_id>
	  	<to_name>Lazy K Kountry Store                    </to_name>
	  	<to_address>12 Orchestra Terrace                 </to_address>
	  	<to_city>Walla Walla    </to_city>
	  	<to_region>WA             </to_region>
	  	<postalcode>99362     </postalcode>
	  	<to_country>USA            </to_country>
	  	<ship_count>USA            </ship_count>
	  	<ship_via>     3</ship_via>
	  	<order_date>12/10/93</order_date>
	  	<order_amt>$530.00</order_amt>
	  	<order_dsc>10</order_dsc>
	  	<order_net>$479.58</order_net>
	  	<require_by>01/07/94</require_by>
	  	<shipped_on>12/11/93</shipped_on>
	  	<freight>$2.58</freight>
	  </orders>
	
	  </orders_table>
	
	- If a root tag or basename is not in the XML document, usually an "OLE error
	  0x00000001: Incorrect function" error occurs.
	
	REFERENCES
	==========
	
	For additional information on XML, click the article number below to view the
	article in the Microsoft Knowledge Base:
	
	  Q191758 HOWTO: Convert FoxPro Cursor into XML Data Format
	
	For more information about XML, see the following Web sites:
	
	  http://msdn.microsoft.com/xml/default.asp
	
	  http://www.xml.com
	
	Additional query words:
	
	======================================================================
	Keywords          : kbDatabase kbInternet kbvfp600 KbDBFDBC kbXML kbGrpDSFox kbDSupport kbMSXML kbGrpDSMSXML 
	Technology        : kbVFPsearch kbAudDeveloper kbMSXMLSearch kbVFP600 kbMSXML250 kbMSXML260 kbMSXML300
	Version           : :2.5,2.6,3.0,6.0
	Issue type        : kbhowto
	
	=============================================================================
	

{% endraw %}
