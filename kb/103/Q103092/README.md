---
layout: page
title: "Q103092: Using Musical Titles with More than One CD-ROM Drive"
permalink: /kb/103/Q103092/
---

## Q103092: Using Musical Titles with More than One CD-ROM Drive

{% raw %}

	Article: Q103092
	Product(s): Microsoft Home Multimedia Titles
	Version(s): 1.00
	Operating System(s): 
	Keyword(s): 
	Last Modified: 08-NOV-2001
	
	-------------------------------------------------------------------------------
	The information in this article applies to:
	
	- Microsoft Multimedia Beethoven for Windows, versions 1.0, 1.0a 
	- Microsoft Multimedia Mozart for Windows, version 1.0 
	- Microsoft Multimedia Stravinsky for Windows, version 1.0 
	- Microsoft Multimedia Schubert for Windows, version 1.0 
	-------------------------------------------------------------------------------
	
	SUMMARY
	=======
	
	On a computer with more than one CD-ROM drive, the programs listed at the top of
	this article will run in the CD-ROM specified by the MCI CD Audio driver and not
	the drive from which the above applications were installed. If one the above
	application's CD is in a different drive than specified by the MCI CD Audio
	driver, the following error message will occur:
	
	  The wrong disc is in the CD-ROM drive. Please insert the Multimedia [Title]
	  CD.
	
	  Click "Retry" to try again, click "Continue" to proceed without the CD-ROM
	  disc, or click "Exit" to leave Multimedia <application name>.
	
	MORE INFORMATION
	================
	
	On a computer with more than one CD-ROM drive, the above applications can be
	installed from either drive by following the setup instructions included with
	the above applications.
	
	Windows 3.x
	-----------
	
	To use the above applications from a second drive:
	
	1. Run the Drivers section of Windows Control Panel.
	
	2. Select the MCI CD Audio driver from the list of installed drivers.
	
	3. Choose the Setup button. The Redbook CD Audio Configuration dialog box will
	  list the available drives starting from zero.
	
	  For example, if there are two CD-ROM drives present, Setup will display a list
	  of drive 0 and 1. Select the drive from which you want the above applications
	  to play CD audio. Drive 0 is the first drive loaded in MS-DOS by Microsoft
	  CD-ROM Extensions (MSCDEX).
	
	Windows 95
	----------
	
	1. Go to Start, point to Settings, Control Panel.
	
	2. Open the Multimedia icon, click on the CD Music tab.
	
	3. Change the CD-ROM drive letter to the appropriate drive letter. Drive letters
	  will be listed in the drop-down menu.
	
	For more information about loading more than one CD-ROM drive, query on the
	following words in the Microsoft Knowledge Base:
	
	  mscdex and multiple and cdrom
	
	Additional query words: 1991 multi media multimedia multi-media install CogApp/Win Usage compact disc
	
	======================================================================
	Keywords          :  
	Technology        : kbHomeProdSearch kbHomeMMsearch kbZNotKeyword kbMMSchubert kbMMStravinsky kbMMMozart100 kbMMBeethoven100 kbMMBeethoven100a
	Version           : 1.00
	
	=============================================================================
	

{% endraw %}
