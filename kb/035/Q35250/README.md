---
layout: page
title: "Q35250: MSETUP Installs on Drive Specified"
permalink: /kb/035/Q35250/
---

## Q35250: MSETUP Installs on Drive Specified

{% raw %}

	Article: Q35250
	Product(s): See article
	Version(s): 6.x 1.00
	Operating System(s): MS-DOS
	Keyword(s): ENDUSER | | mspl13_basic
	Last Modified: 19-SEP-1988
	
	If you have more than one hard-disk partition, MSETUP has the
	capability of installing the mouse software on a partition that may
	not be your C: drive. If you select to do this, you must manually edit your
	AUTOEXEC.BAT file to invoke the mouse driver and optionally CPANEL.
	For example, to install the mouse software on your D: drive, you must
	edit your AUTOEXEC.BAT on your boot drive C: to the following:
	
	D:\mouse1\mouse
	D:\mouse1\cpanel

{% endraw %}
