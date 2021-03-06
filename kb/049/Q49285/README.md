---
layout: page
title: "Q49285: Losing Data When Mouse and Data Transfer Are Involved"
permalink: /kb/049/Q49285/
---

## Q49285: Losing Data When Mouse and Data Transfer Are Involved

{% raw %}

	Article: Q49285
	Product(s): See article
	Version(s): 6.00 6.11 6.14 6.24 6.24b
	Operating System(s): DOS
	Keyword(s): ENDUSER | | mspl13_basic
	Last Modified: 22-MAR-1990
	
	Several customers report lost data or a system lock up when
	transferring high speed data from a modem or mainframe through a
	serial port. The mouse was resident in memory when the problem
	occurred.
	
	With communications going through COM2:, the interrupt 3 is in use.
	This interrupt has a higher priority than either interrupt 4 (for a
	mouse in COM1:) or interrupt 5 (bus mouse with interrupt 5 set on the
	J4 jumper).
	
	You should ensure that the communications equipment is loaded onto
	COM2: so that it can take advantage of the higher priority interrupt.
	The phenomenon is inherent with interrupt handling and established
	priorities.

{% endraw %}
