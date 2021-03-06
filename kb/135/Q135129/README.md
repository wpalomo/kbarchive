---
layout: page
title: "Q135129: Removing FailedHardwareChecks Entry In SMS.INI"
permalink: /kb/135/Q135129/
---

## Q135129: Removing FailedHardwareChecks Entry In SMS.INI

{% raw %}

	Article: Q135129
	Product(s): Microsoft Systems Management Server
	Version(s): winnt:1.0,1.1
	Operating System(s): 
	Keyword(s): kbnetwork smshowto
	Last Modified: 10-SEP-1999
	
	-------------------------------------------------------------------------------
	The information in this article applies to:
	
	- Microsoft Systems Management Server versions 1.0, 1.1 
	-------------------------------------------------------------------------------
	
	SUMMARY
	=======
	
	Systems Management Server 1.0 and 1.1 checks the version of Microsoft TCPIP-32
	on your system. The following procedure adds the FailedHardwareChecks entry to
	the SMS.INI file for Systems Management Server 1.0 only. This article describes
	a method of removing the entry for Systems Management Server 1.0 client
	computers.
	
	The information in this article is intended to correct the problem mentioned
	above for clients that were recently upgraded to Systems Management Server 1.1
	to allow Systems Management Server to report the TCP/IP information to the
	Systems Management Server Site Server.
	
	MORE INFORMATION
	================
	
	To properly remove the FailedHardwareChecks entry for the clients' SMS.INI file,
	create and distribute a MSTEST script using the following procedure:
	
	NOTE: The SMS_INI.PCD file can be created using the information listed below.
	MSTest support is supplied by Microsoft Developer Support, not Corporate Network
	Support. MSTest is available as a separate software package and is not included
	with Microsoft System Management Server version 1.0 and 1.1.
	
	1. Copy the SMS_INI.PCD file (located in the package directory) to the
	  SMS\site.srv\maincfg.box\mstest directory on your site server. You may use
	  Package Command Manager (PCM) to locate the PCD file.
	
	2. Create a Workstation Package for the SMS\site.srv\maincfg.box\mstest
	  directory. For Workstation Command Lines, choose New and enter the
	  following:
	
	        Command Name:  MSTEST
	        Command Line:  WBRUN20.EXE sms_ini.pcd
	
	  Automate the above and configure it as a System task.
	
	3. Select the appropriate platforms. For example, Windows 3.1, MS-DOS, or
	  Windows NT. Choose OK.
	
	4. In the Setup Package for Workstations window, choose Close.
	
	5. In Package Properties, choose OK.
	
	6. For the message "SMS will update the pkg. at all sites.", choose OK.
	
	7. Create the Workstation Job and make it mandatory.
	
	The following is a MSTEST 2.0 script file. You can use MSTEST 3.0 provided you
	have all the runtime files for MSTEST 3.0 in the following directory on the site
	server: SMS\site.srv\maincfg.box\mstest
	
	WARNING: Use of the MSTEST script provided in this article is at your own risk.
	Microsoft provides this script "as is" without warranty of any kind.
	
	  ' **********************************************************************
	  '
	  '   This is a test for finding and removing the WolverineInfo
	  '   error in the FailedHardwareChecks line in the SMS.INI file.
	  '
	  ' **********************************************************************
	  DIM infile%, StringVar$, outfile%
	  infile = Freefile
	  outfile=Freefile
	
	  ' **********************************************************************
	  '   Changing Attributes of the SMS.INI file to be read, write, non-hidden.
	  ' **********************************************************************
	
	  Attrib "C:\SMS.INI" as " -h"
	
	  ' *************************************
	  '   Rename files
	  '       SMS.INI to SMS.OLD
	  '  Opening SMS.INI as the output file
	  ' *************************************
	  name "c:\sms.ini" as "C:\SMS.OLD"
	
	  ' ***************************************
	  '  Opening the SMS.OLD file in input and
	  '  opening the SMS.INI out output
	  ' ***************************************
	
	  open "C:\SMS.OLD" for input as #infile
	  open "C:\SMS.INI" for output as #2
	
	  ' ************************************************************************
	  '   Reading and printing the SMS.INI file into Memory, one line at a time.
	  '   If the parameter left 7 bytes is not "FailedH",  then write the string
	  ' ************************************************************************
	
	  While not (EOF (infile))
	         LINE INPUT #infile, StringVar
	             IF (left$ (StringVar,7) <> "FailedH") Then
	                     Print #2, StringVar
	             endif
	  WEND
	
	  ' ***************************************
	  '   Closing the SMS.INI file
	  ' ***************************************
	
	  Close #infile
	
	  ' ***************************************
	  '   Changing Attributes of the SMS.INI file back to original state
	  ' ***************************************
	
	  Attrib "C:\SMS.INI" as " +h"
	  END
	
	STATUS
	======
	
	Microsoft has confirmed this to be a problem in Systems Management Server
	version 1.0. This problem was corrected in Systems Management Server version
	1.1.
	
	Additional query words: prodsms wolverine
	
	======================================================================
	Keywords          : kbnetwork smshowto 
	Technology        : kbSMSSearch kbSMS100 kbSMS110
	Version           : winnt:1.0,1.1
	
	=============================================================================
	

{% endraw %}
