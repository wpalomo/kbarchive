---
layout: page
title: "Q50383: Inference Rule May Fail When Spaces on Blank Command Line"
permalink: /kb/050/Q50383/
---

## Q50383: Inference Rule May Fail When Spaces on Blank Command Line

{% raw %}

	Article: Q50383
	Product(s): Microsoft Programming Utilities
	Version(s): MS-DOS:1.01,1.1,1.11,1.12,1.13,1.2,1.3,1.4; OS/2:1.01,1.11,1.12,1.21
	Operating System(s): 
	Keyword(s): kb16bitonly
	Last Modified: 30-OCT-1999
	
	-------------------------------------------------------------------------------
	The information in this article applies to:
	
	- Microsoft NMAKE Utility for MS-DOS, versions 1.01, 1.1, 1.11, 1.12, 1.13, 1.2, 1.3, 1.4 
	- Microsoft NMAKE Utility for OS/2, versions 1.01, 1.11, 1.12, 1.21 
	-------------------------------------------------------------------------------
	
	SUMMARY
	=======
	
	When using inference rules in an NMAKE description file, the target/dependency
	line must be followed by a blank line (no space characters); otherwise, the
	inference rule commands will not be executed. NMAKE checks this line for any
	ASCII characters; if ANY characters exist, NMAKE will ignore the inference rule
	and try to execute the line, even if it contains only a space or spaces.
	
	The following is a simple example, which demonstrates this problem:
	
	  .c.exe:
	    cl $**
	   
	  ALL : main.exe
	   
	  main.exe : main.c
	  <space>
	
	Nothing happens if this description file is passed to NMAKE because the space
	character causes NMAKE to assume there are explicit commands following the
	target/dependency line, causing it to ignore the inference rule. Note that this
	is expected behavior for NMAKE.
	
	MORE INFORMATION
	================
	
	MAKE version 4.x inference rules/description blocks do not exhibit this
	behavior. This is something to keep in mind when converting description files
	from MAKE to NMAKE.
	
	Additional query words: kbinf 1.10 1.20 1.30 1.40
	
	======================================================================
	Keywords          : kb16bitonly 
	Technology        : kbVCsearch kbAudDeveloper kbNMAKESearch kbNMAKE101DOS kbNMAKE110DOS kbNMAKE111DOS kbNMAKE112DOS kbNMAKE113DOS kbNMAKE120DOS kbNMAKE130DOS kbNMAKE140DOS kbNMAKE101OS2 kbNMAKE111OS2 kbNMAKE112OS2 kbNMAKE121OS2
	Version           : MS-DOS:1.01,1.1,1.11,1.12,1.13,1.2,1.3,1.4; OS/2:1.01,1.11,1.12,1.21
	
	=============================================================================
	

{% endraw %}
