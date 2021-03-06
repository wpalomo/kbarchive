---
layout: page
title: "Q115171: WD97: Merge Data Source Fails to Attach, Merge, or Allow Check"
permalink: /kb/115/Q115171/
---

## Q115171: WD97: Merge Data Source Fails to Attach, Merge, or Allow Check

{% raw %}

	Article: Q115171
	Product(s): Word 97 for Windows
	Version(s): WINDOWS:97
	Operating System(s): 
	Keyword(s): kbprint kbmerge kbPrinting
	Last Modified: 07-SEP-2001
	
	-------------------------------------------------------------------------------
	The information in this article applies to:
	
	- Microsoft Word 97 for Windows 
	-------------------------------------------------------------------------------
	
	
	SYMPTOMS
	========
	
	When you are working with a mail merge data source, the following symptoms may
	occur:
	
	- Error message: "Word was unable to open the data source"
	
	- The data source appears to have not attached after you try to attach it.
	
	- Navigation of data records may be prevented.
	
	- Merging may halt at a particular record prematurely.
	
	- Data source searching may halt prematurely.
	
	- More than one record merges to the same merged document page unexpectedly.
	
	The lack of helpful error messages that explain the reasons for the problems make
	troubleshooting difficult.
	
	CAUSE
	=====
	
	These problems are most likely caused by mismatched double quotation marks in a
	mail merge data source document.
	
	RESOLUTION
	==========
	
	These problems can be resolved by correcting the quotation marks. Open the data
	source file without attaching it to the main file. Browse or search for any
	mismatched quotation marks and correct them by providing matching left and right
	quotation marks or by removing the offending quotation marks.
	
	STATUS
	======
	
	Microsoft has confirmed this to be a problem in the Microsoft products that are
	listed at the beginning of this article.
	
	
	MORE INFORMATION
	================
	
	The following are more detailed descriptions of the symptoms:
	
	- Choosing the navigation buttons on the main document Mail Merge toolbar does
	  not allow navigation past the record with the mismatched double quotation
	  mark. The record number displayed on the toolbar will correspond to the last
	  good record. If the mismatched quotation mark is in the first data record,
	  the record number displayed will be 0 *(zero).
	
	- Merging will quit after the last good record. The following warning message
	  will appear:
	
	  Word could not finish merging these documents or inserting this database.
	
	- Data record searches will begin at the current insertion point location and
	  quit after the last good record. No warning or error messages will appear.
	
	- Data source error checking will quit after the last good record without
	  pinpointing the error and will display the following warning message:
	
	  Word could not finish merging these documents or inserting this database.
	
	- The header delimiter selection screen will display when the data source is
	  attached to the main document if the mismatched double quotation mark is in
	  the first record of the data source. A delimiter can be selected, but the
	  data source will not attach. No errors or warnings will display. The record
	  number box on the main document Mail Merge toolbar will show a 0 (zero).
	
	- In the Data Form dialog box, if Word is attempting to read a record that
	  contains a mismatched quotation mark, then the following message may appear:
	
	  Word cannot read the next record from the data source because the data source
	  has a mismatched double quotation mark.
	
	Additional query words: datafile data file database unmatched quotes 8.00 word8 word97
	
	======================================================================
	Keywords          : kbprint kbmerge kbPrinting 
	Technology        : kbWordSearch kbWord97 kbWord97Search kbZNotKeyword2
	Version           : WINDOWS:97
	
	=============================================================================
	

{% endraw %}
