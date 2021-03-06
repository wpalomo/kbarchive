---
layout: page
title: "Q167259: WD97: Error in Recorded Macro Using Previous/Next Row Commands"
permalink: /kb/167/Q167259/
---

## Q167259: WD97: Error in Recorded Macro Using Previous/Next Row Commands

{% raw %}

	Article: Q167259
	Product(s): Word 97 for Windows
	Version(s): WINDOWS:97
	Operating System(s): 
	Keyword(s): kbcode kbProgramming kbdta word8 kbwordvba word97
	Last Modified: 13-MAY-2002
	
	-------------------------------------------------------------------------------
	The information in this article applies to:
	
	- Microsoft Word 97 for Windows 
	-------------------------------------------------------------------------------
	
	
	SYMPTOMS
	========
	
	When you attempt to record a macro using the Previous Row or Next Row buttons
	(in the Table Cell Height And Width dialog box), you do not receive the results
	you expect when you play back the macro.
	
	CAUSE
	=====
	
	This problem occurs when either of the following conditions is true when you
	record the macro:
	
	- The macro was recorded using the Previous Row command and the insertion point
	  was in the first row of the table.
	
	-or-
	
	- The macro was recorded using the Next Row command and the insertion point was
	  in the last row of the table.
	
	When you run the recorded macro it does not wrap to the beginning or end of the
	table as it does when you perform these actions manually.
	
	WORKAROUND
	==========
	
	Microsoft provides programming examples for illustration only, without warranty
	either expressed or implied, including, but not limited to, the implied
	warranties of merchantability and/or fitness for a particular purpose. This
	article assumes that you are familiar with the programming language being
	demonstrated and the tools used to create and debug procedures. Microsoft
	support professionals can help explain the functionality of a particular
	procedure, but they will not modify these examples to provide added
	functionality or construct procedures to meet your specific needs. If you have
	limited programming experience, you may want to contact a Microsoft Certified
	Partner or the Microsoft fee-based consulting line at (800) 936-5200. For more
	information about Microsoft Certified Partners, please visit the following
	Microsoft Web site:
	
	  http://www.microsoft.com/partner/referral/
	
	For more information about the support options that are available and about how
	to contact Microsoft, visit the following Microsoft Web site:
	
	  http://support.microsoft.com/default.aspx?scid=fh;EN-US;CNTACTMS
	
	To work around this problem, edit the recorded macro.
	
	In Visual Basic for Applications, there are several methods which can be used to
	move the insertion point. Shown below are suggested methods that can be used to
	effectively wrap the insertion point to the first or last row of the current
	table in a document.
	
	Using the Previous Row command
	------------------------------
	
	Look for the following command line if you recorded a macro that uses the
	Previous Row command
	
	     Selection.Move Unit:=wdRow, Count:=-1
	
	and change the command line to the following:
	
	     ' Make sure the insertion point is within a table.
	     If Selection.Information(wdWithInTable) Then
	        ' If at top of table,
	        If Selection.Rows(1).Index = 1 Then
	           ' Wrap to bottom of table.
	           Selection.Move Unit:=wdRow, Count:=Selection.Tables(1).Rows.Count
	        Else
	           ' Otherwise, move up one row.
	           Selection.Move Unit:=wdRow, Count:=-1
	        End If
	     End If
	
	Using the Next Row command
	--------------------------
	
	Look for the following command line if you recorded a macro that uses the Next
	Row command
	
	     Selection.Move Unit:=wdRow, Count:=1
	
	and change the command line to the following:
	
	       ' Make sure the insertion point is within a table.
	     If Selection.Information(wdWithInTable) Then
	        ' If at bottom of table,
	        If Selection.Rows(1).Index = Selection.Tables(1).Rows.Count Then
	           ' Wrap to top of table.
	           Selection.StartOf wdTable, wdMove
	        Else
	           ' Otherwise, move down one row.
	           Selection.Move Unit:=wdRow, Count:=1
	        End If
	     End If
	
	STATUS
	======
	
	Microsoft has confirmed this to be a problem in the Microsoft products listed at
	the beginning of this article. We are researching this problem and will post new
	information here in the Microsoft Knowledge Base as it becomes available.
	
	MORE INFORMATION
	================
	
	For additional information, please see the following article in the Microsoft
	Knowledge Base:
	
	  Q173707 OFF97: How to Run Sample Code from Knowledge Base Articles
	
	
	REFERENCES
	==========
	
	For more information about getting help with Visual Basic for Applications,
	please see the following article in the Microsoft Knowledge Base:
	
	  Q163435 VBA: Programming Resources for Visual Basic for Applications
	
	Additional query words: wordcon vb vba vbe
	
	======================================================================
	Keywords          : kbcode kbProgramming kbdta word8 kbwordvba word97 
	Technology        : kbWordSearch kbWord97 kbWord97Search kbZNotKeyword2
	Version           : WINDOWS:97
	Issue type        : kbbug
	Solution Type     : kbpending
	
	=============================================================================
	

{% endraw %}
