---
layout: page
title: "Q130302: PRB: OLE Word 6 Object Does Not Close Itself in Windows NT"
permalink: /kb/130/Q130302/
---

## Q130302: PRB: OLE Word 6 Object Does Not Close Itself in Windows NT

{% raw %}

	Article: Q130302
	Product(s): Microsoft FoxPro
	Version(s): WINDOWS:3.0
	Operating System(s): 
	Keyword(s): 
	Last Modified: 10-FEB-2000
	
	-------------------------------------------------------------------------------
	The information in this article applies to:
	
	- Microsoft FoxPro for Windows, version 3.0 
	-------------------------------------------------------------------------------
	
	SYMPTOMS
	========
	
	In the operating environment of Windows NT version 3.5, when you navigate
	through Visual FoxPro and activate Microsoft Word 6.0 for Windows (the 16- bit
	version) to edit a "bound" object, the instance of Word does not quit when you
	skip to the next record or quit Visual FoxPro.
	
	CAUSE
	=====
	
	
	WORKAROUND
	==========
	
	The only way to quit the instance of Word is to use PVIEWER.EXE (a program
	provided with the Windows NT Resource Kit) to kill the "NTVDM" process (the
	Windows NT 16-bit applications process).
	
	STATUS
	======
	
	Microsoft is researching this problem and will post new information here in the
	Microsoft Knowledge Base as it becomes available.
	
	MORE INFORMATION
	================
	
	Steps to Reproduce Behavior
	---------------------------
	
	On a system running Windows NT version 3.5, Workstation:
	
	1. From the Windows file manager, copy one of the Word 16 templates to the Word
	  startup directory. For example, copy PRESENT1.DOT to the C:\WORD16\STARTUP
	  directory.
	
	2. In Visual FoxPro, create a table named Testword.dbf that has PRESENT1.DOT as
	  an embedded Word Object in a general field. The easiest way to do this is to
	  follow these steps:
	
	  a. In the Command window, enter the following command:
	
	        CREATE TABLE Testword (gfield1 g)
	
	  b. Open the Testword table in a Visual FoxPro work area.
	
	  c. Browse the table, and use the APPEND command to add a blank record to the
	     table.
	
	  d. Press ALT+TAB to return to Program Manager. Then start Microsoft Word.
	
	  e. In Word, open the PRESENT1.DOT document. This .DOT file is an empty
	     template.
	
	  f. Select the entire document. Then from Word's Edit menu, choose Copy to
	     copy the document to the clipboard.
	
	  g. Close Word.
	
	  h. Return to Visual FoxPro.
	
	  i. Browse the Testword table. Double-click gfield1. An empty edit window will
	     appear.
	
	  j. From the Edit menu, choose Paste to copy the contents of PRESENT1.DOT from
	     the clipboard into gfield1. Double-click the empty window. Enter some text
	     in the field so it can be seen.
	
	  k. Save gfield1. Append two more empty records to the table.
	
	3. In Visual FoxPro, create a form that has an OLE bound control that is bound
	  to the general field in the table created in step 2. Then add a command
	  button to the form. Add the following commands to the Click method of the
	  command button:
	
	     SKIP
	     THISFORM.Refresh
	
	4. Close and save the form as TESTWORD.SCX.
	
	5. Press CTRL+ESC to open the Task Manager. Close all the processes in Windows
	  NT except Visual FoxPro, Program Manager, and File Manager.
	
	6. Go to File Manager. Start PVIEWER.EXE from the WINDOWS\RESKIT directory. A
	  dialog box titled "Process Viewer" is presented. All of the processes
	  currently active in Windows NT are listed in alphabetical order. Notice that
	  there is no process named "NTVDM..."
	
	7. Press ALT+TAB to return to Visual FoxPro.
	
	8. If it is not still open, open the TESTWORD.DBF table.
	
	9. Run the TESTWORD.SCX form by typing "DO FORM Testword" (without the quotation
	  marks) command in the Command window.
	
	10. Double-click the gfield1 OLE object. Word opens for "in place activation."
	  Press ALT+TAB to switch to the Process Viewer window. Note that an entry for
	  "NTVDM..." has been added to the process list. Switch back to Visual FoxPro.
	
	11. Save gfield1, and click the command button to move to the next record.
	
	12. Press ALT+TAB to switch to the Process Viewer window. Notice that there is
	  still an entry for "NTVDM..."
	
	13. Switch back to Visual FoxPro. Quit Visual FoxPro.
	
	14. Return to the Process Viewer. The entry for NTVDM is still there. Select it
	  with the mouse, and click the Kill Process button.
	
	Additional query words: VFoxWin 3.00 bound OLE Windows NT hang winword
	
	======================================================================
	Keywords          :  
	Technology        : kbAudDeveloper kbFoxproSearch
	Version           : WINDOWS:3.0
	
	=============================================================================
	

{% endraw %}
