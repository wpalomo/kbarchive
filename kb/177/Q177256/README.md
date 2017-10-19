---
layout: page
title: "Q177256: No Validation When Logging on Locally to a WINS Server"
permalink: kb/177/Q177256/
---

## Q177256: No Validation When Logging on Locally to a WINS Server

	Article: Q177256
	Product(s): Microsoft Windows NT
	Version(s): WinNT:3.5,3.51,4.0
	Operating System(s): 
	Keyword(s): kberrmsg kbnetwork
	Last Modified: 10-AUG-2001
	
	-------------------------------------------------------------------------------
	The information in this article applies to:
	
	- Microsoft Windows NT Server versions 3.5, 3.51, 4.0 
	-------------------------------------------------------------------------------
	
	SYMPTOMS
	========
	
	When you attempt to log on locally to your Windows NT Windows Internet Name
	Service (WINS) server, you may receive the following error:
	
	  No domain controller was available to validate your logon.
	
	CAUSE
	=====
	
	The Netlogon service may have started before the WINS service completely
	started.
	
	RESOLUTION
	==========
	
	After you start your WINS server, give the WINS service ample time to start
	before logging on locally.
	
	NOTE: The amount of time will vary depending upon the hardware and software
	configuration of your WINS server.
	
	MORE INFORMATION
	================
	
	A correctly configured WINS server should be set to register and resolve NetBIOS
	names only with itself (as both primary and secondary server). The local WINS
	configuration information can be viewed using either of the following:
	
	- The WINS tab of the TCP/IP Protocol properties within the Network applet of
	  Control Panel
	
	  -or-
	
	- Ipconfig.exe /all from a command prompt.
	
	Although this is the correct configuration for a WINS server, it is possible for
	the Netlogon service to start before the WINS service. As a result, the Netlogon
	service will not be able to resolve the DOMAIN[1Ch] entry required for domain
	logon validation.
	
	For more information regarding WINS server configuration, see the following
	article in the Microsoft Knowledge Base:
	
	ARTICLE-ID: Q150520
	TITLE : WINS Server Sporadically Loses Name Resolution
	
	ARTICLE-ID: Q150737
	TITLE : Setting Primary and Secondary WINS Server Options
	======================================================================
	Keywords          : kberrmsg kbnetwork 
	Technology        : kbWinNTsearch kbWinNT351search kbWinNT350search kbWinNT400search kbWinNTSsearch kbWinNTS400search kbWinNTS400 kbWinNTS351 kbWinNTS350 kbWinNTS351search kbWinNTS350search
	Version           : WinNT:3.5,3.51,4.0
	Issue type        : kbprb
	
	=============================================================================
	