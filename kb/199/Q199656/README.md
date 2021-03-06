---
layout: page
title: "Q199656: XIMS: How to Stop Spam Mail Messages from Using IMS Relay Agent"
permalink: /kb/199/Q199656/
---

## Q199656: XIMS: How to Stop Spam Mail Messages from Using IMS Relay Agent

{% raw %}

	Article: Q199656
	Product(s): Microsoft Exchange
	Version(s): 4.0,5.0,5.5
	Operating System(s): 
	Keyword(s): 
	Last Modified: 16-AUG-2001
	
	-------------------------------------------------------------------------------
	The information in this article applies to:
	
	- Microsoft Exchange Server, versions 5.5, 4.0, 5.0 
	-------------------------------------------------------------------------------
	
	SUMMARY
	=======
	
	The Microsoft Exchange Server Internet Mail Service may be configured as a
	publicly accessible relay mail. In this configuration, the outside users can use
	the relay Internet Mail Service as an agent for unsolicited commercial e-mail
	(UCE or spam), flooding others with many copies of the same message. Spam is an
	attempt to force messages on people who would not otherwise choose to receive
	them. This article illustrates two possible workarounds for this problem.
	
	MORE INFORMATION
	================
	
	Scenario 1
	----------
	
	This workaround requires another Internet Mail Service to be installed and
	dedicated for outbound mail. Essentially, it queues all non-internal mail to a
	dead IP address, which, hopefully, would allow the administrators to track where
	these Internet messages are coming from.
	
	1. Open the properties for the Internet Mail Service on the server accepting
	  inbound mail.
	
	2. On the Connections tab for the server, select the option to forward all
	  messages to the host, and enter the IP address of a valid computer on the
	  network that will not accept an SMTP connection (for example, 2.2.2.2, if
	  that computer is a non-SMTP host).
	
	3. Click the "Specify by email domains" button.
	
	4. Add a domain of "sample.microsoft.com," and forward to the IP address of
	  another Exchange Server configured for outbound SMTP message delivery.
	
	5. Repeat steps 2 through 4 for all other inbound domains.
	
	6. Stop and restart the Internet Mail Service.
	
	Scenario 2
	----------
	
	This workaround restricts the Internet Mail Service from routing mail to your
	hosts' IP address. This applies only if you have Exchange 5.5. For additional
	information, click the article number below to view the article in the Microsoft
	Knowledge Base:
	
	  Q196626 Restricting Routing in the Internet Mail Service
	
	1. Install Service Pack 1 or later for Exchange Server 5.5.
	
	2. Select the Connections applet from the Exchange Server Administrator program,
	  and go to the Routing property page of the Internet Mail Service.
	
	3. Select "Reroute incoming SMTP mail" (required for POP3/IMAP4 support), and
	  then select Routing Restrictions.
	
	4. In "Specify the hosts and clients that can route mail when the following
	  conditions are met" dialog box, choose your hosting option, and then click
	  Add to specify restricted IP addresses.
	
	Additional query words: Spam UCE IMS relay restrictions restrict
	
	======================================================================
	Keywords          :  
	Technology        : kbExchangeSearch kbExchange500 kbExchange550 kbExchange400 kbZNotKeyword2
	Version           : :4.0,5.0,5.5
	Issue type        : kbhowto
	
	=============================================================================
	

{% endraw %}
