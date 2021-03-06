---
layout: page
title: "Q70146: NMAKE Macros Cannot Expand to Multiple Command Lines"
permalink: /kb/070/Q70146/
---

## Q70146: NMAKE Macros Cannot Expand to Multiple Command Lines

{% raw %}

	Article: Q70146
	Product(s): Microsoft Programming Utilities
	Version(s): 
	Operating System(s): 
	Keyword(s): 
	Last Modified: 08-OCT-1999
	
	-------------------------------------------------------------------------------
	The information in this article applies to:
	
	- Microsoft NMAKE Utility for MS-DOS 
	- Microsoft NMAKE Utility for OS/2 
	- Microsoft NMAKE Utility for Windows NT 
	-------------------------------------------------------------------------------
	
	SUMMARY
	=======
	
	NMAKE does not support using a macro to substitute for more than one command
	line in a makefile. An attempt to use a macro in this way fails when NMAKE
	treats the macro expansion as one long concatenated command line.
	
	MORE INFORMATION
	================
	
	A makefile can contain many description blocks, each of which contain the same
	sequence of commands. Therefore, it would be useful to use a macro instead of
	the multiple commands shared between description blocks.
	
	For example, your makefile might somewhat resemble to sample makefile below. The
	macro in that makefile is designed to expand to the commands CLS (clear screen)
	and DIR (directory). However, when this makefile runs, the DIR command does not
	run because the command line passed to the system is as follows:
	
	  CLS <cr/lf> DIR
	
	where <cr/lf> denotes a carriage return and a line feed character.
	
	One method that effectively avoids repeating many command sequences in your
	makefile involved creating a batch file that contains the commands. The makefile
	calls the batch file when these commands are required. In addition, in OS/2, you
	can specify more than one command on a line by separating the commands with an
	ampersand (&) character.
	
	Under Windows NT, you can execute multiple commands by separating them with a
	&&.
	
	Sample Makefile
	---------------
	
	  # This makefile attempts to clear the screen and request a directory
	  # listing by expanding one macro. However, the DIR command is not
	  # executed.
	
	  CMDS = CLS ^
	         DIR
	
	  showdir:
	     $(CMDS)
	
	  In order to achieve this on Windows NT, use
	
	  Sample Makefile
	  ---------------
	
	  #
	  # This works on Windows NT
	  #
	
	  CMDS = CLS && DIR
	
	  showdir:
	     $(CMDS)
	
	Additional query words: kbinf 1.10 1.20 1.30 1.40 1.50
	
	======================================================================
	Keywords          :  
	Technology        : kbVCsearch kbAudDeveloper kbNMAKESearch
	Version           : :
	
	=============================================================================
	

{% endraw %}
