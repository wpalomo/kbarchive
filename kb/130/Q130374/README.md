---
layout: page
title: "Q130374: Incorrect System BIOS Information in Windows NT Diag. Report"
permalink: /kb/130/Q130374/
---

## Q130374: Incorrect System BIOS Information in Windows NT Diag. Report

{% raw %}

	Article: Q130374
	Product(s): Microsoft Windows NT
	Version(s): 
	Operating System(s): 
	Keyword(s): 
	Last Modified: 08-AUG-2001
	
	-------------------------------------------------------------------------------
	The information in this article applies to:
	
	- Microsoft Windows NT Workstation version 3.5 
	- Microsoft Windows NT Server version 3.5 
	-------------------------------------------------------------------------------
	
	SYMPTOMS
	========
	
	When you save or print a Windows NT Diagnostics (WINMSD.EXE) report that
	includes Hardware information, there may be two or more lines for System BIOS
	Version. The first line usually contains correct information, however the rest
	of the System BIOS Version lines have erroneous information. For example:
	
	            Microsoft Diagnostics Report For <Computer Name>
	  ----------------------------------------------------------------------
	  Hardware Report
	  ----------------------------------------------------------------------
	
	                 System BIOS Date: 12/15/94
	              System BIOS Version: 80486 ROM BIOS PLUS Version 1.00 A10
	              System BIOS Version: 0 A??
	              System BIOS Version: ? ? ?
	              System BIOS Version: 2
	              System BIOS Version: <Computer name>
	              System BIOS Version: <Erroneous name>
	                                   6
	                  Video BIOS Date: 94/12/15
	               Video BIOS Version:
	                           OEM ID: 0
	                         CPU Type: Intel Pentium
	                   Number of CPUs: 1
	                        Page Size: 4 KB (4,096)
	      Minimum Application Address: 0x00010000
	      Maximum Application Address: 0x7FFEFFFF
	         Current Video Resolution: 800 x 600 x 65,536
	          Stepping of Processor 0: x86 Family 5 Model 2 Stepping 4
	
	Note:
	
	- This problem occurs three to four times in every ten tries.
	
	- The corruption usually looks different every time.
	
	- This problem also occurs when you save or print Report All.
	
	STATUS
	======
	
	Microsoft has confirmed this to be a problem in Windows NT version 3.5. We are
	researching this problem and will post new information here in the Microsoft
	Knowledge Base as it becomes available.
	
	Additional query words: prodnt msd 3 4 10
	
	======================================================================
	Keywords          :  
	Technology        : kbWinNTsearch kbWinNTWsearch kbWinNT350search kbWinNTW350 kbWinNTW350search kbWinNTSsearch kbWinNTS350 kbWinNTS350search
	
	=============================================================================
	

{% endraw %}
