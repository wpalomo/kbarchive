---
layout: page
title: "Q173841: How to Perform an Unattended Installation of the NT 4.0 ResKit"
permalink: /kb/173/Q173841/
---

## Q173841: How to Perform an Unattended Installation of the NT 4.0 ResKit

{% raw %}

	Article: Q173841
	Product(s): Microsoft Press
	Version(s): 
	Operating System(s): 
	Keyword(s): kbsetup
	Last Modified: 27-FEB-2001
	
	-------------------------------------------------------------------------------
	The information in this article applies to:
	
	- MSPRESS Microsoft Windows NT Server 4.0 Resource Kit ISBN 1-57231-344-7 
	- MSPRESS Microsoft Windows NT Workstation 4.0 Resource Kit ISBN 1-57231-343-9 
	- MSPRESS Microsoft Windows NT Server 4.0 Resource Kit, Supplement One ISBN 1-57231-559-8 
	- MSPRESS Microsoft Windows NT Server 4.0 Resource Kit, Supplement Two ISBN 1-57231-626-8 
	- MSPRESS Microsoft Windows NT Server 4.0 Resource Kit, Supplement Three 
	-------------------------------------------------------------------------------
	
	SUMMARY
	=======
	
	This article describes how to perform an unattended installation of the
	Microsoft Windows NT 4.0 Resource Kit.
	
	MORE INFORMATION
	================
	
	Original Resource Kits & Supplements One And Two
	------------------------------------------------
	
	To perform an unattended installation of the Resource Kit, execute the following
	MS-DOS command from the root directory of the Resource Kit CD- ROM:
	
	  " _setup /q1 " (without the quotation marks)
	
	This will install the Resource Kit files to the default location without
	presenting any dialog boxes.
	
	Supplement Three
	----------------
	
	These directions are only valid for version 3.03 and later of the Supplement
	Three utilities.
	
	PLEASE NOTE: As of August 31, 2000 the Microsoft Press ResourceLink is no longer
	available. Therefore, the FULLNTRK.EXE, (i.e. Supplement Three of the Windows NT
	Server 4.0 Resource Kit) is no longer available. To perform an unattended
	installation of the Resource Kit, you must have downloaded FULLNTRK.EXE from the
	Microsoft Press ResourceLink prior to August 31, 2000.
	
	To install the Windows NT Resource Kit utilities, execute the following MS-DOS
	command from the directory where you saved FULLNTRK.EXE:
	
	  FULLNTRK.exe /c:"rksetup [path] /q"
	
	where path is the path to the directory where you want to install the Windows NT
	Resource Kit (Default = C:/NTRESKIT).
	
	For full instructions on installing an individual component of the Resource Kit
	utilities without prompting, please see the Readme.doc file in the README.exe
	component of the utilities.
	
	Please note that by performing an unattended installation, you have accepted the
	End User License Agreement included with the Resource Kit.
	
	Additional query words: mspress ms_press press ntreskit ntrk 1-57231-344-7 1-57231-343-9 1-57231-559-8 1-57231-626-8
	
	======================================================================
	Keywords          : kbsetup 
	Technology        : kbMSPressSearch kbZNotKeyword6 kbZNotKeyword2 kbZNotKeyword3
	Version           : :
	Issue type        : kbhowto kbinfo
	
	=============================================================================
	

{% endraw %}
