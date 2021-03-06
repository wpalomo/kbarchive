---
layout: page
title: "Q162686: Problems with Incorrect #9FX Reality 332 Video Card"
permalink: /kb/162/Q162686/
---

## Q162686: Problems with Incorrect #9FX Reality 332 Video Card

{% raw %}

	Article: Q162686
	Product(s): Microsoft Windows NT
	Version(s): WINNT:3.51
	Operating System(s): 
	Keyword(s): kbdisplay kbhw kbHardware
	Last Modified: 08-AUG-2001
	
	-------------------------------------------------------------------------------
	The information in this article applies to:
	
	- Microsoft Windows NT Workstation version 3.51 
	- Microsoft Windows NT Server version 3.51 
	-------------------------------------------------------------------------------
	
	SYMPTOMS
	========
	
	After applying any service pack to a computer outfitted with a #9FX Reality 332
	video card that requires a third-party driver, the computer restarts to a black
	screen and stops responding. This will also happen if an Emergency Repair Disk
	(ERD) is run against the computer for repair purposes. Starting the computer to
	VGA mode allows the computer to start; however, using the Last Known Good
	Configuration will not.
	
	Some Dell Dimensions XPS Pro 200 computers come with this video card, and exhibit
	this problem.
	
	The problem occurs if both of the following conditions are true:
	
	- Windows NT 3.51 was initially installed using the third-party video driver.
	
	- The video card is set for at least 1280 X 768 resolution and 256 colors.
	
	CAUSE
	=====
	
	The #9FX Reality 332 video card is based on the S3 chipset and uses a set of
	drivers with the same name as the standard S3 compatible video card; S3.sys and
	S3.dll. However, the drivers that come with Windows NT 3.51 and its service
	packs are not 100 percent compatible with this video adapter. When applying the
	service pack or running an ERD, these files are replaced by the standard S3
	drivers, which cause the computer to fail. When Windows NT 3.51 is preinstalled
	by the manufacturer, the standard S3 driver is not used. The Last Known Good
	startup option does not work because the last successful restart included
	drivers with the same name as the failed attempt.
	
	RESOLUTION
	==========
	
	To resolve this problem, perform the following steps:
	
	1. Obtain the correct drivers from Number Nine Visual Technology. You can obtain
	  these drivers by connecting to http://www.nine.com/drivers.html and
	  downloading the 325n3009.exe file.
	
	2. Start the computer to VGA mode.
	
	3. Install the newer drivers.
	
	MORE INFORMATION
	================
	
	The third-party products discussed here are manufactured by vendors independent
	of Microsoft; we make no warranty, implied or otherwise, regarding these
	products' performance or reliability.
	
	Additional query words: prodnt hang hung freeze frozen chip set
	======================================================================
	Keywords          : kbdisplay kbhw kbHardware 
	Technology        : kbWinNTsearch kbWinNTWsearch kbWinNT351search kbWinNTW351search kbWinNTW351 kbWinNTSsearch kbWinNTS351 kbWinNTS351search
	Version           : WINNT:3.51
	Issue type        : kbprb
	
	=============================================================================
	

{% endraw %}
