---
layout: page
title: "Q176194: XFOR: Messages Fail to Process When No PRMD Defined"
permalink: /kb/176/Q176194/
---

## Q176194: XFOR: Messages Fail to Process When No PRMD Defined

{% raw %}

	Article: Q176194
	Product(s): Microsoft Exchange
	Version(s): WinNT:5.0
	Operating System(s): 
	Keyword(s): 
	Last Modified: 14-MAR-1999
	
	-------------------------------------------------------------------------------
	The information in this article applies to:
	
	- Microsoft Exchange Server, version 5.0 
	-------------------------------------------------------------------------------
	
	
	SYMPTOMS
	========
	
	Messages submitted to Exchange via the Microsoft Mail Connector Interchange
	(MSMI) may fail to process when no private management domain (PRMD) attribute
	has been defined for the X.400 site address. The following event may be
	generated by the store:
	
	  Event ID 2025:
	  The delivery of a message failed due to error 00000bb8. A non-delivery
	  report is being sent to the message's originator.
	  EcDoDeliverMessage():00000bb8
	
	CAUSE
	=====
	
	The MSMI generates an MTS-ID, which includes a null value for the PRMD object
	when the pointer to the PRMD object should be NULL.
	
	STATUS
	======
	
	Microsoft has confirmed this to be a problem in Microsoft Exchange Server
	version 5.0. This problem has been corrected in the latest U.S. Service Pack for
	Microsoft Exchange Server version 5.0. For information on obtaining the Service
	Pack, query on the following word in the Microsoft Knowledge Base (without the
	spaces):
	
	  S E R V P A C K
	
	
	======================================================================
	Keywords          :  
	Technology        : kbExchangeSearch kbExchange500 kbZNotKeyword2
	Version           : WinNT:5.0
	Issue type        : kbbug
	Solution Type     : kbfix
	
	=============================================================================
	

{% endraw %}
