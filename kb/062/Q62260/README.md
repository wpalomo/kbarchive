---
layout: page
title: "Q62260: TSCNIOxx.OBJ Stub Files Remove Screen 0 Page-Switching"
permalink: /kb/062/Q62260/
---

## Q62260: TSCNIOxx.OBJ Stub Files Remove Screen 0 Page-Switching

{% raw %}

	Article: Q62260
	Product(s): See article
	Version(s): 7.00
	Operating System(s): MS-DOS
	Keyword(s): ENDUSER | SR# S900423-7 | mspl13_basic
	Last Modified: 20-JUN-1990
	
	If you link the stub file TSCNIOxx.OBJ to your BASIC object module,
	any attempt to change the visual or active page to any page other than
	Page 0 generates the error "Feature Removed." The run-time routines
	responsible for handling page switching are included in those run-time
	routines stubbed out by TSCNIOxx.OBJ. This information applies to
	Microsoft BASIC Professional Development System (PDS) version 7.00 for
	MS-DOS and MS OS/2.
	
	The TSCNIOxx.OBJ stub file is used to remove all graphics support that
	is automatically inserted in your program at link time so that you may
	generate smaller EXE files.
	
	For more information on this and other stub files, query on the
	following words:
	
	   smaller and stub and EXE
	
	The sample code below reproduces the error "Feature Removed."
	
	Compile and link as follows:
	
	   BC scrntest.bas /o ;
	   LINK scrntest + tscionr.obj,,,bcl70enr.lib /noe ;
	
	Code Example
	------------
	
	   CLS
	   PRINT "Switching pages"
	   SLEEP
	   SCREEN 0, , 1, 1        'This line will generate the Feature.
	                           'Removed error because it tries to switch
	                           'pages in Text mode.

{% endraw %}
