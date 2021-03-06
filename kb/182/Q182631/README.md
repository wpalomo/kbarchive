---
layout: page
title: "Q182631: INF: Using Alternate Code Page When Creating a Recording File"
permalink: /kb/182/Q182631/
---

## Q182631: INF: Using Alternate Code Page When Creating a Recording File

{% raw %}

	Article: Q182631
	Product(s): Microsoft SNA Server
	Version(s): WINDOWS:1.0,4.0
	Operating System(s): 
	Keyword(s): 
	Last Modified: 04-APR-2000
	
	-------------------------------------------------------------------------------
	The information in this article applies to:
	
	- Microsoft COM Transaction Integrator for CICS and IMS, version 1.0, used with:
	   - Microsoft SNA Server, version 4.0 
	-------------------------------------------------------------------------------
	
	SUMMARY
	=======
	
	This article describes how to create a recording file that is capable of
	capturing from a target Remote Environment (RE) which specifies a code page that
	differs from the local machine default.
	
	When a diagnostic capture RE is created using the COMTI Management Console, an
	associated recording file is created. The code page assigned to the recording
	file is the local default selected during Windows NT Server installation. If you
	attempt to select a target RE on the Target property sheet that has a different
	code page, the following error message appears:
	
	  (8022) The selected target Remote Environment uses a locale or code page
	  which is incompatible with the locale settings of the currently selected
	  recording file.
	
	  You may either modify the locale settings for the selected target Remote
	  Environment or identify a different recording file.
	
	MORE INFORMATION
	================
	
	Diagnostic Capture RE's created with the COMTI Management Console are assigned
	an Extended Binary Coded Decimal Interchange Code (EBCDIC) code page appropriate
	for the current Windows NT Server system locale setting. To change this
	assignment, you must create a new recording file with the preferred code page.
	
	To modify a Diagnostic Capture RE so that it is capable of capturing from a
	Target RE with a different code page, use the following steps:
	
	1. Move any components that are currently assigned to the Diagnostic Capture RE
	  to another RE.
	
	2. Right-click the Remote Environment and select Properties.
	
	3. Click the Recording tab, and enter a new recording name in the Name field of
	  the Recording selection group box.
	
	4. Click Browse and then click Open. Only the Type field should now be populated
	  in the Recording information group box. The remaining fields should be empty.
	
	5. Click the Target tab and then click "Use responses from the following Remote
	  Environment."
	
	6. Select the target RE you want to capture from. Click Apply to create the new
	  recording file. It will have the same code page as that of the Target RE.
	
	7. Click the Local tab and view the Code page entry to verify.
	
	To modify a Diagnostic Capture RE so that it has a specific code page, use the
	following steps:
	
	1. Move any components that are currently assigned to the Diagnostic Capture RE
	  to another RE.
	
	2. Right-click the RE and select Properties.
	
	3. Click the Recording tab and enter a new recording name in the Name field
	  under Recording Selection. The remaining fields should be empty.
	
	4. Click the Target tab and then click "Use responses from the turnaround
	  dialog."
	
	5. Click the Local tab and select the preferred code page.
	
	6. Click Apply to create the new recording file with the preferred code page. If
	  you return to the Target tab and choose to capture from a target RE, its code
	  page must match that of the new recording file or the Apply will fail.
	
	Additional query words:
	
	======================================================================
	Keywords          :  
	Technology        : kbAudDeveloper kbCOMTISearch
	Version           : WINDOWS:1.0,4.0
	Hardware          : ALPHA x86
	Issue type        : kbinfo
	
	=============================================================================
	

{% endraw %}
