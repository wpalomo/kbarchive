---
layout: page
title: "Q276259: SMS: Send Requests Are Created with Blank Routing Instructions"
permalink: /kb/276/Q276259/
---

## Q276259: SMS: Send Requests Are Created with Blank Routing Instructions

{% raw %}

	Article: Q276259
	Product(s): Microsoft Systems Management Server
	Version(s): 2.0,2.0 SP1,2.0 SP2,2.0 SP3
	Operating System(s): 
	Keyword(s): kbsms200 kbsms200bug kbSender kbsms200preSP4fix kbSMSSender
	Last Modified: 06-AUG-2002
	
	-------------------------------------------------------------------------------
	The information in this article applies to:
	
	- Microsoft Systems Management Server versions 2.0, 2.0 SP1, 2.0 SP2, 2.0 SP3 
	-------------------------------------------------------------------------------
	
	SYMPTOMS
	========
	
	In a Systems Management Server (SMS) multiple-level hierarchy, an intermittent
	problem can occur when the Scheduler and Sender components repeatedly try to
	evaluate and send jobs to child sites when the send-request file has no routing
	details. When this problem occurs, a build up of these send requests that do not
	have routing instructions causes the SMS Executive service to consume high CPU
	utilization as the Sender threads loop through the send requests.
	
	CAUSE
	=====
	
	This problem can occur if the Scheduler and Sender components collide when they
	read the same send request. When this occurs, the Scheduler component does not
	update the status of that send request and assumes that a new send request is
	required for the same package and instruction files.
	
	A new request file is created, but the Scheduler component does not update
	destination and final destination site details for the send request because the
	routing-instruction file already exists. The Sender component unsuccessfully
	attempts to send directly to a third-tier site or a lower site for which no
	direct address exists. This causes the request to be retried repeatedly, which
	causes the CPU utilization to increase.
	
	RESOLUTION
	==========
	
	To resolve this problem, obtain the latest service pack for Systems Management
	Server version 2.0. For additional information, click the following article
	number to view the article in the Microsoft Knowledge Base:
	
	  Q288239 SMS: How to Obtain the Latest Systems Management Server 2.0 Service
	  Pack
	
	
	
	WORKAROUND
	==========
	
	To work around this problem, create addresses for all downlevel sites in the SMS
	hierarchy.
	
	When you periodically delete the bad send request files, most of the symptoms
	that are produced by this problem do not occur. To delete the bad send request
	files:
	
	1. Stop the SMS Executive and Site Component Manager services on the site
	  server.
	
	2. Delete the .srq and .srs files from the following folders:
	
	  <Sms_root_folder>\Inboxes\Schedule.box\Requests
	
	  -and-
	
	  <Sms_root_folder>\Inboxes\Schedule.box\Outboxes\Lan
	
	3. Start the SMS Executive and Site Component Manager services on the site
	  server.
	
	The send requests are automatically re-created by the SMS Scheduler component.
	
	STATUS
	======
	
	Microsoft has confirmed that this is a problem in the Microsoft products that
	are listed at the beginning of this article. This problem was first corrected in
	Systems Management Server 2.0 Service Pack 4.
	
	MORE INFORMATION
	================
	
	This problem occurs only on primary site servers that do not have direct
	addresses for downlevel sites, which requires routing site-to-site communication
	through a direct child site.
	
	The following log entries indicate that the problem occurs on a site server.
	
	Sched.log:
	
	  Cannot create the routing instruction.
	
	Sender.log:
	
	  Found send request. ID: 1_C6CT01, Dest Site: T30
	  There is no longer an address to destination site T30
	  Returning send request to pending because address cannot not be found.
	  Site T30 added to list of busy sites because there is no available address.
	
	
	Additional query words:
	
	======================================================================
	Keywords          : kbsms200 kbsms200bug kbSender kbsms200preSP4fix kbSMSSender 
	Technology        : kbSMSSearch kbSMS200 kbSMS200SP1 kbSMS200SP2 kbSMS200SP3
	Version           : :2.0,2.0 SP1,2.0 SP2,2.0 SP3
	Hardware          : x86
	Issue type        : kbbug
	Solution Type     : kbfix
	
	=============================================================================
	

{% endraw %}
