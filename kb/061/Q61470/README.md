---
layout: page
title: "Q61470: C 6.00 Command-Line Options /Li and /Gi Documented Incorrectly"
permalink: /kb/061/Q61470/
---

## Q61470: C 6.00 Command-Line Options /Li and /Gi Documented Incorrectly

{% raw %}

	Article: Q61470
	Product(s): See article
	Version(s): 6.00   | 6.00
	Operating System(s): MS-DOS | OS/2
	Keyword(s): ENDUSER | docerr | mspl13_c
	Last Modified: 17-MAY-1990
	
	The following command-line switches are documented incorrectly on
	Pages 6 and 7 of the "Microsoft C Reference" for the C compiler
	version 6.00, as well as in the C 6.00 online help:
	
	1. The /Gi switch that reads /Gi should read /Gi[mdtfile].
	
	2. The /Li switch that reads /Li[number] should read /Li.
	
	The /Gi switch takes an optional mdtfile argument, which specifies the
	name of the file to contain the incremental compilation information.
	If mdtfile is unspecified, /Gi defaults to <basename>.MDT.
	
	The /Li switch does not take an optional argument. In the presence of
	an argument (for example, /Li60) the compiler will generate an
	"unknown switch" warning and ignore it.

{% endraw %}
