---
layout: page
title: "Q159451: INFO: Installing LPR Ports with Windows NT 4.0 Unattended Setup"
permalink: /kb/159/Q159451/
---

## Q159451: INFO: Installing LPR Ports with Windows NT 4.0 Unattended Setup

{% raw %}

	Article: Q159451
	Product(s): Microsoft Windows NT
	Version(s): winnt:4.0
	Operating System(s): 
	Keyword(s): kbsetup kbOPK kbSBK
	Last Modified: 09-AUG-2001
	
	-------------------------------------------------------------------------------
	The information in this article applies to:
	
	- Microsoft Windows NT Workstation version 4.0 
	- Microsoft Windows NT Server version 4.0 
	-------------------------------------------------------------------------------
	
	SUMMARY
	=======
	
	Although there is an option in the Unattended Setup to install TCP/IP printing,
	there is no option available to actually install the LPR port. To install the
	LPR port in an unattended method, the OEMPreinstall features of unattend must be
	used.
	
	MORE INFORMATION
	================
	
	To install LPR ports on a system, the user must be a member of the administrator
	group. An advantage of installing LPR ports during an unattended setup is that
	the administrator is not required to log on to each workstation to install the
	port. A disadvantage of this procedure is that each different LPR port
	configuration required for the workstations will need a separate installation
	point on the network. Each installation point requires about 80 MB of disk
	space.
	
	To install an LPR port (or ports), perform the following steps:
	
	1. Install Microsoft TCP/IP Printing on a Windows NT Workstation or Server
	  through Control Panel, Network, Services.
	
	2. After restarting the computer, install the LPR ports with the correct IP
	  addresses and desired names through Control Panel, Printer, File, Server
	  Properties.
	
	3. Open Regedit.exe (not Regedt32.exe) and go to the
	
	  HKEY_LOCAL_MACHINE/SYSTEM/CurrentControlSet/Control/Print/Monitors/ 
	  LPR Ports/Ports
	
	  subkey. Under Ports, select the IP address and name of the printer you just
	  installed. Click Registry/Export Registry File from the menu. Save it as
	  Lpr.reg. Do this with each LPR port you have installed, making sure to give
	  each .reg file a unique name. Close REGEDIT.
	
	4. Go to the network installation point for Windows NT. Create a subdirectory
	  under i386 labeled $oem$. Copy Regedit.exe and the .reg files created in step
	  3 to this directory.
	
	5. Create a text file in the $oem$ directory using Edit.com called Cmdlines.txt.
	  Add these lines, including quotation marks:
	
	  [Command] ".\regedit /s .\lpr.reg"
	
	  Add an additional line for each port you are installing with the appropriate
	  .reg file name.
	
	6. Modify the Unattend.txt file using Edit.com to do an OEMPreinstall and
	  automatically install TCP/IP protocol and TCP/IP printing.
	
	7. Run setup from the i386 directory with the following command line:
	
	  winnt /b /s:<sourcefiledir> /u:<unattend file name>
	
	  This procedure will install the LPR ports created in Step 2.
	
	Additional Information
	----------------------
	
	The example provides only part of the answer file needed for a complete Windows
	NT 4.0 unattended installation.
	
	For additional information, please see the following article in the Microsoft
	Knowledge Base:
	
	  ARTICLE-ID: Q155197
	  TITLE : Unattended Setup Parameters for Unattend.txt File
	
	Additional query words: prodnt Unattended Setup Install
	
	======================================================================
	Keywords          : kbsetup kbOPK kbSBK 
	Technology        : kbWinNTsearch kbWinNTWsearch kbWinNTW400 kbWinNTW400search kbWinNT400search kbWinNTSsearch kbWinNTS400search kbWinNTS400
	Version           : winnt:4.0
	Issue type        : kbinfo
	
	=============================================================================
	

{% endraw %}
