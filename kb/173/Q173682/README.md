---
layout: page
title: "Q173682: Print Service Doesn't Print Jobs Concurrently If PDT Is Used"
permalink: /kb/173/Q173682/
---

## Q173682: Print Service Doesn't Print Jobs Concurrently If PDT Is Used

{% raw %}

	Article: Q173682
	Product(s): Microsoft SNA Server
	Version(s): WINDOWS:3.0,3.0 SP1
	Operating System(s): 
	Keyword(s): kbnetwork
	Last Modified: 13-JUN-2001
	
	-------------------------------------------------------------------------------
	The information in this article applies to:
	
	- Microsoft SNA Server, versions 3.0, 3.0 SP1 
	-------------------------------------------------------------------------------
	
	
	SYMPTOMS
	========
	
	Multiple print jobs destined for the same physical printer are sent to the SNA
	Server print service; the print sessions are configured to use a PDT file. The
	print service processes only one job at a time until all are printed, rather
	than spooling multiple jobs at once. You can see this problem in SNA Server
	Manager when you view the status for the configured print sessions; only one
	print session at a time is in a spooling state.
	
	If a PDT file is not being used for the print sessions, all print sessions that
	have been sent a print job will be in a spooling state.
	
	CAUSE
	=====
	
	The SNA Server print service calls the StartDocPrinter() API to open a
	connection to a printer when a print session is configured to use a PDT file.
	The StartDocPrinter() API returns a printer handle to the print service when the
	call completes successfully. When multiple print jobs are sent to different
	print sessions configured to print to the same printer, the print service calls
	StartDocPrinter() multiple times, using the printer handle that was returned by
	the initial StartDocPrinter() call to open multiple connections to the printer.
	The first call to StartDocPrinter() succeeds, but subsequent calls fail with an
	ERROR_INVALID_PRINTER_STATE error. The print service tries to open the
	connection to the printer every few seconds for each of the failed connections,
	so all of the print jobs eventually print as the previous jobs complete.
	
	The StartDocPrinter() API does not allow multiple connections to be opened to the
	same printer using the same printer handle. The printer handle can be reused
	after the intial print job is completed.
	
	
	STATUS
	======
	
	Microsoft has confirmed this to be a problem in SNA Server versions 3.0 and 3.0
	Service Pack 1 (SP1). This problem was corrected in the latest SNA Server
	version 3.0 U.S. Service Pack. For information on obtaining this Service Pack,
	query on the following word in the Microsoft Knowledge Base (without the
	spaces):
	
	  S E R V P A C K
	
	MORE INFORMATION
	================
	
	With the fix applied, the SNA Server print service always opens a new printer
	connection for each new print session. Each print session will then get a
	different printer handle, which allows all print jobs to be processed
	concurrently when a PDT file is used.
	
	Additional query words:
	
	======================================================================
	Keywords          : kbnetwork 
	Technology        : kbAudDeveloper kbSNAServSearch kbSNAServ300 kbSNAServ300SP1
	Version           : WINDOWS:3.0,3.0 SP1
	Issue type        : kbbug
	Solution Type     : kbfix
	
	=============================================================================
	

{% endraw %}
