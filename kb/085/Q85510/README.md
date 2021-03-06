---
layout: page
title: "Q85510: CodeView Does Not Use Default Arguments for Functions"
permalink: /kb/085/Q85510/
---

## Q85510: CodeView Does Not Use Default Arguments for Functions

{% raw %}

	Article: Q85510
	Product(s): Microsoft Programming Utilities
	Version(s): 4.0,4.01,4.05,4.1
	Operating System(s): 
	Keyword(s): kberrmsg kbCodeView kbDebug kbVC _IK
	Last Modified: 26-JUN-2001
	
	-------------------------------------------------------------------------------
	The information in this article applies to:
	
	- Microsoft CodeView for MS-DOS, versions 4.0, 4.01, 4.05, 4.1 
	- Microsoft CodeView for Windows, versions 4.0, 4.01, 4.1 
	-------------------------------------------------------------------------------
	
	SUMMARY
	=======
	
	Microsoft CodeView versions 4.0 and later, which support debugging C++ programs,
	do not correctly evaluate functions that use default arguments. When an
	expression is used that requires CodeView to evaluate a function with a default
	argument, the following error message is displayed:
	
	  CXX0047: Error: argument list does not match a function
	
	MORE INFORMATION
	================
	
	The sample code below contains a function that has a default argument. In the
	program, the function PrintOut() can be called either with a void parameter list
	or with a character pointer. When the following command is executed from
	CodeView's command window
	
	     ? PrintOut("This is a string constant")
	
	the function is called and "This is a string constant" is printed to the output
	screen. When the function PrintOut() is called with no parameters, for example
	
	     ? PrintOut()
	
	the error CXX0047 is generated. This occurs only when using the "?" command in
	CodeView to force a function to be evaluated.
	
	Default arguments are supported only in C++ programs.
	
	Sample Code
	-----------
	
	  /* Compile options needed: /Od /Zi
	  */ 
	
	  #include <iostream.h>
	
	  void PrintOut (char *String = "This is a default argument.");
	
	  void main (void)
	  {
	     PrintOut();
	     PrintOut( "This is not a default argument.");
	  }
	
	  void PrintOut (char *String)
	  {
	     cout << String << endl;
	  }
	
	Additional query words: kbinf 4.00 4.10
	
	======================================================================
	Keywords          : kberrmsg kbCodeView kbDebug kbVC _IK 
	Technology        : kbAudDeveloper kbCodeView kbZNotKeyword3 kbCodeView400DOS kbCodeView401DOS kbCodeView405DOS kbCodeView410DOS kbCodeView400 kbCodeView401 kbCodeView410
	Version           : :4.0,4.01,4.05,4.1
	
	=============================================================================
	

{% endraw %}
