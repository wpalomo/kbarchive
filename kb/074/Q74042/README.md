---
layout: page
title: "Q74042: HOWTO: How to Use PeekMessage() Correctly in Windows"
permalink: /kb/074/Q74042/
---

## Q74042: HOWTO: How to Use PeekMessage() Correctly in Windows

{% raw %}

	Article: Q74042
	Product(s): Microsoft Windows Software Development Kit
	Version(s): WINDOWS:3.1,4.0,95; winnt:3.5,3.51
	Operating System(s): 
	Keyword(s): kb16bitonly kbSDKPlatform kbWndw kbWndwMsg
	Last Modified: 11-MAY-2001
	
	3.00 3.10 4.00 | 3.10 3.50 3.51
	WINDOWS        | WINDOWS NT
	kbui
	
	
	-------------------------------------------------------------------------------
	The information in this article applies to:
	
	- Microsoft Windows Software Development Kit (SDK) 3.1 
	- Microsoft Win32 Application Programming Interface (API), used with:
	   - Microsoft Windows 4.0 
	-------------------------------------------------------------------------------
	
	SUMMARY
	=======
	
	In the Windows environment, many applications use a PeekMessage() loop to
	perform background processing. Such applications must allow the Windows system
	to enter an idle state when their background processing is complete. Otherwise,
	system performance, "idle-time" system processes such as paging optimizations,
	and power management on battery-powered systems will be adversely affected.
	
	While an application is in a PeekMessage() loop, the Windows system cannot go
	idle. Therefore, an application should not remain in a PeekMessage() loop after
	its background processing has completed.
	
	NOTE: The PeekMessage method described in this article is only needed if your
	application is a 32-bit application for Windows and is, for some reason, unable
	to create threads and perform background processing.
	
	MORE INFORMATION
	================
	
	Many Windows-based applications use PeekMessage() to retrieve messages while
	they are in the middle of a long process, such as printing, repaginating, or
	recalculating, that must be done "in the background." PeekMessage() is used in
	these situations because, unlike GetMessage(), it does not wait for a message to
	be placed in the queue before it returns.
	
	An application should not call PeekMessage() unless it has background processing
	to do between the calls to PeekMessage(). When an application is waiting for an
	input event, it should call GetMessage() or WaitMessage().
	
	Remaining in a PeekMessage() loop when there is no background work causes system
	performance problems. A program in a PeekMessage() loop continues to be
	rescheduled by the Windows scheduler, consuming CPU time and taking time away
	from other processes.
	
	In enhanced mode, the Virtual Machine (VM) in which Windows is running will not
	appear to be idle as long as an application is calling the PeekMessage function.
	Therefore, the Windows VM will continue to receive a considerable fraction of
	CPU time.
	
	Many power management methods employed on laptop and notebook computers are based
	on the system going idle when there is no processing to do. An application that
	remains in a PeekMessage() loop will make the system appear busy to power
	management software, resulting in excessive power consumption and shortening the
	time that the user can run the system.
	
	In the future, the Windows system will make more and more use of idle time to do
	background processing, which is designed to optimize system performance.
	Applications that do not allow the system to go idle will adversely affect the
	performance of these techniques.
	
	All these problems can be avoided by calling the PeekMessage() function only when
	there is background work to do, and calling GetMessage() or WaitMessage() when
	there is no background work to do.
	
	For example, consider the following PeekMessage() loop. If there is no background
	processing to do, this loop will continue to run without waiting for messages,
	preventing the system from going idle and causing the negative effects described
	above.
	
	     // This PeekMessage loop will NOT let the system go idle.
	
	     for( ;; )
	     {
	
	        while (PeekMessage(&msg, NULL, 0, 0, PM_REMOVE))
	        {
	           if (msg.message == WM_QUIT)
	              return TRUE;
	
	           TranslateMessage(&msg);
	           DispatchMessage(&msg);
	        }
	
	        BackgroundProcessing();
	      }
	
	This loop can be rewritten in two ways, as shown below. Both of the following
	PeekMessage() loops have two desirable properties:
	
	- They process all input messages before performing background processing,
	  providing good response to user input.
	
	- The application "idles" (waits for an input message) when no background
	  processing needs to be done.
	
	Improved PeekMessage Loop 1
	---------------------------
	
	     // Improved PeekMessage() loop
	
	     for(;;)
	     {
	
	        while (PeekMessage(&msg, NULL, 0, 0, PM_REMOVE))
	        {
	           if (msg.message == WM_QUIT)
	              return TRUE;
	
	           TranslateMessage(&msg);
	           DispatchMessage(&msg);
	        }
	
	        if (IfBackgroundProcessingRequired())
	           BackgroundProcessing();
	        else
	           WaitMessage(); // Will not return until a message is posted.
	
	     }
	
	Improved PeekMessage Loop 2
	---------------------------
	
	     // Another improved PeekMessage() loop
	
	     for (;;)
	     {
	
	        for (;;)
	        {
	           if (IfBackgroundProcessingRequired())
	           {
	              if (!PeekMessage(&msg, NULL, 0, 0, PM_REMOVE))
	                 break;
	           }
	           else
	              GetMessage(&msg, NULL, 0, 0, 0);
	
	           if (msg.message == WM_QUIT)
	              return TRUE;
	
	           TranslateMessage(&msg);
	           DispatchMessage(&msg);
	        }
	        BackgroundProcessing();
	
	     }
	
	Note that calls to functions such as IsDialogMessage() and TranslateAccelerator()
	can be added to these loops as appropriate.
	
	There is one case in which the loops above need additional support: if the
	application waits for input from a device (for example, a fax board) that does
	not send standard Windows messages. For the reasons outlined above, a
	Windows-based application should not use a PeekMessage() loop to continuously
	poll the device. Rather, implement an Interrupt Service Routine (ISR) in a
	Dynamic-Link Library (DLL). When the ISR is called, the DLL can use the
	PostMessage function to inform the application that the device requires service.
	DLL functions can safely call the PostMessage() function because the
	PostMessage() function is reentrant.
	
	Additional query words: 3.00 4.00
	
	======================================================================
	Keywords          : kb16bitonly kbSDKPlatform kbWndw kbWndwMsg 
	Technology        : kbAudDeveloper kbSDKSearch kbWin32sSearch kbWin32API kbWinSDKSearch
	Version           : WINDOWS:3.1,4.0,95; winnt:3.5,3.51
	Issue type        : kbhowto
	
	=============================================================================
	

{% endraw %}
