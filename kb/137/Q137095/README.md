---
layout: page
title: "Q137095: HOWTO: Provide Constants from an ActiveX Component"
permalink: /kb/137/Q137095/
---

## Q137095: HOWTO: Provide Constants from an ActiveX Component

{% raw %}

	Article: Q137095
	Product(s): Microsoft Visual Basic for Windows
	Version(s): WINDOWS:4.0,5.0,6.0
	Operating System(s): 
	Keyword(s): kbVBp kbVBp400 kbVBp500 kbVBp600 kbGrpDSVB kbDSupport
	Last Modified: 11-JAN-2001
	
	-------------------------------------------------------------------------------
	The information in this article applies to:
	
	- Microsoft Visual Basic Learning Edition for Windows, version 6.0 
	- Microsoft Visual Basic Professional Edition for Windows, version 6.0 
	- Microsoft Visual Basic Enterprise Edition for Windows, version 6.0 
	- Microsoft Visual Basic Control Creation Edition for Windows, version 5.0 
	- Microsoft Visual Basic Learning Edition for Windows, version 5.0 
	- Microsoft Visual Basic Professional Edition for Windows, version 5.0 
	- Microsoft Visual Basic Enterprise Edition for Windows, version 5.0 
	- Microsoft Visual Basic Standard Edition, 32-bit, for Windows, version 4.0 
	- Microsoft Visual Basic Professional Edition, 32-bit, for Windows, version 4.0 
	- Microsoft Visual Basic Enterprise Edition, 32-bit, for Windows, version 4.0 
	-------------------------------------------------------------------------------
	
	SUMMARY
	=======
	
	The use of constants is an efficient way to keep code clear, easier to document,
	and more understandable. When you create ActiveX components, it is more
	efficient to provide constants with the server in a ready-to-use form. This
	eliminates the need to declare constants in client (container) applications and
	makes it easier to call into server classes. This article describes two ways to
	implement constants with your ActiveX component.
	
	MORE INFORMATION
	================
	
	Two ways to provide constants for use with an ActiveX component:
	
	1. Use the Property Get function to expose the constants as read-only
	  properties. For example, if MY_CONSTANT is a constant set to the value 4, the
	  following shows how to expose it to client applications:
	
	        Public Property Get MY_CONSTANT () As Integer
	           MY_CONSTANT = 4
	        End Property
	
	2. Create a Type Library using Object Description Language (ODL). MkTypLib is
	  the tool used to process ODL source files; it produces a type library (.tlb
	  file) and an optional C- or C++-style header file. The following is an
	  example ODL script that you could use to provide an OLE server with the
	  constant MY_CONSTANT:
	
	        [
	           uuid(12345678-AAAA-BBBB-CCCC-000000000000),
	           lcid (0x0000409),
	           ,helpfile("myhelp.hlp")
	           ,helpstring("More info for my server")
	           ,version(1.0)
	        ]
	
	        library MyServer
	        {
	           [uuid(12345678-AAAA-BBBB-CCCC-111111111111),  \\unique guid
	           helpstring("My Constants"),
	           helpcontext(1011389), dllname(mydll)]
	           module Constants {
	           [helpstring("This is the value for MY_CONSTANT"),
	              helpcontext(1012527)]
	
	              const short MY_CONSTANT = 4; } \\module
	        }\\ library
	
	REFERENCES
	==========
	
	MkTypLib comes with Win32 Software Development Kit (SDK) for Windows NT and
	Microsoft Visual C++ version 2.0 or later
	
	For more information on Type Libraries and ODL, please see the Win32 SDK.
	
	Additional query words: KBSERVER KBACTIVEX KBDLL kbdsd
	
	======================================================================
	Keywords          : kbVBp kbVBp400 kbVBp500 kbVBp600 kbGrpDSVB kbDSupport 
	Technology        : kbVBSearch kbAudDeveloper kbZNotKeyword6 kbZNotKeyword2 kbVB500Search kbVB600Search kbVBA500Search kbVBA500 kbVBA600 kbVB500 kbVB600 kbVB400Search kbVB400 kbZNotKeyword3
	Version           : WINDOWS:4.0,5.0,6.0
	Issue type        : kbhowto
	
	=============================================================================
	

{% endraw %}
