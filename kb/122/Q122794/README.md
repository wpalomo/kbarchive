---
layout: page
title: "Q122794: FTP Command ! Does Not Work with TCP/IP-32"
permalink: /kb/122/Q122794/
---

## Q122794: FTP Command ! Does Not Work with TCP/IP-32

{% raw %}

	Article: Q122794
	Product(s): Windows for Workgroups and Windows NT Networking Issues
	Version(s): WINDOWS:3.11; winnt:3.5; :3.11
	Operating System(s): 
	Keyword(s): 
	Last Modified: 08-AUG-2001
	
	-------------------------------------------------------------------------------
	The information in this article applies to:
	
	- Microsoft Windows NT Workstation version 3.5 
	- Microsoft Windows NT Server version 3.5 
	- Microsoft TCP/IP-32 for Windows for Workgroups, version 3.11 
	- Microsoft Windows for Workgroups version 3.11 
	-------------------------------------------------------------------------------
	
	SYMPTOMS
	========
	
	When you run an FTP script file in Windows for Workgroups version 3.11 with
	TCP/IP-32, commands like "! pause" (without the quotation marks) do not work
	properly.
	
	CAUSE
	=====
	
	The "!" FTP command is not supported with TCP/IP-32. The release notes for
	Microsoft TCP/IP-32 states the following:
	
	  "The FTP application which ships with this product does not support the '!'
	  command, which typically invokes a user shell."
	
	WORKAROUND
	==========
	
	To work around this problem, do one of the following:
	
	- Install Windows NT version 3.5
	
	-or-
	
	- Record a macro with the Recorder application using the FTP command and assign
	  it a shortcut key instead of using a script file. In addition, make sure that
	  the playback speed is set to Recorded Speed.
	
	Additional query words: prodtcp32 wfw wfwg prodnt 3.11
	
	======================================================================
	Keywords          :  
	Technology        : kbWinNTsearch kbWinNTWsearch kbWinNT350search kbWinNTW350 kbWinNTW350search kbWinNTSsearch kbWinNTS350 kbWinNTS350search kbAudDeveloper kbTCPIPSearch kbWFWSearch kbZNotKeyword3 kbWFW311 kbTCPIP311
	Version           : WINDOWS:3.11; winnt:3.5; :3.11
	
	=============================================================================
	

{% endraw %}
