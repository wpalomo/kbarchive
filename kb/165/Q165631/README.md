---
layout: page
title: "Q165631: ODE97: Creating Profiles for Custom Application in Setup Wizard"
permalink: /kb/165/Q165631/
---

## Q165631: ODE97: Creating Profiles for Custom Application in Setup Wizard

{% raw %}

	Article: Q165631
	Product(s): Microsoft Access Distribution Kit
	Version(s): 
	Operating System(s): 
	Keyword(s): kbusage
	Last Modified: 16-JUL-2002
	
	-------------------------------------------------------------------------------
	The information in this article applies to:
	
	- Microsoft Office 97 Developer Edition 
	-------------------------------------------------------------------------------
	
	Advanced: Requires expert coding, interoperability, and multiuser skills.
	
	IMPORTANT: This article contains information about editing the registry.
	Before you edit the registry, you should first make a backup copy of the
	registry files (System.dat and User.dat). Both are hidden files in the
	Windows folder.
	
	SUMMARY
	=======
	
	This article demonstrates how to create registry entries for a user profile for
	your application that includes a Help file, and Clipboard and Report formats.
	
	MORE INFORMATION
	================
	
	When you use the Setup Wizard to add registry entries to your custom Setup
	program that will create user profiles for your custom application, you must
	click to select the Profile check box on the Database Shortcut Properties tab on
	the Add Shortcuts screen, and you must create registry entries for your user
	profiles on the screen marked "Add the registry values that you want your custom
	Setup program to create and then set properties for each."
	
	There are three steps involved in creating a custom application that includes a
	user profile. They are as follows:
	
	1. Adding the necessary files to the List Of Files box.
	
	2. Creating a shortcut that includes the /Profile switch.
	
	3. Creating the registry entries that will be copied to the Windows registry on
	  the computer on which you are installing the application.
	
	For information about how to edit the registry, view the Changing Keys And Values
	online Help topic in Registry Editor (Regedit.exe). Note that you should make a
	backup copy of the registry files (System.dat and User.dat) before you edit the
	registry.
	
	WARNING: Using Registry Editor incorrectly can cause serious problems that may
	require you to reinstall Windows 95. Microsoft cannot guarantee that problems
	resulting from the incorrect use of Registry Editor can be solved. Use Registry
	Editor at your own risk.
	
	1. To add files to the List Of Files box, start the Setup Wizard program and in
	  the List Of Files box, add the files that you are including in your custom
	  application. This should include any .hlp and .cnt files that you may be
	  adding for your Help file. For example, if you were adding a content page, a
	  Help file and a database file to the List Of Files box, your screen would
	  look similar to this:
	
	     List of Files:
	
	     C:\My Documents\Northwind.mdb
	     C:\Program Files\Microsoft Office\Office\Samples\Nwind80.hlp
	     C:\Program Files\Microsoft Office\Office\Samples\Nwind80.cnt
	
	2. To create a shortcut that includes the /Profile switch, follow these steps:
	
	   a. On the Add The Shortcuts screen, click the Database Shortcut
	      Properties tab, click Add, and type a description for your shortcut
	      in the Description box.
	
	   b. Under the Database Command-Line Options, click to select the Profile
	      and Run-time check boxes, and then click Next.
	
	   c. Click Yes and then OK to the Setup Wizard messages.
	
	      NOTE: The shortcut that is created will open your custom application
	      as a run-time application with a profile. You may also want to add a
	      shortcut that will open your Help file.
	
	3. To add the registry entries for your custom application, follow these steps:
	
	   a. In the "List of Registry Values" box, click Add and complete the
	      following information for each entry that needs to be added to the
	      registry:
	
	      Top-Level for Key: $(Machine's Software Key for App)
	      Path to Key: Clipboard Formats
	      Value Name: Microsoft Excel (*.xls)
	      Base Value Data on File: (none)
	      Value Data: soa800.dll,8,xls,Biff5,MicrosoftExcel(*.xls),0
	      Value Data Type: String
	      Component Name: Application
	
	      NOTE: The "Top-Level for Key" entry has the same effect as manually
	      navigating to the HKEY_LOCAL_MACHINE\Software\YourCompanyName\ 
	      YourApplicationName\YourVersionNumber key.
	
	      NOTE: The Path To Key has the same effect as manually adding a new
	      key under the HKEY_LOCAL_MACHINE\Software\YourCompanyName\ 
	      YourApplicationName\YourVersionNumber key.
	
	      Top-Level for Key: $(Machine's Software Key for App)
	      Path to Key: Clipboard Formats
	      Value Name: MS-DOS Text (*.txt)
	      Base Value Data on File: (none)
	      Value Data: soa800.dll,10,txt,7,MS-DOSText(*.txt),0
	      Value Data Type: String
	      Component Name: Application
	
	      Top-Level for Key: $(Machine's Software Key for App)
	      Path to Key: Clipboard Formats
	      Value Name: Rich Text Format (*.rtf)
	      Base Value Data on File: (none)
	      Value Data: soa800.dll,9,rtf,Rich Text
	      Format,RichTextFormat(*.rtf),0
	      Value Data Type: String
	      Component Name: Application
	
	      Top-Level for Key: $(Machine's Software Key for App)
	      Path to Key: Report Formats
	      Value Name: HTML Documents
	      Base Value Data on File: (none)
	      Value Data: html,SOA_RptToHtml,1,HTML (*.html),1
	      Value Data Type: String
	      Component Name: Application
	
	      Top-Level for Key: $(Machine's Software Key for App)
	      Path to Key: Report Formats
	      Value Name: Microsoft Excel
	      Base Value Data on File: (none)
	      Value Data: xls,SOA_RptToBIFF, Biff5,Microsoft Excel (*.xls),0
	      Value Data Type: String
	      Component Name: Application
	
	      Top-Level for Key: $(Machine's Software Key for App)
	      Path to Key: Report Formats
	      Value Name: MS-DOS Text
	      Base Value Data on File: (none)
	      Value Data: txt,SOA_RptToAscii,1,MS-DOS Text (*.txt),0
	      Value Data Type: String
	      Component Name: Application
	
	      Top-Level for Key: $(Machine's Software Key for App)
	      Path to Key: Report Formats
	      Value Name: Rich Text Format
	      Base Value Data on File: (none)
	      Value Data: rtf,SOA_RptToRTF,Rich Text Format,Rich Text Format
	      (*.rtf),0
	      Value Data Type: String
	      Component Name: Application
	
	      Top-Level for Key: $(Machine's Software Key for App)
	      Path to Key: Run-Time Options
	      Value Name: AppHelpFile
	      Base Value Data on File: Nwind80.hlp
	      Value Data Type: String
	      Value Data:
	      Component Name: Application
	
	      NOTE: Use the "Base Value Data on File" box if the value of the key
	      or entry that you are adding is a file name that you are adding to
	      the Setup Wizard program, as in the case of a Custom Help file.
	      The Value Data box will automatically be populated with the
	      path to your Help file when you supply the Base Value Data on File
	      value.
	
	   b. When you are finish adding all of the entries, click Next.
	
	4. Continue through the Setup Wizard, answering the questions to design your
	  custom setup program the way you want it.
	
	5. Run your custom Setup program on a computer that does not have Microsoft
	  Access.
	
	6. Start the Registry Editor and navigate to the following keys:
	
	   a. \HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Access Runtime\Profiles
	
	      You should see an entry similar to the following:
	
	      Name            Data
	      ----------------------------------------------------------------
	      YourAppName     "SOFTWARE\Microsoft Corporation\YourAppName\1.0"
	
	   b. \HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft Corporation\YourAppName
	
	      You should see entries similar to the following:
	
	       Microsoft Corporation
	         YourAppName
	            1.0
	               Clipboard Formats
	               Jet
	               Report Formats
	               Run-Time Options
	
	      Clipboard Formats
	      -----------------
	
	      Name                    Data
	      ----------------------------
	
	      Microsoft Excel(*.xls)  "soa800.dll,8,xls,Biff5,MicrosoftExcel
	                              (*.xls) ,0"
	
	      MS_DOS Text             "MS-DOS Text (*.txt)"
	
	      Rich Text Format        "soa800.dll,9,rtf,Rich Text Format,
	                              RichTextFormat(*.rtf),0"
	
	      Report Formats
	      --------------
	
	      Name                    Data
	      -------------------------------------------------------------------
	
	      Microsoft Excel        "xls,SOA_RptToBIFF, Biff5,Microsoft Excel
	                             (*.xls),0"
	
	      MS-DOS Text            "txt,SOA_RptToAscii,1,MS-DOS Text (*.txt),0"
	
	      Rich Text Format       "rtf,SOA_RptToRTF,Rich Text Format,Rich Text
	                             Format(*.rtf),0"
	
	      Run-Time Options
	      ----------------
	
	      Name                   Data
	      ----------------------------------------------------------------
	
	      AppHelpFile           "Nwind80.hlp"
	
	7. Close the Registry Editor.
	
	Your custom application will now have the added features of the Help file, and
	the Report and Clipboard formats.
	
	REFERENCES
	==========
	
	For more information about creating user profiles, search the ODE Help Index for
	"registry, adding keys in Setup Wizard."
	
	Additional query words:
	
	======================================================================
	Keywords          : kbusage 
	Technology        : kbOfficeSearch kbAudDeveloper kbOffice97Search kbOffice97 kbOffice97DevSearch
	Version           : :
	Hardware          : x86
	Issue type        : kbhowto
	
	=============================================================================
	

{% endraw %}
