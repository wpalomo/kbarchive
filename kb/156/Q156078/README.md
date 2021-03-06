---
layout: page
title: "Q156078: RegMaid.exe Helps Clean Up the Registry"
permalink: /kb/156/Q156078/
---

## Q156078: RegMaid.exe Helps Clean Up the Registry

{% raw %}

	Article: Q156078
	Product(s): Microsoft C Compiler
	Version(s): 4.0,4.1,4.2,5.0,6.0
	Operating System(s): 
	Keyword(s): kbfile kbole kbSample kbAutomation kbCOMt kbMFC kbRegistry kbVC400 kbVC410 kbVC420 kbVC
	Last Modified: 14-AUG-2002
	
	-------------------------------------------------------------------------------
	The information in this article applies to:
	
	- Microsoft Visual C++, versions 4.0, 4.1 
	- Microsoft Visual C++, 32-bit Enterprise Edition, versions 4.2, 5.0, 6.0 
	- Microsoft Visual C++, 32-bit Professional Edition, versions 4.2, 5.0, 6.0 
	- Microsoft Visual C++, 32-bit Learning Edition, version 6.0 
	- Microsoft Visual C++.NET (2002) 
	-------------------------------------------------------------------------------
	
	NOTE: Microsoft Visual C++ .NET (2002) supports both the managed code model that is provided by the .NET Framework and the unmanaged native Windows code model. Part or all of the information in this article applies to managed Visual C++ code and may be applied only by using the .NET Framework.
	
	SUMMARY
	=======
	
	This article describes the RegMaid utility. You can obtain the RegMaid utility
	from the Microsoft Download Center (see the "More Information" section).
	
	The RegMaid utility is designed to clean up invalid registry entries that are
	caused by deleting OLE projects that are created with Visual C++ and Microsoft
	Foundation Classes (MFC).
	
	MORE INFORMATION
	================
	
	RegMaid provides information about entries that are believed to be problematic
	within the HKEY_CLASSES_ROOT: CLSID, ProgId, TypeLib, and Interface sections of
	the registry. This information is in a report form of a list view, where the
	user can make multiple row selections. Once selections have been made, the user
	can then delete them from the registry. Although RegMaid does not currently have
	an Archive and Restore capability, it does provide a printed report mechanism
	for each of the four views.
	
	The CLSID section considers an entry to contain a problem if any handler or
	server file entry cannot be found by the system. This can occur if a server has
	been registered over the net and the network connection has been broken. An
	entry might also be listed if the server has been moved or deleted. The CLSID
	section provides the most information about the entry that is listed to help you
	wisely chose the entries to remove.
	
	The ProgId section tries to match its CLSID entry with one in
	HKEY_CLASSES_ROOT\CLSID. The typical entry being searched in the registry is of
	the format HKEY_CLASSES_ROOT\Some ProgId\CLSID. If the entry under
	HKEY_CLASSES_ROOT does not contain a CLSID sub-entry, then it is ignored. This
	ensures that only ProgIds are listed. The clean-up process is identical to that
	of the CLSID section.
	
	The TypeLib section looks for references to .tlb files and if one is found in the
	registry that cannot be found in the system then the entry is listed as
	problematic. As with the CLSID section, the files in question are listed.
	
	The final section is the Interface portion of HKEY_CLASSES_ROOT. In this section
	each entry with a TypeLib entry is compared to the entries in
	HKEY_CLASSES_ROOT\TypeLib, and if a match is not found, the entry is listed
	here. This entry has the least amount of information available for deciding
	which registry entries to delete. In fact, the only information available are
	the TypeLib and Interface GUIDs. However, because this section is highly
	dependent on the TypeLib section, it should be safe to delete these entries as
	long as you have resolved the TypeLib issues first.
	
	The following files are available for download from the Microsoft Download
	Center:
	
	Visual C++ 6.0:
	
	RegMaid.exe
	
	For additional information about how to download Microsoft Support files, click
	the following article number to view the article in the Microsoft Knowledge
	Base:
	
	  Q119591 How to Obtain Microsoft Support Files from Online Services
	
	Microsoft scanned this file for viruses. Microsoft used the most current
	virus-detection software that was available on the date that the file was
	posted. The file is stored on secure servers that prevent any unauthorized
	changes to the file.
	
	Visual C++ .NET:
	
	  DownloadDownload Regmaid.exe now
	  (http://download.microsoft.com/download/visualcsharp.netstan/other/1.31/win98mexp/en-us/Regmaid.exe)
	
	Release Date: August 14, 2002
	
	For additional information about how to download Microsoft Support files, click
	the following article number to view the article in the Microsoft Knowledge
	Base:
	
	  Q119591 How to Obtain Microsoft Support Files from Online Services
	
	Microsoft scanned this file for viruses. Microsoft used the most current
	virus-detection software that was available on the date that the file was
	posted. The file is stored on secure servers that prevent any unauthorized
	changes to the file.
	
	
	NOTE: Use the -d option when running RegMaid.exe to decompress the file and
	re-create the proper directory structure.
	
	NOTE: As of February 10, 1998, there is a new version of RegMaid.exe (version
	1.1). It greatly reduces the number of erroneous listings that are caused by
	RegMaid's inability to find a server file, including:
	
	- Handling of long file names.
	
	- Handling of environmental variables in the path.
	
	- Confusion caused by multiple data entries for the server.
	
	REFERENCES
	==========
	
	Visual C++ 4.1 Sample: "REGISTRY: Uses the Win32 API to Access the Registry"
	
	Additional query words: Registry Visual Basic reg maid
	
	======================================================================
	Keywords          : kbfile kbole kbSample kbAutomation kbCOMt kbMFC kbRegistry kbVC400 kbVC410 kbVC420 kbVC500 kbVC600 kbGrpDSMFCATL 
	Technology        : kbVCsearch kbVC400 kbAudDeveloper kbVC410 kbVC420 kbVC500 kbVC600 kbVC32bitSearch kbVCNET kbVC500Search
	Version           : :4.0,4.1,4.2,5.0,6.0
	Issue type        : kbhowto
	
	=============================================================================
	

{% endraw %}
