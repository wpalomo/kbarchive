---
layout: page
title: "Q175510: SAMPLE: VB5DCOM.EXE: Using Callbacks and WithEvents with DCOM"
permalink: /kb/175/Q175510/
---

## Q175510: SAMPLE: VB5DCOM.EXE: Using Callbacks and WithEvents with DCOM

{% raw %}

	Article: Q175510
	Product(s): Microsoft Visual Basic for Windows
	Version(s): 5.0,6.0
	Operating System(s): 
	Keyword(s): kbfile kbSample kbDCOM kbVBp500 kbVBp600 kbOSWin98 kbGrpDSVBDB
	Last Modified: 05-NOV-2000
	
	-------------------------------------------------------------------------------
	The information in this article applies to:
	
	- Microsoft Visual Basic Enterprise Edition for Windows, versions 5.0, 6.0 
	-------------------------------------------------------------------------------
	
	SUMMARY
	=======
	
	VB5DCOM.EXE is a Visual Basic sample application that demonstrates how to use
	WithEvents and CallBacks remotely via DCOM (Distributed Component Object
	Model).
	
	NOTE: Building DCOM Application with Microsoft Visual Basic is only enabled in
	the Enterprise Editions of Visual Basic 5.0 and 6.0.
	
	MORE INFORMATION
	================
	
	If you are using Visual Basic 6.0, see the following Microsoft Knowledge Base
	articles:
	
	  Q266717 HOWTO: Create a DCOM Client/Server Application by Using Visual Basic
	
	  Q267836 HOWTO: Create a DCOM Client/Server with Events by Using Visual Basic
	
	For additional help on how to set security and how to troubleshoot DCOM issues,
	see the following articles in the Microsoft Knowledge Base:
	
	  Q268550 HOWTO: Use Dcomcnfg for a Visual Basic DCOM Client/Server Application
	
	  Q269330 HOWTO: Troubleshoot DCOM for Visual Basic Client/Server Applications
	
	VB5DCOM.EXE also addresses all of the security settings that are required to make
	DCOM function correctly with Visual Basic using DCOM Config. It even
	demonstrates how to check a client machines registry to confirm that DCOM is
	installed on Windows 95 platforms and enabled on Windows NT, Windows 2000, and
	Windows 98. If DCOM is not present on the Windows 95 machine, then it presents
	the user with the opportunity to immediately download the necessary DCOM files
	from the Microsoft Web site.
	
	The following file is available for download from the Microsoft Download Center:
	
	  Vb5dcom.exe
	  (http://download.microsoft.com/download/vb60ent/Sample29/1/W9XNT4/EN-US/Vb5dcom.exe)
	
	For additional information about how to download Microsoft Support files, click
	the article number below to view the article in the Microsoft Knowledge Base:
	
	  Q119591 How to Obtain Microsoft Support Files from Online Services
	
	Microsoft used the most current virus detection software available on the date of
	posting to scan this file for viruses. Once posted, the file is housed on secure
	servers that prevent any unauthorized changes to the file.
	
	Place the file Vb5dcom.exe in a root directory of a drive that has at least 150KB
	of available space. This a self-extracting executable so it will create the
	proper folders for you and place all the files in their respective locations.
	Execute the file Vb5dcom.exe. You will now have a DCOMDemo folder with separate
	Client and Server folders.
	
	Open the server project \DCOMDemo\Server\DCOMDemoServer.vbp. In the project's
	properties, make sure that the "remote server files" option on the component tab
	is checked and make an executable of the server. The server will now be
	registered on your machine and you will have a .vbr file containing the registry
	entries for the server. Close the server project.
	
	Open the client project \DCOMDemo\Client\DCOMDemoClient.vbp. Set a reference to
	the DCOMDemoServer in the projects references. Run the project locally to check
	for problems before distributing to other machines for testing remotely.
	
	See the included file \DCOMDemo\Permissions.txt if you encounter problems (such
	as Error 70 - Permission denied).
	
	REFERENCES
	==========
	
	For more information about distributing DCOM applications, please see the
	following article in the Microsoft Knowledge Base:
	
	  Q161837 HOWTO: Create a DCOM Client/Server Application
	
	  Q266717 HOWTO: Create a DCOM Client/Server Application by Using Visual Basic
	
	  Q267836 HOWTO: Create a DCOM Client/Server with Events by Using Visual Basic
	
	  Q268550 HOWTO: Use Dcomcnfg for a Visual Basic DCOM Client/Server Application
	
	  Q269330 HOWTO: Troubleshoot DCOM for Visual Basic Client/Server Applications
	
	Additional query words: Permissions
	
	======================================================================
	Keywords          : kbfile kbSample kbDCOM kbVBp500 kbVBp600 kbOSWin98 kbGrpDSVBDB 
	Technology        : kbVBSearch kbAudDeveloper kbZNotKeyword6 kbZNotKeyword2 kbVB500Search kbVB600Search kbVB500 kbVB600
	Version           : :5.0,6.0
	Issue type        : kbinfo
	
	=============================================================================
	

{% endraw %}
