---
layout: page
title: "Q248348: PRB: SaveSetting and GetSetting Are Not Available in VB WebClass"
permalink: /kb/248/Q248348/
---

## Q248348: PRB: SaveSetting and GetSetting Are Not Available in VB WebClass

{% raw %}

	Article: Q248348
	Product(s): Microsoft Visual Basic for Windows
	Version(s): 6.0
	Operating System(s): 
	Keyword(s): kbRegistry kbVBp600 kbWebClasses kbGrpDSASP kbDSupport
	Last Modified: 22-JUL-2002
	
	-------------------------------------------------------------------------------
	The information in this article applies to:
	
	- Microsoft Visual Basic Learning Edition for Windows, version 6.0 
	- Microsoft Visual Basic Professional Edition for Windows, version 6.0 
	- Microsoft Visual Basic Enterprise Edition for Windows, version 6.0 
	-------------------------------------------------------------------------------
	
	SYMPTOMS
	========
	
	Calls to the SaveSetting, GetSetting, DeleteSetting or GetAllSettings methods in
	a Visual Basic 6.0 WebClass [Internet Information Server (IIS) Application]
	return the following errors in the Application log of the Windows NT Event
	Viewer:
	
	  Application-defined or object-defined error
	
	  -and-
	
	  The VB Application identified by the event source logged this Application
	  Project1: Thread ID: 317 ,Logged: MsgBox , Run-time error '5': Invalid
	  procedure call or argument
	
	CAUSE
	=====
	
	The SaveSetting, GetSetting, DeleteSetting, and GetAllSettings methods in Visual
	Basic are not available in Visual Basic 6.0 WebClasses (IIS Applications) when
	running in a compiled state. You should not use these methods in your WebClass
	applications.
	
	Visual Basic 6.0 WebClasses run under the Internet Information Server service.
	SaveSetting, GetSetting, DeleteSetting, and GetAllSettings manage registry keys
	in the HKEY_CURRENT_USER registry hive. The Internet Information Server service
	does not have an HKEY_CURRENT_USER registry hive available. As a result, the
	error occurs when calling these methods.
	
	RESOLUTION
	==========
	
	If you need to read and write to the registry, you need to write to and read
	from HKEY_LOCAL_MACHINE or HKEY_USERS, which are available to the Internet
	Information Server service. You may use the Windows Script Host for this
	purpose, or another component that provides this functionality.
	
	STATUS
	======
	
	This behavior is by design.
	
	MORE INFORMATION
	================
	
	The following is sample Windows Script Host code to read and write from the
	registry:
	
	  Private Sub WebClass_Start()
	      Dim objWSH As Object
	      
	      Set objWSH = CreateObject("WScript.Shell")
	      
	      objWSH.RegWrite "HKEY_LOCAL_MACHINE\Software\MyApplication\strValue", "Some string value"
	      objWSH.RegWrite "HKEY_LOCAL_MACHINE\Software\MyApplication\strReg\", 1, "REG_DWORD"
	
	      Response.Write objWSH.RegRead("HKEY_LOCAL_MACHINE\Software\MyApplication\strValue") & "<P>"
	      Response.Write objWSH.RegRead("HKEY_LOCAL_MACHINE\Software\MyApplication\strReg\") & "<P>"
	      
	      objWSH.RegDelete "HKEY_LOCAL_MACHINE\Software\MyApplication\strValue"
	      objWSH.RegDelete "HKEY_LOCAL_MACHINE\Software\MyApplication\strReg\"
	      objWSH.RegDelete "HKEY_LOCAL_MACHINE\Software\MyApplication\"
	  End Sub
	
	REFERENCES
	==========
	
	You can download the Windows Script Host from the following location:
	
	  http://www.microsoft.com/msdownload/vbscript/scripting.asp
	
	Additional query words:
	
	======================================================================
	Keywords          : kbRegistry kbVBp600 kbWebClasses kbGrpDSASP kbDSupport 
	Technology        : kbVBSearch kbAudDeveloper kbZNotKeyword6 kbZNotKeyword2 kbVB600Search kbVB600
	Version           : :6.0
	Issue type        : kbprb
	
	=============================================================================
	

{% endraw %}
