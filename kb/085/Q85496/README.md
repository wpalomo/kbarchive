---
layout: page
title: "Q85496: PRB: Assertion Failed: WINAPP.CPP, APPCORE.CPP, or WINMAIN.CPP"
permalink: /kb/085/Q85496/
---

## Q85496: PRB: Assertion Failed: WINAPP.CPP, APPCORE.CPP, or WINMAIN.CPP

{% raw %}

	Article: Q85496
	Product(s): Microsoft C Compiler
	Version(s): winnt:1.0,2.0,2.1,4.0
	Operating System(s): 
	Keyword(s): kbnokeyword kbMFC kbVC kbGrpDSMFCATL
	Last Modified: 22-JUL-2001
	
	-------------------------------------------------------------------------------
	The information in this article applies to:
	
	- The Microsoft Foundation Classes (MFC), used with:
	   - Microsoft C/C++ compiler for MS-DOS 
	   - Microsoft Visual C++ for Windows, 16-bit edition, versions 1.0, 1.5 
	   - Microsoft Visual C++, 32-bit Editions, versions 1.0, 2.0, 2.1, 4.0 
	-------------------------------------------------------------------------------
	
	SYMPTOMS
	========
	
	Running a Microsoft Foundation Classes (MFC) application developed with
	Microsoft C/C++ version 7.0 or Visual C++ for Windows may cause one of the
	following error messages to be displayed:
	
	  Assertion failed - <unknown application>:File winapp.cpp, Line 258
	
	-or-
	
	  Assertion failed - <unknown application>:File appcore.cpp, Line 602
	
	
	Running a MFC application developed with Visual C++, 32-bit Edition, version 1.0
	may cause the following error message to be displayed:
	
	  Assertion failed - <unknown application>:File appcore.cpp, Line 559
	
	Running a MFC application developed with Visual C++, 32-bit Edition, version 2.x,
	may cause the following error message to be displayed:
	
	  Assertion failed - <unknown application>:File winmain.cpp, Line 40
	
	Running a MFC application developed with Visual C++, 32-bit Edition, version 4.0,
	may cause the following error message to be displayed:
	
	  Debug Assertion Failed!
	
	  Program: <program_name>
	  File: winmain.cpp
	  Line: 34
	
	NOTE: In Visual C++, 32-bit Edition, versions 2.0 and above, the assertion will
	be followed by an Application Error.
	
	CAUSE
	=====
	
	The assertion that fails is the check to see whether an application object
	exists. Without the application object, the program cannot run.
	
	RESOLUTION
	==========
	
	Define an object of a class derived from the CWinApp class.
	
	MORE INFORMATION
	================
	
	An example of this error may be seen by commenting out the file scoped statement
	of any MFC application that defines the CWinApp-derived object. This statement
	will look similar to the following:
	
	     CMyWinApp  MyWinApp;
	
	where CMyWinApp is defined as follows:
	
	     class CMyWinApp : public CWinApp
	     {
	        //...
	     };
	
	For an example MFC application, see the HELLOAPP sample program included with any
	of the Microsoft products listed above.
	
	
	Chapter 3 of the "Microsoft C Class Libraries User's Guide," provided with
	Microsoft C/C++ version 7.0, and chapter 1 of the "Programming with MFC:
	Overview," included in the Visual C++ Books Online, contain additional
	information on CWinApp and on the fundamentals of using the Microsoft Foundation
	Classes to build an application for Windows.
	
	Additional query words: 7.00 1.00 1.50 2.00 2.10 2.50 3.00 4.00
	
	======================================================================
	Keywords          : kbnokeyword kbMFC kbVC kbGrpDSMFCATL 
	Technology        : kbAudDeveloper kbMFC
	Version           : winnt:1.0,2.0,2.1,4.0
	Issue type        : kbprb
	
	=============================================================================
	

{% endraw %}
