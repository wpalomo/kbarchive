---
layout: page
title: "Q170950: Intermittent Loss of Connectivity While Using Compaq NetFlex-3"
permalink: /kb/170/Q170950/
---

## Q170950: Intermittent Loss of Connectivity While Using Compaq NetFlex-3

{% raw %}

	Article: Q170950
	Product(s): Microsoft Windows NT
	Version(s): 3.51,4.0
	Operating System(s): 
	Keyword(s): kb3rdparty kbhw kbsetup kbHardware
	Last Modified: 09-AUG-2001
	
	-------------------------------------------------------------------------------
	The information in this article applies to:
	
	- Microsoft Windows NT Workstation versions 3.51, 4.0 
	- Microsoft Windows NT Server versions 3.51, 4.0 
	-------------------------------------------------------------------------------
	
	SYMPTOMS
	========
	
	Network connectivity to a computer using the Compaq NetFlex-3 network card is
	intermittently lost and then restored every few minutes without having to
	restart the system.
	
	Depending on the application, the client or application may have to be restarted
	to restore the connection. If the application has open files on the server, data
	may be lost.
	
	Some applications report the lost connections. Others applications may seem to
	stop responding (hang) for several minutes before continuing.
	
	On a Compaq computer running Windows NT Server version 4.0 Service Pack 3 (SP3)
	and has a Compaq NetFlex3 network adapter and Compaq Support Software Disk (SSD)
	version 2.04 installed, Event Viewer may record the following events:
	
	  Event ID: 4105
	  Source: CpqNF31
	  Description: Network link is down. Please check your cabling. See
	  documentation for more information or contact your service provider.
	
	  Event ID: 4106
	  Source: CpqNF31
	  Description: Network link has been restored.
	
	CAUSE
	=====
	
	The NetFlex-3 10/100 network PCI card is set to 100 MB/full duplex. The
	NetFlex-3 driver provided with Windows NT 4.0 does not support full duplex mode
	at 100 MB.
	
	WORKAROUND
	==========
	
	To work around this problem, do one of the following:
	
	- Obtain the updated driver for the NetFlex-3 PCI card in Softpack SP3206 from
	  Compaq.
	
	  NOTE: SP3942 was the current version as of this writing. Go to:
	
	  http://www.compaq.com/support/files/server/softpaqs/WINNT/NTSSDNTFLX.html
	
	For Windows NT 3.51 systems, get Compaq Softpack SP3302 (SSD 1.23A and NetFlex 3
	driver version 3.06) from the following location:
	
	  http://www.compaq.com/support/files/server/softpaqs/WINNT/NTSSDNTFLX3.html
	
	The third-party contact information included in this article is provided to help
	you find the technical support you need. This contact information is subject to
	change without notice. Microsoft in no way guarantees the accuracy of this
	third-party contact information.
	
	
	-or-
	
	- Set the NetFlex-3 card to half duplex.
	
	  -or-
	
	- Set the NetFlex-3 card to 10 MB.
	
	STATUS
	======
	
	Microsoft has confirmed this to be a problem in Windows NT version 4.0. We are
	researching this problem and will post new information here in the Microsoft
	Knowledge Base as it becomes available.
	
	Additional query words: NetFlex3 NIC connection lost netflx3
	
	======================================================================
	Keywords          : kb3rdparty kbhw kbsetup kbHardware 
	Technology        : kbWinNTsearch kbWinNTWsearch kbWinNTW400 kbWinNTW400search kbWinNT351search kbWinNT400search kbWinNTW351search kbWinNTW351 kbWinNTSsearch kbWinNTS400search kbWinNTS400 kbWinNTS351 kbWinNTS351search
	Version           : :3.51,4.0
	
	=============================================================================
	

{% endraw %}
