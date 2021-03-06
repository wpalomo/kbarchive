---
layout: page
title: "Q100011: Troubleshooting Windows for Workgroups Interoperability"
permalink: /kb/100/Q100011/
---

## Q100011: Troubleshooting Windows for Workgroups Interoperability

{% raw %}

	Article: Q100011
	Product(s): Windows for Workgroups and Windows NT Networking Issues
	Version(s): WinNT:3.5,3.51,4.0;Windows:3.1,3.11
	Operating System(s): 
	Keyword(s): kbinterop
	Last Modified: 19-FEB-2002
	
	-------------------------------------------------------------------------------
	The information in this article applies to:
	
	- Microsoft Windows NT Server version 3.1 
	- Microsoft Windows NT Workstation version 3.1 
	- Microsoft Windows NT Advanced Server, version 3.1 
	- Microsoft Windows NT Workstation versions 3.5, 3.51, 4.0 
	- Microsoft Windows NT Server versions 3.5, 3.51, 4.0 
	- Microsoft Windows for Workgroups versions 3.1, 3.11 
	-------------------------------------------------------------------------------
	
	SUMMARY
	=======
	
	There are several issues that need to be addressed in order to ensure smooth
	interoperability between Windows NT and Windows for Workgroups. When setting up
	your network, note the following three issues:
	
	Browsemaster Conflicts
	----------------------
	
	Browsemaster contentions can occur between Windows for Workgroups workstations
	and Windows NT workstations when a workgroup or domain contains at least one
	machine of each type. You may have difficulty seeing servers in a Windows NT
	network from a Windows for Workgroups workstation if the workstation is a backup
	browsemaster and not registered in the Windows NT network. To work around this
	problem, do the following:
	
	- Make sure there is a guest account enabled in the Windows NT domain.
	
	-or-
	
	- Add the following line to the [network] section of the SYSTEM.INI files in
	  all Windows for Workgroups machines on the network:
	
	  MaintainServerList=no
	
	  This workaround stops all Windows for Workgroups workstations from trying to
	  be browsemasters. If you use this workaround, you need to ensure that at
	  least one Windows NT machine (workstation or server) in the workgroup or
	  domain is running at all times. Until a Windows NT machine is running or a
	  user changes the value of the MaintainServerList variable to "auto" and
	  reboots, no browsing can occur (you receive error 6118).
	
	  -or-
	
	- Log on to the domain or workgroup with a valid account (even a guest account
	  works).
	
	Guest Accounts
	--------------
	
	Guest accounts should remain enabled on domain controllers. Instead of removing
	guest accounts to restrict access to certain services, simply remove any of the
	undesired or all of the guest account rights in User Manager.
	
	User Name Duplication
	---------------------
	
	There should not be user name duplicates on different domains. If a user name is
	duplicated across different domains, there will be inconsistent results when a
	logon is attempted from a Windows for Workgroups workstation on that Windows NT
	network.
	
	Additional query words:
	
	======================================================================
	Keywords          : kbinterop 
	Technology        : kbWinNTsearch kbWinNTWsearch kbWinNTW400 kbWinNTW400search kbWinNT351search kbWinNT350search kbWinNT400search kbWinNTW350 kbWinNTW350search kbWinNTW351search kbWinNTW351 kbWinNTW310 kbWinNTSsearch kbWinNTS400search kbWinNTS400 kbWinNTS351 kbWinNTS350 kbWinNTS310 kbWinNTAdvSerSearch kbWinNTAdvServ310 kbWinNTS351search kbWinNTS350search kbWinNTS310search kbAudDeveloper kbWinNT310Search kbWinNTW310Search kbWFWSearch kbWFW310 kbWFW311
	Version           : WinNT:3.5,3.51,4.0;Windows:3.1,3.11
	
	=============================================================================
	

{% endraw %}
