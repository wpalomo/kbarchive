---
layout: page
title: "Q40176: Inserting Time and Date into Files"
permalink: /kb/040/Q40176/
---

## Q40176: Inserting Time and Date into Files

{% raw %}

	Article: Q40176
	Product(s): See article
	Version(s): 1.00   | 1.00
	Operating System(s): MS-DOS | OS/2
	Keyword(s): ENDUSER | | mspl13_basic
	Last Modified: 1-MAY-1989
	
	To write a macro to insert the time and date into your file, use the
	following insert commands:
	
	   Command     Action
	
	   Curdate     Inserts current date
	   Curday      Inserts current day of the week
	   Curfile     Inserts current filename
	   Curfileext  Inserts current file extension
	   Curfilenam  Inserts base name of current file
	   Curtime     Inserts current time
	   Curuser     Inserts name specified in USER environment variable
	
	The following macro can be inserted into your TOOLS.INI to insert the
	filename, time, and date:
	
	;Macro for time and date.
	    Header:= Curfilenam tab Curtime tab Curdate
	    Header:Alt+H

{% endraw %}
