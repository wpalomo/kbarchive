---
layout: page
title: "Q275617: SMS: Inbox Mgr Can't Remove Inboxlck.tok; Stops Software Distrib"
permalink: /kb/275/Q275617/
---

## Q275617: SMS: Inbox Mgr Can't Remove Inboxlck.tok; Stops Software Distrib

{% raw %}

	Article: Q275617
	Product(s): Microsoft Systems Management Server
	Version(s): 2.0 SP2,2.0 SP3
	Operating System(s): 
	Keyword(s): kbenv kbtool kbsms200 kbsms200bug kbsms120 kbsms120bug kbsms200preSP4fix
	Last Modified: 15-AUG-2002
	
	-------------------------------------------------------------------------------
	The information in this article applies to:
	
	- Microsoft Systems Management Server versions 2.0 SP2, 2.0 SP3 
	-------------------------------------------------------------------------------
	
	SYMPTOMS
	========
	
	Before the release of Systems Management Server (SMS) Service Pack 2 (SP2),
	Inbox Manager periodically could not replicate files to the Client Access Points
	(CAPs) because the files were in use by client computers. Because of the added
	functionality in SMS SP2, Inbox Manager can create a lock file on the CAP to
	prevent client access when Inbox Manager updates the Inboxes on the CAP. The
	lock file is created for each Inbox that Inbox Manager replicates to the CAP;
	however, there is a situation where Inbox Manager may not remove the
	Inboxlck.tok file from the Inbox. When this occurs, the processing of offers by
	clients may be prevented. Advertised Program Manager (APM) in SP2 checks for the
	Inboxlck.tok file in the Offerinf.box file on the CAP. If the Inboxlck.tok file
	is present on the CAP, offer processing is prevented.
	
	The presence of the Inboxlck.tok file may also prevent clients from upgrading the
	Software Distribution component to a newer version, from a QFE or Service Pack
	applied to the Site server. When this happens, the status of the Software
	Distribution component on the clients would remain at "Install pending."
	
	CAUSE
	=====
	
	This problem occurs because Inbox Manager attempts to delete the Inboxlck.tok
	file after the Inbox is updated. This deletion may not work if the Inboxlck.tok
	is opened by a client. The clients attempt to open the Inboxlck.tok file to
	verify that it exists.
	
	WORKAROUND
	
	If the symptoms are observed during software distribution on a site running SMS
	2.0 SP2 or SMS 2.0 SP3, please apply the fix discussed in the "Resolution"
	section of this article. If however the symptoms are observed after a QFE
	application or Service Pack upgrade, please use the following workaround to
	clear the lock file:
	
	1. Stop the SMS_INBOX_MANAGER component on the Site Server using the SMS Service
	  Manager.
	
	2. Using Computer Management or Server Manager, close all Open File connections
	  on \CAP_xxx\clicomp.box\SWDist. Repeat this step for all affected CAPs.
	
	3. Start the SMS_INBOX_MANAGER component on the Site Server, and verify that it
	  removes the lock file.
	
	RESOLUTION
	==========
	
	To resolve this problem, obtain the latest service pack for Systems Management
	Server version 2.0. For additional information, click the following article
	number to view the article in the Microsoft Knowledge Base:
	
	  Q288239 SMS: How to Obtain the Latest Systems Management Server 2.0 Service
	  Pack
	
	
	
	
	
	STATUS
	======
	
	Microsoft has confirmed that this is a problem in the Microsoft products that
	are listed at the beginning of this article. This problem was first corrected in
	Systems Management Server 2.0 Service Pack 4.
	
	MORE INFORMATION
	================
	
	When you view the Odpsys32.log file, the client retries the Offerinf.box every
	5,000 milliseconds until the retry count interval is reached after the lock file
	is found. If APM reaches the retry count interval before the Inboxlck.tok file
	is removed, APM stops and reports that the CAP offer Inbox is not accessible;
	therefore, no offers are processed.
	
	The following examples are samples of Odpsys32.log file entries:
	
	  TEST : Attempting to make an accessible remote path. ODP\WNet User Groups
	  9/15/2000 8:55:02 AM 260 (0x104)
	
	  TEST : The accessible remote path is '\\OSHER\CAP_DAN\'. ODP\WNet User Groups
	  9/15/2000 8:55:04 AM 260 (0x104)
	
	  TEST : The remote path is part of site 'CH2' ODP\WNet User Groups 9/15/2000
	  8:55:04 AM 260 (0x104)
	
	  TEST : Attempting to make an accessible remote path. ODP\WNet User Groups
	  9/15/2000 8:55:04 AM 260 (0x104)
	
	  TEST : The accessible remote path is '\\OSHER\CAP_DAN\OfferInf.box\'. ODP\WNet
	  User Groups 9/15/2000 8:55:10 AM 260 (0x104)
	
	  TEST : The remote path has been set to '\\OSHER\CAP_DAN\OfferInf.box\'.
	  ODP\WNet User Groups 9/15/2000 8:55:10 AM 260 (0x104)
	
	  TEST : The remote path is '\\OSHER\CAP_DAN\OfferInf.box\'. ODP\WNet User
	  Groups 9/15/2000 8:55:10 AM 260 (0x104)
	
	  TEST : CAP Offer Inbox is accessible: \\OSHER\CAP_DAN\OfferInf.box\ ODP\WNet
	  User Groups 9/15/2000 8:55:10 AM 260 (0x104)
	
	  TEST : Found Lock File '\\OSHER\CAP_DAN\OfferInf.box\Inboxlck.tok'.Continuing
	  retry attempts at every 5000 ms ODP\WNet User Groups
	
	  TEST : Found Lock File '\\OSHER\CAP_DAN\OfferInf.box\Inboxlck.tok'.Continuing
	  retry attempts at every 5000 ms ODP\WNet User Groups
	
	  TEST : Found Lock File '\\OSHER\CAP_DAN\OfferInf.box\Inboxlck.tok'.Continuing
	  retry attempts at every 5000 ms ODP\WNet User Groups
	
	  TEST : Found Lock File '\\OSHER\CAP_DAN\OfferInf.box\Inboxlck.tok'.Continuing
	  retry attempts at every 5000 ms ODP\WNet User Groups
	
	  TEST : Found Lock File '\\OSHER\CAP_DAN\OfferInf.box\Inboxlck.tok'.Continuing
	  retry attempts at every 5000 ms ODP\WNet User Groups
	
	  TEST : Found Lock File '\\OSHER\CAP_DAN\OfferInf.box\Inboxlck.tok'.Continuing
	  retry attempts at every 5000 ms ODP\WNet User Groups
	
	  TEST : CAP offer Inbox is not accessible or is locked. ODP\WNet User Groups
	  9/15/2000 8:57:54 AM 260 (0x104)
	
	  TEST : Shutdown has not been signaled. ODP\WNet User Groups 9/15/2000 8:57:54
	  AM 260 (0x104)
	
	  TEST : No accessible CAP offer Inbox found. ODP\WNet User Groups 9/15/2000
	  8:57:54 AM 260 (0x104)
	
	  TEST : No CAP offer Inbox is accessible. ODP\WNet User Groups 9/15/2000
	  8:57:54 AM 260 (0x104)
	
	With the hotfix installed, Inbox Manager attempts to delete the Inboxlck.tok ten
	times before proceeding. The Offer Data Providers (ODPs) that are running on the
	client have also been changed. After you install the hotfix, the ODPs scan for
	the presence of the Inboxlck.tok file, instead of opening the file to verify
	that it exists.
	
	
	Additional query words: prodsms inboxlck.tok
	
	======================================================================
	Keywords          : kbenv kbtool kbsms200 kbsms200bug kbsms120 kbsms120bug kbsms200preSP4fix 
	Technology        : kbSMSSearch kbSMS200SP2 kbSMS200SP3
	Version           : :2.0 SP2,2.0 SP3
	Issue type        : kbbug
	Solution Type     : kbfix
	
	=============================================================================
	

{% endraw %}
