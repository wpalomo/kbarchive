---
layout: page
title: "Q157688: XCLN: Reminders not Processed When Default Store is PST"
permalink: /kb/157/Q157688/
---

## Q157688: XCLN: Reminders not Processed When Default Store is PST

{% raw %}

	Article: Q157688
	Product(s): Microsoft Exchange
	Version(s): WINDOWS:4.0; :4.0
	Operating System(s): 
	Keyword(s): kbusage
	Last Modified: 16-JAN-2000
	
	-------------------------------------------------------------------------------
	The information in this article applies to:
	
	- Microsoft Exchange Windows 3.x client, version 4.0 
	- Microsoft Exchange Windows NT client, version 4.0 
	- Microsoft Exchange for Windows 95, version 4.0 
	-------------------------------------------------------------------------------
	
	SYMPTOMS
	========
	
	Microsoft Exchange user reminders stop processing after a period of time when
	the default information store is a personal store (PST).
	
	CAUSE
	=====
	
	When the default information store is a PST, a search folder is used to locate
	items in a user's calendar that have reminders. If there is a folder added
	during the time that this background search was happening, all events after the
	folder addition will fail to process.
	
	
	WORKAROUND
	==========
	
	If you restart the Microsoft Exchange client, events after the folder addition
	will be processed. However, this will not prevent the problem from occurring
	again.
	
	STATUS
	======
	
	Microsoft has confirmed this to be a problem in the Microsoft Exchange clients,
	version 4.0, listed at the beginning of this article. This problem was corrected
	in Microsoft Exchange Server 4.0 U.S. Service Pack 4. For information on
	obtaining the service pack, query on the following word in the Microsoft
	Knowledge Base:
	
	  " SERVPACK" (without the quotation marks)
	
	Additional query words: Outlook97
	
	======================================================================
	Keywords          : kbusage 
	Technology        : kbZNotKeyword8 kbExchangeSearch kbExchange400 kbExchangeClientSearch kbZNotKeyword2 kbZNotKeyword3 kbExchange400NT kbExchange400Win95
	Version           : WINDOWS:4.0; :4.0
	
	=============================================================================
	

{% endraw %}
