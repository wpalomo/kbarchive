---
layout: page
title: "Q157576: INFO: How to Troubleshoot the Sysdiff Tool in Windows NT"
permalink: kb/157/Q157576/
---

## Q157576: INFO: How to Troubleshoot the Sysdiff Tool in Windows NT

	Article: Q157576
	Product(s): Microsoft Windows NT
	Version(s): 4.0
	Operating System(s): 
	Keyword(s): kbsetup kbtool kbtshoot kbOPK kbSBKkbfaq
	Last Modified: 15-FEB-2002
	
	-------------------------------------------------------------------------------
	The information in this article applies to:
	
	- Microsoft Windows NT Server version 4.0 
	- Microsoft Windows NT Workstation version 4.0 
	-------------------------------------------------------------------------------
	
	
	SUMMARY
	=======
	
	This article describes how to troubleshoot the Sysdiff tool included in Windows
	NT 4.0.
	
	An updated version of the Sysdiff tool that resolves some common Sysdiff issues
	is available for download from the following location on the Microsoft FTP
	site:
	
	  ftp://ftp.microsoft.com/bussys/winnt/winnt-public/fixes/usa/NT40/utilities/Sysdiff-fix
	
	MORE INFORMATION
	================
	
	General Error Messages
	----------------------
	
	When you troubleshoot error messages generated by Sysdiff, you can obtain
	descriptions of the error messages by using the Net Helpmsg command. For
	example, if you receive a Sysdiff Error 32, you can obtain more information
	about the error message by typing the following command at a command prompt in
	Windows NT:
	
	  "net helpmsg 32" (without the quotation marks)
	
	In this example, you receive the following response:
	
	  The process cannot access the file because it is being used by another
	  process.
	
	Computer Stops Responding (Hangs) When You Use Sysdiff /Apply
	-------------------------------------------------------------
	
	This behavior can occur if one or more of the following conditions exist:
	
	- The target computer has low disk space.
	
	- There is a problem with one of the programs contained in the image file.
	
	- You use the Sysdiff /inf command to integrate the image file in Windows NT
	  setup, and the image file or the Windows NT source files in the $OEM$ folder
	  on the server are corrupt.
	
	To resolve this problem, use the appropriate method below:
	
	- Free some disk space, and then reapply the difference file.
	
	- Try smaller images or image the programs one at a time until you determine
	  which program is causing the problem.
	
	- To verify that your image file is valid, follow these steps:
	
	  1. Create the image file on the local computer, and then copy it to the
	     server.
	
	  2. Manually apply the difference file. To do so, type the following command
	     at a command prompt in Windows NT:
	
	  Sysdiff /apply /m <image file>
	
	Error 112
	---------
	
	When you use the Sysdiff /diff command, a difference file containing the
	differences between a your previous configuration and your current configuration
	is created. If there is insufficient disk space to generate this difference
	file, error 112 occurs. Error 112 is a standard Win32 error code and represents
	an out of disk space error.
	
	NOTE: If many changes are made to your computer's configuration after the
	creation of the initial Sysdiff image, your difference file can become very
	large. According to chapter 2 of the Windows NT Workstation Resource Guide:
	
	  The information in the difference file includes all the binary files for the
	  applications, as well as the initialization file settings and registry
	  settings for the applications.
	
	To resolve this issue, follow these steps:
	
	- If you have low disk space on your hard disk, free additional disk space, and
	  then use the Sysdiff /diff command again.
	
	- Use the /log switch to trace the activities of Sysdiff during the /diff
	  operation.
	
	Error Message: Diff Failed (error=32)
	-------------------------------------
	
	This error message indicates that a file the Sysdiff tool is trying to open is
	currently in use.
	
	To resolve this issue, use the appropriate method below:
	
	- Close all programs, restart the computer, and then start the Sysdiff tool
	  without starting any other programs.
	
	- Use the [ExcludeFiles] section in the Sysdiff.inf file.
	
	- Use the Sysdiff.inf file from the Support\Deptools\<platform> folder on
	  the Windows NT CD-ROM.
	
	Error Message: System Error 5
	-----------------------------
	
	If you use the Sysdiff tool to install programs that add system services,
	hardware drivers, or other drivers in Windows NT, the Sysdiff tool may attempt
	to access restricted registry keys. When this occurs, you may receive a System
	Error 5 error message, which is equivalent to "access denied." You should not
	use the Sysdiff tool to install programs that need to make these types of
	modifications.
	
	To resolve this issue, follow these steps:
	
	1. Identify which program installed the system service, hardware driver, or
	  other driver.
	
	2. Create a new difference file without the program identified in step 1.
	
	3. Apply the new difference file.
	
	4. Install the program identified in step 1 using its own installation program
	  or routine.
	
	NOTE: Microsoft does not support the use of the Sysdiff tool for the installation
	of system services, programs that include system services, device drivers, or
	network client software. System services and device drivers write to trees or
	values in the registry, which are dynamic or were found to be sensitive to
	access by the Sysdiff tool during testing. These trees and values are excluded
	from the /Snap and /Diff modes in the Sysdiff.inf file. In some cases you may
	find that the Sysdiff tool will successfully install these types of programs.
	
	Computer Name Is Incorrect or a Duplicate
	-----------------------------------------
	
	This error message can occur if the name of the computer on which you used the
	Sysdiff tool to snap the original image file and create the difference file has
	changed between the original snap and the creation of the difference file.
	
	To resolve this problem, re-create both the original image file and the
	difference file, making sure the computer name does not change.
	
	Image File Is Very Large and Takes a Long Time to Complete
	----------------------------------------------------------
	
	This behavior can occur if you include the image folder when you use the Sysdiff
	tool to create an image file. When you create the image on the local hard disk,
	exclude the folder being used to store the image file.
	
	To resolve this behavior, type the full path to the folder in which you are
	storing the image file in the [ExcludeDirectoryTrees] section in the Sysdiff.inf
	file. For example, if you run the Sysdiff tool from the C:\Image folder, type
	the following line in the [ExcludeDirectoryTrees] section:
	
	  C:\Image
	
	The Sysdiff Tool Only Appears on the Screen Briefly
	---------------------------------------------------
	
	This behavior can occur if you attempt to start the Sysdiff tool from a command
	line, and you use the wrong command line syntax.
	
	Changes Are Not Applied When You Use the Sysdiff /Apply Command
	---------------------------------------------------------------
	
	When you apply a difference file, it may appear that some user specific settings
	are not applied. Many of these settings are located in the HKEY_USERS or
	HKEY_CURRENT_USER keys in the registry. Because these settings are user
	specific, they are not present if you log on to Windows NT using an account
	other than the one that was used to create the difference file. The Sysdiff tool
	is not designed to incorporate these types of user specific settings.
	
	
	The Sysdiff /Apply /log Command Does Not Create a Log File
	----------------------------------------------------------
	
	The /apply command line parameter of the Sysdiff tool does not support the
	logging feature. The /log parameter can be used with the /snap and /diff command
	line parameters of the Sysdiff tool.
	
	NOTE: The "Windows NT Workstation Resource Kit" incorrectly shows the /log
	parameter being used with the /apply parameter on page 44.
	
	Network Drives Appear in My Computer
	------------------------------------
	
	Network drives, which are created after you snap the base image file and before
	the difference file is created, are applied to the new installation. Network
	drive connections are stored in the registry and are recognized by the Sysdiff
	tool. If you do not want additional network drives to be mapped for a user, you
	must disconnect from the network drives before you create the difference file.
	
	Error Message: Contact the Manufacturer
	---------------------------------------
	
	If you attempt to apply a difference file to a computer in which the %SystemRoot%
	folder has a different name than the %SystemRoot% folder of the computer from
	which the difference file was created, you may receive the following error
	message:
	
	  A problem exists with a file supplied by your computer's manufacturer.
	  Contact the manufacturer and report the following:
	
	  A snapshot or diff file specified on the command line was created with a
	  different sysroot and cannot be used now.
	
	  Click OK. Setup will continue but certain applications or other features may
	  not work correctly.
	
	Temporary Files Remain in the Sydiff Folder
	-------------------------------------------
	
	This behavior can occur if you quit the Sysdiff tool before it completes. To
	resolve this behavior, delete the temporary files, and then re-create the
	Sysdiff files.
	
	Error Message: Diff Failed (error=2)
	------------------------------------
	
	This error message can occur if you misspell a Sysdiff command line argument. For
	example, this error occurs if you you type the following command:
	
	  Sysdiff /diff base.img offic.img
	
	where base.img is actually named base2.img.
	
	Error Message: Access Denied
	----------------------------
	
	This error message can occur if you apply multiple image files to a network share
	of the Windows NT source files. For example, this error message can occur if you
	have an image of Microsoft Word and an image of Microsoft Excel, and you use the
	Sysdiff /inf command to apply the Microsoft Excel image to the network
	location.
	
	Microsoft has confirmed this to be a problem in the Microsoft products listed at
	the beginning of this article. We are researching this problem and will post new
	information here in the Microsoft Knowledge Base as it becomes available.
	
	
	Some Registry Changes, .ini Changes, or Files Are Missing
	---------------------------------------------------------
	
	Many programs require that you restart your computer after you run Setup. While
	your computer is restarting, the program makes additional changes. If you do not
	restart your computer, the Sysdiff /diff command may not detect all relevant
	changes. Make sure you restart your computer after you install any programs and
	before you use the Sysdiff /diff command.
	
	You Are Unable to Close the Sysdiff Program Window
	--------------------------------------------------
	
	This behavior can occur on certain computers, but typically is not a cause for
	concern. To work around this behavior, follow these steps:
	
	NOTE: Verify that Sysdiff is finished running before you follow these steps:
	
	1. Right-click the taskbar, and then click Task Manager.
	
	2. On the Application tab, click Sysdiff, and then click End Task.
	
	3. Quit Task Manager.
	
	Error Message: Installation Failed
	----------------------------------
	
	This error message can occur during Windows NT Setup when you use the Sysdiff
	/inf command to integrate the image into Windows NT Setup. This error message
	usually indicates a problem with a registry key that Sysdiff is attempting to
	update.
	
	To determine which registry key is causing the problem, follow these steps:
	
	1. Open the .inf file created by the Sysdiff tool in a text editor (such as
	  Notepad). This .inf file is located in the $OEM$ folder and has the same name
	  as the original image file.
	
	2. Choose a registry key at the beginning of the .inf file as a starting point,
	  and then use Registry Editor (Regedit.exe) to determine if that key was
	  actually added to the registry. If this key does exist in the registry, there
	  is a problem with a key further down the list.
	
	3. Repeat step 2, but choose a registry key further down the list. If the
	  registry key does not exist in the registry, the bad registry key is above
	  this key and after the key you checked in step 2.
	
	4. Repeat steps 2-3 until you determine the registry key in the .inf file that
	  is causing the problem.
	
	Debugging .inf files can be a time consuming process. You do not have to test an
	.inf file using a full Sysdiff /apply command each time you use a semi-colon (;)
	to remark out a line in an .inf file. During Windows NT Setup, the cmdlines.txt
	file reads the .inf file and writes each registry entry. To troubleshoot this
	process using the Cmdlines.txt file, follow these steps:
	
	1. Copy the Cmdlines.txt file and the .inf file from the $OEM$ folder to an
	  empty folder on your computer (for example, c:\debug).
	
	2. At a command prompt, type the following commands, pressing ENTER after each
	  command:
	
	  cd\debug
	  copy cmdlines.txt go.bat
	  edit go.bat
	
	3. In the text editor, delete the [Commands] heading, remove the quotation marks
	  from any lines that modify the registry, save the changes, and then quit the
	  text editor.
	
	4. Run the Go.bat batch file to determine if the changes you made to the .inf
	  file were added to the registry.
	
	NOTE: You should follow these steps on a computer on which the Sysdiff
	installation has failed. The program folders and .ini files must exist for these
	steps to work properly. Also, verify that the SystemRoot%\system32 folder exists
	in the environment path.
	
	Microsoft Office Does Not Work Properly
	---------------------------------------
	
	If user profiles are enabled in Windows NT, some versions of Microsoft Office may
	not work properly. In some cases, if you install Microsoft Office as one user
	and then log on as another user, some registry keys may be missing. This problem
	occurs because some versions of Office do not recognize Windows NT user
	profiles.
	
	For additional information about this issue, please see the following article in
	the Microsoft Knowledge Base:
	
	  Q159212 Office 95 Used on Windows NT 3.51 or Windows 95 with Profiles
	
	
	To work around this issue, use the appropriate method below:
	
	- Log on to Windows NT using the account that is going to use Microsoft Office,
	  and then apply the Sysdiff image. To apply the image file, the user account
	  must be a member of the Administrators group. Once the Sysdiff image is
	  complete, you can remove the user from the Administrators group.
	
	- Use another method for deploying Microsoft Office to Windows NT users. For
	  information about the different deployment methods that are available, please
	  see the following Microsoft web site:
	
	  http://www.microsoft.com/office/ork/default.htm
	
	For additional information about unattended installations and the Sysdiff tool,
	please see the following articles in the Microsoft Knowledge Base:
	
	  Q155197 Unattended Setup Parameters for Unattend.txt File
	
	  Q158548 Sysdiff Changes Dates on Files It Applies to WinNT
	
	  Q159839 Sysdiff Does Not Add Empty Directories
	
	  Q154888 SYSDIFF /inf Does Not Propagate Shortcuts to the Desktop
	
	
	  Q154487 SYSDIFF /dump Err. Msg: The Data Is Invalid
	
	  Q151908 SYSDIFF /dump Displays Some Registry Data Types Incorrectly
	
	  Q113583 SYSDIFF Does Not Remove Folders That Are Not Empty
	
	
	Additional query words: corrupt SBK OPK Unattended Setup Install
	
	======================================================================
	Keywords          : kbsetup kbtool kbtshoot kbOPK kbSBK kbfaq
	Technology        : kbWinNTsearch kbWinNTWsearch kbWinNTW400 kbWinNTW400search kbWinNT400search kbWinNTSsearch kbWinNTS400search kbWinNTS400
	Version           : :4.0
	Issue type        : kbinfo
	
	=============================================================================
	