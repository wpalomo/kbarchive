---
layout: page
title: "Q179938: PRB: Sybase Formula One OCX Dependency Warning w/Setup Wizard"
permalink: /kb/179/Q179938/
---

## Q179938: PRB: Sybase Formula One OCX Dependency Warning w/Setup Wizard

{% raw %}

	Article: Q179938
	Product(s): Microsoft Visual Basic for Windows
	Version(s): 5.0
	Operating System(s): 
	Keyword(s): kbwizard kbAppSetup kbVBp500 kbGrpDSVB
	Last Modified: 11-JAN-2001
	
	-------------------------------------------------------------------------------
	The information in this article applies to:
	
	- Microsoft Visual Basic Professional Edition for Windows, version 5.0 
	- Microsoft Visual Basic Enterprise Edition for Windows, version 5.0 
	-------------------------------------------------------------------------------
	
	SYMPTOMS
	========
	
	When using the Visual Basic Setup Wizard to create a setup application, you
	receive the following warning:
	
	  No dependency information could be found for: COMCTL32.DLL
	
	which may be followed by:
	
	  No dependency information could be found for: COMDLG32.DLL
	
	CAUSE
	=====
	
	When using the Setup Wizard on a project that includes references to the Sybase
	Visual Components Formula One 5.0 control, VCF15.OCX, the Setup Wizard requires
	additional information to be added to the control's dependency file, VCF15.DEP.
	
	RESOLUTION
	==========
	
	To work around this problem, the following information should be added to the
	dependency file for the VCF15.OCX control, entitled VCF15.DEP. This file should
	be located in the System or System32 directory, depending on the version of
	Windows installed.
	
	The dependency file is a text file that can be opened in any typical word
	processing application, such as Notepad. The contents of the VCF15.DEP file
	include:
	
	[VCF15.OCX]
	Register=$(DLLSelfRegister)
	Uses1=OLEAUT32.DLL
	Uses2=OLEPRO32.DLL
	Uses3=STDOLE2.TLB
	Uses4=COMCTL32.DLL
	Uses5=COMDLG32.DLL
	
	Once the file has been opened, the following information needs to be added to the
	end of the file:
	
	[COMCTL32.DLL]
	Dest=$(WinSysPathSysFile)
	Uses1=
	
	[COMDLG32.DLL]
	Dest=$(WinSysPathSysFile)
	Uses1=
	
	After the information has been added, save the dependency file and run the Setup
	Wizard again. This allows the Setup Wizard to finish the creation of the setup
	application, and allows the application to install correctly.
	
	REFERENCES
	==========
	
	For additional information, click the article number below to view the article
	in the Microsoft Knowledge Base:
	
	  Q178354 INFO: How Setup Wizard and PDW Uses Dependency Files
	
	Additional query words: formula sybase
	
	======================================================================
	Keywords          : kbwizard kbAppSetup kbVBp500 kbGrpDSVB 
	Technology        : kbVBSearch kbAudDeveloper kbZNotKeyword6 kbZNotKeyword2 kbVB500Search kbVBA500 kbVB500
	Version           : :5.0
	Issue type        : kbprb
	
	=============================================================================
	

{% endraw %}
