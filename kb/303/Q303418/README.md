---
layout: page
title: "Q303418: TRAP Page Fault Error Message with Damaged System Hive"
permalink: /kb/303/Q303418/
---

## Q303418: TRAP Page Fault Error Message with Damaged System Hive

{% raw %}

	Article: Q303418
	Product(s): Microsoft Windows NT
	Version(s): 4.0
	Operating System(s): 
	Keyword(s): kbenv kberrmsg
	Last Modified: 11-JUN-2002
	
	-------------------------------------------------------------------------------
	The information in this article applies to:
	
	- Microsoft Windows NT Server version 4.0 
	- Microsoft Windows NT Workstation version 4.0 
	-------------------------------------------------------------------------------
	
	IMPORTANT: This article contains information about modifying the registry. Before you modify the registry, make sure to back it up and make sure that you understand how to restore the registry if a problem occurs. For information about how to back up, restore, and edit the registry, click the following article number to view the article in the Microsoft Knowledge Base:
	
	  Q256986 Description of the Microsoft Windows Registry
	
	SYMPTOMS
	========
	
	When you start your Windows NT-based computer, you may receive the following
	error message:
	
	  TRAP 0000000E ============ PAGE FAULT =============
	
	  ** at linear address 00000002
	
	  tr=0028 cr0=80000011 cr2=00000002 cr3=00300000
	
	Note that the register values you receive may vary.
	
	CAUSE
	=====
	
	This issue may occur if one of the following conditions is true:
	
	- The System registry hive is damaged.
	
	- The Boot.ini file contains invalid characters or incorrect settings.
	
	RESOLUTION
	==========
	
	To resolve this issue, use one of the following methods.
	
	Method 1
	--------
	
	If your computer can boot off of a CD-ROM, start your computer with the Windows
	NT 4.0 CD-ROM, click Repair, and then click Inspect registry files. If you have
	an updated Emergency Repair Disk (ERD), choose the option to use the ERD for
	repairs. If you do not have an updated ERD, choose the If you do not have the
	Emergency Repair Disk, press ESC option, and then choose to repair the SYSTEM
	registry file.
	
	Method 2
	--------
	
	Replace the System hive in the Config folder with the SYSTEM._ hive from the
	Repair folder. If you are using NTFS, start your computer from a Windows 2000
	CD-ROM or Startup disk into the Recovery Console, and then copy the System hive
	file (SYSTEM) from the %SYSTEMROOT%\Repair folder to the
	%SYSTEMROOT%\System32\Config folder. If you are using the FAT file system, use a
	Microsoft Windows 98 Startup disk to copy the System hive.
	
	IMPORTANT: The %SYSTEMROOT%\Repair folder contains a compressed copy of the
	System hive in the SYSTEM._ file. Expand and then rename the file to SYSTEM
	prior to using it. Note that this System hive is only updated if RDISK is run
	and the Update repair information option is chosen. If this is the case, use
	"Method 3".
	
	Method 3
	--------
	
	If the %SYSTEMROOT%\Repair\System._ file is old and RDISK has not been run to
	update repair information, copy the %SYSTEMROOT%\SYSTEM32\CONFIG\System.Alt file
	(to create a backup), and then rename this file to
	%SYSTEMROOT%\SYSTEM32\CONFIG\System.
	
	Method 4
	--------
	
	If the preceding methods do not resolve the issue, create a parallel installation
	of Windows NT 4.0, and then restore the System hive from a tape backup to the
	original %SYSTEMROOT%\System32\Config folder.
	
	MORE INFORMATION
	================
	
	WARNING: If you use Registry Editor incorrectly, you may cause serious problems
	that may require you to reinstall your operating system. Microsoft cannot
	guarantee that you can solve problems that result from using Registry Editor
	incorrectly. Use Registry Editor at your own risk.
	
	If one of the first three methods in the "Resolution" section of this article
	resolves the issue, you can verify if the original System hive is actually
	damaged. To do so, run Regedt32.exe, and try to open the original System hive by
	using the Load hive command on the Registry menu. If you receive a message that
	the file is not a valid registry file, this confirms that the System hive you
	replaced was damaged.
	
	Additional query words:
	
	======================================================================
	Keywords          : kbenv kberrmsg 
	Technology        : kbWinNTsearch kbWinNTWsearch kbWinNTW400 kbWinNTW400search kbWinNT400search kbWinNTSsearch kbWinNTS400search kbWinNTS400
	Version           : :4.0
	Issue type        : kbprb
	
	=============================================================================
	

{% endraw %}
