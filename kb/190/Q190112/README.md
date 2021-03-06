---
layout: page
title: "Q190112: PRB: Data Object Wizard Fails If Field Names Contain Spaces"
permalink: /kb/190/Q190112/
---

## Q190112: PRB: Data Object Wizard Fails If Field Names Contain Spaces

{% raw %}

	Article: Q190112
	Product(s): Microsoft Visual Basic for Windows
	Version(s): WINDOWS:6.0
	Operating System(s): 
	Keyword(s): kbGrpDSVBDB
	Last Modified: 11-JAN-2001
	
	-------------------------------------------------------------------------------
	The information in this article applies to:
	
	- Microsoft Visual Basic Professional Edition for Windows, version 6.0 
	- Microsoft Visual Basic Enterprise Edition for Windows, version 6.0 
	-------------------------------------------------------------------------------
	
	SYMPTOMS
	========
	
	When you run the Data Object Wizard against a Data Environment Command object,
	you may receive the following error message:
	
	  The field 'xxx yyy' has a space in it. You cannot select a Command where a
	  field has a space in its name.
	
	CAUSE
	=====
	
	This error occurs because the Data Object Wizard creates methods corresponding
	to field names, and method names cannot contain spaces in them.
	
	RESOLUTION
	==========
	
	Rename fields to eliminate spaces, or base the Command on a SELECT statement
	where the field names are aliased to remove spaces.
	
	STATUS
	======
	
	This behavior is by design.
	
	MORE INFORMATION
	================
	
	Steps to Add a Field Name with a Space
	--------------------------------------
	
	NOTE: Not all data providers support this technique. For instance the Microsoft
	Jet 3.51 OLE DB Provider does not support this technique. In this case, you can
	use a tool, such as VISDATA, which is one of the Visual Basic sample
	applications, or Access, to change the field names.
	
	1. Open a new Standard EXE project in Visual Basic 6.0.
	
	2. Open the Data View window (on the View menu, click Data View Window).
	
	3. Right-click Data Links in the tree-view and add a new data link with the
	  following properties:
	
	  1. Provider Tab: Select Microsoft OLE DB Provider for ODBC Drivers.
	
	  2. Connection Tab: Provide the connection to your SQL Server database and
	     choose "pubs" as the initial catalog name.
	
	4. Click OK on the Data Link properties dialog box.
	
	5. Expand the tree under the newly added datalink (DataLink1) to expose:
	
	  DataLinks\DataLink1\Tables\Authors
	
	  You may have to complete an ODBC login dialog box.
	
	6. Right-click "authors" and select Design.
	
	7. In the design view, rename au_lname to au lname.
	
	8. Close the designer and save the changes. You do not have to save the script
	  generated by the designer.
	
	Steps to Activate the Data Object Wizard
	----------------------------------------
	
	1. In your Visual Basic 6.0 project, activate the Add-In Manager (Add-Ins menu).
	
	2. Select the VB6 Data Object Wizard. If it is not already loaded, click the
	  Loaded/Unloaded check box.
	
	3. Click OK on the Add-In Manager dialog box.
	
	Steps to Add a Data Environment
	-------------------------------
	
	1. In your Visual Basic 6.0 project, click Project, then Add Data Environment.
	
	2. In the Data Environment designer, right-click Connection1 and choose
	  Properties.
	
	3. Set the Data Link Properties:
	
	  1. Provider Tab: Select Microsoft OLE DB Provider for ODBC Drivers.
	
	  2. Connection Tab: Provide the connection to your SQL Server database and
	     choose "pubs" as the initial catalog name.
	
	4. Click OK on the dialog box. NOTE: You may also have to complete an ODBC login
	  at this point.
	
	5. Right-click Connection1 in the Data Environment designer and choose Add
	  Command. This creates Command1.
	
	6. Right-click Command1 in the Data Environment designer and choose Properties.
	
	7. In the Command1 Properties dialog box, set the following:
	
	     General Tab: Database Object:  Table
	                  Object Name:      authors
	
	  NOTE: You may have to complete an ODBC login dialog box at this point.
	
	8. Click OK on the Command1 Properties dialog box.
	
	9. Close the Data Environment designer.
	
	Steps to Reproduce the Bug
	--------------------------
	
	1. In your Visual Basic 6.0 project, click Add-Ins, then VB6 Data Object Wizard.
	
	2. In the wizard, click Next to bypass the Introduction page and the Create
	  Object page, accepting default values for these settings.
	
	3. On the Select Data Environment Command page, select the Command object
	  created in the previous sections and click Next. The error is displayed.
	
	Additional query words: kbvbp600 kbDatabase kbDataview kbAddIn kbdse kbDSupport kbVBp
	
	======================================================================
	Keywords          : kbGrpDSVBDB 
	Technology        : kbVBSearch kbAudDeveloper kbZNotKeyword6 kbZNotKeyword2 kbVB600Search kbVBA600 kbVB600
	Version           : WINDOWS:6.0
	Issue type        : kbprb
	
	=============================================================================
	

{% endraw %}
