---
layout: page
title: "Q72731: BUG: PWB Generates &quot;Error Reading Program&quot; with CTRL+Z"
permalink: /kb/072/Q72731/
---

## Q72731: BUG: PWB Generates &quot;Error Reading Program&quot; with CTRL+Z

{% raw %}

	Article: Q72731
	Product(s): Microsoft Programming Utilities
	Version(s): MS-DOS:1.0,1.1; OS/2:1.0,1.1
	Operating System(s): 
	Keyword(s): kb16bitonly
	Last Modified: 30-OCT-1999
	
	-------------------------------------------------------------------------------
	The information in this article applies to:
	
	- Microsoft Programmer's Workbench for MS-DOS, versions 1.0, 1.1 
	- Microsoft Programmer's Workbench for OS/2, versions 1.0, 1.1 
	-------------------------------------------------------------------------------
	
	SYMPTOMS
	========
	
	When attempting to set a Program List using a makefile generated by the
	Programmer's WorkBench (PWB) version 1.0 or 1.1, the following message may be
	generated if the makefile has been edited by an editor (other than PWB) that
	places a CTRL+Z at the end of the file:
	
	  Error reading program list line xxx
	  ':' or '=' expected
	
	If you select the "OK" button in response to this dialog box, another dialog box
	will appear, asking if you want to use the makefile as a non-PWB makefile.
	
	CAUSE
	=====
	
	Some editors other than PWB or the Microsoft Editor (for example, the OS/2
	System Editor) will automatically append a CTRL+Z (end-of-file) character to
	every file that is modified. PWB reads this CTRL+Z as a standard character and
	expects either a colon (indicating a build rule) or an equal sign (indicating a
	macro) to follow it. Finding neither, PWB will return the error above.
	
	RESOLUTION
	==========
	
	If you want to make modifications to PWB-generated makefiles, while still
	allowing PWB to use them as native makefiles, you should add a "fence" to the
	end of the makefile. The fence is a separator line of the following form:
	
	  # << User_supplied_information >>
	
	The comment marker (#) must begin in the first column, and the line must appear
	exactly as shown above. Any information placed below this line is ignored by
	PWB, but may still be executed by NMAKE. This method eliminates the possibility
	of the CTRL+Z problem described above, as well as ensuring that you retain full
	functionality of all PWB menu commands, since PWB never tries to interpret or
	modify anything below the fence.
	
	STATUS
	======
	
	Microsoft has confirmed this to be a problem in PWB versions 1.0 and 1.1. We are
	researching this problem and will post new information here as it becomes
	available.
	
	Additional query words: 1.00 1.10 buglist1.00 buglist1.10
	
	======================================================================
	Keywords          : kb16bitonly 
	Technology        : kbAudDeveloper kbPWBSearch kbZNotKeyword3 kbPWB100DOS kbPWB110DOS kbPWB100OS2 kbPWB110OS2
	Version           : MS-DOS:1.0,1.1; OS/2:1.0,1.1
	
	=============================================================================
	

{% endraw %}
