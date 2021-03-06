---
layout: page
title: "Q129802: PRB: Can't Have Fixed Length Strings &gt;32K in 32-bit Windows"
permalink: /kb/129/Q129802/
---

## Q129802: PRB: Can't Have Fixed Length Strings &gt;32K in 32-bit Windows

{% raw %}

	Article: Q129802
	Product(s): Microsoft Visual Basic for Windows
	Version(s): WINDOWS:4.0
	Operating System(s): 
	Keyword(s): kberrmsg kbprogramming kbVBp400 kb32bitOnly
	Last Modified: 11-JAN-2001
	
	-------------------------------------------------------------------------------
	The information in this article applies to:
	
	- Microsoft Visual Basic Standard Edition, 32-bit, for Windows, version 4.0 
	- Microsoft Visual Basic Professional Edition, 32-bit, for Windows, version 4.0 
	- Microsoft Visual Basic Enterprise Edition, 32-bit, for Windows, version 4.0 
	-------------------------------------------------------------------------------
	
	SYMPTOMS
	========
	
	Attempting to create fixed-length strings within a user-defined type in the
	32-bit version of Microsoft Visual Basic version 4.0 generates this error:
	
	  "Fixed or static data can't be larger than 64K"
	
	CAUSE
	=====
	
	Because 32-bit Microsoft Visual Basic uses Unicode to store strings and Unicode
	requires two bytes per character in a string, fixed-length strings take twice as
	many bytes of storage as the 16-bit versions of Visual Basic. If you assign or
	dimension more that 32K characters to a string, the storage actually exceeds the
	64K limit of Visual Basic user-defined types.
	
	RESOLUTION
	==========
	
	Larger strings can be assigned to string elements of user-defined types by using
	variable-length strings instead of fixed-length strings.
	
	STATUS
	======
	
	This behavior is by design.
	
	MORE INFORMATION
	================
	
	Steps to Reproduce Behavior
	---------------------------
	
	1. Start a new project in Visual Basic. Form1 is created by default.
	
	2. Add a code module (Module1) to your project by choosing Module from the
	  Insert menu.
	
	3. Add the following code to the General Declarations section of Module1:
	
	        Type MyType
	           MyString As String * 33000
	        End Type
	
	4. Start the program by choosing Start from the Run menu or by pressing the F5
	  key. You should see the following run-time error message:
	
	  "Fixed or static data can't be larger than 64K"
	
	Additional query words: double byte character set dbcs
	
	======================================================================
	Keywords          : kberrmsg kbprogramming kbVBp400 kb32bitOnly 
	Technology        : kbVBSearch kbAudDeveloper kbVB400Search kbVB400
	Version           : WINDOWS:4.0
	Issue type        : kbprb
	
	=============================================================================
	

{% endraw %}
