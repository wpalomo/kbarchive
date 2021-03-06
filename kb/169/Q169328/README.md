---
layout: page
title: "Q169328: MSMail: Network Name Could Not be Found When Creating a New PO"
permalink: /kb/169/Q169328/
---

## Q169328: MSMail: Network Name Could Not be Found When Creating a New PO

{% raw %}

	Article: Q169328
	Product(s): Microsoft Exchange
	Version(s): WINDOWS:3.0,3.2,3.5
	Operating System(s): 
	Keyword(s): kbtshoot kbusage
	Last Modified: 22-JUN-2001
	
	-------------------------------------------------------------------------------
	The information in this article applies to:
	
	- Microsoft Mail for PC Networks, versions 3.0, 3.2, 3.5 
	- Microsoft Exchange Server, version 5.5 
	-------------------------------------------------------------------------------
	
	SYMPTOMS
	========
	
	When you create a new Microsoft Mail for PC Networks postoffice using the
	Administrator program, you may get the following error message:
	
	  The network name could not be found.
	
	CAUSE
	=====
	
	You may have selected the route type as Indirect, and in the Via field you have
	entered a network name that does not exist. You must define the external
	postoffice before using it as a hub to the new, indirect postoffice that you are
	creating.
	
	RESOLUTION
	==========
	
	To resolve this problem:
	
	1. Press ESC, then while still in the MS Mail Administrator program, select
	  External Admin (letter E), the select Create (letter C).
	
	2. Type the network name of the hub postoffice.
	
	3. Type the postoffice name of the hub postoffice.
	
	4. Specify the route type, which probably will be "Direct" routing. If this hub
	  postoffice is downstream from another hub, make sure that the other hub is
	  defined. If the other hub is not defined, repeat steps 1 through 4 for the
	  other hub before going on to step 5.
	
	5. Finish defining all the hubs and the new postoffices in the relative order
	  from closest to farthest, starting from this new postoffice.
	
	MORE INFORMATION
	================
	
	To exchange mail with newly defined downstream postoffices, you need to map
	consecutive drive letters, one for every postoffice. Next you need to run the
	External.exe program against all these drive letters. Please refer to the
	"Microsoft Mail for PC Networks Administrators Guide" for additional
	information.
	
	Additional query words:
	
	======================================================================
	Keywords          : kbtshoot kbusage 
	Technology        : kbMailSearch kbZNotKeyword3 kbMailPCN320 kbMailPCN300 kbMailPCN350
	Version           : WINDOWS:3.0,3.2,3.5
	Issue type        : kbprb
	
	=============================================================================
	

{% endraw %}
