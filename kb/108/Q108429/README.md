---
layout: page
title: "Q108429: How to Use PostMessage() with FOXTOOLS"
permalink: /kb/108/Q108429/
---

## Q108429: How to Use PostMessage() with FOXTOOLS

{% raw %}

	Article: Q108429
	Product(s): Microsoft FoxPro
	Version(s): 2.5,2.5a,2.5b,2.5x,2.6x,3.0
	Operating System(s): 
	Keyword(s): kbcode
	Last Modified: 19-SEP-2001
	
	-------------------------------------------------------------------------------
	The information in this article applies to:
	
	- Microsoft Visual FoxPro for Windows, version 3.0 
	- Microsoft FoxPro Library Construction Kit for Windows, versions 2.5, 2.5x, 2.6x 
	- Microsoft FoxPro for Windows, versions 2.5, 2.5a, 2.5b 
	-------------------------------------------------------------------------------
	
	SUMMARY
	=======
	
	The code example below demonstrates how FOXTOOLS.FLL can be used to call the
	PostMessage() function from FoxPro for Windows.
	
	NOTE: For backward compatibility, Visual FoxPro still supports FOXTOOLS.FLL
	(included in earlier FoxPro versions), the Visual FoxPro API library that allows
	calls to 16-bit .DLL functions. However, in Visual FoxPro, the DECLARE command
	is the preferred method for calling .DLL functions.
	
	MORE INFORMATION
	================
	
	The FOXTOOLS.FLL file is a FoxPro application programming interface (API)
	library that allows FoxPro programs to call many Windows dynamic-link library
	(DLL) functions. The FOXTOOLS.WRI document explains how to use FOXTOOLS.FLL.
	Both files are located in the GOODIES\FOXTOOLS subdirectory of the main FoxPro
	for Windows directory.
	
	The PostMessage() function posts (places) a message in a window's message queue
	and then returns without waiting for the corresponding window to process the
	message. This function is part of the Microsoft Windows API. This function
	accepts the following parameters:
	
	     BOOL PostMessage(hwnd, uMsg, wParam, lParam)
	
	     HWND hwnd;     /* handle of the destination window */ 
	     UINT uMsg;     /* message to post */ 
	     WPARAM wParam;     /* first message parameter */ 
	     LPARAM lParam;     /* second message parameter */ 
	
	This article demonstrates how to use PostMessage() to send a WM_SYSCOMMAND,
	SC_MAXIMIZE message to the main FoxPro window. The WM_SYSCOMMAND message is sent
	when the user chooses a command from the Control (system) menu or when the user
	chooses the Maximize button or the Minimize button. The second parameter
	specifies the type of system command requested. SC_MAXIMIZE is sent when the
	Maximize command is chosen.
	
	By using the PostMessage() function to send this message to the FoxPro window,
	you can "trick" FoxPro for Windows into thinking that the user chose Maximize
	from the Control menu.
	
	Both WM_SYSCOMMAND and SC_MAXIMIZE are constants. These constants are defined in
	the WINDOWS.H file, which is included with the Windows Software Development Kit
	(SDK). By finding the location in WINDOWS.H where WM_SYSCOMMAND and SC_MAXIMIZE
	are defined, you can to determine that WM_SYSCOMMAND has a hexadecimal value of
	"0x0112" and SC_MAXIMIZE has a hexadecimal value of "0xF030". These hexadecimal
	values can be converted to decimal values of 274 and 61,488 respectively.
	
	     * Load the FOXTOOLS library
	
	     SET LIBRARY TO SYS(2004)+"FOXTOOLS.FLL"
	
	     * Call RegFn() to register the PostMessage() function.
	
	     func_ref = regfn("PostMessage", "IIIL", "I")
	
	     * If RegFn() returned a value that is greater than -1, it
	     * can be assumed that the function was successfully
	     * registered.
	
	     IF func_ref > -1
	
	          * The mainhwnd() function, found in FOXTOOLS, is used to
	          * obtain a handle for the main FoxPro window.
	
	          wnd_hndl = mainhwnd()
	
	          * CallFn() is used to call the PostMessage() function with
	          * the appropriate parameters. The parameters required
	          * by PostMessage() are found in the Windows Software
	          * Development Kit. This particular call will place
	          * a Maximize (274,61488) message in the message queue
	          * for the FoxPro window (wnd_hndl). FoxPro will
	          * respond by maximizing its main window.
	
	          = callfn(func_ref,wnd_hndl,274,61488,0)
	
	     ENDIF
	
	     * Unload the library
	
	     SET LIBRARY TO
	
	REFERENCES
	==========
	
	Microsoft FoxPro for Windows FOXTOOLS.WRI document Microsoft Windows Software
	Development Kit Microsoft Visual C++
	
	Additional query words: VFoxWin FoxWin 2.50 foxtools api fll
	
	======================================================================
	Keywords          : kbcode 
	Technology        : kbVFPsearch kbAudDeveloper kbFoxproSearch kbFoxPro250 kbFoxPro250a kbFoxPro250b kbVFP300
	Version           : :2.5,2.5a,2.5b,2.5x,2.6x,3.0
	
	=============================================================================
	

{% endraw %}
