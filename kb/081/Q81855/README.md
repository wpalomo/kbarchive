---
layout: page
title: "Q81855: Windows Problems on AST Premium/286"
permalink: /kb/081/Q81855/
---

## Q81855: Windows Problems on AST Premium/286

{% raw %}

	Article: Q81855
	Product(s): Microsoft Windows 95.x Retail Product
	Version(s): WINDOWS:3.0,3.0a,3.1,3.11
	Operating System(s): 
	Keyword(s): 
	Last Modified: 05-OCT-1999
	
	-------------------------------------------------------------------------------
	The information in this article applies to:
	
	- Microsoft Windows versions 3.0, 3.0a, 3.1, 3.11 
	-------------------------------------------------------------------------------
	
	SUMMARY
	=======
	
	Certain hardware revisions of the AST Premium/286 computer are required for
	proper operation under Microsoft Windows in standard mode, and under enhanced
	mode on machines using the FAST BOARD 80386 upgrade. If a system does not have
	the proper revisions, the following problems may result.
	
	Standard Mode
	-------------
	
	- Keyboard lockup, erratic or slow keyboard input, and system locks when key is
	  pressed
	
	- Unrecoverable Application Errors (UAEs) in 3.0; general protection (GP) fault
	  error in 3.1
	
	- Network read/write errors
	
	- Video problems
	
	Enhanced Mode
	-------------
	
	- Problems using FAST BOARD 80386 upgrade
	
	This article contains detailed technical information on the hardware revisions
	required. This information is intended for persons familiar with microcomputer
	repair and maintenance. If you do not feel comfortable partially dismantling
	your computer, refer this information to a qualified service person. These
	problems are not specific to Windows, but occur in other protected-mode
	applications such as Lotus 1-2-3 version 3.x.
	
	MORE INFORMATION
	================
	
	KEYBOARD PROBLEMS OR UAEs/GP FAULTS IN STANDARD MODE
	----------------------------------------------------
	
	To prevent these problems, the following chip revisions are required:
	
	System Board ROM BIOS:
	----------------------
	
	AST BIOS - version 2.0
	AST Phoenix BIOS - version 3.03
	
	These chips are located at system board locations U10 (odd) and U12 (even). The
	AST part numbers are 107000-656 (odd) and 107000-657 (even). They are also
	included in the comprehensive AST Premium/286 BIOS Upgrade Kit (see below).
	
	System Board Keyboard Controller
	--------------------------------
	
	The Keyboard controller chip (located at system board location U50) should have
	AST part number 107000-669 on the chip label. This keyboard controller is also
	included in the AST Premium/286 BIOS Upgrade Kit described below.
	
	Keyboard ROM BIOS
	-----------------
	
	The Keyboard ROM BIOS (located on the keyboard itself) should be AST part number
	107210-008. The proper version of this chip is included in the AST BIOS upgrade
	kit (see below).
	
	AST Premium/286 Comprehensive BIOS Upgrade Kit
	----------------------------------------------
	
	All of the chip updates specified above are included in the AST BIOS upgrade kit,
	which is AST part number 500529-001 (101-key keyboards) or 500529-002 (102-key
	keyboards).
	
	NETWORK READ ERRORS IN STANDARD MODE
	------------------------------------
	
	Some Premium/286 systems will exhibit network read/write errors, especially
	during large data transfers (2MB-6MB in size). Errors displayed by Windows may
	include the following:
	
	  Cannot read from device NETWORK
	
	  Cannot write to device NETWORK
	
	  Network Error on drive x:
	
	This problem occurs even at the MS-DOS level outside of Windows, but will happen
	more often under Windows because of the large data transfers frequently
	requested by the environment.
	
	These symptoms are caused by a problem found in a particular release of the
	interrupt controller chips used on some Premium/286 motherboards. The interrupt
	controllers are soldered to the motherboard at locations U25 and U26. This
	affects Premium/286 motherboard part numbers 202143-004 and 202322-001.
	
	The chips in question are Toshiba 82C59 Interrupt Controllers, release A. They
	may be identified by the large letter "T" and the word "JAPAN", followed by an
	"xxxxEAI" code (for example, "8822EAI"). If an EAI code is present, these chips
	must be replaced by an authorized AST service center.
	
	NOTE: If an AST Premium/286 is used as the server, it must also be inspected for
	the proper interrupt controller revision.
	
	If any of the following network cards are used in a Premium/286, there may be
	some hardware compatibility issues. Contact AST Technical Support for further
	information.
	
	  Novell NE1000
	  Western Digital Ethernet
	  Gateway Ethernet
	  IBM Token Ring
	
	VIDEO PROBLEMS IN STANDARD MODE
	-------------------------------
	
	If an AST VGA adapter is used, a VGA card BIOS upgrade may be required for proper
	operation. Everex EV-678 display cards may cause compatibility problems. Contact
	AST Technical Support for further information.
	
	ENHANCED MODE PROBLEMS USING FAST BOARD 80386 UPGRADE
	-----------------------------------------------------
	
	AST Premium/286 machines using this 386 upgrade require AST BIOS version 2.0 or
	later to run Windows in enhanced mode. Machines with the earlier AST BIOS or AST
	Phoenix BIOS may not be able to run Windows in 386-enhanced mode. The BIOS
	upgrades are AST part numbers 107000-656 (odd) and 107000-657 (even), and are
	included with the AST BIOS Upgrade Kit described above.
	
	The products mentioned here are available through AST Parts.
	
	The products included here are manufactured by a vendor independent of Microsoft.
	We make no warranty, implied or otherwise, regarding the performance or
	reliability of these products.
	
	Additional query words: 3.00 3.0 3.00a 3.0a 3.10 3.1 3.11
	
	======================================================================
	Keywords          :  
	Technology        : kbWin3xSearch kbZNotKeyword3 kbWin300 kbWin300a kbWin310 kbWin311
	Version           : WINDOWS:3.0,3.0a,3.1,3.11
	
	=============================================================================
	

{% endraw %}
