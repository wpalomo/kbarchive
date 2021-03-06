---
layout: page
title: "Q258469: Cluster Service May Not Start After Restricting IP Ports for RPC"
permalink: /kb/258/Q258469/
---

## Q258469: Cluster Service May Not Start After Restricting IP Ports for RPC

{% raw %}

	Article: Q258469
	Product(s): Microsoft Windows NT
	Version(s): 2000,4.0
	Operating System(s): 
	Keyword(s): kbenv
	Last Modified: 12-AUG-2002
	
	-------------------------------------------------------------------------------
	The information in this article applies to:
	
	- Microsoft Windows NT Server, Enterprise Edition version 4.0 
	- Microsoft Windows 2000 Advanced Server 
	- Microsoft Windows 2000 Datacenter Server 
	-------------------------------------------------------------------------------
	
	IMPORTANT: This article contains information about modifying the registry. Before you 
	modify the registry, make sure to back it up and make sure that you understand how to restore 
	the registry if a problem occurs. For information about how to back up, restore, and edit the 
	registry, click the following article number to view the article in the Microsoft Knowledge Base:
	
	  Q256986 Description of the Microsoft Windows Registry
	
	SYMPTOMS
	========
	
	When you restrict the available Internet Protocol (IP) ports that are available
	for remote procedure call (RPC) dynamic port allocation by adding the DCOM
	Internet key in the HKEY_LOCAL_MACHINE\Software\Microsoft\RPC registry key, the
	Cluster service may not start or you may not be able to remotely connect to the
	Cluster service by using Cluster Administrator. This problem typically occurs if
	the Cluster nodes are seperated by a firewall. When the Cluster service on a
	node starts, it first tries to contact one of the other nodes in the Cluster
	through RPC.
	
	CAUSE
	=====
	
	This behavior can occur when the range of available IP ports that the Cluster
	service uses to initiate communication through RPCs is too small. The Cluster
	service relies heavily on RPC to function properly. If there are not enough
	ports available, the Cluster service cannot communicate.
	
	RESOLUTION
	==========
	
	WARNING: If you use Registry Editor incorrectly, you may cause serious problems
	that may require you to reinstall your operating system. Microsoft cannot
	guarantee that you can solve problems that result from using Registry Editor
	incorrectly. Use Registry Editor at your own risk.
	
	To resolve this behavior, make a minimum of 20 ports available in the defined
	range of available ports. For example, the following registry entry has 20 ports
	available in the defined port range:
	
	  HKEY_LOCAL_MACHINE\Software\Microsoft\RPC
	
	  Ports: REG_MULTI_SZ: 8011-8031
	  PortsInternetAvailable: REG_SZ: Y
	  UseInternetPorts: REG_SZ: Y
	
	MORE INFORMATION
	================
	
	It is best to have 50-100 ports available, because many other services use DCOM
	ports in the dynamic range (1025-65000, everything below 1025 is a pre-defined
	port). Examples of other services that use dynamic ports include Domain Name
	System (DNS), Windows Internet Naming Service (WINS), and Microsoft SQL Server.
	
	REFERENCES
	==========
	
	For additional information, click the article number below to view the article
	in the Microsoft Knowledge Base:
	
	  Q154596 Configuring RPC Dynamic Port Allocation to Work With Firewall
	
	Additional query words: mscs com
	
	======================================================================
	Keywords          : kbenv 
	Technology        : kbWinNTsearch kbWinNT400search kbwin2000AdvServ kbwin2000AdvServSearch kbwin2000DataServ kbwin2000DataServSearch kbWinNTSsearch kbWinNTSEntSearch kbWinNTSEnt400 kbWinNTS400search kbwin2000Search kbWinAdvServSearch kbWinDataServSearch
	Version           : :2000,4.0
	Issue type        : kbprb
	
	=============================================================================
	

{% endraw %}
