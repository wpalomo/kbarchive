---
layout: page
title: "Q194835: PRB: Custom AppWizard Creates Defective 2nd-Generation Project"
permalink: /kb/194/Q194835/
---

## Q194835: PRB: Custom AppWizard Creates Defective 2nd-Generation Project

{% raw %}

	Article: Q194835
	Product(s): Microsoft C Compiler
	Version(s): WINNT:5.0,6.0
	Operating System(s): 
	Keyword(s): kberrmsg kbwizard kbVC500 kbVC600 kbAppWizard kbCustomWizard kbGrpDSTools
	Last Modified: 17-JUL-2001
	
	-------------------------------------------------------------------------------
	The information in this article applies to:
	
	- Microsoft Visual C++, 32-bit Enterprise Edition, versions 5.0, 6.0 
	- Microsoft Visual C++, 32-bit Professional Edition, versions 5.0, 6.0 
	- Microsoft Visual C++, 32-bit Learning Edition, version 6.0 
	-------------------------------------------------------------------------------
	
	SYMPTOMS
	========
	
	When you build a project created with a Custom AppWizard that was based on
	another project, the following link errors might occur:
	
	  
	
	  mfcs42d.lib(dllmodul.obj) : error LNK2005: _DllMain@12 already defined
	  in <projname>.obj
	
	  
	
	  mfcs42d.lib(dllmodul.obj) : error LNK2005: __pRawDllMain already defined
	  in <projname>.obj
	
	  
	
	  Debug/<projname>.dll : fatal error LNK1169: one or more multiply defined
	  symbols found
	
	  
	
	  LINK : fatal error LNK1104: cannot open file "mfcapwzd.lib"
	
	CAUSE
	=====
	
	The Custom AppWizard project creation wizard does not carry over build
	configurations of base projects. Instead, it generates standard Release and
	Debug configurations. It ignores any custom settings in the original project,
	such as preprocessor defines, additional libraries, custom build steps, and so
	on.
	
	RESOLUTION
	==========
	
	Modify the project settings in the CustomizeProject function of your Custom
	AppWizard.
	
	STATUS
	======
	
	Microsoft is researching this problem and will post new information here in the
	Microsoft Knowledge Base as it becomes available.
	
	
	MORE INFORMATION
	================
	
	Starting with Visual C++ 6.0, the object model supports adding new
	configurations and modifying build settings for single files. Use these methods
	to create appropriate configurations during the CustomizeProject phase of your
	custom AppWizard. For more information, please see the following topics in the
	Visual C++ Documentation:
	
	  Visual C++ Documentation: What's New in Visual C++ 6.0 ?;
	  What's New in Visual C++ Version 6.0 ?; Object Model
	
	  Visual C++ Documentation: Using Visual C++; Visual C++ Programmer's
	  Guide; Beginning Your Program; Details; AppWizard Programming Reference;
	  CCustomAppWiz; CCustomAppWiz::CustomizeProject
	
	In Visual C++ 5.0, you may create custom build steps for an entire project, and
	modify project settings for the two standard configurations the Custom AppWizard
	generates. For additional information, please see the following article in the
	Microsoft Knowledge Base:
	
	  Q181503 PRB: Custom AppWizards Can't Make Per-File Settings/Build Steps
	
	
	Steps to Reproduce Behavior
	---------------------------
	
	1. In Visual C++ 6.0, on the File menu, click New, and then click the Projects
	  tab.
	
	2. Select Custom AppWizard from the Projects list; give it a name and click OK.
	  In this example, the name is Cstm1.
	
	3. Click Finish on the next dialog box, Step 1, then click OK on the
	  confirmation dialog box.
	
	4. Press F7 to build Cstm1. It should build without errors.
	
	5. Now, follow steps 1 through 4 again, with the following changes:
	
	  a. Name the Custom AppWizard Cstm2.
	
	  b. In step 3, click Next instead of Finish, browse for Cstm1.dsp as the base
	     project, then click Finish.
	
	Continue with the following steps:
	
	6. From the File menu, click New, and then click the Projects tab.
	
	7. Select Cstm2 AppWizard from the Projects list; give it a name and click OK.
	  In this example, the name is Cstm2Proj.
	
	8. Click OK on the confirmation dialog box. The Cstm2Proj project loads.
	
	9. Press F7 to build Cstm2Proj.
	
	RESULT: The results are as described in SYMPTOMS. The Cstm2Proj project does not
	build a Custom AppWizard identical to Cstm1, as you might expect.
	
	Additional query words:
	
	======================================================================
	Keywords          : kberrmsg kbwizard kbVC500 kbVC600 kbAppWizard kbCustomWizard kbGrpDSTools 
	Technology        : kbVCsearch kbAudDeveloper kbVC32bitSearch kbVCPE500 kbVCPE600 kbVCEE500 kbVCEE600 kbVCLE600
	Version           : WINNT:5.0,6.0
	Issue type        : kbprb
	
	=============================================================================
	

{% endraw %}
