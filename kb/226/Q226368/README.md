---
layout: page
title: "Q226368: SMS: NAL May Search Mapped Drives for Network DLLs"
permalink: /kb/226/Q226368/
---

## Q226368: SMS: NAL May Search Mapped Drives for Network DLLs

{% raw %}

	Article: Q226368
	Product(s): Microsoft Systems Management Server
	Version(s): winnt:1.2,2.0
	Operating System(s): 
	Keyword(s): kbnetwork kbsms200 kbsms200bug kbsms120 kbsms120bug
	Last Modified: 08-MAY-2002
	
	-------------------------------------------------------------------------------
	The information in this article applies to:
	
	- Microsoft Systems Management Server versions 1.2, 2.0 
	-------------------------------------------------------------------------------
	
	SYMPTOMS
	========
	
	If your path contains network drives, the Network Abstraction Layer (NAL) may
	search those network drives for network DLLs. This may lead to increased network
	traffic. To work around this problem, remove network drives from the path.
	
	CAUSE
	=====
	
	NAL uses the Win32 API LoadLibrary() to load network DLLs. NAL calls
	LoadLibrary() without specifying a path for the network DLLs. LoadLibrary()
	searches for the network DLLs in the following sequence:
	
	1. The directory from which the application loaded.
	
	2. The current directory.
	
	3. Windows 95/98: The Windows System directory. Use the GetSystemDirectory
	  function to get the path of this directory.
	
	  Windows NT/2000: The 32-bit Windows system directory. Use the
	  GetSystemDirectory function to get the path of this directory. The name of
	  this directory is System32.
	
	4. Windows NT/2000: The 16-bit Windows system directory. There is no function
	  that obtains the path of this directory, but it is searched. The name of this
	  directory is System.
	
	5. The Windows directory. Use the GetWindowsDirectory function to get the path
	  of this directory.
	
	6. The directories that are listed in the PATH environment variable.
	
	RESOLUTION
	==========
	
	To resolve this problem, obtain the latest service pack for Systems Management
	Server 2.0. For additional information, please see the following article in the
	Microsoft Knowledge Base:
	
	  Q236325 How to Obtain the Latest Systems Management Server 2.0 Service Pack
	
	
	STATUS
	======
	
	Microsoft has confirmed this to be a problem in Systems Management Server 2.0.
	This problem was first corrected in Systems Management Server 2.0 Service Pack
	1.
	
	Additional query words: prodsms NAL
	
	======================================================================
	Keywords          : kbnetwork kbsms200 kbsms200bug kbsms120 kbsms120bug 
	Technology        : kbSMSSearch kbSMS120 kbSMS200
	Version           : winnt:1.2,2.0
	Issue type        : kbbug
	Solution Type     : kbfix
	
	=============================================================================
	

{% endraw %}
