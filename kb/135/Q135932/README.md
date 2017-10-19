---
layout: page
title: "Q135932: PC DB: LISTUSER Version 2.1 Displays Unrecognizable Characters"
permalink: kb/135/Q135932/
---

## Q135932: PC DB: LISTUSER Version 2.1 Displays Unrecognizable Characters

	Article: Q135932
	Product(s): Microsoft Mail For PC Networks
	Version(s): WINDOWS:3.2
	Operating System(s): 
	Keyword(s): 
	Last Modified: 29-OCT-1999
	
	-------------------------------------------------------------------------------
	The information in this article applies to:
	
	- Microsoft Mail for PC Networks, version 3.2 
	-------------------------------------------------------------------------------
	
	SYMPTOMS
	========
	
	When you review the contents of the output generated by LISTUSER.EXE version
	2.1, unrecognizable ASCII characters are displayed at the end of file. This
	problem applies to postoffices that have over 475 users defined that includes
	active and deleted users.
	
	
	RESOLUTION
	==========
	
	Update to the latest version of LISTUSER.EXE. For more information about the
	LISTUSER.EXE utility and how to obtain it, please see the following article in
	the Microsoft Knowledge Base:
	
	  Q99419 PC DB: Database Maintenance Utilities (Complete)
	
	
	When you update to the latest version of LISTUSER.EXE, and it does not resolve
	your problem, one or more files on the Microsoft Mail postoffice may be corrupt.
	You can determine corruption of files by checking the file sizes.
	
	If any of the following calculations results in a remainder, the corresponding
	file is corrupt:
	
	NOTE: All three access files should equal the same whole number.
	
	  (size of ACCESS.GLB) / 586
	  (size of ACCESS2.GLB) / 69
	  (size of ACCESS3.GLB) / 512
	
	If corruption exists with any of the three Access files, restore from backup. The
	complete list of files to restore is:
	
	- ACCESS.GLB
	
	- ACCESS2.GLB
	
	- ACCESS3.GLB
	
	- ADMIN.NME
	
	- ADMINSHD.NME
	
	- ADMIN.GRP
	
	- ADMINSHD.GRP
	
	Before you restore the files, check the ADMIN.NME, ADMINSHD.NME, ADMIN.GRP, and
	ADMINSHD.GRP files for corruption. The ADMIN.NME and ADMINSHD.NME files should
	be divisible by 45 and should be the same size and date. The ADMIN.GRP and
	ADMINSHD.GRP files should be the same size and date stamp. To check the
	ADMIN.GRP and ADMINSHD.GRP for corruption, subtract 8 prior to dividing by 8.
	All files should come out to whole numbers.
	
	All the files should be restored from the most recent valid backup. If users have
	been added to the mail system since the last backup, these users will have to be
	redefined after the restoration.
	
	For Mail for PC Networks, MS-DOS workstation users:
	
	  You should make an archive of your mail folders and Inbox prior to restoring
	  the files that can be unarchived upon recreation of the mailbox.
	
	For Mail for Windows users:
	
	  You should make a backup of your MMF file prior to restoring the files that
	  can be re-imported (from the File menu, choose Import Folders) upon
	  recreation of your mailbox.
	
	MORE INFORMATION
	================
	
	For additional information on how to tell if an ACCESS file is corrupt, please
	see the following article in the Microsoft Knowledge Base:
	
	  Q87465 How to Tell if an ACCESS File Is Corrupt
	
	Additional query words: 3.20 garbage
	
	======================================================================
	Keywords          :  
	Technology        : kbMailSearch kbZNotKeyword3 kbMailPCN320
	Version           : WINDOWS:3.2
	
	=============================================================================
	