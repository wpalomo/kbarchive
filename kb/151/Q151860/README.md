---
layout: page
title: "Q151860: STOP 0x0A While Writing to the Middle of a Cached File"
permalink: /kb/151/Q151860/
---

## Q151860: STOP 0x0A While Writing to the Middle of a Cached File

{% raw %}

	Article: Q151860
	Product(s): Microsoft Windows NT
	Version(s): winnt:4.0
	Operating System(s): 
	Keyword(s): kberrmsg kbWinNT400sp4fix
	Last Modified: 08-AUG-2001
	
	-------------------------------------------------------------------------------
	The information in this article applies to:
	
	- Microsoft Windows NT Workstation version 4.0 
	- Microsoft Windows NT Server version 4.0 
	- Microsoft Windows NT Server version 4.0, Terminal Server Edition 
	-------------------------------------------------------------------------------
	
	
	SYMPTOMS
	========
	
	Under heavy file I/O a computer running Windows NT may blue screen with The
	following Stop error in CcFastCopyWrite.
	
	  Stop 0x0000000A (0xC8663000, 0x00000002, 0x00000001, 0x80101A6C)
	
	CAUSE
	=====
	
	When an application writes data to the middle of a file, Cache Manager does not
	check this case properly against a write beyond the end of the file. For this to
	happen both the end of the file and the current write location need to be in the
	cache plus there needs to be a special layout of cache memory.
	
	
	RESOLUTION
	==========
	
	To resolve this problem, obtain the latest service pack for Windows NT 4.0 or
	Windows NT Server 4.0, Terminal Server Edition. For additional information,
	please see the following article in the Microsoft Knowledge Base:
	
	  Q152734 How to Obtain the Latest Windows NT 4.0 Service Pack
	
	
	STATUS
	======
	
	Microsoft has confirmed this to be a problem in Windows NT 4.0 and Windows NT
	Server 4.0, Terminal Server Edition. This problem was first corrected in Windows
	NT 4.0 Service Pack 4.0 and Windows NT Server 4.0, Terminal Server Edition
	Service Pack 4.
	
	
	
	Additional query words: 4.00 prodnt 0xa 0x0a
	
	======================================================================
	Keywords          : kberrmsg kbWinNT400sp4fix 
	Technology        : kbWinNTsearch kbWinNTWsearch kbWinNTW400 kbWinNTW400search kbWinNT400search kbWinNTSsearch kbWinNTS400search kbWinNTS400 kbNTTermServ400 kbNTTermServSearch
	Version           : winnt:4.0
	Issue type        : kbbug
	Solution Type     : kbfix
	
	=============================================================================
	

{% endraw %}
