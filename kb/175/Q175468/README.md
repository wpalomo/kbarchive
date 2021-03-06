---
layout: page
title: "Q175468: Effects of Machine Account Replication on a Domain"
permalink: /kb/175/Q175468/
---

## Q175468: Effects of Machine Account Replication on a Domain

{% raw %}

	Article: Q175468
	Product(s): Microsoft Windows NT
	Version(s): 2000,4.0
	Operating System(s): 
	Keyword(s): kbWinNT400sp4fix
	Last Modified: 09-AUG-2001
	
	-------------------------------------------------------------------------------
	The information in this article applies to:
	
	- Microsoft Windows NT Workstation version 4.0 
	- Microsoft Windows 2000 Professional 
	- Microsoft Windows 2000 Server 
	- Microsoft Windows NT Server version 4.0, Terminal Server Edition 
	-------------------------------------------------------------------------------
	
	IMPORTANT: This article contains information about editing the registry.
	Before you edit the registry, make sure you understand how to restore it
	if a problem occurs. For information on how to do this, view the "Restoring
	the Registry" online Help topic in Regedit.exe or the "Restoring a Registry
	Key" online Help topic in Regedt32.exe.
	
	SYMPTOMS
	========
	
	For each Windows NT Workstation that is a member of a domain, there is a
	discrete communication channel (for example, the secure channel) with a domain
	controller.
	
	The secure channel's password is stored along with the computer account on the
	primary domain controller (PDC), and is replicated to all backup domain
	controllers (BDCs). The password is also in LSA secret $MACHINE.ACC of the
	workstation. Each workstation owns such secret data.
	
	Every seven days, the workstation sends a secure channel password change and the
	computer account password is updated. If the primary domain controller (PDC) is
	running Windows NT 4.0 Service Pack 3 or earlier, the computer account password
	changes are marked as "Announce Immediate" and each time a computer account
	password is modified, a replication takes place immediately. If the PDC is
	running Windows NT 4.0 Service Pack 4 or later, the computer account is
	replicated during the next replication pulse.
	
	A new Netlogon parameter is available as a hotfix so that the 7-day period may be
	extended up to 1,000,000 days.
	
	For Windows 2000, the default computer account password change is 30 days.
	
	MORE INFORMATION
	================
	
	
	For example, if a domain has 1,000 workstations, a computer account password
	change will occur every:
	
	  1 week / 1000 = 7 x 24 x 60 / 1000 minutes = 10 minutes
	
	Using the same example, for Windows 2000, a default computer account will change
	every:
	
	  30 days * 24 hours/day * 60 minutes/hour = 43200 minutes
	  43200 minutes / 1000 workstations = One password change very 43.2
	                                      minutes.
	
	Therefore, a SAM replication takes place every 10 minutes regardless of the
	replication interval defined on the PDC (for example, with the Pulse and
	PulseMaximum registry settings).
	
	
	RESOLUTION
	==========
	
	To resolve this problem, obtain the latest service pack for Windows NT 4.0 or
	Windows NT Server 4.0, Terminal Server Edition. For additional information,
	please see the following article in the Microsoft Knowledge Base:
	
	  Q152734 How to Obtain the Latest Windows NT 4.0 Service Pack
	
	
	WARNING: Using Registry Editor incorrectly can cause serious problems that may
	require you to reinstall Windows. Microsoft cannot guarantee that problems
	resulting from the incorrect use of Registry Editor can be solved. Use Registry
	Editor at your own risk.
	
	For information about how to edit the registry, view the "Changing Keys And
	Values" online Help topic in Registry Editor (Regedit.exe) or the "Add and
	Delete Information in the Registry" and "Edit Registry Data" online Help topics
	in Regedt32.exe. Note that you should back up the registry before you edit it.
	
	There are three workarounds for this issue.
	
	Method One
	----------
	
	The first workaround consists in adding the following registry parameter on all
	Windows NT workstations:
	
	  Key     = HLM\SYSTEM\CurrentControlSet\Services\NetLogon\Parameters
	  Value   = DisablePasswordChange REG_DWORD 1
	  Default = 0
	
	This will prevent workstations from changing passwords. This registry value could
	be added after having joined the domain (and restarted) so that the computer
	account password would have at least been changed once with a random value only
	known by the system.
	
	Method Two
	----------
	
	A second workaround consists of refusing passwords changed at domain controllers
	levels. On all domain controllers, add the following registry value:
	
	  Key     = HLM\SYSTEM\CurrentControlSet\Services\NetLogon\Parameters
	  Value   = RefusePasswordChange REG_DWORD 1
	  Default = 0
	
	For additional information, please see the following article(s) in the Microsoft
	Knowledge Base:
	
	  Q154501 How to Disable Automatic Machine Account Password Changes
	
	Method Three
	------------
	
	A new parameter has been added as a hotfix in order to change the frequency at
	which workstations change secure channel password. It can be added on all
	workstations and also on all BDCs.
	
	  Key     = HLM\SYSTEM\CurrentControlSet\Services\NetLogon\Parameters
	  Value   = MaximumPasswordAge REG_DWORD
	  Default = 7 (entered in decimal)
	  Range   = 1 to 1,000,000 (in days)
	
	The above parameter is specified in days. The default value is seven and the
	minimum value is one.
	
	STATUS
	======
	
	Microsoft has confirmed this to be a problem in Windows NT 4.0 and Windows NT
	Server 4.0, Terminal Server Edition. This problem was first corrected in Windows
	NT 4.0 Service Pack 4.0 and Windows NT Server 4.0, Terminal Server Edition
	Service Pack 4.
	
	
	Additional query words: registry regedit regedt32
	
	======================================================================
	Keywords          : kbWinNT400sp4fix 
	Technology        : kbWinNTsearch kbWinNTWsearch kbWinNTW400 kbWinNTW400search kbWinNT400search kbwin2000Serv kbWinNTSsearch kbWinNTS400search kbwin2000ServSearch kbwin2000Search kbwin2000ProSearch kbwin2000Pro kbNTTermServ400 kbNTTermServSearch
	Version           : :2000,4.0
	Hardware          : x86
	Issue type        : kbbug
	Solution Type     : kbfix
	
	=============================================================================
	

{% endraw %}
