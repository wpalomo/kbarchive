---
layout: page
title: "Q215368: XCON: MTA Content Conversion Error 4101 with HP Openmail"
permalink: /kb/215/Q215368/
---

## Q215368: XCON: MTA Content Conversion Error 4101 with HP Openmail

{% raw %}

	Article: Q215368
	Product(s): Microsoft Exchange
	Version(s): winnt:5.5 SP1
	Operating System(s): 
	Keyword(s): exc55sp1 EXC55SP3Fix
	Last Modified: 01-OCT-1999
	
	-------------------------------------------------------------------------------
	The information in this article applies to:
	
	- Microsoft Exchange Server, version 5.5 SP1 
	-------------------------------------------------------------------------------
	
	SYMPTOMS
	========
	
	When you use Microsoft Exchange Server 5.5 Service Pack 1 with HP Openmail, you
	may experience content conversion problems with the Exchange Message Transfer
	Agent (MTA) under the following circumstances:
	
	- A message was sent from Exchange Server 5.5 Service Pack 1 to an Openmail
	  user with delivery and read receipts.
	
	- The sender receives the delivery receipt.
	
	- The recipient reads the message.
	
	- The recipient of the original message receives an NDR to their read receipt:
	
	  Message corruption detected.
	  MSEXCH:MSExchangeMTA:<sitename>:<servername>
	
	The sender of the original message never receives the read receipt for their
	message.
	
	The Exchange Server computer will also log a 210 content conversion error with
	conversion error 4101 when this problem occurs.
	
	CAUSE
	=====
	
	The Exchange Server MTA was not handling the read receipt correctly.
	
	RESOLUTION
	==========
	
	To resolve this problem, obtain the latest service pack for Exchange Server
	version 5.5. For additional information, please see the following article in the
	Microsoft Knowledge Base:
	
	  Q191014 XGEN: How to Obtain the latest Exchange Server 5.5 Service Pack
	
	The English version of this fix should have the following file attributes or
	later:
	
	Component: Message Transfer Agent (MTA)
	
	+---------------------------+
	| File name    | Version    | 
	+---------------------------+
	| Dbserver.sch | N/A        | 
	+---------------------------+
	| Dcprods.cat  | N/A        | 
	+---------------------------+
	| Ems_rid.dll  | 5.5.2512.0 | 
	+---------------------------+
	| Emsmta.exe   | 5.5.2512.0 | 
	+---------------------------+
	| Info4log.cfg | N/A        | 
	+---------------------------+
	| Infoblog.cfg | N/A        | 
	+---------------------------+
	| Infodlog.cfg | N/A        | 
	+---------------------------+
	| Infollog.cfg | N/A        | 
	+---------------------------+
	| Infotlog.cfg | N/A        | 
	+---------------------------+
	| Mtacheck.exe | 5.5.2512.0 | 
	+---------------------------+
	| Mtamsg.dll   | 5.5.2512.0 | 
	+---------------------------+
	| P2.xv2       | N/A        | 
	+---------------------------+
	| X400om.dll   | 5.5.2512.0 | 
	+---------------------------+
	| X400omv1.dll | 5.5.2512.0 | 
	+---------------------------+
	
	
	STATUS
	======
	
	Microsoft has confirmed this to be a problem in Microsoft Exchange Server
	version 5.5. This problem was first corrected in Exchange Server 5.5 Service
	Pack 3.
	
	Additional query words: 210 metamorf
	
	======================================================================
	Keywords          : exc55sp1 EXC55SP3Fix 
	Technology        : kbExchangeSearch kbZNotKeyword2 kbExchange550SP1
	Version           : winnt:5.5 SP1
	Issue type        : kbbug
	Solution Type     : kbfix
	
	=============================================================================
	

{% endraw %}
