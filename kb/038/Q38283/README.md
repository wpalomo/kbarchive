---
layout: page
title: "Q38283: Example Incorrect on Page 373 of C Run-Time Library Reference"
permalink: /kb/038/Q38283/
---

## Q38283: Example Incorrect on Page 373 of C Run-Time Library Reference

{% raw %}

	Article: Q38283
	Product(s): See article
	Version(s): 5.00 5.10
	Operating System(s): MS-DOS
	Keyword(s): ENDUSER | docerr | mspl13_c
	Last Modified: 22-NOV-1988
	
	The example for intdosx on Page 373 of the "Microsoft C 5.1 Optimizing
	Compiler Run-Time Library Reference" is incorrect.
	
	To get the example to work correctly, the line that reads
	
	   char far *dir = "\newdir";   /* Directory to create */
	
	must be changed to read as follows:
	
	   char far *dir = "\\newdir";  /* Directory to create */
	
	The backslash character \ in a C string is interpreted as part of an
	escape code. To actually represent the backslash character for a
	file's path, use two consecutive backslashes.

{% endraw %}
