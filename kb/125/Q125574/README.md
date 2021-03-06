---
layout: page
title: "Q125574: Excessive Server Manager File Lock Counts"
permalink: /kb/125/Q125574/
---

## Q125574: Excessive Server Manager File Lock Counts

{% raw %}

	Article: Q125574
	Product(s): Microsoft Windows NT
	Version(s): winnt:3.5
	Operating System(s): 
	Keyword(s): 
	Last Modified: 08-AUG-2001
	
	-------------------------------------------------------------------------------
	The information in this article applies to:
	
	- Microsoft Windows NT Workstation version 3.5 
	- Microsoft Windows NT Server version 3.5 
	-------------------------------------------------------------------------------
	
	SYMPTOMS
	========
	
	In Server Manager, or Control Panel Server, the value for File Locks is very
	large (over four billion).
	
	CAUSE
	=====
	
	The Server service does not increment the File Locks count after successfully
	locking a byte range in response to a Lock&Read Server Message Block (SMB)
	(typically issued by a LAN Manager version 2.2c client (either MS-DOS- or OS/2)-
	based). However, the Server service does correctly decrement the File Lock count
	in response to a later Lock&X SMB which unlocks the same byte range. As a
	result, the zero File Lock count is decremented to 0xFFFFFFFF. Because is an
	unsigned value, it is displayed as 4294967295.
	
	STATUS
	======
	
	Microsoft has confirmed this to be a problem in Windows NT version 3.5. A fix to
	this problem is in development, but has not been regression-tested and may be
	destabilizing in production environments. Microsoft does not recommend
	implementing this fix at this time. Contact Microsoft Product Support Services
	for more information on the availability of this fix. This is a hotfix, and
	distribution requires manager approval. To receive the hotfix, customers must be
	encountering the bug as described above. You must track the customers you send
	this to and supply them with the next Service Pack when it becomes available. To
	obtain the new file, contact the Escalation Team. The new file is SRV.SYS on
	http://hotfix
	
	Additional query words: 3.50 prodnt 4,294,967,295 Usage Summary Open Resources dialog box In Use
	
	======================================================================
	Keywords          :  
	Technology        : kbWinNTsearch kbWinNTWsearch kbWinNT350search kbWinNTW350 kbWinNTW350search kbWinNTSsearch kbWinNTS350 kbWinNTS350search
	Version           : winnt:3.5
	
	=============================================================================
	

{% endraw %}
