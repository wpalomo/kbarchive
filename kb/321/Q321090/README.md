---
layout: page
title: "Q321090: SMS: Only Principal Site Creates an Advertisement for Client"
permalink: /kb/321/Q321090/
---

## Q321090: SMS: Only Principal Site Creates an Advertisement for Client

{% raw %}

	Article: Q321090
	Product(s): Microsoft Systems Management Server
	Version(s): 2.0
	Operating System(s): 
	Keyword(s): kbsms200 kbsms200bug
	Last Modified: 17-JUL-2002
	
	-------------------------------------------------------------------------------
	The information in this article applies to:
	
	- Microsoft Systems Management Server version 2.0 
	-------------------------------------------------------------------------------
	
	SYMPTOMS
	========
	
	If you assign a Systems Management Server (SMS) client computer to multiple
	sites, issues may occur if sites other than the principal site try to target the
	client for a software distribution job. The principal site is the site that
	appears at the top of the list in the Systems Management tool in Control Panel.
	Additionally, the following messages may be logged in Offermgr.log on any other
	site server that creates an advertisement for the client:
	
	  Offermgr.log:
	  Updated offer VA120001 in the offer info inbox.
	  Sent offer VA120001 to all child sites.
	  Package VA100002 is on at least one distribution point, it's ready to be
	  offered
	  CCollectionSource_SQL::CreatePrivateCopy - Inserted table
	  _CPY_OfferManagerTemp_16 with 4 rows.
	  Did not find previously saved membership list for collection VA100010, enum
	  the membership list directly.
	  Found 4 members for collection VA100010
	  Resource IDS02205 is not from the current site, it won't get any offers.
	  Resource IDS22081 is not from the current site, it won't get any offers.
	  Resource IDSRMS2 is not from the current site, it won't get any offers.
	  Resource IDSRMS1 is not from the current site, it won't get any offers.
	  Flushed the offer info cache data to disk.Successfully created private
	  membership list for collection VA100010
	
	In this message, the package identifier (ID) is VA100002, the advertisement ID is
	VA120001, and the collection that is targeted in the advertisement is VA100010.
	
	CAUSE
	=====
	
	When the Offer Manager component creates or updates the advertisement for a
	client, it checks the assignment state of each client that is targeted in the
	advertisement. If the client is assigned to multiple sites, only the principal
	site successfully creates an advertisement. All other sites that the client is
	assigned to generate the message that is described in the "Symptoms" section of
	this article in Offermgr.log. This message is not an error message; it is an
	informational message.
	
	WORKAROUND
	==========
	
	A workaround does not exist for this issue. The client only receives software
	distribution jobs from the principal site to which it is assigned.
	
	STATUS
	======
	
	Microsoft has confirmed this to be a problem in Systems Management Server
	version 2.0.
	
	MORE INFORMATION
	================
	
	The following information is from Chapter 12 of the SMS Administrators Guide:
	
	  SMS 2.0 allows clients to belong to more than one site (for more information,
	  see "Site Assignment" in Chapter 9, "Discovering Resources and Installing
	  Clients"). If a client belongs to more than one site, the client receives
	  advertisements from each of the sites. When a client runs an advertised
	  program, it connects only to the CAP and distribution point of the site
	  advertising the program. Status messages for that advertisement are sent only
	  to the advertising site.
	
	The client receive advertisements from multiple sites, but only the principal
	site successfully creates an advertisement for the client. To create an
	advertisement for a client that is in multiple sites, you must change the site
	order in the Systems Management tool in Control Panel so that the site that you
	want to create the advertisement is listed at the top of the list.
	
	
	Additional query words: prodsms multiple advertisement offermgr error
	
	======================================================================
	Keywords          : kbsms200 kbsms200bug 
	Technology        : kbSMSSearch kbSMS200
	Version           : :2.0
	Issue type        : kbbug
	
	=============================================================================
	

{% endraw %}
