---
layout: page
title: "Q125323: Err Msg: Cannot Find NETAPI.DLL; Cannot Find PMSPL.DLL"
permalink: /kb/125/Q125323/
---

## Q125323: Err Msg: Cannot Find NETAPI.DLL; Cannot Find PMSPL.DLL

{% raw %}

	Article: Q125323
	Product(s): Windows for Workgroups and Windows NT Networking Issues
	Version(s): MS-DOS:3.0; WINDOWS:3.1,3.11; winnt:3.5
	Operating System(s): 
	Keyword(s): 
	Last Modified: 08-AUG-2001
	
	-------------------------------------------------------------------------------
	The information in this article applies to:
	
	- Microsoft Windows NT Server version 3.5 
	- Microsoft Network Client for MS-DOS version 3.0 
	- Microsoft Windows versions 3.1, 3.11 
	-------------------------------------------------------------------------------
	
	SYMPTOMS
	========
	
	When you start Windows with Network Client version 3.0 for MS-DOS, the following
	error message appears:
	
	  File Error
	  Cannot find NETAPI.DLL
	
	When you choose Close, the following appears:
	
	  File Error
	  Cannot find PMSPL.DLL
	
	CAUSE
	=====
	
	This problem occurs in one of the following situations:
	
	1. If LAN Manager version 2.0 Enhanced driver (LANMAN.DRV) is installed as the
	  network driver in Windows version 3.1 Setup.
	
	2. If LAN Manager version 2.1 Enhanced driver (LANMAN21.DRV) is installed as the
	  network driver in Windows version 3.1 Setup and the network is currently
	  running. If the network is not running when Windows starts, the network
	  driver for "Microsoft Network (or 100% compatible)" (MSNET.DRV) is installed.
	  However, Windows version 3.1 Setup displays that LAN Manager version 2.1
	  Enhanced driver is installed.
	
	RESOLUTION
	==========
	
	To correct this problem:
	
	1. Start Windows Setup (either from the Main group in Windows or from the
	  WINDOWS directory in MS-DOS).
	
	2. Change the network to "Microsoft Network (or 100% compatible)."
	
	3. Restart Windows.
	
	Additional query words: prodlm prodnt 3.11 3.10 win3x
	
	======================================================================
	Keywords          :  
	Technology        : kbWinNTsearch kbWinNT350search kbWinNTSsearch kbWinNTS350 kbWinNTS350search kbAudDeveloper kbWin3xSearch kbZNotKeyword kbZNotKeyword3 kbNetworkClientSearch kbWin310 kbWin311 kbNetworkClient300DOS
	Version           : MS-DOS:3.0; WINDOWS:3.1,3.11; winnt:3.5
	
	=============================================================================
	

{% endraw %}
