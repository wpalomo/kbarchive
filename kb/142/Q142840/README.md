---
layout: page
title: "Q142840: INFO: Visual Basic Requirements for Exported DLL Functions"
permalink: /kb/142/Q142840/
---

## Q142840: INFO: Visual Basic Requirements for Exported DLL Functions

{% raw %}

	Article: Q142840
	Product(s): Microsoft Visual Basic for Windows
	Version(s): WINDOWS:4.0
	Operating System(s): 
	Keyword(s): kbVBp400 kbGrpDSVB
	Last Modified: 11-JAN-2001
	
	-------------------------------------------------------------------------------
	The information in this article applies to:
	
	- Microsoft Visual Basic Standard Edition, 32-bit, for Windows, version 4.0 
	- Microsoft Visual Basic Professional Edition, 16-bit, for Windows, version 4.0 
	- Microsoft Visual Basic Professional Edition, 32-bit, for Windows, version 4.0 
	- Microsoft Visual Basic Enterprise Edition, 16-bit, for Windows, version 4.0 
	- Microsoft Visual Basic Enterprise Edition, 32-bit, for Windows, version 4.0 
	-------------------------------------------------------------------------------
	
	SUMMARY
	=======
	
	To use a function from an exported DLL in a Visual Basic program, certain
	requirements must be met for the function to be successfully used by Visual
	Basic. Visual Basic expects this exported DLL function to work like a Windows
	API call. This article summarizes the Visual Basic requirements and some of the
	requirements if you are creating your own exported DLL.
	
	MORE INFORMATION
	================
	
	One of the features of Visual Basic is the ability to use a function stored in a
	DLL. Visual Basic assumes that the exported DLL functions have the same
	attributes as a Windows API function. In order to use a function from an
	exported DLL in a Visual Basic program, Visual Basic requires the following:
	
	Requirements for Calling Functions
	----------------------------------
	
	- Arguments are passed from right to left: Arguments are passed by value unless
	  you specify a pointer or reference type.
	
	
	- Passing Arguments by Value or by Reference-By default: Visual Basic passes
	  all arguments by reference; arguments passed by reference contain the 32-bit
	  address containing the argument rather than the value of the argument.
	  However, most functions in an exported DLL expect the value of the argument
	  rather than the 32-bit address. To pass an argument by value, use the ByVal
	  keyword.
	
	
	- Stack-maintenance is handled by the called function.
	
	- Case sensitivity of the name: Under Win16, function names are not case
	  sensitive. Under Win32, function names are now case-sensitive. If you attempt
	  to call a function using a name that is letter similar but case different
	  from the function stored in an exported DLL, a run-time error will occur
	  because the function name does not exist.
	
	  For example, User32.dll has a function name called GetSystemMetrics that
	  returns information about the Windows Environment. Using the following
	  declare statement to call this function:
	
	        Declare Function GETSYSTEMMETRICS% Lib "User" ByVal nIndex%)
	
	  Results in a run-time error because the function, GETSYSTEMMETRICS is not in
	  User32.dll.
	
	  To avoid errors caused by incorrectly typing the function name, assign an
	  alias to the function name. For example, you can assign the alias
	  GetWindowsEnv to the GetSystemMetrics function by using the following declare
	  statement:
	
	        Declare Function GetWinEnv Lib "User32" Alias GetSystemMetrics _
	                         (ByVal int1 As Integer) As Integer.
	
	Notes on Creating Exported DLL in Visual C++
	--------------------------------------------
	
	This section provides some information for creating an exported DLL that meets
	the Visual Basic requirements using Microsoft Visual C++. Other C++ compilers
	may or may not support the keywords used in this section.
	
	Visual Basic requires that the function receiving the arguments also maintain the
	stack. The Visual C++ keyword that can perform the correct stack maintenance is
	_stdcall.
	
	The _stdcall keyword decorates the function name with a preceding underscore and
	appends '@n' where n is the number of bytes required to contain the function's
	arguments and the return value. For example, if you create a function called
	GetWindowSize and use the _stdcall keyword to provide stack maintenance, the
	function is defined as follows:
	
	     int GetWindowSize (int nIndex)
	
	The following is the exported name result:
	
	  _GetWindowSize@8
	
	Note the preceding underscore that is added by the _stdcall keyword.
	
	To export the file, you can either use the _declspec(dllexport) keyword or a DEF
	file EXPORT section. The _declspec(dllexport) keyword exports the function but
	maintains the name decoration. The following example shows how to implement both
	the _stdcall and _declspec(dllexport) keyword on a function called
	DisplayMessage:
	
	     _delcspec(dllexport) long _stdcall DisplayMessage (LPSTR szMessage)
	
	A DEF file also exports the function name and removes the name decoration. The
	following example shows how the EXPORT section of a DEF file is implemented for
	a function called DisplayMessage:
	
	  EXPORTS
	     DisplayMessage
	
	REFERENCES
	==========
	
	Vb4dll.txt included with Visual Basic.
	
	Visual Basic "Visual Basic Programmer's Guide," Chapter 26, "Calling Procedures
	in DLLs"
	
	Additional query words: kbNoKeyword Export Dll Function C++ C
	
	======================================================================
	Keywords          : kbVBp400 kbGrpDSVB 
	Technology        : kbVBSearch kbAudDeveloper kbVB400Search kbVB400 kbVB16bitSearch
	Version           : WINDOWS:4.0
	Issue type        : kbinfo
	
	=============================================================================
	

{% endraw %}
